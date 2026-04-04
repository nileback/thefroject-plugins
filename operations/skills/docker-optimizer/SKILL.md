---
name: docker-optimizer
description: Write, review, and optimize Dockerfiles and docker-compose configurations. Use when building container images, reducing image sizes, or hardening container security.
triggers:
  - optimize dockerfile
  - docker review
  - container security
---

# Docker Optimizer

Build containers that are small, fast to build, fast to deploy, and hardened for production.

## Base Image Selection

Choose the smallest base that meets your requirements:

| Base Image | Size | Use Case | Tradeoff |
|-----------|------|----------|----------|
| `distroless` | ~2-20 MB | Production runtime | No shell, no package manager. Most secure but hardest to debug |
| `alpine` | ~5-8 MB | General purpose | musl libc (not glibc). Some packages may behave differently |
| `*-slim` | ~50-80 MB | When alpine causes compatibility issues | Good balance of size and compatibility |
| `*:latest` (full) | ~200-900 MB | Development only | Never use in production. Unpinned, bloated |

**Always pin the version:** `node:20.11-alpine3.19` not `node:alpine` or `node:latest`.

## Multi-Stage Build Pattern

Separate build environment from runtime environment:

```dockerfile
FROM node:20.11-alpine3.19 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci --production=false
COPY . .
RUN npm run build

FROM node:20.11-alpine3.19 AS runtime
WORKDIR /app
RUN addgroup -g 1001 appgroup && \
    adduser -u 1001 -G appgroup -s /bin/sh -D appuser
COPY --from=builder --chown=appuser:appgroup /app/dist ./dist
COPY --from=builder --chown=appuser:appgroup /app/node_modules ./node_modules
COPY --from=builder --chown=appuser:appgroup /app/package.json ./
USER appuser
EXPOSE 3000
CMD ["node", "dist/server.js"]
```

Build tools, dev dependencies, source code, and intermediate artifacts stay out of the final image.

## Layer Caching Optimization

Docker caches each layer. Order instructions from least to most frequently changed: base image, system packages, dependency manifests, dependency install, application code, build step.

**Key rule:** Copy dependency manifests and install dependencies BEFORE copying source code. The expensive install step is cached unless the manifest changes.

**Bad (busts cache on every code change):**
```dockerfile
COPY . .
RUN npm install
```

**Good (caches dependency install):**
```dockerfile
COPY package*.json ./
RUN npm ci
COPY . .
```

## Security Hardening

### Non-Root User (mandatory)
```dockerfile
RUN addgroup -g 1001 appgroup && \
    adduser -u 1001 -G appgroup -s /bin/sh -D appuser
USER appuser
```

Always set a non-root USER before the CMD/ENTRYPOINT. Running as root in a container gives an attacker root on the host if they escape the container.

### No Secrets in Layers
Never `COPY .env` or hardcode secrets via `ENV` — every layer persists in image history. Pass secrets at runtime via environment variables, mounted volumes, or a secrets manager.

### Pin Package Versions
```dockerfile
RUN apk add --no-cache \
    curl=8.5.0-r0 \
    ca-certificates=20240226-r0
```

Unpinned versions make builds non-reproducible and can introduce vulnerabilities.

### Minimize Attack Surface
- Remove unnecessary packages and files in the final stage
- Use `--no-cache` with package managers to avoid storing package indexes
- Do not install debugging tools in production images
- Use read-only filesystem where possible (`--read-only` flag at runtime)

## .dockerignore

Create a `.dockerignore` that excludes `.git`, `node_modules`, `.env*`, `tests/`, `coverage/`, and IDE config directories.

## Health Checks

Add a HEALTHCHECK instruction for orchestrators (Kubernetes, ECS, Docker Swarm):

```dockerfile
HEALTHCHECK --interval=30s --timeout=3s --start-period=10s --retries=3 \
  CMD curl -f http://localhost:3000/health || exit 1
```

Use `interval=30s`, `timeout=3-5s`, `start-period=5-30s` (grace period during startup), and `retries=3`.

## Audit Checklist

| Check | Status | Impact | Typical Fix |
|-------|--------|--------|-------------|
| Pinned base image version | ✅/❌ | Reproducibility | Pin to specific tag |
| Multi-stage build | ✅/❌ | Image size (often 50-90% reduction) | Separate build and runtime stages |
| Non-root user | ✅/❌ | Security (critical) | Add USER instruction |
| No secrets in layers | ✅/❌ | Security (critical) | Use runtime env vars or secrets manager |
| Layer order optimized | ✅/❌ | Build speed | Move deps install before code copy |
| .dockerignore present | ✅/❌ | Build speed, security | Create file excluding dev artifacts |
| HEALTHCHECK defined | ✅/❌ | Orchestration reliability | Add HEALTHCHECK instruction |
| Cache cleanup | ✅/❌ | Image size | `--no-cache` flags on package installs |
| Package versions pinned | ✅/❌ | Reproducibility | Pin all system packages |
| Minimal final image | ✅/❌ | Size, security | Remove unused packages and files |

## Output Format

Save to `outputs/docker-audit-[service-name].md` with:

- Audit results table (above)
- Current image size vs. estimated optimized size
- Optimized Dockerfile with inline comments explaining each decision
- .dockerignore file if missing
- docker-compose recommendations if applicable

## Do NOT
- Use `latest` tag for base images — always pin versions
- Run as root in production containers
- Copy secrets into image layers — they persist in image history
- Install packages without cleaning up caches (`--no-cache`, `rm -rf /var/cache/*`)
- Use COPY . . before installing dependencies — this busts the cache on every code change
- Skip the .dockerignore — it prevents sending gigabytes of unnecessary data to the build context

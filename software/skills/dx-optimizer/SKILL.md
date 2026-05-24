---
name: dx-optimizer
description: Audit and improve developer experience inside a codebase. Cover local setup time, build/test feedback loops, common workflows, error legibility, and onboarding friction. Use when a team's velocity is slipping for non-architectural reasons, when new joiners take too long to ship, or as a quarterly hygiene pass.
triggers:
  - audit DX
  - developer experience
  - speed up the build
  - onboarding friction
  - improve dev loop
---

# DX Optimizer

Find the friction points that quietly slow every developer in the codebase, every day. The goal is a measurable improvement in feedback-loop time, not a tooling rewrite.

## Gather Context First

Before recommending anything, understand the current state:

1. **Read** `README.md`, any `CONTRIBUTING.md`, and onboarding docs in `context/`
2. **Run** the documented setup steps in a fresh checkout — time them, note errors
3. **Inspect** `package.json` / `Makefile` / build config: what scripts exist, what they depend on
4. **Check** CI config for cache hits, parallelization, and total wall-clock time
5. **Skim** recent PRs — how long between push and merge? What blocks reviews?
6. **Ask** the team (or read `outputs/feedback/` if it exists) for their top friction items

Don't recommend before measuring. A "slow build" might be a 30-second annoyance the team has worked around. Fixing it first when CI takes 25 minutes is wasted effort.

## The DX Surface

Audit across these dimensions. Score each as **green / yellow / red** with one line of evidence.

### 1. Onboarding (clone → first commit)
- Time from `git clone` to running app
- Number of manual steps not in the script
- External accounts/secrets required
- Documentation accuracy (does it match reality?)

### 2. Inner loop (file save → feedback)
- Local build/reload time
- Test execution speed (single file, single test)
- Lint/typecheck speed
- Hot reload reliability

### 3. Outer loop (push → merged)
- CI duration (P50 and P95)
- Flaky test rate
- PR review SLA
- Merge friction (rebase storms, branch conflicts)

### 4. Error legibility
- Are stack traces actionable?
- Do error messages name the file and the cause?
- Is there a known-issues doc for common gotchas?

### 5. Common workflows
- "How do I add a new endpoint/component/migration?" — is there a recipe or scaffolding?
- Are common tasks scripted (one-command create-X) or manual (10 file edits)?

### 6. Toolchain hygiene
- Lockfile churn
- Unused dependencies
- Diverging tool versions across team (`.tool-versions`, `.nvmrc`, etc.)

## Recommend in Tiers

After scoring, group findings by impact × effort:

### Tier 1 — Quick wins (this sprint)
Anything < 1 day of work that saves > 5 min/dev/day. Examples:
- Add caching to the slowest CI step
- Replace a 30-second yarn install with a turborepo/pnpm equivalent
- Fix the top 3 flaky tests
- Add a one-command bootstrap script

### Tier 2 — Worth the investment (this quarter)
Multi-day projects that pay back within months:
- Parallelize the test suite across N workers
- Add incremental builds via the build tool's dependency graph
- Migrate from CRA/Webpack to Vite (when the team feels the pain weekly)
- Introduce a code generator for the most-repeated boilerplate

### Tier 3 — Strategic (roadmap)
Architectural moves with long horizons:
- Monorepo split or merge
- Replace the framework
- Move from local dev to a cloud dev env

## Output Format

Save findings to `outputs/dx-audit/<date>.md`:

```
# DX Audit — <Date>

## Snapshot
- Clone-to-first-commit: <time>
- Local build (cold): <time>  | (warm): <time>
- Single-test run: <time>
- CI P50: <time>  | CI P95: <time>
- Flaky test rate: <%>

## Score by surface
| Surface | Score | Top friction |
|---|---|---|
| Onboarding | green/yellow/red | <one-line evidence> |
| Inner loop | … | … |
| Outer loop | … | … |
| Error legibility | … | … |
| Common workflows | … | … |
| Toolchain hygiene | … | … |

## Tier 1 — Quick wins
1. **<change>** — saves <minutes>/dev/day. Effort: <hours>. Owner: <name>.
2. …

## Tier 2 — This quarter
1. …

## Tier 3 — Strategic
1. …

## Measurement plan
- Re-run this audit on <date>. Specifically watch <metric> drop from <X> to <Y>.
```

## Do NOT

- Recommend tooling rewrites without baseline numbers. "Webpack feels slow" is not a brief.
- Optimize the inner loop while the outer loop is broken (or vice versa). Find the bottleneck.
- Pick changes by novelty. Pick by minutes-saved-per-dev-per-day × team size.
- Skip the team interview. The friction you don't feel as the auditor is the friction the team works around silently.
- Promise a single change will fix DX. DX is the sum of small frictions. The audit is a backlog, not a silver bullet.

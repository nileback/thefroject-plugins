---
description: Infrastructure and deployment standards
globs:
  - "infra/**"
  - "terraform/**"
  - "docker/**"
  - "*.yml"
  - "*.yaml"
---

# Infrastructure Rules

- All infrastructure changes must be defined as code (IaC)
- Use consistent naming conventions for resources
- Tag all cloud resources with environment, team, and purpose
- Never store secrets in code or config files — use secret managers
- Require approval for production deployments
- Maintain runbooks for common operational procedures
- Monitor all critical services with alerts on key metrics

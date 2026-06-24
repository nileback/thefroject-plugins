---
name: terraform-writer
description: Write, review, and refactor Terraform configurations. Use when provisioning cloud infrastructure, setting up environments, or reviewing IaC for best practices.
triggers:
  - write terraform
  - infrastructure as code
  - provision cloud resources
---

# Terraform Writer

Write clean, modular Terraform that teams can maintain, review, and extend safely.

## Project Structure

Organize Terraform code using this standard layout:

```
infrastructure/
  modules/
    [module-name]/
      main.tf           # Resource definitions
      variables.tf      # Input variables with descriptions
      outputs.tf        # Output values
      versions.tf       # Provider version constraints
      README.md         # Module purpose, inputs, outputs, usage example
  environments/
    dev/
      main.tf           # Module calls with dev-specific values
      backend.tf        # Remote state configuration
      terraform.tfvars  # Variable values (never commit secrets)
    staging/
    production/
  global/               # Resources shared across environments (IAM, DNS)
```

**Key principle:** Modules contain the logic. Environments contain the values. Never mix the two.

## Phase 1 — Requirements Gathering

Before writing any HCL, answer these questions:

| Question | Answer | Implication |
|----------|--------|-------------|
| What cloud provider? | AWS / GCP / Azure | Provider configuration, naming conventions |
| What resources? | Compute, storage, networking, etc. | Module scope and dependency graph |
| What environments? | Dev, staging, production | State file separation, variable structure |
| What compliance requirements? | SOC2, HIPAA, PCI, etc. | Encryption, logging, access control defaults |
| Who maintains this? | Team size, Terraform experience | Complexity budget, documentation depth |

## Phase 2 — Module Design

### Module Principles
- **Single responsibility** — Each module manages one logical unit (e.g., "VPC," "ECS service," "RDS cluster")
- **Configurable, not customizable** — Use variables for values that change between environments. Do not add variables for every possible option
- **Opinionated defaults** — Set sensible defaults for security, tagging, and monitoring. Make the safe path the easy path

### Variable Design
```hcl
variable "instance_type" {
  description = "EC2 instance type for the application servers"
  type        = string
  default     = "t3.medium"

  validation {
    condition     = can(regex("^t3\\.", var.instance_type))
    error_message = "Only t3 instance types are approved for this environment."
  }
}
```

**Rules for variables:**
- Every variable has a `description`
- Use `type` constraints (never `any`)
- Set `default` for values that rarely change
- Add `validation` blocks for values with constraints
- Group related variables with comments
- Use `sensitive = true` for secrets

### Output Design
Expose only what downstream modules or users need. Every output gets a `description`. Do not output internal implementation details.

## Phase 3 — Resource Patterns

### Mandatory Tagging
Every resource must have these tags:

```hcl
locals {
  common_tags = {
    Environment = var.environment
    Team        = var.team
    ManagedBy   = "terraform"
    Repository  = var.repository_url
    CostCenter  = var.cost_center
  }
}
```

### Security Defaults
- **Encryption at rest** — Enable by default on all storage resources (S3, EBS, RDS, etc.)
- **Encryption in transit** — Enforce TLS on all endpoints
- **Least privilege IAM** — Start with zero permissions and add only what is needed. Never use `*` in IAM actions for production
- **No public access** — Resources are private by default. Public access requires explicit opt-in with a justification comment
- **Logging** — Enable access logging and audit trails on all applicable resources

### Lifecycle Management
Use `prevent_destroy = true` on stateful resources: databases, S3 buckets with data, encryption keys, and anything where accidental deletion causes data loss.

## Phase 4 — State Management

- One state file per environment per logical unit
- Always enable encryption and locking (DynamoDB for S3, native for Terraform Cloud)
- Never store state locally for shared infrastructure
- Use `terraform_remote_state` data source for cross-state reads
- Configure remote backend in each environment's `backend.tf` with bucket, key, region, encrypt, and lock table

## Phase 5 — Review Checklist

Before applying any Terraform plan:

1. `terraform fmt -check` — no formatting changes needed
2. `terraform validate` — no errors
3. `terraform plan` — review every change, no surprises
4. Review IAM and security group rules — least privilege, no wildcards
5. Verify all resources tagged with common tags

## Output Format

Deliver Terraform code with:
- Clean formatting (`terraform fmt` compliant)
- Comments explaining WHY, not what (the code shows what)
- Variable descriptions for every input
- Output descriptions for every output
- README with usage example for modules
- Tags on every resource

## Do NOT
- Hardcode values that differ between environments — use variables
- Create resources without tags — untagged resources are orphaned resources
- Use `*` in IAM actions for production — always specify exact permissions
- Use default VPC or default security groups — create explicit ones
- Skip state locking — concurrent applies cause state corruption
- Store secrets in `.tfvars` files — use a secret manager or environment variables
- Use `latest` AMI or image references — pin to specific versions for reproducibility

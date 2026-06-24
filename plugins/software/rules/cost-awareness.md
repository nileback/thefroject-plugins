---
description: Consider cost implications when making infrastructure, tooling, and scaling decisions
---

# Cost Awareness Rules

- Always check pricing before recommending new tools or services
- Use appropriate instance sizes — don't over-provision "just in case"
- Set up cost alerts and budgets for cloud resources
- Prefer reserved/committed-use pricing for stable workloads
- Tag all cloud resources for cost attribution by team/project
- Review and terminate unused resources (idle instances, orphaned storage, old snapshots)
- Consider cost per transaction/request, not just monthly cost
- Document the cost impact of architectural decisions

**Cost review triggers:**
- Before provisioning new infrastructure
- Before committing to annual SaaS contracts
- When scaling up existing services
- Monthly cloud bill review
- Before choosing between build vs. buy

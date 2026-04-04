# /compliance-check — Compliance Audit

Audit a process, document, or system for regulatory compliance.

## Workflow

1. **Scope** — What regulation/standard? (GDPR, SOC 2, ISO 27001, HIPAA, labor law)
2. **Inventory** — What data, systems, or processes are in scope?
3. **Assess** — Check each requirement against current state
4. **Gap analysis** — Document what's missing or insufficient
5. **Remediation** — Prioritized action plan

## Output Format

### Compliance Scorecard
| Requirement | Status | Evidence | Gap | Priority |
|-------------|--------|----------|-----|----------|
| ... | ✅/⚠️/❌ | ... | ... | P1/P2/P3 |

### Summary
- **Compliant:** X of Y requirements met
- **Critical gaps:** [List]
- **Remediation effort:** [Estimate]

### Action Plan
1. [Gap] → [Fix] → [Owner] → [Deadline]

## Important
- This is an internal assessment tool, not legal advice
- Flag items that need legal or auditor review
- Document evidence for compliant items (auditors will ask)

Usage: `/compliance-check [standard] [scope]`

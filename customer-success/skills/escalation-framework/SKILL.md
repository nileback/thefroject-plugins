---
name: escalation-framework
description: Define and execute customer escalation processes including severity classification, routing, communication cadences, and resolution tracking. Use when handling active escalations or building an escalation policy.
triggers:
  - customer escalation
  - escalation management
  - escalation process
  - account crisis
---

# Escalation Framework

Handle customer escalations with structure, speed, and transparency. The goal is not just resolution but maintaining trust through the process.

## Severity Classification

| Level | Name | Definition | Response Time | Update Cadence | Escalation Path |
|-------|------|-----------|--------------|---------------|----------------|
| **S1** | Critical | Service down, data loss, or business-stopping issue | 1 hour | Every 2 hours | VP/C-level engaged immediately |
| **S2** | High | Major feature broken, significant workaround needed | 4 hours | Daily | Director-level within 24 hours |
| **S3** | Medium | Feature impaired, workaround available | 1 business day | Every 3 days | Manager-level within 48 hours |
| **S4** | Low | Minor issue, cosmetic, or enhancement request | 3 business days | Weekly | Normal support flow |

## Escalation Intake

When an escalation is raised, capture immediately:

| Field | Detail |
|-------|--------|
| **Customer** | [Name, ARR, tier, renewal date] |
| **Reported by** | [Name, role, contact info] |
| **Severity** | [S1-S4 with justification] |
| **Issue summary** | [One paragraph: what is happening, what is the impact] |
| **Business impact** | [Revenue at risk, users affected, regulatory implications] |
| **Timeline** | [When did it start? When does it need to be resolved?] |
| **Previous attempts** | [What has been tried? Ticket numbers?] |
| **Desired outcome** | [What does the customer consider "resolved"?] |

## Escalation Management Process

### Step 1 — Acknowledge (within response time SLA)

Send the customer:
- Confirmation that the escalation has been received and classified
- Name and contact info of the escalation owner
- Next update time (commit to a specific time, not "soon")

### Step 2 — Assemble the Response Team

| Role | Responsibility | Required For |
|------|---------------|-------------|
| **Escalation owner** | Single point of accountability | All levels |
| **Technical lead** | Root cause investigation and fix | S1, S2 |
| **CSM** | Customer communication and relationship | All levels |
| **Product/Engineering** | Fix or workaround development | S1, S2 |
| **Executive sponsor** | Strategic decisions, customer executive contact | S1 |

### Step 3 — Investigate and Communicate

Maintain an internal escalation log:

| Timestamp | Update | Source | Action Taken | Next Step |
|-----------|--------|--------|-------------|----------|
| | | | | |

**Communication rules:**
- Update the customer at every committed interval, even if there is no progress
- "We are still investigating" is better than silence
- Share what you know, what you do not know, and what you are doing about it
- Never blame the customer, even internally

### Step 4 — Resolve and Verify

Before closing:
- [ ] Root cause identified and explained to the customer
- [ ] Fix deployed or workaround in place
- [ ] Customer confirms the issue is resolved
- [ ] Prevention plan communicated (what will prevent recurrence)

### Step 5 — Post-Escalation Review

Within 1 week of resolution:

| Question | Answer |
|----------|--------|
| What happened? | [Root cause] |
| Why was it not caught earlier? | [Gap in monitoring, testing, or process] |
| What is the fix? | [Technical or process change] |
| What prevents recurrence? | [Specific preventive action] |
| Was the response adequate? | [What went well, what could improve] |
| Customer satisfaction? | [Did we recover the relationship?] |

## Output Format

Save escalation records to `outputs/escalation-[customer]-[date].md`:

```markdown
# Escalation — [Customer] — [Date]
**Severity:** [S1-S4] | **Status:** [Active/Resolved] | **Owner:** [Name]

## Issue Summary
[What happened and the business impact]

## Timeline
[Chronological log of events, actions, and communications]

## Resolution
[What fixed it and what prevents recurrence]

## Lessons Learned
[Process improvements identified]
```

## Principles

- Speed of acknowledgment matters as much as speed of resolution. Customers can tolerate a slow fix. They cannot tolerate being ignored.
- Every escalation is a relationship test. How you handle the problem defines the relationship more than when things go well.
- Document everything. Escalation records inform process improvements, staffing decisions, and product priorities.

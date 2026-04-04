---
name: incident-responder
description: Guide production incident response and post-mortem analysis.
triggers:
  - incident response
  - production issue
  - post-mortem
---

# Incident Responder

You guide structured incident response and blameless post-mortems. Speed of mitigation matters more than speed of root cause analysis during an active incident.

## Phase 1: Active Incident Response

### Severity Classification

| Severity | Criteria | Response Time | Communication |
|----------|---------|---------------|---------------|
| SEV-1 | Service down, data loss, security breach | Immediate | All-hands, exec notification |
| SEV-2 | Major feature broken, significant user impact | 15 min | Team leads, status page |
| SEV-3 | Minor feature degraded, workaround exists | 1 hour | Team channel |
| SEV-4 | Cosmetic issue, no user impact | Next business day | Ticket |

### Incident Commander Checklist
1. **Declare the incident.** Name an Incident Commander (IC). Open a dedicated channel.
2. **Assess impact.** How many users affected? Is data at risk? Is revenue impacted?
3. **Communicate immediately.** Status page update within 10 minutes. Internal stakeholder notification.
4. **Mitigate first, diagnose second.** The goal is to reduce user impact, not find root cause.
   - Rollback the last deployment.
   - Toggle feature flags off.
   - Scale infrastructure if load-related.
   - Redirect traffic if region-specific.
5. **Assign roles.** IC coordinates. One person investigates. One person communicates updates.
6. **Document in real-time.** Timestamp every action and finding in the incident channel.
7. **Verify the fix.** Monitor key metrics for 30 minutes after mitigation.
8. **Declare resolved.** Update status page. Send all-clear to stakeholders.

### Communication Templates

**Initial notification:**
"We are investigating [symptom]. [X users / X% of traffic] affected. [Feature/service] is [degraded/unavailable]. Next update in [15/30] minutes."

**Update:**
"Update: Root cause identified as [brief description]. Mitigation in progress. ETA to resolution: [time]. [Feature] remains [status]."

**Resolution:**
"Resolved: [Symptom] has been resolved as of [time]. Root cause: [one sentence]. Duration: [X hours]. Full post-mortem to follow within [48 hours]."

## Phase 2: Post-Mortem

Write the post-mortem within 48 hours while memory is fresh. Save to `outputs/post-mortems/`.

### Post-Mortem Structure

```markdown
# Post-Mortem: [Incident Title]
Date: [date]
Severity: [SEV-1/2/3/4]
Duration: [start time] to [end time] ([total duration])
Author: [name]

## Summary
[2-3 sentences: what happened, impact, resolution]

## Impact
- Users affected: [number or percentage]
- Revenue impact: [estimated if applicable]
- SLA impact: [if applicable]

## Timeline
| Time | Event |
|------|-------|
| HH:MM | [First symptom detected] |
| HH:MM | [Incident declared] |
| HH:MM | [Root cause identified] |
| HH:MM | [Mitigation applied] |
| HH:MM | [Incident resolved] |

## Root Cause
[Technical explanation of why this happened. Use the "5 Whys" technique.]

## Contributing Factors
- [What made the incident worse or harder to detect]
- [Missing monitoring, documentation gaps, process failures]

## What Went Well
- [Fast detection, good communication, effective rollback]

## Action Items
| Action | Owner | Priority | Due Date |
|--------|-------|----------|----------|
| [Preventive measure] | [name] | P1 | [date] |
| [Detection improvement] | [name] | P2 | [date] |
```

### The 5 Whys Technique
Start with the symptom and ask "Why?" five times:
1. Why did the service go down? -> Deployment introduced a null pointer.
2. Why was the null pointer not caught? -> No test covered that code path.
3. Why was the code path untested? -> The feature was rushed to meet a deadline.
4. Why was the deadline not negotiated? -> Scope was not re-evaluated when complexity grew.
5. Why was complexity not flagged? -> No design review step in the process.

The root cause is usually the 4th or 5th "why," not the first.

## Principles
- **Blameless.** Focus on systems and processes, never individuals. "The deployment process allowed..." not "Engineer X deployed..."
- **Honest.** Do not downplay impact or hide contributing factors.
- **Actionable.** Every action item has an owner, priority, and due date.
- **Public internally.** Share post-mortems widely. Transparency builds trust.

## Do NOT
- Assign blame to individuals in post-mortems.
- Skip the post-mortem because "it was a small incident."
- List action items without owners and deadlines.
- Spend time on root cause analysis during an active SEV-1. Mitigate first.
- Close the incident without verifying the fix with monitoring data.

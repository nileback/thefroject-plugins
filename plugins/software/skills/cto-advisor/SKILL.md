---
name: cto-advisor
description: CTO-level strategic counsel. Technology strategy, build-vs-buy decisions, engineering leadership at scale, technical debt management, platform strategy. Tagged executive + software.
triggers:
  - cto strategy
  - eng leadership
  - tech strategy
  - build vs buy
  - tech debt
  - platform strategy
  - cto advisor
---

# CTO Advisor

CTO-level strategic counsel. The CTO's job is making sure the engineering org is shipping the right things, in the right way, at the right pace, on architecture that won't trap the company in a year.

## Gather context

Ask if not provided:

1. **Stage** — early (pre-PMF), growth, scale, mature?
2. **Eng team size** — 1-5, 5-30, 30-100, 100+?
3. **Architecture state** — monolith, services, distributed? Cloud, on-prem, hybrid?
4. **Decision** — hire, restructure, replatform, build vs buy, technical debt budget, security/compliance?
5. **Pain** — slow shipping, reliability issues, attrition, hiring difficulty?

## Build vs buy

Single highest-leverage CTO decision area. Default to BUY for non-differentiating capabilities.

Build when:
- The capability is core to the product's differentiation.
- No vendor offers a viable solution.
- The cost of vendor lock-in or pricing power is real.
- The team has the depth to maintain it indefinitely.

Buy when:
- The capability is undifferentiated (auth, monitoring, payments, CRM).
- Vendor solutions are mature.
- Build cost > 12 months of vendor cost.
- Maintaining custom code crowds out customer-facing work.

Common build-vs-buy mistakes:
- Building auth (always buy, almost always Auth0/Clerk/Supabase/etc.).
- Building monitoring (always buy: Datadog, New Relic, Sentry).
- Building payments (always buy: Stripe).
- NOT buying when buying is right because "we can build it cheaper" (usually wrong when measuring true cost).
- Buying when building is right because vendor lock-in becomes existential.

## Engineering org design

Stage-appropriate:

### 1-5 engineers
- All ICs. CTO is hands-on coding.
- No managers. No specialization.

### 5-15 engineers
- 1-2 tech leads (player-coaches).
- CTO transitions out of daily coding.
- Specialization emerging (frontend / backend / infra).

### 15-50 engineers
- VP eng or director(s) running 2-4 teams of 4-8.
- Each team has tech lead + EM.
- Platform team possibly emerging (5-10 people serving other teams).
- Site reliability function emerging.
- Hiring at scale becomes a function (engineering-led recruiting).

### 50-200 engineers
- VPs running multiple director-led groups.
- Platform engineering as a real org (15-30 people).
- Specialized functions: data, ML, security, devex, IT.

### 200+
- CTO with VP-level reports for major functions.
- Geographic / time-zone distribution mattering.
- Internal services / standards / governance functions.

## Technical debt management

Technical debt is real but unevenly visible. CTO must:
- **Make it visible**: track tech debt items in the same backlog as features.
- **Allocate explicitly**: 20-30% of capacity to foundations; specific number negotiated with CPO/CEO.
- **Distinguish**: deliberate debt (taken on knowingly to ship faster) vs. accidental debt (sloppy work) vs. structural debt (architecture choices that no longer fit).
- **Prioritize ruthlessly**: not all tech debt is equal. Some compounds; some is OK to live with.

A useful litmus: when shipping new features takes 2x longer than expected, technical debt is the most likely cause.

## Platform vs application teams

When the eng org is 30+, the question of platform vs application teams arises.

Platform teams should:
- Have customer (other engineers) commitment.
- Measure satisfaction (internal NPS) and adoption.
- Avoid building platform for theoretical needs.
- Default to "use the open-source thing" before building custom platforms.

Bad platform teams:
- Build for theoretical needs.
- No internal customers using their work.
- Become a place senior engineers go to escape user-facing pressure.

## Reliability and security

CTO owns systemic reliability and security. Common failures:
- No incident response process. First major incident reveals it (badly).
- Security as bolt-on. Becomes existential when first breach attempted.
- No SRE function. Eng teams burn out on call.
- No disaster recovery plan. First major outage tests it.

Maturity model:
- **Crawl**: incident response runbook exists, on-call rotation, basic monitoring.
- **Walk**: dedicated SRE function, error budgets, postmortem culture, security review on major changes.
- **Run**: chaos engineering, advanced observability, threat modeling, SOC 2 / ISO compliance.

## Hiring and retention

CTO's job is making engineering an attractive place to work AND filtering aggressively for fit.

Hiring filters by stage:
- Early stage: generalists who can learn fast. Resilience over expertise.
- Growth: domain experts in critical areas (e.g., distributed systems, ML).
- Scale: leaders + ICs in equal measure.

Retention drivers (in order):
- Compensation (table stakes).
- Manager quality.
- Interesting work.
- Career growth.
- Culture / mission.

Most attrition is manager-driven. Invest there.

## Output format

Save advisory notes to `outputs/cto-advisor/<topic>-<date>.md`:

```
## CTO advisory: <topic>
- Stage: <stage>
- Eng size: <count>

## Current state
[Architecture, org, debt position, reliability, hiring]

## Recommendation
[Specific direction with reasoning]

## Sequencing / risks
[Order of operations, watchouts]

## Measurement
[Leading indicators of progress]
```

## Common mistakes

- Building when buying is right.
- Hiring specialists before generalists are utilized.
- Treating platform teams as "no-customer" zones.
- Letting technical debt go invisible.
- Underinvesting in reliability / security until forced.
- Confusing engineering with the CTO's hands-on coding (at any meaningful scale, the CTO must be a leader, not just a tech).

## Cross-references

For tactical engineering skills, use the development-tagged skills (code-reviewer, security-auditor, debug-assistant, refactor-assistant, etc.). For incident response, use `incident-responder`. For team-level project management, use `project-manager`. For ops decisions adjacent to engineering, use `devops-assistant`.

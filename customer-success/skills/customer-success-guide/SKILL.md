---
name: customer-success-guide
description: Build customer success playbooks, health scoring models, and retention strategies. Use when designing onboarding flows, QBR prep, churn prevention, or expansion plays.
triggers:
  - customer success
  - churn prevention
  - QBR prep
---

# Customer Success Guide

Build systems that keep customers successful and growing. Drive outcomes before the customer asks for help, using health scores and lifecycle playbooks to trigger action.

## Customer Lifecycle Framework

Every customer moves through these stages. Map playbooks and health indicators to each:

```
[Closed Won] → Onboarding → First Value → Adoption → Steady State → Expansion → Renewal
```

### Stage Definitions
| Stage | Duration | Success Criteria | Risk If Stalled |
|-------|----------|-----------------|----------------|
| Onboarding | 0-30 days | Core setup complete, key users trained | Buyer's remorse, early churn |
| First Value | 30-60 days | Customer achieves their stated primary goal | Abandonment, support escalation |
| Adoption | 60-120 days | Usage expands beyond initial users/use cases | Flat usage, single-threaded risk |
| Steady State | 120+ days | Consistent usage, positive sentiment, low support | Complacency, competitor vulnerability |
| Expansion | Any | Customer sees value in additional products/seats | Missed revenue opportunity |
| Renewal | 90 days pre-renewal | Decision maker engaged, value documented | Churn or downgrade |

## Health Score Model

Build a composite health score from leading indicators. Weight signals by their predictive power for renewal:

### Signal Categories
| Signal | Weight | Data Source | Green (Healthy) | Yellow (At Risk) | Red (Critical) |
|--------|--------|-----------|-----------------|-----------------|---------------|
| **Product usage** | 30% | Analytics | Above median for segment | Declining >20% MoM | Below 25th percentile or no login 14+ days |
| **Engagement** | 25% | CRM, email | Responds to outreach, attends calls | Slow responses, declines meetings | Unresponsive for 30+ days |
| **Support** | 20% | Ticketing | Low volume, high satisfaction | Increasing volume or escalations | Unresolved P1, executive complaint |
| **Sentiment** | 15% | NPS, calls | NPS 8+, positive call notes | NPS 6-7, neutral/mixed signals | NPS 0-5, negative feedback, complaints |
| **Contract** | 10% | CRM | Multi-year, expanding | Single year, flat | Month-to-month, downgraded, overdue payment |

### Score Calculation
```
Health Score = Sum of (Signal Score x Weight) for all signals
Green: 80-100  |  Yellow: 50-79  |  Red: 0-49
```

### Refresh Cadence
- Automated signals (usage, support): Daily
- Manual signals (engagement, sentiment): After every customer interaction
- Full score review: Weekly for Red accounts, biweekly for Yellow, monthly for Green

## Playbook: Onboarding (Day 0-30)

| Day | Action | Owner | Deliverable |
|-----|--------|-------|------------|
| 0 | Internal handoff call (Sales → CS) | AE + CSM | Handoff doc with goals, stakeholders, deal context |
| 1 | Welcome email with onboarding timeline | CSM | Email template with login, resources, first meeting |
| 3 | Kickoff call | CSM | Kickoff deck: goals, timeline, success criteria, roles |
| 7 | Technical setup checkpoint | CSM | Setup completion checklist |
| 14 | Training session for end users | CSM | Training materials, recording |
| 21 | First value check-in | CSM | Usage report, goal progress assessment |
| 30 | Onboarding graduation | CSM | Transition to steady-state cadence, document milestones achieved |

**Onboarding risk triggers:**
- Setup not completed by day 10 → Escalate to technical resources
- Key stakeholder disengaged by day 14 → Executive sponsor outreach
- No usage by day 21 → Emergency intervention: discovery call to re-align goals

## Playbook: QBR Preparation

### 30 Days Before QBR
- Pull usage data and trend analysis
- Compile ROI metrics tied to the customer's original goals
- Identify expansion opportunities based on usage patterns
- Prepare risk items that need executive attention

### QBR Agenda (60 minutes)
| Section | Time | Content |
|---------|------|---------|
| Wins review | 15 min | Measurable outcomes achieved (their metrics, not yours) |
| Usage insights | 10 min | Adoption trends, power users, underused features |
| Roadmap alignment | 15 min | Upcoming features mapped to their priorities |
| Strategic discussion | 15 min | Their business changes, new goals, expansion needs |
| Action items | 5 min | Clear next steps with owners and deadlines |

**QBR rule:** Lead with THEIR results, not your product updates. The customer cares about their outcomes, not your release notes.

## Playbook: Churn Prevention

### Early Warning Detection
| Signal | Threshold | Urgency | Response |
|--------|----------|---------|----------|
| Login frequency drop | >30% decline over 2 weeks | High | Personalized check-in call |
| Champion departure | Key contact leaves company | Critical | Identify new champion within 48 hours |
| Support escalation | P1 ticket unresolved 5+ days | Critical | Executive involvement, daily updates |
| NPS drop | Score drops below 6 | High | Root cause call within 1 week |
| Payment issues | Invoice overdue 30+ days | Medium | Finance + CS joint outreach |
| Competitor mention | Customer mentions evaluating alternatives | Critical | Executive engagement, value reinforcement |

### Save Motion
When a customer signals churn intent:
1. **Acknowledge** — Do not get defensive. Thank them for being direct
2. **Diagnose** — Ask: "What would need to change for you to stay?"
3. **Propose** — Offer a concrete resolution with timeline
4. **Escalate** — Bring in executive sponsor if needed
5. **Document** — Win or lose, record the reasons for future prevention

## Playbook: Expansion

Identify expansion signals:
- Feature usage approaching plan limits
- New departments or teams requesting access
- Customer asking about capabilities they do not have
- Successful ROI that enables budget for more investment

**Expansion approach:** Frame expansion as solving a new problem, not selling more product. "Based on your usage, your design team would benefit from..." not "Would you like to add more seats?"

## Output Format

Save to `outputs/cs-playbook-[segment-or-account].md` with:

- Customer lifecycle stage map with criteria
- Health score model with signal definitions and thresholds
- Stage-specific playbook (actions, owners, timelines)
- QBR template
- Churn risk detection matrix
- Expansion signal inventory

## Do NOT
- Treat all customers the same regardless of segment or ARR tier
- Wait for churn signals before engaging — proactive outreach prevents problems
- Focus only on retention — expansion is often the bigger revenue opportunity
- Present QBRs as product demos — focus on the customer's business outcomes
- Ignore champion changes — a new decision maker is the highest-risk moment in any account

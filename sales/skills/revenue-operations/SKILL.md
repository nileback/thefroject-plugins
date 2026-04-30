---
name: revenue-operations
description: Optimize the revenue pipeline from lead to closed deal to renewal. Covers forecasting, CRM hygiene, marketing-to-sales handoffs, deal velocity, and GTM metrics. Use when pipeline is leaking, forecasts are unreliable, or growth is stalling despite lead volume.
triggers:
  - revenue operations
  - RevOps
  - pipeline analysis
  - forecast accuracy
  - CRM cleanup
  - revenue pipeline
  - deal velocity
allowed-tools: []
---

# Revenue Operations

Fix the revenue pipeline. Revenue operations sits at the intersection of marketing, sales, and customer success. The goal is reliable, predictable revenue growth.

## Context Scan

Check `context/` for sales targets, pipeline data, or CRM documentation. Check `outputs/` for prior pipeline analyses.

## Writes
- `outputs/revops-analysis-[date].md`

## Step 1: Pipeline Health

Assess:
- **Coverage ratio** — pipeline value / quota. Healthy: 3-4x for enterprise, 2-3x for SMB.
- **Stage distribution** — where are deals clustering? Bottleneck = conversion problem at that stage.
- **Aging** — average days in each stage. Stale deals (2x average age) should be killed or re-engaged.
- **Win rate** — by stage, by rep, by source, by deal size. Where is it dropping?
- **Velocity** — (# opportunities x win rate x deal size) / sales cycle length

## Step 2: Handoff Audit

Map every handoff in the revenue process:
- Marketing → SDR (MQL criteria, response time, routing rules)
- SDR → AE (SQL criteria, what context transfers, how fast)
- AE → CS (onboarding kickoff, what information transfers, timeline)

For each handoff:
- Is the criteria documented and agreed upon by both sides?
- What data travels with the handoff? What gets lost?
- What is the SLA (response time, follow-up cadence)?

## Step 3: Forecasting

Build or audit the forecast:
- **Commit** — deals the rep is confident will close this period
- **Best case** — deals that could close with favorable conditions
- **Pipeline** — everything else that is qualified
- **Weighted pipeline** — deal value x probability by stage

Track forecast accuracy: compare predictions to actuals each month. If accuracy is below 80%, the problem is usually stage definitions (deals in wrong stages) or happy ears (reps overcommitting).

## Step 4: CRM Hygiene

Common CRM problems:
- Deals stuck in early stages for months (not real opportunities)
- Missing close dates or amounts
- Duplicate contacts/companies
- No activity logged on "active" deals
- Inconsistent stage definitions across reps

Prescribe specific cleanup actions and ongoing hygiene rules.

## Step 5: Recommendations

Prioritized list of:
1. **Quick wins** — things that improve pipeline visibility this week
2. **Process fixes** — handoff improvements, stage redefinition, SLA enforcement
3. **Tooling changes** — CRM configuration, automation, reporting
4. **Strategic shifts** — targeting, pricing, or go-to-market changes

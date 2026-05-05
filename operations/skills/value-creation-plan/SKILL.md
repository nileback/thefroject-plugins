---
name: value-creation-plan
description: Build a post-acquisition value creation plan (VCP). Identifies the levers — revenue, cost, capital structure, exit readiness — and assigns owners and timelines. For pre-deal due diligence use dd-checklist.
triggers:
  - value creation plan
  - vcp
  - post-acquisition plan
  - 100-day plan
  - portfolio company plan
---

# Value Creation Plan (VCP)

Build a value creation plan for a portfolio company or post-acquisition target. The VCP is the operational blueprint for delivering the returns underwritten in the deal model.

## Gather context

Ask if not provided:

1. **Deal context** — entry multiple, hold period, target IRR/MOIC, key thesis points?
2. **Current state** — recent financials, growth trajectory, profitability, leadership team?
3. **Sponsor model** — financial buyer (PE), strategic buyer (corporate), founder?
4. **Time horizon** — full hold period (3-7 years) or first-100-day specifically?
5. **Operational constraints** — debt covenants, regulatory, talent gaps?

## The four lever categories

Every VCP works across the same four lever categories. Identify 2-4 specific levers per category for this company.

### 1. Revenue levers

- **Pricing optimization** — raise prices on under-priced segments, premium-tier introduction, eliminate discount creep.
- **Customer expansion** — cross-sell, upsell, geographic expansion, new use case.
- **New segment entry** — adjacent vertical or geography.
- **Product expansion** — adjacent products, platform extension.
- **Sales productivity** — improve rep ramp time, win rate, ACV.

### 2. Cost levers

- **Procurement** — renegotiate vendor contracts, consolidate spend, shift to better-priced alternatives.
- **Headcount efficiency** — span-of-control improvements, hiring discipline, role consolidation.
- **Working capital** — DSO reduction, DPO extension, inventory optimization.
- **Real estate** — consolidation, sublet, remote-first transitions.
- **Tech stack** — eliminate redundant tools, renegotiate enterprise contracts.

### 3. Capital structure levers

- **Debt optimization** — refinance at better rates, extend maturity, optimize capital stack.
- **Working capital financing** — A/R financing, factoring, supply chain finance.
- **Tax structure** — entity rationalization, tax-loss utilization.
- **Dividend recapitalization** — return capital to sponsor before exit.

### 4. Exit-readiness levers

- **Multiple expansion drivers** — improve growth, margin, durability metrics that buyers reward.
- **Audit-ready financials** — clean Big-4 audited statements, especially for public exit.
- **Management team strength** — fill gaps, develop successors so the team doesn't follow you on exit.
- **Customer concentration** — diversify away from any single customer over 20% of revenue.
- **Strategic story** — clear narrative for the next buyer.

## Workflow

### Step 1: Diagnose
Where is the company today on each lever? Quantify if possible.

### Step 2: Prioritize
Rank levers by:
- Expected dollar impact.
- Time to capture (faster = higher priority).
- Resource cost.
- Strategic risk.

Pick 5-8 highest-priority levers for active focus. The rest go to a backlog.

### Step 3: Set targets and own
For each priority lever:

```
Lever: <name>
Owner: <name>
Baseline: <current state>
Target: <specific number, by when>
Plan: <key actions in next 90 days>
Risk: <what could prevent this>
```

### Step 4: Build the cadence
- Weekly: lever owners check in on top 3-5 levers.
- Monthly: cross-functional review.
- Quarterly: VCP refresh — what's working, what to drop, what to add.
- Annual: full VCP rebuild.

### Step 5: Track in the model
Update the financial model quarterly with VCP impact. Show: with VCP execution vs. without. The delta is the value being created.

## First-100-day variant

For brand-new acquisitions, a focused first-100-day plan often precedes the full VCP. Format:

```
Days 1-30 — Stabilize
- Establish operating cadence with new exec team.
- Cultural integration check.
- Quick-win lever execution (1-2 high-confidence items).

Days 31-60 — Diagnose
- Full operating review by function.
- Refined lever list with quantified targets.

Days 61-100 — Activate
- Top 3 levers active with owners and milestones.
- 100-day report to sponsor / investment committee.
```

## Output

Save the VCP to `outputs/vcp/<company>-<date>/`:
- `master-plan.md` — the full plan with all priority levers.
- `100-day-plan.md` — first-100-day version (if applicable).
- `tracking.md` — running scoreboard updated quarterly.
- `exit-readiness.md` — exit-side levers tracked separately.

For portfolio of companies (sponsor-side), maintain a portfolio-wide view at `outputs/vcp/portfolio.md`.

These files are highly sensitive. Store privately.

## Common mistakes

- Generic plan that could apply to any company. VCP must be specific.
- Too many priorities. Pick 5-8 levers; the rest goes to backlog.
- No quantification. "Improve pricing" without target = aspiration, not plan.
- Owner without authority. Lever owner must have the power to execute.
- Set-and-forget. Plans need quarterly refresh as conditions change.

## Cross-references

For pre-acquisition due diligence, use `dd-checklist`. For investment committee memos, use `ic-memo`. For ongoing portfolio monitoring, use `portfolio-monitoring`. For underlying financial model, use `three-statement-model`. For specific lever execution at the company level, use the relevant tactical skills (`pricing-strategist`, `procurement` skills, etc.).

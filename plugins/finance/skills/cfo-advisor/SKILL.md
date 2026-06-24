---
name: cfo-advisor
description: CFO-level strategic counsel. Capital allocation, runway, fundraise prep, working capital, financial discipline, M&A finance. Tagged executive + finance. For tactical financial modeling use financial-model-builder; for unit economics specifically use saas-metrics-coach.
triggers:
  - cfo decision
  - capital allocation
  - runway management
  - fundraise prep
  - cfo advisor
  - financial strategy
---

# CFO Advisor

CFO-level advice on capital and financial strategy. The CFO's job is making sure the company has the money it needs at the moments it needs it, deployed where it creates the most value.

## Gather context

Ask if not provided:

1. **Stage** — pre-revenue, early revenue, growth, mature?
2. **Capital structure** — venture-backed, bootstrapped, debt, hybrid?
3. **Runway** — cash + commit revenue ÷ monthly burn?
4. **Decision** — fundraise sizing, capital deployment, restructuring, M&A, IPO prep?
5. **Constraints** — board expectations, debt covenants, regulatory?

## Capital allocation framework

The CFO's primary role: deciding where the next dollar goes. Frame each option on:

- **Expected return** — what's the realistic upside?
- **Time to return** — months until impact?
- **Risk** — what's the downside if it fails?
- **Reversibility** — can we redeploy if it doesn't work?

Common allocations to evaluate:
- Sales hiring (typical payback: 12-18 months for SMB, 18-24 for enterprise).
- Marketing spend (payback: 6-12 months for paid; 12-24 for content/SEO).
- Engineering (payback measured in product capability + retention impact).
- M&A (payback varies wildly; often longer than projected).
- Cash reserve (the option value of not deploying).

Each dollar competes with the others. The CFO's job is to surface the trade-offs, not pick favorites.

## Runway management

Runway = cash + future committed revenue minus future committed costs, calculated monthly.

Targets by stage:
- Pre-PMF: 18+ months desired; 12 months acceptable.
- Post-PMF, growth mode: 18-24 months desired.
- Late-stage / mature: 12+ months acceptable; varies by predictability.

Runway monitoring:
- Update monthly with actuals.
- Refresh assumptions quarterly.
- Triggered alerts: 18 months (start fundraise prep), 12 months (begin raise), 9 months (cut costs if no commitment), 6 months (emergency mode).

## Fundraise prep

Six months before round close:
- Define the round size based on what the company actually needs (not what's "trendy" for the stage).
- Build the financial model: 3-year forecast with monthly granularity for year 1, quarterly for years 2-3.
- Document key metrics: ARR growth rate, magic number, net retention, gross margin, payback, burn multiple.
- Prep the data room: financials, metrics, customer logos, hiring plan, KPI dashboards.
- Identify lead investor candidates first; fill the round around the lead.

Three months before:
- Final model review; align with CEO on numbers and narrative.
- Practice the investor pitch with hostile questions.
- Set the timeline: target 6-week process, hard end-date.

## Working capital

Often-overlooked CFO domain. Cash gets stuck in:
- Accounts receivable (long DSO with enterprise customers).
- Inventory (for any physical goods).
- Prepaid expenses.

For SaaS specifically:
- Annual upfront billing dramatically improves working capital.
- Mid-cycle pricing-tier changes recover lost cash.
- Revenue financing can bridge cash needs without dilution.

## Burn multiple framework

A modern way to evaluate burn efficiency:

```
Burn Multiple = Net Burn ÷ Net New ARR
```

Reasonable ranges:
- <1: efficient
- 1-1.5: good
- 1.5-2: questionable
- 2-3: bad
- >3: very bad

Use this in board reporting and as a north star for capital efficiency.

## M&A from the CFO seat

Three roles in M&A:
- **Source side** (CFO of acquirer): financial diligence, deal structure, integration plan.
- **Target side** (CFO of target): preparing for diligence, negotiating terms, post-close transition.
- **Advisor**: helping CEO evaluate strategic fit and price.

Each requires the financial model, but with different sensitivities.

## Output format

Save analysis to `outputs/cfo-advisor/<topic>-<date>.md`:

```
## CFO advisory: <topic>
- Stage: <stage>
- Constraint: <key constraint>

## Current state
- Runway: <months>
- Burn multiple: <ratio>
- Other key metrics: ...

## Decision options
1. ...
2. ...

## Capital allocation recommendation
[Reasoning, expected impact, watchouts]

## Triggers
[What signals would change this recommendation]
```

## Common mistakes

- Optimizing for accounting income instead of cash.
- Treating runway as a single number; it varies by scenario.
- Fundraising too late (forced, weak terms).
- Underweighting working capital.
- Not communicating the financial reality to the rest of the leadership team.

## Cross-references

For tactical financial modeling, use `financial-model-builder`, `forecast-modeler`, `cash-flow-forecaster`. For unit economics, use `saas-metrics-coach`. For board reporting, use `board-deck-builder`. For scenario modeling, use `scenario-modeling` and `scenario-war-room`. For investor updates, use `investor-update-writer`. For M&A specifically, use `m-and-a-playbook`.

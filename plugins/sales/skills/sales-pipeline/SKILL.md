---
name: sales-pipeline
description: Run pipeline reviews. Audit stage hygiene, surface stalled deals, identify coaching moments, build the weekly forecast. The manager view across open deals; for a single deal's strategy use deal-strategy-analyzer.
triggers:
  - pipeline review
  - weekly forecast
  - pipeline hygiene
  - deal review
  - sales pipeline coverage
  - stalled deals
---

# Sales Pipeline

Run a structured pipeline review. The output is a forecast, a list of deals needing intervention, and coaching themes for the team.

## Gather context

Ask if not provided:

1. **Sales motion** — SMB / mid-market / enterprise. Different stage definitions and review cadences.
2. **Stage definitions** — what does each stage mean and what's the entry/exit criteria? (See `revops-analyst` for the lifecycle framework.)
3. **Forecast methodology** — commit / best case / worst case / weighted? AI-assisted?
4. **Cadence** — daily standup, weekly review, monthly forecast call?
5. **Reps** — how many, tenure mix, current quota attainment?

## Pipeline hygiene checklist

Run these checks before any forecast meeting. Bad hygiene corrupts every downstream metric.

### Per-deal checks
- **Stage matches entry/exit criteria.** A deal in "proposal sent" with no proposal attached is mis-staged.
- **Close date is realistic.** Deals with close dates in the past (and still open) are stale.
- **Next step is concrete.** "Follow up next week" is not a next step. "Call with VP Eng on Tuesday 2pm" is.
- **Last activity within 14 days.** Anything older is stalled until proven otherwise.
- **Amount is realistic.** Enterprise deals at SMB amounts and vice versa flag mis-segmentation.
- **Champion identified.** No champion = no deal.

### Per-rep checks
- **Coverage ratio** = open pipeline ÷ remaining quota. Healthy = 3-4x.
- **Win rate** by stage (last 90 days). Drops at specific stages indicate coaching needs.
- **Avg deal cycle.** Outliers (deals taking 2x longer than average) need scrutiny.
- **Stage distribution.** Top-heavy (mostly early stages) means a forecasting risk; bottom-heavy means closing pipeline isn't being replenished.

### Per-team checks
- **Pipeline composition** — net new vs renewal vs expansion. Should match strategy.
- **Lead source mix** — diversified or over-indexed on one channel?
- **Average deal size** trend — growing, flat, or shrinking?
- **Manufactured pipeline** — deals created in last 30 days vs last quarter. Flat or declining = top-of-funnel problem.

## Forecast methodology

A defensible forecast has three views:

| View | Definition | Confidence |
|---|---|---|
| Commit | Will close this period unless something extraordinary. | 90%+ |
| Best case | Realistic upside with current effort. | 50-70% |
| Worst case | Confirmed signed business minus refunds. | 95%+ |
| Pipeline | Everything else with realistic close. | Variable |

Each rep submits commit + best case weekly. Manager rolls up. Compare to history: if the team consistently misses commit by 20%, the commit definition is broken.

## Coaching themes from pipeline data

Patterns that signal coaching opportunities:
- Many deals stall at the same stage -> stage-specific skills gap (e.g., negotiation, technical demo, exec engagement).
- Deals close-won at much smaller amounts than initial quote -> discounting habit, weak champion.
- High win rate but small deals -> upmarket capability gap.
- Long deal cycles vs peer reps -> qualification weakness or mid-funnel skills gap.

Tag these themes in the review and assign 1-2 coaching focuses per rep for the next month.

## Output format

After each review, save `outputs/sales-pipeline/<date>-review.md`:

```
## Pipeline review — <date>

## Forecast
- Commit: $<amount> (<count> deals)
- Best case: $<amount>
- Worst case: $<amount>
- Pipeline: $<amount>

## Hygiene issues found
- <count> deals with stale next steps -> assigned to reps for cleanup by <date>
- <count> deals mis-staged -> moved to <stage>
- <count> stalled deals -> action plan or close-lost decision needed

## At-risk deals (intervention required)
- <Account> — <amount> — <reason> — <action> — <owner>

## Coaching themes
- <Rep>: <theme> -> <next step>
```

## Common mistakes

- Reviewing the forecast without first cleaning hygiene. Garbage in, garbage out.
- "Happy ears" — taking the rep's word that a deal is on track without evidence.
- No standardized stage definitions across reps. Each rep means something different by "proposal sent."
- Skipping the team-level pattern review. Individual deals add up to systemic problems.

## Cross-references

For lifecycle stage definitions and the revops layer, use `revops-analyst`. For single-deal strategy, use `deal-strategy-analyzer`. For cold outreach to refill the pipeline top, use `sales-outreach-writer` and `cold-email-writer`. For coaching specifically, use (when added) `sales-coaching`. For ABM-driven pipeline, use `abm-orchestration`.

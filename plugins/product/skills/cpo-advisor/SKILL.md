---
name: cpo-advisor
description: Chief Product Officer-level strategic counsel. Product strategy, roadmap-to-strategy alignment, product/eng partnership, product org design. For tactical product skills use the product role.
triggers:
  - cpo strategy
  - product leadership
  - product strategy
  - roadmap strategy
  - cpo advisor
  - product org
---

# CPO Advisor

Chief Product Officer counsel — connecting business strategy to product execution. The CPO's job is making sure what gets built ladders up to what matters.

## Gather context

Ask if not provided:

1. **Stage** — pre-PMF, growth, scale, mature?
2. **Product nature** — single product, multi-product, platform?
3. **Org size** — PM team size, eng team size, design team size?
4. **Current state** — roadmap mature? Strategy alignment? Tech debt position?
5. **Decision** — strategy refresh, org change, ship/cut, hire?

## Strategy-to-roadmap alignment

The single most common CPO failure: roadmap that doesn't ladder to strategy.

Test: pick the next 3 things shipping. Ask "which strategic priority does this serve?" If unclear, the strategy or the roadmap is wrong.

To fix:
- Re-articulate strategy in 3-5 priorities (one quarter at a time, max).
- Force every roadmap item to declare which priority it serves.
- Cut items that serve nothing on the priority list.
- Add items that serve priorities but aren't on the roadmap yet.

## Roadmap principles

Working roadmaps have these traits:

### Quarterly granularity (not weekly)
Roadmaps that try to predict weeks of work 6 months out are fiction. Quarterly granularity is honest.

### Three time horizons
- **Now**: this quarter's commitments. Specific.
- **Next**: next quarter's likely focus. Less specific; subject to learning.
- **Later**: 6+ months out. Themes, not features.

### Themes over features at the higher level
"Q3 focus: deepen mid-market integrations" beats "Ship Salesforce integration, ship HubSpot integration, ship Marketo integration."

### Outcome-tied
Each roadmap item should have an outcome it's meant to drive (activation rate up X%, expansion conversion up Y%). Not all items will hit; the discipline of stating the outcome forces clarity.

## Product/eng partnership

The CPO and CTO/VP Eng have to be a unit. Common failure modes:
- **Throwing requirements over the wall** — PM writes spec, eng builds, neither talks. Bad shipping.
- **Process bloat** — too many ceremonies (planning, refinement, retro, demo), low signal-to-noise.
- **Capacity mismatch** — PM team plans for 3x what eng team can deliver. Constant slippage.
- **Tech debt invisible** — eng wants to invest 30%+ of time in foundations; PM rejects because no customer-facing impact.

Healthy partnership:
- Shared roadmap (not "PM roadmap" + "eng roadmap").
- Tech debt as first-class roadmap items, not "if there's time."
- Joint decisions on staffing, hiring, structure.
- Weekly leadership lockstep.

## Product org design

Org structure by stage:

### Pre-PMF
- 1-2 PMs (often founder).
- No design managers; designers work directly with PMs.
- Eng team small enough to not need product hierarchy.

### Growth (5-15 PMs)
- 1 PM per major product area or persona.
- Senior PMs / lead PMs for systems work.
- Design as a peer function, paired with eng + PM.
- Research function emerging (1-2 user researchers).

### Scale (15-50 PMs)
- VP product with PM directors per area.
- Design directors per area.
- Research function with manager.
- Product ops (analytics, tooling, processes).
- Product marketing tightly partnered (could report to PMM lead in marketing or to CPO).

### Mature
- CPO with VPs.
- Specialty functions: platform PMs, growth PMs, AI/ML PMs, etc.

Don't over-specialize early. Generalist senior PMs cover more ground than specialists with low utilization.

## Common patterns to flag

- "We need to ship faster." -> Usually need to ship LESS (cut roadmap), not faster.
- "Engineering is too slow." -> Usually scope is too large. Right-size the work.
- "Customers don't want what we're building." -> Find out why; usually misaligned with the actual ICP.
- "We need a platform team." -> Maybe. Often a platform team is created to escape the customer-facing roadmap. Validate.

## Reporting up

The CPO owes the CEO and board:
- **Monthly**: shipping cadence, key metric movement (activation, retention, expansion), roadmap progress.
- **Quarterly**: strategy fit retro, customer feedback themes, competitive moves and product responses.
- **Annually**: product strategy refresh, org evolution, tech debt position.

## Output format

Save advisory notes to `outputs/cpo-advisor/<topic>-<date>.md`:

```
## CPO advisory: <topic>
- Stage: <stage>
- Org state: <PM/eng/design size>

## Current state
[Strategy clarity, roadmap-to-strategy fit, eng partnership, org structure]

## Recommendation
[Specific direction]

## Sequencing
[What changes when, dependencies]

## Watchouts
[Risks specific to this change]
```

## Common mistakes

- Roadmap not connected to strategy.
- Too much eng capacity on visible features, not enough on foundations.
- Hiring specialists before generalists are saturated.
- Letting product management process bloat.
- Underinvesting in research/discovery.

## Cross-references

For tactical product skills (PRDs, roadmaps, user research, JTBD), use product-tagged skills like `prd-writer`, `roadmap-planner`, `jobs-to-be-done`, `user-researcher`. For strategy specifically, use `positioning-generator` and `messaging-hierarchy` (often blended product/marketing). For PLG-specific strategy, use `plg-strategy-builder`.

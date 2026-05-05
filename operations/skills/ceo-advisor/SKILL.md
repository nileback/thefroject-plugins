---
name: ceo-advisor
description: CEO-level strategic advice. Frames decisions across strategy, board management, fundraising, hiring, and operating cadence. Tagged for executive role users (founders, CEOs, COOs operating as CEO). Distinct from chief-of-staff (operational support) and founder-coach (personal development).
triggers:
  - ceo decision
  - founder strategy
  - board prep
  - exec strategy
  - ceo advisor
  - ceo coaching
---

# CEO Advisor

Help a CEO or founder think through strategic decisions. Not operational tactics; strategic decisions are characterized by reversibility (low) and impact (high).

## Gather context

Ask if not provided:

1. **Stage** — pre-product/market fit, post-PMF, scale, mature. Different decisions matter at each.
2. **The decision at hand** — fundraise sizing, key hire, geo expansion, pivot, layoff, M&A, board management, succession?
3. **Constraints** — runway, board composition, team readiness, market window?
4. **Information available** — what's known? What's assumed? What's missing?
5. **Time pressure** — when does this need to be decided?

## The CEO operating cadence

Mature CEOs have a consistent rhythm. Map the user's current cadence against this:

- **Daily** — leadership team check-in (10-15 min), inbox triage, top-priority deep work.
- **Weekly** — leadership 1:1s, exec team meeting, business review (key metrics).
- **Monthly** — investor update, deeper financial review, hiring pipeline review.
- **Quarterly** — board meeting, strategic planning, performance reviews.
- **Annually** — strategic planning offsite, comp planning, board composition review.

If any are missing, that's the first thing to fix.

## Strategic decision frameworks

### Resource allocation
At any time, the CEO should be able to answer: "What are the 3 things this company is investing the most in, and why those?"

If the answer is "growth, product, customer success" — too vague. The right answer is specific bets ("expanding to mid-market, building the integration layer, launching the certification program").

If the team can't articulate the top 3, the CEO has not allocated.

### Hiring strategy
For each role at exec level (VP and above):
- Why now? (Trigger event or capability gap.)
- What are we NOT doing because we'll have this person?
- Build vs buy: can someone internal grow into it?
- Cost of getting it wrong: how much does the wrong hire cost in time + capital + team morale?

The cost of a wrong VP hire is typically 2-4x their annual comp. Double the time-to-hire over rushing to a mediocre fit.

### Board management
Boards work when the CEO drives the relationship. Common failure modes:
- Treating the board as an audit (hiding bad news).
- Treating the board as therapy (dumping problems without ownership).
- Treating the board as decision-makers (asking them to decide things you should decide).

The right model: monthly investor update + quarterly board meeting + ad-hoc 1:1s on specific topics. CEO frames decisions; board provides input + holds CEO accountable for execution.

### Fundraising rhythm
Round timing is strategic, not opportunistic.
- Raise when you have a story (after a clear data point: PMF signal, expansion success, market shift).
- Don't raise when you're forced to (low runway = bad terms).
- Best CEOs maintain 18-24 months runway minimum and raise from a position of strength.

### Pivot decisions
The hardest CEO call. Indicators that a pivot is needed:
- 12+ months without meaningful PMF signal.
- Customers buy but don't expand or refer.
- Each new feature gets the same shrug from the market.
- Your best hires are leaving.

If the indicators are there, a pivot is harder to delay than to execute. Most pivots happen too late.

### Layoffs / restructuring
The decision to lay off is preceded by 2-3 quarters of evidence the company can't grow into the cost structure. Once decided:
- Speed matters: long-rumored layoffs damage trust more than the layoff itself.
- Cut deeper than feels comfortable: 10% cuts often need to be done twice; 15-20% once.
- Communicate honestly: see `internal-comms` for sensitive memo writing.
- Take responsibility publicly. The CEO made the calls that led here.

## Common patterns to flag

- "Everything is on fire." -> If everything is critical, nothing is. Force prioritization.
- "We need to hire faster." -> Usually slower-with-more-rigor hiring is the right answer.
- "Our team is the best in the industry." -> Heard universally. Not a fact, not actionable.
- "We just need to ship X." -> What's after X? If unclear, the strategy isn't a strategy.
- "We need to think about strategy more." -> Time-box it. A quarter of "thinking" is procrastination.

## Output format

Save advisory notes to `outputs/ceo-advisor/<topic>-<date>.md`:

```
## CEO advisory: <topic>
- Stage: <stage>
- Decision: <what's being decided>
- Time pressure: <when>

## Frame
[How to think about the decision — relevant framework, comparable cases]

## Options considered
1. ...
2. ...

## Recommendation
[The advisor's take, with reasoning]

## Watchouts
[Risks specific to this decision]

## Next steps
[Specific, time-bound]
```

## Common mistakes

- Asking the CEO advisor to make the decision instead of frame it.
- Generic advice ("focus on the customer") that doesn't engage the specifics.
- Ignoring constraints (runway, team, market window) that change the answer.
- Optimizing for short-term certainty over long-term right answer.

## Cross-references

For the personal-leadership side (energy, delegation, IC-to-CEO), use `founder-coach`. For decision documentation through the lifecycle, use `decision-tracker`. For board materials, use `board-deck-builder` and `board-report-builder`. For investor-update writing between board meetings, use `investor-update-writer`. For scenario planning behind major decisions, use `scenario-war-room` and `scenario-modeling`. For the operational-execution layer behind the CEO, use `chief-of-staff`.

---
name: compensation-benchmarker
description: Research compensation benchmarks for specific roles and markets.
triggers:
  - compensation benchmark
  - salary research
  - pay bands
allowed-tools: [WebSearch, WebFetch, Read, Write]
---

# Compensation Benchmarker

Produce compensation analysis that supports fair, competitive pay decisions grounded in real market data.

## Phase 1 — Role Definition

Before searching for data, lock down the role parameters:

1. **Title normalization** — Map the internal title to market-standard equivalents (e.g., "Engineering Lead" may map to "Staff Engineer" or "Engineering Manager" depending on scope)
2. **Level calibration** — Use a leveling framework: IC1-IC6 for individual contributors, M1-M4 for management. Map to Radford levels or equivalent
3. **Scope markers** — Team size (if manager), revenue responsibility, technical depth, years of relevant experience
4. **Skills premium** — Identify specialized skills that command a premium (ML/AI, security, specific cloud certifications)

## Phase 2 — Market Scoping

Define the competitive market precisely:

- **Geography tiers** — Tier 1 (SF, NYC, London), Tier 2 (Austin, Denver, Berlin), Tier 3 (smaller metros), Remote-adjusted
- **Company stage** — Pre-seed through Series D, growth-stage, public. Each has different comp philosophy
- **Industry** — Tech, fintech, healthcare, etc. Industry premiums can shift ranges 10-20%
- **Headcount** — Sub-50, 50-200, 200-1000, 1000+. Correlates with formality of comp bands

## Phase 3 — Data Collection

Gather from multiple sources and cross-reference:

| Source | Strength | Limitation |
|--------|----------|------------|
| Levels.fyi | Real verified offers, equity detail | Skews Big Tech |
| Glassdoor | Broad coverage | Self-reported, often stale |
| Payscale | Good for non-tech roles | Less granular at senior levels |
| Radford/Mercer | Gold standard for enterprises | Requires paid subscription |
| Pave/Carta | Real-time startup data | Startup-biased |
| Job postings | Shows current market intent | May not reflect actual offers |

For each source, record: date of data, sample size, geography, and any methodology notes.

## Phase 4 — Compensation Modeling

Build the full compensation picture at three percentiles:

### Total Compensation Breakdown
| Component | P25 | P50 | P75 | Notes |
|-----------|-----|-----|-----|-------|
| Base salary | | | | Annual, pre-tax |
| Annual bonus | | | | Target %, not guaranteed |
| Equity/RSU | | | | Annualized 4-year value |
| Signing bonus | | | | Amortized over expected tenure |
| **Total comp** | | | | Sum of above |

### Adjustment Factors
- **Cost of living** — Apply a geographic differential using a consistent index (e.g., Numbeo, ERI)
- **Remote discount/premium** — Document the policy: geo-based, national band, or location-agnostic
- **Stage adjustment** — Early-stage companies often offset lower base with higher equity upside
- **Hot market premium** — Identify if the role is in a talent shortage (quantify with time-to-fill data if available)

## Phase 5 — Recommendation

Synthesize into a clear recommendation:

1. **Proposed band** — Low / Mid / High with specific dollar amounts
2. **Positioning rationale** — Where in the band and why (experience, market conditions, internal equity)
3. **Internal equity check** — Flag if the proposed range creates compression with existing team members
4. **Offer strategy** — Suggested starting offer point, negotiation ceiling, and which levers to use (base vs. equity vs. signing)

## Output Format

Save to `outputs/comp-benchmark-[role-slug].md` with:

- Executive summary (3-4 sentences with the recommendation)
- Role definition table
- Market data table with source attributions
- Total comp breakdown at P25/P50/P75
- Geographic comparison (if multi-geo)
- Recommendation with rationale
- Data freshness statement: "Data collected [date], sources dated [range]"
- Confidence rating: High (3+ sources, large samples) / Medium (2 sources or small samples) / Low (limited data)

## Do NOT
- Present a single data source as definitive
- Mix base salary and total comp in the same comparison
- Omit the data vintage — compensation data older than 12 months is unreliable
- Provide ranges without percentile labels
- Include equity valuations without stating the valuation methodology and date
- Make recommendations without considering internal equity impact

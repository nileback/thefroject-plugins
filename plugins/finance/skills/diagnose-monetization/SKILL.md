---
name: diagnose-monetization
description: Evaluate your monetization strategy, identify revenue opportunities, and diagnose pricing issues. Use when revenue is below target, planning pricing changes, or exploring new revenue streams.
triggers:
  - diagnose monetization
  - pricing analysis
  - revenue diagnosis
  - monetization strategy
---

# Monetization Diagnostician

Monetization is not just pricing. It is the entire system of how value creation converts to revenue capture. Diagnose where the system leaks, where it could expand, and where pricing friction blocks growth.

## Phase 1 — Revenue Anatomy

Break down your current revenue by structure:

### Revenue Streams
| Stream | Monthly Revenue | % of Total | Growth Trend | Margin |
|--------|----------------|------------|-------------|--------|
| [subscription/license/usage/etc.] | [$] | [%] | [up/flat/down] | [%] |

### Revenue by Segment
| Segment | Users | Revenue | ARPU | % of Revenue |
|---------|-------|---------|------|-------------|
| Free/trial | [n] | $0 | $0 | 0% |
| [tier 1] | [n] | [$] | [$] | [%] |
| [tier 2] | [n] | [$] | [$] | [%] |
| Enterprise | [n] | [$] | [$] | [%] |

**Key question:** Do your highest-value users pay the most? If not, your pricing does not align with value delivery.

## Phase 2 — Pricing Health Check

### Value Metric Alignment
The best pricing is based on a metric that:
1. Scales with the value the customer receives
2. Is easy for the customer to understand
3. Grows as the customer succeeds

| Current Pricing Basis | Does it scale with value? | Is it intuitive? | Does it grow with success? |
|----------------------|--------------------------|-------------------|---------------------------|
| [per seat / per usage / flat / etc.] | [yes/no] | [yes/no] | [yes/no] |

### Willingness to Pay
If you have pricing survey data or competitive benchmarks:
- What is the "too cheap" threshold? (Below this, customers question quality)
- What is the "too expensive" threshold? (Above this, most customers will not buy)
- What is the "just right" range?
- How does your current price compare?

### Conversion Funnel
| Stage | Users | Conversion | Revenue Impact |
|-------|-------|------------|---------------|
| Visitors → Signup | [n] | [%] | |
| Signup → Trial/Free | [n] | [%] | |
| Trial → Paid | [n] | [%] | [$ impact of +1%] |
| Paid → Upgrade | [n] | [%] | [$ impact of +1%] |
| Paid → Churn | [n] | [%] | [$ lost per month] |

## Phase 3 — Find Revenue Leaks

### Under-Monetized Users
Are there users getting significant value but paying little or nothing?
- Power users on free tiers
- Large teams on per-seat plans that haven't grown
- Heavy usage accounts on flat-rate plans

### Pricing Friction
Where does pricing prevent growth?
- Do users avoid inviting teammates because of per-seat pricing?
- Do users limit usage to stay under thresholds?
- Do free tiers give away too much core value?
- Is the upgrade path unclear or poorly timed?

### Expansion Revenue
Are you capturing revenue growth from existing customers?
- **Net Revenue Retention (NRR):** Revenue from existing customers this period / Revenue from those same customers last period
- NRR above 100% means existing customers are growing. Below 100% means contraction outpaces expansion.

## Phase 4 — Opportunities

| Opportunity | Type | Estimated Impact | Effort | Risk |
|-------------|------|-----------------|--------|------|
| [specific change] | [pricing/packaging/new stream] | [$] | [S/M/L] | [H/M/L] |

### Common Levers
- **Packaging:** Bundle features differently to create clear upgrade reasons
- **Usage-based component:** Add a variable element that grows with value
- **Annual plans:** Offer discount for commitment, improve cash flow
- **Add-ons:** Premium features, support tiers, integrations as upsells
- **Expansion triggers:** Automated nudges when usage approaches tier limits

## Output

Write to `outputs/monetization-diagnosis-[date].md`:

1. **Revenue structure** — streams, segments, key metrics
2. **Pricing health** — value alignment, willingness to pay, conversion funnel
3. **Revenue leaks** — where money is left on the table
4. **Opportunities** — prioritized list of changes with expected impact
5. **Risks** — what could go wrong with each proposed change

## Do NOT
- Change pricing without understanding current customer sentiment
- Optimize for short-term revenue at the cost of activation or retention
- Ignore the psychological impact of pricing changes on trust
- Assume competitors' pricing is optimal — they may be wrong too

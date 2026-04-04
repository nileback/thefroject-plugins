---
name: renewal-strategist
description: Develop renewal strategies that maximize retention and expansion. Analyze timing, pricing, packaging, and negotiation approach for upcoming renewals. Use 60-120 days before renewal dates.
triggers:
  - renewal strategy
  - renewal planning
  - contract renewal
  - retention plan
---

# Renewal Strategist

Plan every renewal with the same rigor as a new deal. The renewal is where you prove the value you promised.

## Input Required

1. **Contract details** — current ARR, contract end date, terms, auto-renewal clauses
2. **Account health** — health score, usage data, support history (run Health Score Builder if needed)
3. **Stakeholder map** — decision maker, champion, detractors, new contacts since last deal
4. **Value delivered** — ROI metrics, outcomes achieved, usage milestones
5. **Expansion signals** — new use cases, additional teams, feature requests, budget conversations

## Renewal Assessment

### Step 1 — Risk and Opportunity Matrix

| Factor | Status | Impact | Notes |
|--------|--------|--------|-------|
| **Contract value** | $[ARR] | | |
| **Renewal date** | [Date] | [Days until renewal] | |
| **Health score** | [Score/100] | [Tier] | |
| **Champion status** | Active / Changed / Lost | High | |
| **Decision maker** | Identified / Unknown / Changed | High | |
| **Usage trend** | Growing / Flat / Declining | High | |
| **Open issues** | [Count and severity] | Medium | |
| **Competitive threat** | None / Evaluating / Active RFP | High | |
| **Budget climate** | Expanding / Stable / Cutting | Medium | |

### Step 2 — Value Summary

Build the case for renewal based on delivered outcomes:

| Value Category | Metric | Before | After | Impact |
|---------------|--------|--------|-------|--------|
| [Time savings] | [Hours/week] | [X] | [Y] | [Z hours saved] |
| [Cost reduction] | [$] | [X] | [Y] | [$Z saved] |
| [Revenue impact] | [$] | [X] | [Y] | [$Z generated] |
| [Quality] | [Metric] | [X] | [Y] | [Z% improvement] |

### Step 3 — Pricing Strategy

| Scenario | Price Change | Justification | Risk |
|----------|-------------|--------------|------|
| **Flat renewal** | 0% | Retain at current terms | Leaves money on the table if value is strong |
| **Inflationary** | 3-5% | Standard annual increase | Low risk if communicated early |
| **Value-based** | 10-20%+ | Expanded usage, demonstrated ROI | Moderate risk, requires strong value evidence |
| **Discount** | Negative | Save a at-risk account | Short-term fix, sets bad precedent |
| **Multi-year** | 5-10% discount | Lock in commitment, reduce churn risk | Lower per-year revenue, higher total contract value |

### Step 4 — Expansion Opportunities

| Opportunity | Type | Estimated Value | Readiness | Approach |
|------------|------|---------------|-----------|---------|
| [New team/department] | Cross-sell | $[Amount] | High/Med/Low | [How to introduce] |
| [Additional seats] | Upsell | $[Amount] | | |
| [Premium tier] | Upsell | $[Amount] | | |
| [New product/module] | Cross-sell | $[Amount] | | |

### Step 5 — Negotiation Planning

**Your position:**
- Walk-away point: $[minimum acceptable ARR]
- Target: $[ideal outcome including expansion]
- Opening: $[first proposal]

**Their likely position:**
- What they will ask for: [discount, features, terms]
- Their alternatives: [competitors, build in-house, do nothing]
- Budget constraints: [known or estimated]

**Concession strategy:**
| If they ask for... | Offer instead... | Because... |
|-------------------|-----------------|-----------|
| Price reduction | Multi-year commitment | Lock-in offsets the discount |
| Free features | Paid pilot with success criteria | Demonstrates value before commitment |
| Shorter term | Quarterly reviews | Addresses their flexibility concern |

## Output Format

Save to `outputs/renewal-strategy-[customer]-[date].md`:

```markdown
# Renewal Strategy — [Customer]
**ARR:** $[Amount] | **Renewal:** [Date] | **Risk:** [Low/Medium/High]

## Recommendation
[One paragraph: renew at $X with Y expansion, approach Z]

## Value Summary
[Key metrics showing ROI delivered]

## Pricing Proposal
[Recommended pricing with justification]

## Expansion Opportunities
[Ranked list with estimated values]

## Risk Mitigation
[Actions to address identified risks before the renewal conversation]

## Timeline
| Week | Action | Owner |
|------|--------|-------|
| [T-90 days] | Health check and value review | CSM |
| [T-60 days] | Stakeholder alignment meetings | CSM + AE |
| [T-45 days] | Pricing proposal prepared | AE + Finance |
| [T-30 days] | Formal renewal proposal sent | AE |
| [T-14 days] | Negotiation and close | AE |
```

## Principles

- Start renewal conversations 90+ days out. Renewals that start 30 days before expiration are negotiations from weakness.
- The renewal conversation is a value conversation, not a pricing conversation. Lead with outcomes delivered.
- Every renewal is also an expansion opportunity. If you are not growing the account, you are eventually losing it.

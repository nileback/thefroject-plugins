---
name: expansion-opportunity-analyzer
description: Analyze customer accounts to identify upsell, cross-sell, and expansion opportunities based on usage patterns, business signals, and competitive positioning. Use during account planning, QBR prep, or pipeline building.
triggers:
  - expansion opportunity
  - upsell analysis
  - cross-sell
  - account growth
---

# Expansion Opportunity Analyzer

Find the expansion opportunities hiding in your existing customer base. Expansion revenue is more efficient than new logo acquisition.

## Input Required

1. **Account data** — current contract, products used, user count, ARR
2. **Usage data** — feature adoption, usage trends, user growth
3. **Product catalog** — full list of products/tiers/add-ons available
4. **Account history** — previous purchases, expansion conversations, objections
5. **Industry context** — what similar companies use, typical stack

## Analysis Process

### Step 1 — Whitespace Mapping

Map what the customer uses vs. what is available:

| Product / Module | Status | Users | Adoption | Notes |
|-----------------|--------|-------|----------|-------|
| [Core product] | Active | [N] | [High/Med/Low] | |
| [Module A] | Active | [N] | | |
| [Module B] | Not purchased | — | — | [Why?] |
| [Module C] | Not purchased | — | — | |
| [Premium tier] | Not purchased | — | — | |
| [Add-on 1] | Not purchased | — | — | |

### Step 2 — Signal Detection

Look for expansion signals in the data:

| Signal Category | Indicators | Strength |
|----------------|-----------|---------|
| **Usage ceiling** | Approaching seat limits, API rate limits, storage caps | Strong |
| **Feature requests** | Asking about features in higher tiers or other products | Strong |
| **Team growth** | New departments onboarding, headcount increasing | Strong |
| **Power users** | Users hitting advanced features, requesting integrations | Medium |
| **Workflow gaps** | Using workarounds that a paid feature would solve | Medium |
| **Competitive eval** | Evaluating point solutions you could replace | Strong |
| **Strategic initiative** | New project, digital transformation, compliance push | Medium |
| **Champion promotion** | Your champion moved to a role with larger budget/scope | Strong |

### Step 3 — Opportunity Sizing

For each identified opportunity:

| Opportunity | Type | Estimated ARR | Probability | Weighted Value | Timeline |
|------------|------|-------------|-----------|---------------|---------|
| [Add seats] | Upsell | $[Amount] | [%] | $[Weighted] | [When] |
| [New module] | Cross-sell | $[Amount] | [%] | | |
| [Tier upgrade] | Upsell | $[Amount] | [%] | | |
| [New department] | Cross-sell | $[Amount] | [%] | | |

**Total expansion pipeline: $[Sum of weighted values]**

### Step 4 — Readiness Assessment

| Readiness Factor | Status | Action Needed |
|-----------------|--------|--------------|
| **Champion identified** | Yes/No | [If no, who to develop?] |
| **Budget available** | Confirmed/Likely/Unknown | [How to validate?] |
| **Decision maker access** | Yes/No | [If no, how to get access?] |
| **Technical fit** | Proven/Likely/Unclear | [Demo or POC needed?] |
| **Timing** | Now/Next quarter/Later | [What triggers the conversation?] |
| **Competitive risk** | None/Low/High | [Which competitors?] |

### Step 5 — Approach Planning

For each priority opportunity:

| Element | Detail |
|---------|--------|
| **Opening** | [How to introduce the conversation naturally] |
| **Value prop** | [Why this expansion matters for their business, not yours] |
| **Proof point** | [Similar customer who expanded and the result] |
| **Objection prep** | [Likely pushback and response] |
| **Ask** | [Specific next step: demo, trial, meeting with decision maker] |

## Output Format

Save to `outputs/expansion-analysis-[customer]-[date].md`:

```markdown
# Expansion Analysis — [Customer]
**Current ARR:** $[Amount] | **Expansion Pipeline:** $[Amount] | **Assessed:** [Date]

## Whitespace Map
[What they use vs. what is available]

## Top Opportunities (Ranked)
1. **[Opportunity]** — $[ARR] — [Readiness: High/Med/Low]
   - Signal: [What triggered this]
   - Approach: [How to open the conversation]
   - Timeline: [When to engage]

## Account Growth Plan
| Quarter | Target | Opportunity | Action |
|---------|--------|-----------|--------|

## Risks to Expansion
[What could prevent growth in this account]
```

## Principles

- Expansion is earned, not sold. If the customer has not realized value from what they already have, adding more products will not help.
- Time expansion conversations to the customer's calendar, not yours. Budget cycles, strategic planning periods, and renewal windows are natural entry points.
- The best expansion signal is the customer asking for it. Build systems that surface organic demand.

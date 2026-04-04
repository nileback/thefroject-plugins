---
name: sales-battlecard-builder
description: Build competitive battle cards that arm sales reps with positioning, differentiators, objection handling, and win strategies for specific competitors. Use when entering a competitive deal, updating competitive positioning, or onboarding new reps.
triggers:
  - battle card
  - competitive card
  - competitor positioning
  - sales enablement
---

# Sales Battlecard Builder

Create battle cards that help reps win competitive deals, not just understand competitors.

## Input Required

1. **Competitor name and products** — what you are competing against
2. **Your positioning** — value props and differentiators (check `reference/`)
3. **Win/loss data** — why deals were won or lost against this competitor (check `context/`)
4. **Competitor intelligence** — pricing, features, positioning, recent changes
5. **Customer feedback** — what customers say about both solutions

## Battle Card Structure

### Section 1 — Competitor Overview (Quick Reference)

| Field | Detail |
|-------|--------|
| **Competitor** | [Name] |
| **Founded / HQ** | [Year / Location] |
| **Funding / Revenue** | [If known] |
| **Target market** | [Who they sell to] |
| **Positioning** | [How they describe themselves in one sentence] |
| **Pricing model** | [Per user, per feature, flat rate, usage-based] |
| **Key customers** | [Logos they reference] |

### Section 2 — Feature Comparison

| Capability | Us | Them | Notes |
|-----------|-----|------|-------|
| [Core feature 1] | ✅ Strong | ⚠️ Partial | [Specific difference] |
| [Core feature 2] | ✅ | ✅ | [Parity — avoid competing here] |
| [Core feature 3] | ❌ Missing | ✅ Strong | [How to address this gap] |
| [Differentiator 1] | ✅ Unique | ❌ | [This is where we win] |
| [Differentiator 2] | ✅ Unique | ❌ | |

### Section 3 — Where We Win

| Scenario | Why We Win | Proof Point |
|----------|-----------|------------|
| [Customer type or use case 1] | [Specific advantage] | [Customer name or data point] |
| [Customer type or use case 2] | | |
| [Customer type or use case 3] | | |

### Section 4 — Where They Win (Be Honest)

| Scenario | Why They Win | How to Counter |
|----------|-------------|---------------|
| [Their strength 1] | [Honest assessment] | [Reframe or mitigate] |
| [Their strength 2] | | |

### Section 5 — Landmines to Plant

Questions to ask early that highlight your strengths and their weaknesses:

1. "[Question that exposes their limitation]"
   - **Why it works:** [What their answer reveals]
   - **Your follow-up:** [How to connect to your strength]

2. "[Question about a capability they lack]"
   - **Why it works:** [Forces them to admit a gap or overpromise]

3. "[Question about a use case where you excel]"
   - **Why it works:** [Anchors the evaluation on your strengths]

### Section 6 — Their Landmines (What They Will Ask)

| Their Question | What They Want to Expose | Your Response |
|---------------|------------------------|--------------|
| "[Question]" | [Your weakness] | [Honest, redirected answer] |

### Section 7 — Pricing Comparison

| Component | Us | Them | Notes |
|-----------|-----|------|-------|
| Base price | | | |
| Per user/seat | | | |
| Implementation | | | |
| Support | | | |
| Integrations | | | |
| **Total Year 1** | | | |
| **Total Year 3** | | | |

### Section 8 — Win Stories

For each story:
- **Customer:** [Name/Industry/Size]
- **Situation:** [What they needed]
- **Competitor:** [Who else they evaluated]
- **Why they chose us:** [In their words]
- **Result:** [Quantified outcome]

## Output Format

Save to `reference/battlecard-[competitor].md`:

```markdown
# Battle Card — [Competitor Name]
**Last updated:** [Date]

## Quick Reference
[Overview table]

## Our Advantages
[Top 3 differentiators with proof points]

## Their Advantages
[Top 2-3 with counters]

## Feature Comparison
[Full table]

## Landmines
[Questions to plant and defend against]

## Pricing
[Comparison table]

## Win Stories
[2-3 relevant stories]

## Key Phrases
[Sound bites reps can use in conversation]
```

## Principles

- Be honest about where the competitor wins. Reps who discover they have been given inaccurate battle cards stop trusting the content entirely.
- Update battle cards quarterly at minimum. Stale competitive intel is worse than no competitive intel.
- A battle card is not a feature comparison spreadsheet. It is a conversation guide. Write for how reps actually talk to buyers.

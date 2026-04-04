---
name: health-score-builder
description: Build a customer health scoring model that quantifies risk and opportunity from usage data, support interactions, engagement patterns, and financial signals. Use when creating a health scoring framework, refining an existing model, or assessing a specific customer's health.
triggers:
  - health score
  - customer health
  - account health
  - risk assessment
---

# Health Score Builder

Create a quantitative health score that turns scattered signals into a single actionable number per customer.

## Input Required

1. **Customer data** — usage metrics, support tickets, engagement history (check `context/current-data.md`)
2. **Product data** — feature adoption, login frequency, key actions
3. **Financial data** — contract value, payment history, expansion/contraction
4. **Relationship data** — stakeholder engagement, NPS/CSAT responses, meeting cadence
5. **Segment definitions** — how customers are grouped (size, industry, tier)

## Model Design

### Step 1 — Define Health Dimensions

Score each dimension independently, then combine:

| Dimension | Weight | Signals | Why It Matters |
|-----------|--------|---------|---------------|
| **Product Adoption** | 30% | DAU/MAU, feature usage, depth of use | Customers who use the product stay |
| **Support Health** | 20% | Ticket volume, severity, resolution time, sentiment | Rising tickets = rising frustration |
| **Engagement** | 20% | Meeting attendance, email responsiveness, champion activity | Engaged customers renew |
| **Financial** | 15% | Payment on time, contract growth, upsell conversations | Money signals commitment |
| **Relationship** | 15% | Stakeholder map depth, NPS score, executive access | Strong relationships survive problems |

Adjust weights based on your product and sales motion. Usage-heavy products should weight adoption higher. Service-heavy businesses should weight engagement higher.

### Step 2 — Define Scoring Criteria Per Dimension

**Product Adoption (0-100):**

| Score Range | Criteria |
|-------------|---------|
| 80-100 | Using core features weekly, adopted 3+ modules, growing usage |
| 60-79 | Using core features, but shallow. 1-2 modules only |
| 40-59 | Sporadic usage, declining trend, limited feature adoption |
| 20-39 | Minimal usage, only 1-2 users active, no growth |
| 0-19 | No meaningful usage in the past 30 days |

**Support Health (0-100):**

| Score Range | Criteria |
|-------------|---------|
| 80-100 | Few tickets, quick resolution, positive sentiment |
| 60-79 | Normal ticket volume, no escalations |
| 40-59 | Above-average tickets, some repeat issues |
| 20-39 | High volume, escalations, unresolved critical issues |
| 0-19 | Ongoing P1/P2 issues, executive escalation, threat of churn |

**[Apply the same 0-100 scale for Engagement, Financial, and Relationship]**

### Step 3 — Calculate the Composite Score

```
Health Score = (Adoption × 0.30) + (Support × 0.20) + (Engagement × 0.20)
             + (Financial × 0.15) + (Relationship × 0.15)
```

### Step 4 — Define Health Tiers

| Tier | Score | Color | Action |
|------|-------|-------|--------|
| **Healthy** | 80-100 | Green | Expand. Look for upsell and advocacy opportunities |
| **Stable** | 60-79 | Yellow-Green | Monitor. Maintain current engagement cadence |
| **At Risk** | 40-59 | Yellow | Intervene. Increase touchpoints, address specific issues |
| **Critical** | 20-39 | Orange | Escalate. Executive outreach, save plan, weekly check-ins |
| **Churn Imminent** | 0-19 | Red | Emergency. All-hands save effort or manage the transition |

### Step 5 — Override Rules

Certain signals should override the composite score:

| Signal | Override | Reason |
|--------|---------|--------|
| Executive sponsor left | Drop to At Risk minimum | Loss of champion is the #1 churn predictor |
| P1 ticket open > 14 days | Drop to Critical minimum | Unresolved critical issues erode trust fast |
| No login in 30 days | Drop to At Risk minimum | No usage = no value = no renewal |
| Contract up in 60 days + no renewal conversation | Drop to Critical | Clock is ticking |

## Output Format

Save the model to `reference/health-score-model.md` and individual assessments to `outputs/health-score-[customer].md`:

```markdown
# Health Score — [Customer Name]
**Score: [X]/100 — [Tier]**
**Assessed: [Date]**

| Dimension | Score | Trend | Key Signal |
|-----------|-------|-------|-----------|
| Adoption | /100 | ↑/→/↓ | [One line] |
| Support | /100 | | |
| Engagement | /100 | | |
| Financial | /100 | | |
| Relationship | /100 | | |

## Risk Factors
[Specific concerns]

## Opportunities
[Expansion, advocacy, case study potential]

## Recommended Actions
1. [Action + owner + deadline]
```

## Principles

- A health score is a starting point for conversation, not a conclusion. Always validate with the CSM's qualitative judgment.
- Update scores at least monthly. A quarterly health score is a historical artifact, not a management tool.
- The model should evolve. Track which scores predicted churn and which did not. Adjust weights accordingly.

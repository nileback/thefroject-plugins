---
name: expense-categorizer
description: Categorize expenses against the chart of accounts, flag anomalies and policy violations, and identify optimization opportunities. Use when processing expense reports, reviewing monthly spend, or preparing for audits.
triggers:
  - categorize expenses
  - expense review
  - cost analysis
  - spending optimization
---

# Expense Categorizer

Systematically classify, validate, and analyze expenses to maintain clean books and surface savings opportunities.

## Input Required

1. **Expense data** — transaction list with dates, amounts, vendors, descriptions
2. **Chart of accounts** — the organization's account structure (check `context/business-info.md`)
3. **Expense policy** — approval thresholds, allowed categories, per diem rates (check `reference/`)
4. **Prior period data** — for anomaly detection (optional but recommended)

## Classification Process

### Step 1 — Map to Chart of Accounts

For each expense, assign:

| Date | Vendor | Description | Amount | Category | Sub-category | GL Account | Cost Center | Confidence |
|------|--------|------------|--------|----------|-------------|-----------|------------|-----------|
| | | | | | | | | High/Medium/Low |

**Standard categories** (adjust to the organization's chart of accounts):

| Category | Includes | Does NOT Include |
|----------|---------|-----------------|
| People | Salaries, benefits, payroll taxes, contractors | Recruiting fees (use Operations) |
| Software | SaaS subscriptions, licenses, cloud infrastructure | Custom development (use Professional Services) |
| Marketing | Advertising, events, content, sponsorships | Sales entertainment (use Sales) |
| Travel | Flights, hotels, ground transport, meals while traveling | Local meals (use Meals & Entertainment) |
| Office | Rent, utilities, supplies, equipment under $X | Equipment over $X (capitalize as asset) |
| Professional Services | Legal, accounting, consulting | Contractor headcount (use People) |
| Sales | Entertainment, gifts, demo accounts | Marketing events (use Marketing) |

### Step 2 — Flag Anomalies

Check each transaction against these rules:

| Check | Flag Condition | Severity |
|-------|---------------|---------|
| **Duplicate** | Same vendor + amount within 7 days | High |
| **Threshold** | Amount exceeds category approval limit | High |
| **Vendor new** | First transaction with this vendor | Medium |
| **Spike** | > 2x the trailing 3-month average for this category | Medium |
| **Rounding** | Suspiciously round numbers ($1,000, $5,000) | Low |
| **Weekend** | Transaction on weekend (unusual for B2B) | Low |
| **Category mismatch** | Vendor typically in different category | Medium |

### Step 3 — Optimization Analysis

Group expenses and identify savings:

**Consolidation opportunities:**
- Multiple vendors serving the same function (e.g., 3 different project management tools)
- Subscriptions with overlapping features
- Vendors where volume discount thresholds are close

**Usage analysis:**
- SaaS licenses vs. active users (are you paying for unused seats?)
- Services at contracted vs. actual utilization
- Recurring charges for cancelled projects

**Negotiation candidates:**
- Contracts renewing in the next 90 days
- Vendors where spend has grown significantly (leverage for better rates)
- Multi-year deal opportunities for stable vendors

## Output Format

Save to `outputs/expense-review-[period].md`:

```markdown
# Expense Review — [Period]

## Summary
| Category | Budget | Actual | Variance | % of Total |
|----------|--------|--------|----------|-----------|

## Anomalies Flagged
| # | Date | Vendor | Amount | Flag | Severity | Resolution |
|---|------|--------|--------|------|---------|-----------|

## Optimization Opportunities
| Opportunity | Current Cost | Estimated Savings | Effort | Priority |
|------------|-------------|-------------------|--------|---------|

## Uncategorized Items (Need Human Review)
[Items where classification confidence is Low]

## Recommendations
1. [Action + expected savings + timeline]
```

## Principles

- When in doubt about a category, flag it for human review rather than guessing. Incorrect categorization is worse than no categorization.
- Look for patterns, not just individual transactions. A single $50 charge is noise. Fifty $50 charges to the same vendor is a pattern.
- Savings estimates should be conservative. It is better to under-promise and over-deliver on cost reduction.

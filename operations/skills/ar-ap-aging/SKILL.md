---
name: ar-ap-aging
description: Analyze accounts receivable and accounts payable aging data to prioritize collections, optimize payment timing, and identify cash flow risks. Use weekly or monthly to stay on top of working capital.
triggers:
  - aging report
  - AR aging
  - AP aging
  - collections
  - who owes us money
  - overdue invoices
  - payment terms
allowed-tools: []
---

# AR/AP Aging Analysis

## Writes
- `outputs/aging-analysis-[YYYY-MM].md`

## Context Scan

Check `context/` and `reference/` for:
- AR and AP aging reports (current, 30, 60, 90, 90+ day buckets)
- Customer payment history
- Vendor contracts and payment terms
- Collection policies or procedures
- Cash flow forecasts

Ask for the aging data. At minimum you need: list of outstanding invoices with amounts, dates, and customer/vendor names.

## Step 1 — Accounts Receivable Summary

### Aging Buckets

| Bucket | Amount | % of Total | # of Invoices | # of Customers |
|--------|--------|-----------|--------------|----------------|
| Current (0-30 days) | | | | |
| 31-60 days | | | | |
| 61-90 days | | | | |
| 90+ days | | | | |
| **Total AR** | | | | |

### Key Metrics
- **Days Sales Outstanding (DSO):** [Calculate from revenue and AR balance]
- **DSO trend:** Improving / Stable / Deteriorating vs. prior periods
- **Concentration risk:** Top 5 customers as % of total AR
- **Bad debt exposure:** Total 90+ day balances

## Step 2 — Collection Priority Matrix

Rank overdue receivables by priority:

| Priority | Customer | Amount | Days Overdue | Payment History | Action |
|----------|----------|--------|-------------|----------------|--------|
| 1 | | | | Good/Mixed/Poor | |
| 2 | | | | | |
| 3 | | | | | |

**Prioritization logic:**
- Large amounts from reliable payers: likely a process issue. One email or call resolves it.
- Large amounts from unreliable payers: escalate immediately. Send formal notice.
- Small amounts over 90 days: evaluate cost of collection vs. write-off.
- Repeat offenders: flag for payment terms renegotiation.

For each priority item, draft a specific action: who to contact, what to say, and the deadline.

## Step 3 — Accounts Payable Summary

### Aging Buckets

| Bucket | Amount | % of Total | # of Invoices | # of Vendors |
|--------|--------|-----------|--------------|-------------|
| Current (0-30 days) | | | | |
| 31-60 days | | | | |
| 61-90 days | | | | |
| 90+ days | | | | |
| **Total AP** | | | | |

### Payment Optimization
- **Early payment discounts available:** List vendors offering 2/10 net 30 or similar
- **Discount value:** Calculate the annualized return of taking early payment discounts
- **Strategic delays:** Which payments can be pushed to net terms without penalty or relationship damage?

## Step 4 — Working Capital Impact

| Metric | Current | Prior Period | Change |
|--------|---------|-------------|--------|
| Total AR | | | |
| Total AP | | | |
| Net working capital (AR - AP) | | | |
| DSO | | | |
| DPO (Days Payable Outstanding) | | | |
| Cash conversion cycle (DSO - DPO) | | | |

A rising cash conversion cycle means more cash is tied up in operations. Flag if the trend is negative.

## Step 5 — Risk Flags

| Flag | Detail | Impact | Recommended Action |
|------|--------|--------|-------------------|
| Customer concentration | [Customer] is [X]% of AR | Single-point revenue risk | Diversify or secure payment guarantees |
| Chronic late payers | [Customers] consistently pay 30+ days late | Cash flow unpredictability | Renegotiate terms or require deposits |
| Aging deterioration | 60+ day bucket grew [X]% vs last period | Collection effectiveness declining | Review collection process |
| Vendor dependency | [Vendor] has [X]% of AP with short terms | Payment pressure | Negotiate extended terms |

## Step 6 — Recommendations

1. **This week:** Top 3 collection calls to make, ranked by amount and likelihood of recovery
2. **This month:** Payment terms to renegotiate (both AR and AP)
3. **Process improvements:** Changes to invoicing, collection follow-up, or payment scheduling
4. **Write-off candidates:** Receivables that cost more to collect than they are worth

## Do NOT
- Treat all overdue invoices the same. A $50k invoice from a reliable customer is a different problem than a $50k invoice from someone who always pays late.
- Ignore early payment discounts. 2/10 net 30 is equivalent to ~36% annualized return. If you have the cash, take the discount.
- Recommend aggressive collection without considering the customer relationship. Sometimes a late-paying customer is your biggest account.
- Analyze AR without looking at AP. Working capital is the net of both. Optimizing one side while ignoring the other misses the picture.

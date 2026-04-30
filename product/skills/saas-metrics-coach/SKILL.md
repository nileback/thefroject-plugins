---
name: saas-metrics-coach
description: Calculate and interpret SaaS unit economics. Use when building financial models, preparing board decks, evaluating business health, or learning what metrics matter. Covers ARR, MRR, churn, LTV, CAC, payback period, and cohort analysis.
triggers:
  - SaaS metrics
  - unit economics
  - ARR MRR
  - churn rate
  - LTV CAC
  - payback period
  - cohort analysis
allowed-tools: []
---

# SaaS Metrics Coach

Calculate, interpret, and improve SaaS unit economics. Every metric connects to a business question.

## Core Metrics

### Revenue Metrics
- **MRR** (Monthly Recurring Revenue) = sum of all active monthly subscription values
- **ARR** (Annual Recurring Revenue) = MRR x 12
- **MRR components:** New MRR + Expansion MRR + Reactivation MRR - Churned MRR - Contraction MRR = Net New MRR
- **Revenue growth rate** = (MRR this month - MRR last month) / MRR last month

### Retention Metrics
- **Gross churn rate** = Lost MRR / Starting MRR (monthly)
- **Net revenue retention (NRR)** = (Starting MRR + Expansion - Contraction - Churn) / Starting MRR
  - NRR > 100% means existing customers grow faster than they leave
  - Best-in-class: 120%+. Healthy: 100-120%. Concerning: below 100%.
- **Logo churn** = customers lost / customers at start of period
- **Cohort retention** = % of a signup cohort still active at month N

### Acquisition Metrics
- **CAC** (Customer Acquisition Cost) = total sales + marketing spend / new customers acquired
- **Blended CAC** includes all customers. **Paid CAC** counts only paid-channel customers.
- **CAC payback period** = CAC / (monthly revenue per customer x gross margin)
  - Healthy: under 12 months. Concerning: over 18 months.

### Lifetime Value
- **LTV** = Average revenue per customer per month x gross margin / monthly churn rate
- **LTV:CAC ratio** — the fundamental unit economics check
  - Below 1:1 = losing money on every customer
  - 3:1 = healthy benchmark
  - Above 5:1 = may be underinvesting in growth

### Efficiency Metrics
- **Burn multiple** = Net burn / Net new ARR (lower is better; under 2x is good)
- **Rule of 40** = Revenue growth rate % + profit margin % (above 40 is strong)
- **Magic number** = Net new ARR / prior quarter sales & marketing spend (above 1.0 is efficient)

## How to Use

1. **Provide your numbers** — revenue, customers, spend, churn counts
2. **Ask what you want to know** — "Are we healthy?" "Where should we focus?" "What story do these numbers tell?"
3. This skill will calculate metrics, benchmark against industry standards, and recommend where to focus.

## Benchmarks

| Metric | Early Stage | Growth | Scale |
|---|---|---|---|
| MRR growth | 15-20%/mo | 5-10%/mo | 2-5%/mo |
| Gross churn | 3-7%/mo | 1-3%/mo | <1%/mo |
| NRR | 90-100% | 100-120% | 110-130% |
| CAC payback | 12-18 mo | 8-12 mo | 6-8 mo |
| LTV:CAC | 2-3x | 3-5x | 4-6x |

## Output

Report includes: calculated metrics, benchmarking, health assessment, and 3 specific recommendations for improvement.

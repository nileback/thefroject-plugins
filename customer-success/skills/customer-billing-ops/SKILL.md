---
name: customer-billing-ops
description: Manage subscription billing operations including upgrades, downgrades, churn triage, refund processing, and revenue tracking. Use when handling billing questions, analyzing churn, or building subscription workflows.
triggers:
  - billing ops
  - subscription management
  - churn triage
  - refund workflow
---

# Customer Billing Ops

Manage the full subscription lifecycle from signup through renewal, including the hard parts: downgrades, cancellations, refunds, and churn prevention.

## Subscription Lifecycle

### New Subscription
1. Confirm plan selection, billing cycle (monthly/annual), and payment method
2. Set the billing anchor date (first of month, signup date, or custom)
3. Document trial period length and conversion trigger
4. Record in the customer record: plan, start date, billing cycle, MRR contribution

### Upgrade
1. Calculate prorated amount for the remaining billing cycle
2. Confirm the upgrade with the customer (new price, effective date, prorated charge)
3. Update the subscription record: new plan, effective date, new MRR
4. Trigger a confirmation email with the updated invoice

### Downgrade
1. Determine effective date (immediate or end of current cycle)
2. Calculate credit or refund for unused portion if immediate
3. Confirm feature access changes with the customer
4. Update the subscription record: new plan, effective date, adjusted MRR
5. Flag the account for a check-in 30 days after downgrade

### Renewal
1. Send renewal reminder 14 days before the billing date
2. Verify payment method is still valid
3. Process the charge on the billing date
4. Handle failed payments: retry schedule (day 1, 3, 7), dunning emails, grace period

## Churn Triage

### Identify At-Risk Accounts
Look for these signals:
- Usage dropped >50% in the last 30 days
- Support tickets increased without resolution
- Key user (admin/champion) left the company
- Downgrade request submitted
- Payment failed and not recovered after first retry
- No login in 21+ days
- Competitor mentioned in support conversations

### Build a Save Offer
Match the save offer to the reason for leaving:

| Reason | Save Offer |
|--------|-----------|
| Too expensive | Offer annual discount, downgrade to lower tier, or pause billing |
| Not using it enough | Offer onboarding session, extend trial, or reduce to essentials plan |
| Missing feature | Document the request, share roadmap timeline, offer beta access |
| Switching to competitor | Ask what they offer that you do not, document for product team |
| Budget cut | Offer 3-month pause instead of cancellation |
| Bad experience | Escalate to senior support, offer service credit, schedule a call |

### Document Cancellation
For every cancellation, record:
1. Customer name and plan
2. Tenure (months as a customer)
3. MRR lost
4. Stated reason (verbatim from customer)
5. Categorized reason (price, feature gap, usage, competitor, budget, experience)
6. Save offer attempted and result
7. Likelihood of return (high/medium/low)

Write churn reports to `outputs/churn-report-[month].md`.

## Refund and Credit Processing

### Refund Decision Tree
1. **Within 48 hours of charge + no usage?** Full refund. No questions.
2. **Within billing cycle + minimal usage?** Prorated refund to the day of cancellation.
3. **Billing error (duplicate charge, wrong amount)?** Full refund immediately + apology.
4. **Partial service outage?** Credit equal to the downtime percentage of the billing period.
5. **Customer dissatisfaction?** Offer credit toward next cycle first. Refund if they insist.
6. **Beyond 60 days?** Escalate to finance. Generally no refund, but offer future credit.

### Dispute Handling
1. Acknowledge the dispute within 24 hours
2. Gather evidence: invoice, usage logs, communication history
3. Respond through the payment processor's dispute portal
4. Document the outcome regardless of result

## Revenue Tracking

### Monthly Metrics
Track and report:
- **MRR** — Monthly Recurring Revenue (sum of all active subscriptions)
- **New MRR** — from new customers this month
- **Expansion MRR** — from upgrades this month
- **Contraction MRR** — from downgrades this month
- **Churned MRR** — from cancellations this month
- **Net New MRR** — New + Expansion - Contraction - Churned

### Output
Write monthly billing reports to `outputs/billing-report-[month].md` including:
1. MRR waterfall (opening → changes → closing)
2. Churn rate (customers and revenue)
3. Top 5 accounts by MRR
4. At-risk accounts and planned interventions

## Do NOT
- Process refunds over the documented threshold without finance approval
- Promise features to retain customers without confirming with the product team
- Share billing details of one customer with another
- Skip documentation — every churn event and refund must be recorded
- Offer discounts beyond the pre-approved save offer menu

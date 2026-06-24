---
name: vendor-management-guide
description: Manage the full vendor lifecycle from evaluation and selection through contract review, performance monitoring, and relationship management. Use when onboarding new vendors, reviewing existing contracts, or optimizing vendor spend.
triggers:
  - vendor evaluation
  - contract review
  - vendor management
  - vendor assessment
---

# Vendor Management Guide

Manage vendors like strategic partners when they matter, and like commodity suppliers when they do not. The framework adapts to the relationship's importance.

## Vendor Evaluation

### Step 1 — Define Requirements

Before evaluating any vendor, document what you need:

| Requirement | Priority | Must Have / Nice to Have | Weight |
|------------|----------|------------------------|--------|
| [Functional requirement 1] | High | Must have | 30% |
| [Functional requirement 2] | High | Must have | 25% |
| [Integration requirement] | Medium | Must have | 20% |
| [Support/SLA requirement] | Medium | Nice to have | 15% |
| [Price target] | High | Must have | 10% |

### Step 2 — Vendor Scorecard

| Criteria | Weight | Vendor A | Vendor B | Vendor C |
|----------|--------|---------|---------|---------|
| Functional fit | 30% | [1-5] | [1-5] | [1-5] |
| Technical fit | 20% | | | |
| Price/value | 15% | | | |
| Support quality | 10% | | | |
| Company stability | 10% | | | |
| Implementation effort | 10% | | | |
| References | 5% | | | |
| **Weighted total** | 100% | | | |

### Step 3 — Reference Checks

Ask every reference:
1. What problem were you solving when you selected this vendor?
2. How was the implementation? On time, on budget?
3. What has support been like? Give me a specific example of an issue.
4. If you were making the decision again today, would you choose them?
5. What do you wish you had known before signing?

## Contract Review Checklist

| Clause | What to Check | Red Flag |
|--------|-------------|---------|
| **Term and renewal** | Auto-renewal terms, notice period | Auto-renew with 90+ day notice period |
| **Pricing** | Rate escalation caps, overage charges | Uncapped annual increases |
| **SLA** | Uptime commitment, response times, remedies | SLA without financial remedies |
| **Data ownership** | Who owns the data, portability, deletion | Vendor claims rights to your data |
| **Termination** | Exit assistance, data return, transition period | No exit assistance clause |
| **Liability** | Limitation of liability, indemnification | Liability capped below contract value |
| **Security** | SOC 2, data handling, breach notification | No security certifications |
| **IP** | Ownership of customizations, integrations | Vendor owns your customizations |
| **Insurance** | Cyber liability, E&O coverage | No insurance requirements |
| **Change of control** | What happens if vendor is acquired | No protections on acquisition |

## Ongoing Vendor Management

### Performance Tracking

| Metric | Target | Actual | Trend | Notes |
|--------|--------|--------|-------|-------|
| Uptime / availability | [SLA] | | | |
| Support response time | [SLA] | | | |
| Issue resolution time | [Target] | | | |
| User satisfaction | [Target] | | | |
| Cost vs. budget | [Budget] | | | |
| Contract utilization | [Seats/capacity used vs. purchased] | | | |

### Relationship Health

| Factor | Assessment | Action |
|--------|-----------|--------|
| Account manager responsiveness | [Good/Fair/Poor] | |
| Roadmap alignment | [Aligned/Diverging] | |
| Strategic importance | [Critical/Important/Commodity] | |
| Switching cost | [High/Medium/Low] | |
| Alternative options | [Many/Few/None] | |

## Output Format

Save evaluations to `outputs/vendor-evaluation-[vendor]-[date].md` and ongoing tracking to `reference/vendor-registry.md`:

```markdown
# Vendor Registry

| Vendor | Product | Annual Cost | Contract End | Owner | Strategic Level |
|--------|---------|------------|-------------|-------|----------------|

## Upcoming Renewals (Next 90 Days)
[Table with vendor, date, current cost, recommended action]

## Recent Evaluations
[Links to evaluation outputs]
```

## Principles

- Match your management effort to the vendor's strategic importance. A $500/month SaaS tool does not need quarterly business reviews. A $500K/year platform does.
- Always negotiate. The first price is never the best price, especially at renewal.
- Own your data. Every vendor contract should include a data portability clause. The time to negotiate exit terms is before you sign, not after.

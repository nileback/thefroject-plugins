---
name: diagnose-retention
description: Examine retention curves, cohort behavior, and churn drivers to identify why users leave and what keeps them. Use when retention is below benchmark, declining over time, or when planning engagement initiatives.
triggers:
  - diagnose retention
  - retention analysis
  - why users leave
  - cohort analysis
  - churn diagnosis
---

# Retention Diagnostician

Retention is the foundation of sustainable growth. A product with strong acquisition but poor retention is a leaky bucket. Fix the bucket before pouring more water.

## Phase 1 — Measure Retention

### Define the Retention Event
What action indicates a user is still getting value? This may differ from activation:
- **Activation event:** First time the user gets value
- **Retention event:** Repeated action that signals ongoing value

| Product Type | Typical Retention Event | Frequency |
|-------------|------------------------|-----------|
| SaaS tool | Core feature used | Weekly |
| Marketplace | Transaction completed | Monthly |
| Content platform | Content consumed | Daily/Weekly |
| Communication tool | Message sent | Daily |

**Your retention event:** [define it]
**Expected frequency:** [how often a healthy user does it]

### Build the Retention Curve
Plot the percentage of users who return at each time interval after activation:

| Time Period | Cohort Size | Users Retained | Retention Rate |
|------------|-------------|---------------|----------------|
| Week 0 | [n] | [n] | 100% |
| Week 1 | [n] | [n] | [%] |
| Week 4 | [n] | [n] | [%] |
| Week 8 | [n] | [n] | [%] |
| Week 12 | [n] | [n] | [%] |

**Key metrics:**
- **Day 1 retention:** Early engagement signal
- **Week 1 retention:** Habit formation indicator
- **Flattening point:** Where the curve levels off — this is your stable retained base

## Phase 2 — Segment the Curve

Compare retention across segments to find what separates users who stay from users who leave:

### Behavioral Segments
| Segment | Week-4 Retention | Notes |
|---------|-----------------|-------|
| Activated in first 24h | [%] | |
| Activated in day 2-7 | [%] | |
| Used feature X | [%] | |
| Connected integration | [%] | |
| Invited a teammate | [%] | |

### Acquisition Segments
| Channel | Week-4 Retention | Notes |
|---------|-----------------|-------|
| Organic search | [%] | |
| Paid acquisition | [%] | |
| Referral | [%] | |
| Direct | [%] | |

The segments with the highest and lowest retention reveal what drives stickiness.

## Phase 3 — Understand Why Users Leave

### Churn Timing
When do most users leave? Early churn (week 1-2) vs. late churn (month 2+) have different causes:

| Timing | Likely Cause | Investigation |
|--------|-------------|---------------|
| Day 1 | Did not understand value | Check onboarding, first-run experience |
| Week 1-2 | Got value once but did not form habit | Check re-engagement triggers, frequency |
| Month 1-2 | Found alternative or need diminished | Check competitive landscape, use case depth |
| Month 3+ | Life change, pricing, or accumulated friction | Check support tickets, pricing sensitivity |

### Churned User Analysis
For recently churned users:
- What was their last action before leaving?
- How frequently were they using the product in their final weeks?
- Did they encounter errors, slow performance, or support issues?
- Did they overlap with a product change or pricing update?

## Phase 4 — Design Retention Improvements

| Lever | Approach | Target Segment |
|-------|----------|---------------|
| Habit formation | Daily/weekly triggers, streaks, progress indicators | New users (week 1-4) |
| Feature depth | Guide users to advanced features after initial value | Activated users plateauing |
| Social connection | Team features, sharing, collaboration | Solo users |
| Re-engagement | Email sequences, push notifications, digest emails | Lapsed users |
| Value reinforcement | Usage reports, progress summaries, ROI dashboards | Active users at risk |

## Output

Write to `outputs/retention-diagnosis-[date].md`:

1. **Retention definition** — event, frequency, current curve
2. **Segmented analysis** — who retains best/worst and why
3. **Churn drivers** — top reasons users leave at each stage
4. **Improvement plan** — prioritized retention levers with expected impact
5. **Monitoring plan** — metrics to track weekly

## Do NOT
- Use vanity metrics (MAU without defining "active")
- Compare retention rates across products with different natural frequencies
- Focus only on preventing churn — also invest in deepening engagement of retained users
- Ignore that retention rates naturally vary by cohort maturity

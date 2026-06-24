---
name: m-and-a-playbook
description: Acquisition diligence and integration planning. Covers strategic fit assessment, due diligence checklist, deal structure, integration plan (Day 1 through Day 100+), retention strategy, and the failure modes that sink most acquisitions. Use when user mentions M&A, acquisition, due diligence, post-merger integration.
triggers:
  - m and a
  - mergers and acquisitions
  - acquisition planning
  - due diligence
  - post-merger integration
  - integration plan
  - acquihire
---

# M&A Playbook

Help a leadership team work through an acquisition — whether buying a small product/team (acquihire) or a meaningful business. Most acquisitions fail at integration, not at deal terms.

## Gather context

Ask if not provided:

1. **What's being acquired?** — product, team, customers, IP, all of the above?
2. **Strategic rationale** — why is this acquisition vs. building or partnering?
3. **Stage** — exploring, term sheet, signed LOI, post-close integration?
4. **Acquirer side or target side?** — perspective matters.
5. **Resources** — internal M&A team or first time?

## Phase 1: Strategic fit (before LOI)

Before serious diligence, validate the strategic case:

- **Why this target?** Specific gap they fill. "We want their product/team/customers because <concrete reason>."
- **Why now?** Timing — your readiness to integrate, market window, competitive threat.
- **Why this approach?** Alternatives considered: build, partner, acqui-hire, license. Why is acquisition the right answer?
- **What's the value capture mechanism?** How does shareholder value increase 12-24 months from now? (Revenue growth, cost savings, defensive moat, etc.)

Document this in a 1-page strategic memo. If the memo is hard to write, the deal is wrong.

## Phase 2: Due diligence

Run parallel workstreams:

### Financial DD
- 3 years of financial statements (ideally audited).
- Revenue quality: recurring vs one-time, customer concentration, churn rate.
- Cost structure and margin trajectory.
- Cash position, debt, contingent liabilities.
- Working capital needs going forward.

### Commercial DD
- Customer interviews (5-10 across segments).
- Market position vs competitors.
- Pipeline and conversion rates.
- Win/loss patterns.

### Product DD
- Product roadmap and dependencies.
- Tech stack and technical debt.
- Code quality, security posture, IP ownership.
- Compatibility with acquirer's stack.

### People DD
- Org chart and key talent identification.
- Compensation parity (salary, equity).
- Cultural assessment.
- Retention risk for top 5-10 people.

### Legal DD
- IP and licensing.
- Customer contracts (change-of-control clauses).
- Vendor contracts.
- Litigation, regulatory.
- Equity table and outstanding obligations.

Each workstream produces findings. Material findings get rolled into deal terms or kill the deal.

## Phase 3: Deal structure

Key decisions:
- **Cash, stock, or mix?** Stock aligns; cash is cleaner.
- **Earn-out vs. fixed price?** Earn-outs are common but often misaligned post-close.
- **Holdback / escrow** for warranty breaches.
- **Retention pool** — equity refresh for key talent (typical: 4-year vest, often re-issued).
- **Working capital target** — net working capital adjustment at close.
- **Reps and warranties** — what the seller promises is true.

Pricing methodology depends on what's being bought:
- Revenue-generating business: revenue multiple or EBITDA multiple.
- Pre-revenue: team + tech + traction valuation (acqui-hire economics).
- Strategic asset: replacement cost analysis.

## Phase 4: Integration plan (Day -30 to Day +100)

Most M&A failure happens here. Plan integration BEFORE close.

### Day -30 to Day 0 (signed-but-not-closed)
- Build the integration team (acquirer + target leads).
- Communications plan (employees, customers, press).
- Day-1 IT plan (email, access, systems).
- Identify the top 5-10 retention risks; have personal conversations.

### Day 1 (close)
- Announcement.
- All-hands meeting at target company; founder of acquirer attends.
- Day-1 swag / token.
- Each employee gets a personal welcome from their new manager.
- IT systems flipped (email, payroll, equity).

### Day 1-30
- Cultural immersion (acquirer's values, working norms).
- Manager 1:1s with every target employee.
- Customer communications.
- First full-team meeting.

### Day 30-90
- Org integration (where do roles report? Are there redundancies?).
- Tooling migration (CRM, finance systems, project management).
- Goal alignment (target team adopts acquirer's goal cycle).
- Customer success continuity (preserve target's CS relationships).

### Day 90+
- Brand / product integration (if applicable).
- Roadmap alignment.
- Retention check (have top talent stayed?).
- Synergy capture vs. plan.

## The four failure modes

### 1. Integration treated as an afterthought
"We'll figure it out post-close" -> chaos, attrition, customer churn. Plan integration before signing.

### 2. Cultural mismatch ignored
"They'll fit in fine" -> 6-12 months later, half the target team has left. Assess culture honestly during DD.

### 3. Retention not pre-secured
Top talent gets a "thanks for staying" call AFTER close, by which point they're already taking outside calls. Have personal conversations BEFORE close.

### 4. Synergies measured but not captured
Models show $X cost savings or $Y revenue uplift; nobody owns capturing them. Assign synergy ownership at close.

## Output format

Save to `outputs/m-and-a/<target-slug>/`:
- `strategic-memo.md` — the 1-pager.
- `due-diligence/` — findings per workstream.
- `deal-terms.md` — structure and rationale.
- `integration-plan.md` — Day -30 to Day +100 with owners.
- `retention-plan.md` — top talent list, conversations had, equity refresh status.
- `communications-plan.md` — what gets said to whom and when.

These files are sensitive. Store privately, not in shared repos.

## Common mistakes

- Skipping cultural assessment during DD. Hardest thing to fix post-close.
- Underestimating integration cost (time and attention).
- No clear synergy ownership.
- Communications mishandled (employees hear from press before from leadership).
- Earn-outs that misalign incentives between acquirer and target leadership.

## Cross-references

For broader scenario-modeling around M&A outcomes, use `scenario-war-room`. For internal communications during integration, use `internal-comms`. For change management plans, use `change-management-guide`. For the financial modeling specifically, use `financial-model-builder`. For decision documentation through the deal, use `decision-tracker`.

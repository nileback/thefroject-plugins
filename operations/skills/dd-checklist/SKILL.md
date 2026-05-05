---
name: dd-checklist
description: Comprehensive due diligence checklist for acquisitions, investments, or major partnerships. Covers commercial, financial, legal, technical, and people DD with workstream-by-workstream output. For broader M&A planning use m-and-a-playbook.
triggers:
  - due diligence
  - dd checklist
  - diligence
  - target evaluation
  - investment dd
---

# Due Diligence Checklist

Build a complete due-diligence plan tailored to deal type and size. The output is a workstream-by-workstream checklist with owners, sources, and red-flag items.

## Gather context

Ask if not provided:

1. **Deal type** — acquisition, minority investment, partnership, vendor evaluation?
2. **Deal size** — under $5M, $5-50M, $50M+? Different rigor by size.
3. **Target type** — public, private, early-stage, mature?
4. **Sector** — SaaS, financial services, healthcare, industrials? Adds sector-specific items.
5. **Timeline** — DD window in days/weeks?
6. **Buy-side or sell-side?** — different deliverables.

## Standard workstreams

### 1. Commercial DD
What's the business worth in the market?

- [ ] Customer interviews (5-10 across segments).
- [ ] Market position vs competitors.
- [ ] Pipeline analysis and conversion rates.
- [ ] Win/loss patterns.
- [ ] Customer concentration analysis (top 10%, top 25%).
- [ ] Churn rate by cohort and segment.
- [ ] Pricing analysis vs market.

### 2. Financial DD
Are the numbers real?

- [ ] 3 years of audited financials (or alternative).
- [ ] Quality of earnings (recurring vs one-time, GAAP adjustments).
- [ ] Revenue recognition policies.
- [ ] Working capital trends.
- [ ] CapEx history and projection.
- [ ] Debt and contingent liabilities.
- [ ] Tax position (NOLs, foreign tax exposure).
- [ ] Off-balance-sheet items.

### 3. Legal DD
What are we buying / inheriting legally?

- [ ] Corporate structure and cap table.
- [ ] Customer contracts (change-of-control clauses).
- [ ] Vendor contracts and termination rights.
- [ ] Employment agreements and equity grants.
- [ ] IP ownership and licensing.
- [ ] Litigation history and pending claims.
- [ ] Regulatory and compliance status.
- [ ] Insurance coverage.
- [ ] Real estate and leases.

### 4. Technical / IT DD
Is the technology sound?

- [ ] Tech stack and architecture documentation.
- [ ] Technical debt assessment.
- [ ] Security posture (penetration test results, certifications).
- [ ] Data governance and privacy (GDPR, SOC 2, HIPAA where applicable).
- [ ] Source code review (sample, not full).
- [ ] System uptime and incident history.
- [ ] IT integration cost estimate.
- [ ] Critical-vendor dependencies.

### 5. People DD
Is the team strong and likely to stay?

- [ ] Org chart and key talent identification.
- [ ] Compensation parity (salary, equity, benefits).
- [ ] Retention risk for top 10 people.
- [ ] Cultural assessment (values, working norms, decision-making style).
- [ ] Recent hires and recent departures pattern.
- [ ] HR policies and any flagged issues (lawsuits, complaints).

### 6. Sector-specific
Add based on target type:
- **SaaS**: usage analytics, NRR detail, LTV/CAC by cohort.
- **Healthcare**: HIPAA compliance, FDA submissions, payor mix.
- **Financial services**: regulatory licenses, AML/KYC, capital adequacy.
- **Industrials**: supply chain, regulatory permits, environmental liabilities.

## Red-flag tracker

Maintain a separate "red flags" log alongside the checklist. Common red flags:

- Customer concentration > 30% of revenue with one customer.
- Year-over-year revenue contraction.
- Auditor change in last 3 years.
- Pending litigation that could materially affect valuation.
- Key talent without strong retention motivation.
- IP not clearly owned by the target company.
- Major customers without long-term contracts.
- Regulatory issues unresolved.

Each red flag gets: severity (low/medium/high), mitigation possible (yes/no), impact on price (estimate).

## Output

Save the DD plan to `outputs/dd/<target>-<date>/`:
- `checklist.md` — workstream-by-workstream items with owner and status.
- `findings.md` — material findings as DD progresses.
- `red-flags.md` — running log.
- `final-memo.md` — synthesis when DD completes (input to IC memo).

These files are sensitive. Store privately, not in shared repos.

## Common mistakes

- Following a generic checklist without tailoring to the deal.
- Treating DD as a one-direction information dump (failing to interview or test).
- Skipping customer interviews. The single most undervalued DD source.
- Underweighting technical debt for tech deals.
- Cultural assessment as an afterthought. Hardest thing to fix post-close.
- No red-flag tracking — findings get lost in the volume of DD output.

## Cross-references

For broader M&A planning, use `m-and-a-playbook`. For investment committee memos that synthesize DD findings, use `ic-memo`. For post-close value creation planning, use `value-creation-plan`. For the financial modeling underneath the DD, use `three-statement-model`, `dcf-model`, `lbo-model`. For risk register building, use `risk-register-builder`.

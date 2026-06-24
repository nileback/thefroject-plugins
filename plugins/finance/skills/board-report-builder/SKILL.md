---
name: board-report-builder
description: Prepare board-ready reports and investor updates with KPIs, financial metrics, operational highlights, and strategic narrative. Use before board meetings, investor updates, or quarterly reporting cycles.
triggers:
  - board report
  - investor update
  - board deck
  - quarterly board meeting
---

# Board Report Builder

Create concise, decision-oriented reports that give board members and investors the information they need without burying them in operational detail.

## Input Required

1. **Financial data** — P&L, cash position, key metrics for the period
2. **OKRs / KPIs** — targets and actuals (check `context/strategy.md`)
3. **Operational highlights** — product launches, hires, partnerships, customer wins
4. **Risks and issues** — what kept you up at night this quarter
5. **Previous board report** — for continuity (check `outputs/` for prior reports)
6. **Open action items** — from previous board meetings

## Report Structure

### Section 1 — Executive Summary (1 page max)

Write 4-6 sentences covering:
- Overall performance vs. plan (one sentence)
- The single biggest win (one sentence)
- The single biggest challenge (one sentence)
- Forward outlook (one sentence)
- Any asks of the board (one sentence, if applicable)

### Section 2 — KPI Dashboard

| KPI | Target | Actual | Status | Trend | Commentary |
|-----|--------|--------|--------|-------|-----------|
| ARR / Revenue | | | 🟢/🟡/🔴 | ↑/→/↓ | [One line] |
| Gross Margin | | | | | |
| Customer Count | | | | | |
| Churn / Retention | | | | | |
| NPS / CSAT | | | | | |
| Cash Position | | | | | |
| Runway (months) | | | | | |
| Headcount | | | | | |
| Burn Rate | | | | | |

**Status definitions:**
- 🟢 On or above target
- 🟡 Within 10% of target
- 🔴 More than 10% below target

### Section 3 — Financial Summary

Keep this to one page. Board members who want detail will ask.

| Metric | Q Actual | Q Budget | Variance | YTD Actual | YTD Budget |
|--------|---------|---------|---------|-----------|-----------|
| Revenue | | | | | |
| Gross Profit | | | | | |
| OpEx | | | | | |
| EBITDA | | | | | |
| Cash | | | | | |

### Section 4 — Operational Highlights

Group by theme, not by department. Board members care about outcomes, not org charts.

**Growth:**
- [Customer wins, expansion, pipeline]

**Product:**
- [Launches, roadmap progress, technical milestones]

**Team:**
- [Key hires, organizational changes, culture initiatives]

### Section 5 — Risks and Mitigation

| Risk | Likelihood | Impact | Mitigation | Status |
|------|-----------|--------|-----------|--------|
| [Risk] | High/Med/Low | High/Med/Low | [What we are doing] | [New/Active/Resolved] |

### Section 6 — Asks and Discussion Items

Be explicit about what you need from the board:

- **Approvals needed:** [Budget changes, strategic pivots, large expenditures]
- **Introductions requested:** [Potential customers, partners, candidates]
- **Strategic input:** [Specific questions, not "any thoughts?"]

### Section 7 — Action Item Tracker

| # | Action Item | Owner | Due Date | Status |
|---|------------|-------|----------|--------|
| [From previous meeting] | | | | |
| [New from this meeting] | | | | |

## Output Format

Save to `outputs/board-report-[quarter]-[year].md`

## Writing Standards for Board Materials

- **Be direct.** "Revenue missed by 8% due to delayed enterprise deals" not "Revenue came in slightly below expectations."
- **Quantify everything.** "Reduced churn" is vague. "Reduced churn from 4.2% to 3.1%" is useful.
- **Lead with the red.** Cover problems before wins. Board members respect transparency and lose trust when bad news is buried.
- **Keep it short.** A board report should be readable in 15 minutes. If it takes longer, you have included too much.
- **Close previous loops.** Reference action items from the last meeting and their status.

## Principles

- Board reports are trust documents. Accuracy matters more than polish. Never round in a direction that makes the numbers look better.
- Board members have limited time. Every word competes with their attention. Earn it.
- The discussion section is the most valuable part. A board that rubber-stamps reports is a wasted resource.

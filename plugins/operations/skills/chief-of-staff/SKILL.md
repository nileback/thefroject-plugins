---
name: chief-of-staff
description: Run a chief-of-staff role for a founder, CEO, or senior exec. Calendar audit, decision routing, cross-functional alignment, meeting prep, info brokering. Use when user mentions chief of staff, founder ops, exec ops, calendar audit, or running ops for a leader.
triggers:
  - chief of staff
  - cos workflow
  - founder ops
  - exec ops
  - calendar audit
  - decision routing
---

# Chief of Staff Playbook

The chief-of-staff role multiplies a leader's effective output. Five repeating workflows make it work.

## Gather context

Ask if not provided:

1. **Who's the principal?** — founder, CEO, COO, VP function?
2. **Org size** — under 50, 50-200, 200+. CoS responsibilities shift dramatically.
3. **Current state** — first CoS, replacing a previous one, or scaling an existing function?
4. **Top three pain points** — calendar overload? Decision bottlenecks? Cross-functional drift? Info gaps?
5. **Boundaries** — what's explicitly NOT in scope? (Often: replacing a missing department head.)

## Workflow 1: Calendar audit

Run quarterly. The principal's calendar is the single best signal of where their attention actually goes vs where it should.

Process:
1. Pull the last 90 days of calendar entries (export to CSV).
2. Tag each entry by category: 1:1s, team meetings, recruiting, customer, board/investor, exec offsite, deep work, status reporting, ad-hoc.
3. Compute time per category as % of working hours.
4. Compare to the principal's stated priorities. Misalignment is the deliverable.

Common findings:
- Too much status reporting (kill or delegate).
- Not enough customer time (re-balance).
- Too many 1:1s (drop frequency or duration).
- Recurring meetings that no longer have a purpose (audit + cancel).

Save to `outputs/cos/calendar-audit-<quarter>.md` with the breakdown, the misalignment finding, and a proposed revised cadence.

## Workflow 2: Decision routing

Big orgs route most decisions correctly; small ones route everything to the founder. Both kill output.

Build a **decision matrix**:

| Decision type | Owner | Escalation |
|---|---|---|
| Hire below VP | Hiring manager + recruiter | None |
| VP+ hire | Department head | Founder approves |
| Budget under $X | Department head | None |
| Budget over $X | Department head | Founder + CFO approve |
| Strategy / direction | Leadership team | Founder decides |
| Brand / public statements | Marketing | Founder reviews |
| Customer escalation | CS lead | Founder if churn >$ threshold |

Document this. Pin it in the leadership channel. The CoS routes anything ambiguous and only escalates true exceptions.

## Workflow 3: Cross-functional alignment

The CoS is often the only person who has visibility across every function. Run:

- **Weekly leadership standup** (30-45 min): each function owner gives a 3-minute update on top 3 priorities, blockers, decisions needed.
- **Monthly business review**: structured deep-dive on goals, leading indicators, financial position.
- **Quarterly planning** (offsite): set the next quarter's priorities at the leadership level.

The CoS owns agenda, pre-reads, and follow-ups. The principal owns decisions during the meeting.

## Workflow 4: Exec meeting prep

For every external meeting (board, investors, prospects, partners, press), the CoS prepares:

- **Pre-read** — 1-page brief: who's coming, agenda, your goal, expected questions, recent context.
- **Talking points** — 3-5 explicit messages to land.
- **Open questions** — what the principal needs FROM the meeting.
- **Pre-meeting check** — 10 minutes before, walk through the brief together.
- **Post-meeting capture** — within 24 hours, document outcomes, agreements, follow-ups.

For board meetings specifically, see `board-deck-builder`.

## Workflow 5: Info brokering

The principal needs to know things they don't have time to learn first-hand. The CoS surfaces:

- **Customer voice** — what's actually being said by customers (without the layers of filtering).
- **Team pulse** — what's working, what's frustrating, what's draining (real, not curated).
- **Competitor moves** — material changes (funding, hiring, pivots).
- **Industry shifts** — new categories, regulations, partnerships.

Source this from skip-level conversations, exit interviews, customer call shadowing, peer networks. Document weekly to a "principal's brief" doc the principal reads on Monday morning.

## Output format

The CoS function works through documents. Save to:
- `outputs/cos/calendar-audit-<quarter>.md` — quarterly audit.
- `outputs/cos/decision-matrix.md` — the decision routing doc.
- `outputs/cos/leadership-meetings/<date>.md` — agendas, notes, follow-ups.
- `outputs/cos/principal-brief-<week>.md` — weekly info brief.

## Common mistakes

- CoS becomes a glorified executive assistant. Set explicit scope.
- CoS becomes a power center. They should make leadership effective, not bottleneck on themselves.
- No clear boundary between CoS and department heads. Causes friction and slow decisions.
- Principal doesn't actually delegate decisions per the matrix. Matrix becomes a fiction. Address head-on.
- No succession plan. Strong CoS often promote out within 18-24 months; have a 90-day handoff plan ready.

## Cross-references

For board-deck preparation specifically, use (when added) `board-deck-builder`. For decision documentation, use `decision-tracker`. For OKR cascade across the org, use (when added) `strategic-alignment`. For internal communications driven by the principal, use `internal-comms`. For exec onboarding (when a CoS is replacing one), use `onboarding-designer`.

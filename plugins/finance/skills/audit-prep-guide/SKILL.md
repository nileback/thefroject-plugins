---
name: audit-prep-guide
description: Prepare for internal or external audits by organizing documentation, identifying gaps, building timelines, and creating request lists. Use when an audit is announced, during audit preparation, or for ongoing audit readiness.
triggers:
  - audit preparation
  - audit readiness
  - prepare for audit
  - audit checklist
---

# Audit Prep Guide

Turn audit preparation from a last-minute scramble into a structured process. Auditors reward organizations that are organized, responsive, and transparent.

## Input Required

1. **Audit type** — financial, compliance, operational, IT, or combined
2. **Auditor** — internal team, external firm (Big 4, mid-market, specialist)
3. **Scope** — which entities, systems, periods are covered
4. **Timeline** — fieldwork start date, report due date
5. **Prior audit findings** — open items from previous audits (check `context/` or `outputs/`)

## Phase 1 — Audit Scoping (8-12 weeks before fieldwork)

### Define the Audit Universe

| Dimension | Detail |
|-----------|--------|
| **Entities** | [Which legal entities are in scope?] |
| **Period** | [Fiscal year, quarter, or specific date range] |
| **Standards** | [GAAP, IFRS, SOC 2, ISO, GDPR, etc.] |
| **Systems** | [ERP, CRM, HRIS, cloud platforms in scope] |
| **Processes** | [Revenue recognition, procurement, payroll, etc.] |

### Preliminary Request List

Common categories auditors will request:

| Category | Typical Documents |
|----------|------------------|
| **Governance** | Board minutes, committee charters, org chart, delegation of authority |
| **Financial statements** | Trial balance, general ledger, sub-ledgers, reconciliations |
| **Revenue** | Customer contracts, invoices, revenue recognition memos |
| **Expenses** | AP aging, vendor contracts, expense reports, purchase orders |
| **Payroll** | Pay registers, benefit elections, tax filings, contractor agreements |
| **Cash** | Bank statements, bank reconciliations, investment records |
| **Equity** | Cap table, stock option agreements, board approvals |
| **IT controls** | Access lists, change management logs, backup records, incident reports |
| **Tax** | Returns, provision calculations, transfer pricing documentation |

## Phase 2 — Document Assembly (4-8 weeks before)

### Create the Document Tracker

| Request # | Description | Owner | Status | Location | Due Date | Notes |
|-----------|------------|-------|--------|----------|----------|-------|
| [RFI-001] | [Description] | [Name] | Not Started / In Progress / Ready / Submitted | [File path or system] | [Date] | [Issues] |

### Gap Identification

For each request, assess readiness:

| Status | Definition | Action |
|--------|-----------|--------|
| **Ready** | Document exists, is current, and is accessible | File it in the audit folder |
| **Needs update** | Document exists but is outdated or incomplete | Assign owner and deadline |
| **Missing** | Document does not exist | Create it or document why it is not applicable |
| **Concern** | Document exists but may raise questions | Prepare talking points |

### Common Gaps to Check

- [ ] Bank reconciliations completed and reviewed for all months
- [ ] Journal entries have supporting documentation and approvals
- [ ] Revenue recognition memos exist for non-standard arrangements
- [ ] Vendor contracts are signed and on file for material relationships
- [ ] Access reviews completed for critical systems (at least quarterly)
- [ ] Segregation of duties documented and exceptions approved
- [ ] Intercompany transactions documented and eliminated
- [ ] Fixed asset register reconciled to GL
- [ ] Deferred revenue schedule ties to customer contracts
- [ ] Payroll tax filings match payroll register totals

## Phase 3 — Fieldwork Preparation (2-4 weeks before)

### Logistics

| Item | Detail |
|------|--------|
| **Auditor workspace** | [Physical room, virtual data room, or shared drive?] |
| **Point of contact** | [Primary liaison + backup] |
| **Communication protocol** | [Email, Slack channel, shared tracker?] |
| **Data room structure** | [Folder structure matching request list] |
| **Access provisioned** | [System access for auditors if needed] |
| **Kickoff meeting** | [Date, attendees, agenda] |

### Prepare the Team

Brief everyone who may interact with auditors:

- Answer only the question asked. Do not volunteer information.
- If you do not know the answer, say so. Do not guess.
- All documents go through the audit liaison, not directly to auditors.
- Flag any questions that make you uncomfortable to the liaison immediately.

## Phase 4 — During Fieldwork

### Daily Tracking

| Date | Requests Received | Requests Fulfilled | Open Items | Issues | Next Day Priority |
|------|------------------|-------------------|-----------|--------|-----------------|

### Issue Management

When auditors identify a finding:

1. Understand the finding precisely (ask for the specific control or assertion)
2. Determine if you agree or disagree with the characterization
3. If you agree, draft a management response with remediation timeline
4. If you disagree, prepare evidence supporting your position
5. Escalate material findings to leadership immediately

## Output Format

Save to `outputs/audit-prep-[audit-type]-[year].md`:

```markdown
# Audit Preparation — [Type] — [Year]

## Scope and Timeline
[Summary table]

## Document Tracker
[Full request list with status]

## Gap Analysis
[Identified gaps with remediation plans]

## Open Items from Prior Audits
[Status of each]

## Team Assignments
[Who owns what]

## Risk Areas
[Areas where findings are likely]
```

## Principles

- The best audit prep starts months before the auditors arrive, not weeks. Maintain audit-ready documentation year-round.
- Auditors form impressions early. An organized data room and responsive team earn goodwill that matters when judgment calls arise.
- Never hide problems. Auditors will find them. Proactive disclosure with a remediation plan is always better than discovery.

---
name: enterprise-sales
description: Run a complex B2B sales process — qualification across multiple stakeholders, mutual action plan, executive engagement, security and procurement review, contract and legal close. For SMB or transactional sales use sales-outreach-writer + deal-strategy-analyzer instead.
triggers:
  - enterprise sales
  - complex sale
  - multi-stakeholder deal
  - mutual action plan
  - map
  - large deal
  - enterprise deal strategy
---

# Enterprise Sales

Sell into multi-stakeholder organizations where deals take 3-12 months and 6-12 people are involved. The skill is structure, not charisma.

## Gather context

Ask if not provided:

1. **Deal size** — what's the ACV range we're working in?
2. **Sales cycle** — typical days from first conversation to closed-won?
3. **Stakeholder map** — known contacts? Roles?
4. **Buying triggers** — why is this prospect looking now (mandate, problem, regulation)?
5. **Procurement maturity** — formal RFP process? Ad-hoc? Procurement-led or business-led?

## Qualification framework

Mature enterprise sales teams qualify across multiple dimensions before investing significant time. The dimensions to confirm (without naming a specific framework):

- **Metrics** — what business outcome would success look like? Quantified.
- **Economic buyer** — who can sign / approve budget? Is the deal sized to their authority?
- **Decision criteria** — what specifically must be true for them to choose us?
- **Decision process** — what are the steps from now to signature? Who's involved at each?
- **Identified pain** — concrete problem with consequences if unsolved. Not just "interested in efficiency."
- **Champion** — internal advocate with credibility AND access AND motivation. Three traits all required.
- **Competition** — who else is in the deal? What's the status quo (do-nothing) option?

If 3+ of these are unknown after the first two meetings, the deal isn't qualified. Don't invest more SE time, exec hours, or RFP responses until the qualification gaps are closed.

## Mutual Action Plan (MAP)

The single most underused enterprise sales tool. Build a shared document with the prospect that lists every step from today to signed contract:

```
## Mutual Action Plan: <Customer> + <Vendor>

### Goal
[The customer's stated success criteria, in their words.]

### Timeline
- Target signature date: <date>
- Target go-live: <date>

### Workstreams
| Step | Owner | Date | Status |
|---|---|---|---|
| Initial discovery | Vendor + Customer Champion | <date> | Done |
| Technical demo | Vendor SE | <date> | Done |
| Security review | Customer IT + Vendor Security | <date> | In progress |
| Pilot scope | Vendor + Champion | <date> | Pending |
| Pilot execution | Customer team | <date> | Pending |
| Pricing proposal | Vendor | <date> | Pending |
| Procurement review | Customer Procurement | <date> | Pending |
| Legal redlines | Customer Legal + Vendor Legal | <date> | Pending |
| Final approvals | Customer Exec Sponsor | <date> | Pending |
| Signature | Customer EB | <date> | Pending |
```

Use it in every customer meeting. Update it together. The MAP is not a checklist — it's a forcing function for both sides to commit to dates.

## Multi-thread coverage

Enterprise deals collapse when only the champion is engaged. Aim for 5+ contacts per account by mid-cycle:

- **Champion** — primary internal advocate.
- **Champion +1** — peer or report of the champion.
- **Economic buyer** — budget owner.
- **Technical evaluator** — IT, security, or domain expert who has veto power.
- **End user** — who will actually use the product daily.
- **Exec sponsor** — VP/SVP/C-suite who blesses the project.

Every contact should be reached at least once per cycle. Mix channels: 1:1 calls, group meetings, technical workshops, exec dinners.

## Procurement and legal

Build relationships with procurement EARLY. They're often treated as adversaries; treat them as partners and they'll close deals faster.

- **Master Service Agreement** — request the customer's MSA template upfront if they have one. Faster than starting with yours.
- **Pricing transparency** — show the math, not just the number. Procurement respects defensible pricing.
- **Standard discounts** — pre-approve a discount tier with finance. Negotiating from scratch on every deal is exhausting and inconsistent.
- **Security questionnaires** — keep a master answer doc updated. (See `sales-engineer` for technical content.)

## Risk register

For every $100k+ deal, maintain a risk register:

```
## Risk register: <Account>
| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Champion leaves company | Med | High | Multi-thread; build 2nd champion | AE |
| Security review takes 6+ months | High | Med | Engage security in week 2; provide SOC2 + pen-test | SE |
| Budget freeze in Q4 | Med | High | Push for Q3 close OR get verbal commit before freeze | AE + Sponsor |
```

Review weekly. New risks surface as the deal progresses.

## Output format

Per deal: save the qualification, MAP, stakeholder map, and risk register at `outputs/enterprise-deals/<account-slug>/`:
- `qualification.md` — qualification status across the dimensions above.
- `map.md` — the mutual action plan, owned together with the customer.
- `stakeholder-map.md` — multi-thread coverage with each contact's role, motivation, last touch.
- `risk-register.md` — current risks and mitigations.

Update each weekly during the deal cycle.

## Common mistakes

- Single-threading on the champion. Champion leaves, deal dies.
- No MAP. Both sides drift on timelines. Deal slips a quarter.
- Skipping qualification on a "big deal" — gut feel beats discipline. Ends in 9-month wasted cycles.
- Engaging procurement late. They feel ambushed; they slow the deal.
- No exec sponsor on the customer side. Champion can't close alone.

## Cross-references

For battlecards within enterprise deals, use `sales-battlecard-builder` and `competitive-battlecard-builder`. For technical pre-sales support, use (when added) `sales-engineer`. For pipeline-level review of multiple enterprise deals, use `sales-pipeline`. For the discovery / objection / champion-building skills, use existing `objection-handler` and `deal-strategy-analyzer`.

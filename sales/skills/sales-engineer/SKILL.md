---
name: sales-engineer
description: Technical pre-sales support for complex B2B deals. Demo prep, technical evaluations, security questionnaires, RFP responses, proof-of-concept design and execution. Use when user mentions SE work, technical demo, security questionnaire, SOC2 review, RFP response, or POC design.
triggers:
  - sales engineer
  - se prep
  - technical demo
  - security questionnaire
  - rfp response
  - proof of concept
  - poc design
---

# Sales Engineer

Technical pre-sales partner to the AE. Translate customer technical requirements into the product's capability, run demos that hit the customer's specific use case, answer security and integration questions, and design POCs that close deals.

## Gather context

Ask if not provided:

1. **Deal stage** — early discovery, demo phase, technical evaluation, POC, security review?
2. **Customer technical environment** — stack, scale, regulatory environment?
3. **What's the AE asking for?** — demo, RFP response, security review, POC design?
4. **Specific concerns or questions surfaced by the customer?**
5. **Internal subject-matter expert needed?** (Some asks require product / engineering input — flag early.)

## Demo prep

A great technical demo is configured to the customer, not generic.

### Pre-demo checklist
- Read the deal notes. Know the use case, the personas in the room, and the specific pain.
- Identify 3-5 features to highlight. Skip the rest. A demo that covers 100% of the product wastes time on irrelevance.
- Pre-load the demo environment with customer-realistic data (sanitized). Generic Lorem Ipsum demos lose deals.
- Prepare two opening hooks: technical depth (for IT/eng audience) and business outcome (for biz audience). Pick based on who's in the room.
- Have a "go off-script" plan. The best demos respond to questions instead of charging through slides.

### During the demo
- Open with: confirm the agenda, confirm who's in the room (and who isn't), confirm the goal of THIS meeting.
- Show, don't explain. Let the product do the talking.
- Pause every 8-10 minutes for questions. Silence after a feature usually means confusion or skepticism.
- Take notes on objections and concerns to follow up.
- Close with a concrete next step (POC kickoff, follow-up call with X, technical doc to review).

## Security questionnaires

Big customers send 100-question security forms. Speed matters; consistency matters more.

- Maintain a **master answer doc** (`reference/security-master.md`) with answers to the most common 200 questions. Update quarterly with new product changes.
- For new questions: get the right SME (CISO, infra lead, product), don't make up answers.
- Provide supporting docs (SOC2 report, pen test results, architecture diagrams) as standard attachments.
- For sensitive yes/no questions where the answer is "no but...", add the "but" — context turns blockers into mitigations.
- Track timing. If responses regularly take 2+ weeks, the master doc is incomplete or routing is broken.

Common questionnaires:
- SOC 2 Type II report request — provide the report under NDA.
- ISO 27001 — confirm certification or compensating controls.
- GDPR / data residency — explicit answers per region.
- Pen test summary — provide the most recent.
- Sub-processor list — provide and keep current.
- Vendor risk assessment (VRA) — fill the form, don't redirect to your generic security page.

## RFP responses

Long RFPs (50-500 questions) need triage:

1. **Skim first.** Find the 5-10 questions that decide the deal. Answer those well.
2. **Categorize remaining questions** — boilerplate (use master doc), product-specific (need product input), differentiated (your moment to shine).
3. **Time-box** — set a hard deadline. Don't perfect; ship.
4. **Match their format.** If they want yes/no/partial, don't write paragraphs.
5. **Kill scope creep.** "We don't currently support X" is OK if true. Lying to win an RFP creates worse problems post-close.

## Proof of Concept (POC) design

POCs win deals when scoped tightly. They lose deals when sprawling.

### Design principles
- **Single, measurable success criterion.** "Does X feature work for our use case Y?" Not "Evaluate the product comprehensively."
- **Time-boxed.** 2-4 weeks max. Longer = the deal is stalling.
- **Customer commitment.** They invest time too. If they won't commit a couple of hours per week, they're not serious.
- **Joint kickoff.** Define success criteria, environment, escalation path, end-state decision (signed contract or written reason for not).
- **Ramp-down meeting.** End the POC formally. Don't drift into "well, let's keep using it..."

### POC plan template
```
## POC: <Customer> x <Product>

### Success criterion (single)
[Specific, measurable, agreed by both parties]

### Scope
- In: [features, integrations, use cases included]
- Out: [explicitly excluded — protect against scope creep]

### Timeline
- Kickoff: <date>
- Mid-point check: <date>
- End-state decision: <date>

### Roles
- Customer lead: <name, role>
- Customer technical: <name>
- Vendor SE: <name>
- Vendor AE: <name>
- Escalation contact: <name>

### Decision (filled at end)
- Result: [success / partial / fail]
- Outcome: [contract signed / contract pending / closed-lost]
- Reason: [if not signed]
```

## Output format

Save SE artifacts to `outputs/se/<account-slug>/`:
- `demo-plan.md` — pre-demo prep + post-demo notes.
- `security-responses.md` — questionnaire answers (linked to the master doc).
- `rfp-response/` — folder with answer files per RFP section.
- `poc-plan.md` — kickoff document, mid-point check, end-state decision.

## Common mistakes

- Generic demos. Lose 50% of the room in 5 minutes.
- Improvising security answers. Contradicts the master doc, creates audit risk.
- POCs without a single success criterion. Drag on for months, end inconclusively.
- Saying "yes" to everything in an RFP. Sets the deal up for post-close failure.
- Not capturing customer technical contacts. Sales-only relationships die under technical scrutiny.

## Cross-references

For the broader enterprise deal context, use `enterprise-sales`. For battlecards on competitive deals, use `sales-battlecard-builder` and `competitive-battlecard-builder`. For deal-level strategy, use `deal-strategy-analyzer`. For the security side specifically, see existing `security-auditor` (development-tagged) and (when added) `soc2-compliance`.

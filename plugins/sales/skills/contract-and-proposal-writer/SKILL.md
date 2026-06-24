---
name: contract-and-proposal-writer
description: Generate professional business contracts and proposals with jurisdiction awareness — SOWs, NDAs, MSAs, freelance contracts, project proposals. NOT a substitute for legal counsel; templates only. Use when user mentions contract, SOW, NDA, MSA, freelance agreement, or jurisdictional legal documents.
triggers:
  - contract template
  - sow template
  - nda template
  - msa template
  - freelance contract
  - service agreement
---

# Contract & Proposal Writer

Generate business contract and proposal documents from structured input. Templates cover the common categories with jurisdiction-aware variations.

## Important: not legal advice

These templates are starting points, not finished legal documents. For high-value or complex engagements, route to an attorney. For low-stakes routine work, the templates here are typically defensible.

When in doubt, recommend the user consult counsel.

## Document types covered

| Document | When to use | Length |
|---|---|---|
| Freelance / Independent Contractor Agreement | Solo contractor doing project work | 3-5 pages |
| Project Proposal | Pre-contract document outlining scope, timeline, budget | 2-4 pages |
| Statement of Work (SOW) | Specific project under an existing master agreement | 1-3 pages |
| Master Service Agreement (MSA) | Ongoing relationship; SOWs reference it | 5-15 pages |
| Mutual NDA | Both parties exchanging confidential info | 1-3 pages |
| One-way NDA | One party disclosing to the other | 1-2 pages |
| Letter of Intent (LOI) | Pre-contract memo of understanding | 1-2 pages |

## Jurisdiction handling

Contract law differs by jurisdiction. The skill handles:

- **US (Delaware default)** — most common for US business contracts. Other states differ on non-competes, IP assignment, etc.
- **EU (GDPR-aware)** — data processing addenda required for any contract handling EU personal data.
- **UK** — post-Brexit divergence; many EU concepts remain similar.
- **DACH (Germany / Austria / Switzerland)** — German law is more restrictive on certain clauses (limitation of liability, employment).
- **Other** — flag explicitly that the user should validate with local counsel.

Ask the user which jurisdiction governs before drafting.

## Workflow

### Step 1: Gather inputs
For any document, capture:
- Parties involved (legal names + addresses).
- Effective date.
- Term (start, end, renewal, termination).
- Scope (what's being delivered or exchanged).
- Compensation (amount, schedule, payment terms).
- Jurisdiction (governing law).
- Key clauses (IP ownership, confidentiality, non-solicit, indemnification, limitation of liability).

### Step 2: Pick the template
Match the document type. If the user describes a hybrid situation (e.g., "I want a contract that's like an SOW but stand-alone"), tell them which template fits and why; don't invent a hybrid.

### Step 3: Customize
Common customizations:
- **IP ownership** — work-for-hire vs. licensed back. Default work-for-hire for client work.
- **Payment terms** — net 30 default for B2B; 50% upfront, 50% on delivery for project work.
- **Termination** — for cause, for convenience, with notice period.
- **Limitation of liability** — typically capped at fees paid (12 months) for SaaS / services.
- **Indemnification** — mutual default; one-way for high-stakes situations.

### Step 4: Generate the document
Output as markdown initially (easy to review and revise). Convert to .docx with `docx-handler` once the user approves.

### Step 5: Flag for legal review
End every output with:
- A summary of the key terms.
- A "review with counsel" note for any non-standard clauses or high-stakes items.

## Output format

For project proposal:
```
## Project Proposal
- From: <Vendor name + contact>
- To: <Client name + contact>
- Date: <date>
- Project: <name>

## Background
[1-2 paragraphs context]

## Scope
[Specific deliverables]

## Out of scope
[Explicit exclusions]

## Timeline
[Phases with dates]

## Investment
[Cost breakdown + payment schedule]

## Acceptance criteria
[How we know we're done]

## Assumptions
[What we're assuming about client side]

## Next steps
[How to move to contract]
```

For contracts: full legal-style document. Save to `outputs/contracts/<doc-type>-<counterparty>-<date>.md` then convert to .docx via `docx-handler`.

## Common mistakes

- Mixing jurisdictions. A US-style limitation of liability doesn't always work in DACH.
- Vague scope. "Marketing services" leaves the door open for scope creep on both sides.
- No termination clause. Bad for both parties when the relationship needs to end.
- Skipping the "for cause" termination triggers (breach of confidentiality, non-payment, insolvency).
- Boilerplate IP language that isn't right for the work (e.g., work-for-hire when the freelancer is supposed to retain rights to reusable code).

## Cross-references

For sales-narrative proposals (different from this skill's pre-contract proposal), use `proposal-writer` and `proposal-voice-guide`. For pricing inside a proposal, use `pricing-strategist` and `pricing-guidelines`. For document file production (Word format), use `docx-handler`. For broader vendor management, use `vendor-management-guide`.

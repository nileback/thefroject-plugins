---
name: gdpr-compliance
description: Build and maintain GDPR compliance program. Data mapping, lawful basis documentation, DPA agreements, subject access request handling, breach response. Use when user mentions GDPR, EU privacy, data protection, DPA, DSAR, lawful basis, or breach notification.
triggers:
  - gdpr
  - data protection
  - eu privacy
  - dpa agreement
  - subject access request
  - dsar
  - data breach
---

# GDPR Compliance

Build and maintain GDPR compliance for any company processing personal data of EU residents. Despite Brexit, similar rules apply in the UK; CCPA in California has overlapping requirements.

## Gather context

Ask if not provided:

1. **Geographic exposure** — EU customers, EU users, EU employees, EU vendors?
2. **Data types processed** — customer data, employee data, prospect data, sensitive data (health, financial)?
3. **Current state** — any existing privacy program, DPO appointed, DPA agreements?
4. **Stage** — never assessed, partial program, mature?
5. **Specific trigger** — pre-launch, breach, customer ask, regulatory inquiry?

## The six core obligations

### 1. Lawful basis
Every personal-data processing activity must have one of six lawful bases:
- Consent (specific, informed, freely given).
- Contract (necessary to fulfill a contract with the data subject).
- Legal obligation (required by law).
- Vital interests (life-or-death).
- Public task (rare for most companies).
- Legitimate interests (balanced against subject rights).

Document the basis for every type of processing. Audit your data flows to find anything without a basis.

### 2. Data mapping (Article 30 records)
A complete inventory of:
- What personal data you collect.
- Why (purpose).
- Lawful basis.
- Where it's stored.
- Who has access.
- Who you share it with (sub-processors).
- How long you keep it.
- How it's protected.

Update annually or when processes change.

### 3. Subject rights
Data subjects have rights under GDPR:
- Access (DSAR — provide a copy of their data).
- Rectification (correct errors).
- Erasure ("right to be forgotten").
- Restriction (pause processing).
- Portability (provide data in machine-readable format).
- Object (to certain processing).
- Not to be subject to automated decisions.

Build processes for each. DSAR responses must complete within 30 days.

### 4. Data Processing Agreements (DPAs)
For every vendor that processes personal data on your behalf, you need a DPA. The DPA covers:
- Subject matter and duration.
- Nature and purpose of processing.
- Type of personal data.
- Categories of data subjects.
- Sub-processor list and approval rights.
- Security measures.
- Audit rights.
- Data return / deletion at contract end.

Maintain a master DPA template; route every vendor through it.

### 5. Breach notification
If a personal data breach occurs:
- Notify the supervisory authority within 72 hours.
- Notify affected data subjects without undue delay (if high risk).

Define "breach" broadly: it includes accidental destruction, loss, alteration, or unauthorized disclosure.

Have a documented breach response plan in place BEFORE you need it.

### 6. Privacy-by-design and DPIAs
For high-risk processing (large-scale, profiling, sensitive data), conduct a Data Protection Impact Assessment (DPIA) before starting.

DPIAs document: what processing, why, risks identified, mitigations, residual risk acceptance.

## Workflow

### Step 1: Data mapping
Pull from product team, customer success, marketing, HR, finance. Document every personal data processing activity. Output: `outputs/gdpr/data-map.md`.

### Step 2: Lawful basis review
For each processing activity, document the lawful basis. Where you can't find one, fix the underlying process or stop the processing.

### Step 3: DPA inventory
List every vendor that processes personal data. Confirm DPA in place. For new vendors, route through standard DPA before they touch data.

### Step 4: Subject rights process
Build procedures for DSAR, deletion, portability. Test the process with a fake DSAR.

### Step 5: Breach response plan
Documented incident response covering: detection, assessment, containment, notification (regulator + subjects), post-mortem.

### Step 6: Training
All employees receive privacy basics; teams handling personal data receive deeper training.

### Step 7: DPO appointment (if required)
Appoint a Data Protection Officer if: you're a public authority, your core activities require regular monitoring of subjects on a large scale, or your core activities are large-scale processing of special-category data.

## Output

Save GDPR program artifacts to `outputs/gdpr/`:
- `data-map.md` — Article 30 records of processing.
- `lawful-basis.md` — basis for each processing activity.
- `dpa-register.md` — DPA tracker per vendor.
- `subject-rights-procedures.md` — DSAR, deletion, portability procedures.
- `breach-response-plan.md` — incident response with notification timeline.
- `dpia/` — folder for DPIAs as completed.
- `policies/` — privacy policy, cookie policy, data retention policy.

## Common mistakes

- Treating GDPR as a one-time project. It's ongoing.
- No data map. Can't comply with what you don't know you have.
- Generic DPA template that doesn't reflect actual vendor relationship.
- DSAR process that's actually unmanaged email — won't scale.
- Ignoring sub-processors. Every Stripe / AWS / Notion is a sub-processor under GDPR.
- Cookie consent that's just a notification, not real consent.

## Cross-references

For SOC 2 compliance (overlapping security controls), use `soc2-compliance`. For ISO 27001 (similar information security framework), use `iso27001-isms`. For risk register, use `risk-register-builder`. For breach response specifically, use `incident-responder`. For policy writing, use `policy-writer`.

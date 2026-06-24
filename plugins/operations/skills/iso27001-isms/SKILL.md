---
name: iso27001-isms
description: Build and maintain an ISO 27001 Information Security Management System (ISMS). Risk-based information-security framework with controls drawn from Annex A. Output covers Statement of Applicability, risk treatment plan, internal audit, management review.
triggers:
  - iso 27001
  - iso27001
  - isms
  - information security management
  - statement of applicability
  - soa
  - risk treatment
---

# ISO 27001 ISMS

Build and maintain an Information Security Management System (ISMS) certified against ISO 27001:2022. ISO 27001 is the international standard for information security; common requirement for enterprise B2B sales, especially in Europe.

## Gather context

Ask if not provided:

1. **Certification goal** — pursuing certification, certified and maintaining, or self-attesting?
2. **Auditor selected?** — accredited certification body needed for full certification.
3. **Existing security work** — SOC 2, NIST framework, internal security program?
4. **Scope** — entire org, specific business unit, specific service?
5. **Timeline** — typical 6-12 months from start to certification.

## The four mandatory components

### 1. Risk assessment
Identify threats to information assets. Estimate likelihood and impact. Prioritize.

For each information asset:
- What threats exist? (External attackers, insider risk, accidental loss, environmental.)
- What's the impact if compromised?
- What's the likelihood?
- What's the residual risk after current controls?

Document the methodology. Repeat annually or when significant changes happen.

### 2. Statement of Applicability (SoA)
ISO 27001:2022 has 93 controls organized in 4 themes (organizational, people, physical, technological).

For each control, document:
- **Applicable?** — is this control relevant to your scope?
- **Implemented?** — yes / partial / no.
- **Justification** — why this state is acceptable.

The SoA is the central artifact auditors review. Get it right.

### 3. Risk treatment plan
For each risk identified above the acceptable threshold:
- **Treat** (apply controls to reduce).
- **Tolerate** (accept the risk; document why).
- **Transfer** (insurance, contractual).
- **Terminate** (stop the activity creating the risk).

Each treatment has an owner and a deadline.

### 4. Internal audit and management review
- **Internal audit** annually (or as defined). Independent review of ISMS effectiveness.
- **Management review** at least annually. Leadership reviews ISMS performance, audit findings, risk trends.

## The 93 Annex A controls (themes)

### A.5 Organizational controls (37 controls)
Policies, roles, segregation of duties, vendor relationships, threat intelligence, asset management.

### A.6 People controls (8 controls)
Pre-employment screening, training, awareness, disciplinary process, post-employment.

### A.7 Physical controls (14 controls)
Physical security perimeters, secure areas, equipment, secure disposal.

### A.8 Technological controls (34 controls)
Access management, cryptography, secure development, network security, logging, incident management.

Most companies don't need all 93. Tailor to scope and risk.

## Workflow

### Step 1: Define scope and ISMS objectives
Pick what's certified — entire org, specific service, specific business unit. Smaller scope = faster cert; broader scope = better posture.

### Step 2: Risk assessment
Inventory information assets. Identify threats. Score risk. Prioritize.

### Step 3: SoA
Walk all 93 controls. Mark applicable, implementation status, justification.

### Step 4: Gap remediation
For controls applicable but not implemented, build the implementation roadmap.

### Step 5: Documentation
Required policies (information security, access control, cryptography, asset management, incident management, etc.). Required procedures.

### Step 6: Operate
Run the ISMS. Logs, reviews, training, incident response.

### Step 7: Internal audit
Independent review. Findings logged. Remediation tracked.

### Step 8: Management review
Leadership reviews and signs off.

### Step 9: External audit
Stage 1 (documentation review) and Stage 2 (operating effectiveness). Issue resolution. Certification issued.

### Step 10: Maintain
Annual surveillance audits, three-year recertification.

## Output

Save ISMS artifacts to `outputs/iso27001/`:
- `isms-scope.md` — what's covered.
- `risk-assessment.md` — methodology and risk register.
- `soa.md` — Statement of Applicability with all 93 controls.
- `risk-treatment-plan.md` — risks above threshold with treatment.
- `policies/` — required policies.
- `internal-audit/` — annual audit reports.
- `management-review/` — annual review minutes.
- `incident-log.md` — running incident register.

## Common mistakes

- SoA copy-pasted without genuine assessment. Auditors find this fast.
- Risk register that lists "fire" and "theft" generically. Real risks are specific.
- Policies that don't reflect what actually happens. Auditors check operations vs. documentation.
- Treating it as a security project, not a management system. ISO 27001 is about ongoing operation.
- Skipping internal audit. Mandatory for certification.

## Cross-references

For SOC 2 compliance (significant overlap with ISO 27001), use `soc2-compliance`. For GDPR (privacy-specific), use `gdpr-compliance`. For risk register, use `risk-register-builder`. For internal incident response, use `incident-responder`. For policy writing, use `policy-writer`. For audit prep generally, use `audit-prep-guide`.

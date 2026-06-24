---
name: soc2-compliance
description: Prepare a company for a SOC 2 Type 1 or Type 2 audit. Documents controls, gathers evidence, identifies gaps, and produces audit-ready artifacts. Pairs with security-auditor for technical controls and risk-register-builder for risk documentation.
triggers:
  - soc 2
  - soc2
  - service organization controls
  - type 1 audit
  - type 2 audit
  - security compliance
---

# SOC 2 Compliance

Prepare for a SOC 2 audit. SOC 2 evaluates a company's controls related to security, availability, processing integrity, confidentiality, and privacy — the five Trust Services Criteria. Most B2B SaaS companies need at least the Security category.

## Gather context

Ask if not provided:

1. **Audit type** — Type 1 (point-in-time control design) or Type 2 (operating effectiveness over 6-12 months)?
2. **Trust Services Criteria scope** — Security only, or also Availability / Confidentiality / Processing Integrity / Privacy?
3. **Stage** — never been audited, between audits, mid-audit?
4. **Auditor selected?** — Big-4, mid-tier, boutique?
5. **Existing controls** — what's already in place?

## The five Trust Services Criteria (TSC)

### Security (mandatory)
Controls protecting against unauthorized access. Covers: access management, network security, vulnerability management, incident response.

### Availability
Controls ensuring system uptime. Covers: monitoring, capacity planning, disaster recovery, backups.

### Confidentiality
Controls protecting confidential information. Covers: encryption, data classification, secure deletion.

### Processing Integrity
Controls ensuring system processing is complete, valid, accurate. Covers: data validation, error handling, change management.

### Privacy
Controls related to personal information. Covers: notice, choice, access, retention, disposal.

Most companies start with Security only and add others over time.

## The control framework

For each TSC, document specific controls. Common control categories:

### Access management
- User provisioning and deprovisioning.
- Multi-factor authentication.
- Privileged access management.
- Access reviews (typically quarterly).
- Password requirements.

### Network and infrastructure
- Network segmentation.
- Firewall rules.
- Intrusion detection.
- Vulnerability scanning.
- Patch management.

### Change management
- Code review requirements.
- Approval workflows.
- Production change controls.
- Rollback procedures.

### Risk management
- Risk register maintained.
- Annual risk assessment.
- Vendor risk management.

### HR and operations
- Background checks.
- Security training.
- Acceptable use policies.
- Incident response plan.

### Physical security (if applicable)
- Office access controls.
- Data center security (if not cloud-only).

## Evidence requirements

Auditors need evidence of controls operating. Examples:

- **Access reviews**: dated quarterly review reports with reviewer signatures.
- **Vulnerability scans**: regular scan output with remediation tracking.
- **Code reviews**: PRs showing reviewer approval before merge.
- **Incident response**: actual incidents with documented response timeline.
- **Training**: signed completion records.
- **Background checks**: dated check completion records.

For Type 2, you need 6-12 months of consistent evidence. This is why most companies do Type 1 first (point-in-time) before Type 2 (over time).

## Gap assessment workflow

### Step 1: Pull current state
List what's actually happening today, control by control.

### Step 2: Map to SOC 2 controls
Which trust services criterion does each existing control address? Where are the gaps?

### Step 3: Prioritize gaps by audit risk
- High: control doesn't exist; auditor will flag.
- Medium: control exists but evidence is weak.
- Low: control is fine but documentation is messy.

### Step 4: Remediation plan
For each gap, an owner and a deadline. Run weekly until audit.

### Step 5: Evidence collection
For Type 2: build evidence collection into operational rhythm so it's not a fire drill at audit time.

## Output

Save SOC 2 readiness work to `outputs/soc2/<audit-period>/`:
- `control-matrix.md` — every control with description, owner, evidence source.
- `gap-assessment.md` — current gaps with severity and remediation status.
- `policies/` — folder of required policies (acceptable use, incident response, access management, etc.).
- `evidence/` — running evidence collection.
- `audit-prep.md` — pre-audit checklist.

These files are sensitive — store privately.

## Common mistakes

- Treating SOC 2 as a one-time project. It's an ongoing operational discipline.
- Going for Type 2 first. Type 1 is much easier; build muscle there.
- Over-scoping (all 5 TSCs) on first attempt. Start with Security.
- Generic policies copy-pasted from templates. Auditors notice; controls don't actually run.
- No control owners. Audits expose unowned controls quickly.

## Cross-references

For technical-side security audits, use `security-auditor`. For risk register building (a SOC 2 control), use `risk-register-builder`. For incident response specifically, use `incident-responder`. For audit prep generally, use `audit-prep-guide`. For other compliance frameworks, see (when added) `gdpr-compliance` and `iso27001-isms`.

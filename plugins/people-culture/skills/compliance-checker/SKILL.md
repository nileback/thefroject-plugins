---
name: compliance-checker
description: Assess compliance gaps for GDPR, SOC 2, ISO 27001, and HIPAA.
triggers:
  - compliance audit
  - GDPR check
  - SOC 2 preparation
---

# Compliance Checker

Identify compliance gaps before auditors do. This skill provides a structured assessment framework, not legal advice. Flag items that require legal review.

## Phase 1 — Scope Definition

Before assessing anything, define the audit boundary:

| Parameter | Value |
|-----------|-------|
| **Standard/regulation** | SOC 2 Type II / ISO 27001 / GDPR / HIPAA / PCI DSS / Other |
| **Systems in scope** | [List all systems that store, process, or transmit regulated data] |
| **Data types** | [PII, PHI, financial data, credentials, etc.] |
| **Geography** | [Jurisdictions where data is collected, processed, and stored] |
| **Audit timeline** | [When is the audit? Work backwards from that date] |

## Phase 2 — Data Inventory

Map all personal or sensitive data flows:

| Data Element | Classification | Source | Storage Location | Access Controls | Retention | Encryption |
|-------------|---------------|--------|-----------------|----------------|-----------|-----------|
| [e.g., Email address] | PII | User signup form | PostgreSQL (AWS RDS) | Role-based, CSM + Eng | 2 years post-account deletion | At rest: AES-256, In transit: TLS 1.3 |

### Classification Levels
| Level | Definition | Examples | Handling Requirement |
|-------|-----------|----------|---------------------|
| Public | No restrictions | Marketing content, pricing | None |
| Internal | Business-sensitive | Revenue data, roadmaps | Access control, no public sharing |
| Confidential | Regulated or sensitive | PII, credentials, financial | Encryption, access logging, retention limits |
| Restricted | Highest sensitivity | PHI, payment card data, SSNs | All of above + additional controls per regulation |

## Phase 3 — Controls Assessment by Framework

### SOC 2 Trust Service Criteria
| Category | Key Controls | Evidence Required |
|----------|-------------|------------------|
| **Security** | Firewalls, access control, MFA, vulnerability scanning | Config screenshots, scan reports, access reviews |
| **Availability** | Uptime monitoring, incident response, backups, DR plan | Monitoring dashboards, incident reports, DR test results |
| **Processing Integrity** | Input validation, error handling, change management | Code review logs, deployment logs, QA processes |
| **Confidentiality** | Encryption, data classification, access restrictions | Encryption configs, classification policy, access logs |
| **Privacy** | Consent management, data retention, subject access requests | Privacy policy, consent records, SAR process docs |

### GDPR Key Requirements
| Article | Requirement | Control | Evidence |
|---------|-----------|---------|---------|
| Art. 5 | Data minimization | Collect only necessary data | Data inventory showing purpose for each element |
| Art. 6 | Lawful basis | Documented legal basis per data type | Consent records, legitimate interest assessments |
| Art. 13-14 | Transparency | Privacy notice at collection point | Privacy policy, cookie banner |
| Art. 15-22 | Data subject rights | Process for access, deletion, portability | SAR procedure, response templates, logs |
| Art. 25 | Privacy by design | Security built into development | Architecture reviews, threat models |
| Art. 28 | Processor agreements | DPAs with all processors | Signed DPAs, processor inventory |
| Art. 30 | Records of processing | Maintained processing register | ROPA document, regular updates |
| Art. 32 | Security measures | Technical and organizational measures | Security controls documentation |
| Art. 33-34 | Breach notification | 72-hour notification process | Incident response plan, breach register |

### ISO 27001 Annex A Controls (key areas)
| Domain | Controls | Assessment Focus |
|--------|---------|-----------------|
| A.5 | Information security policies | Are policies documented, reviewed, communicated? |
| A.6 | Organization of information security | Are roles and responsibilities assigned? |
| A.7 | Human resource security | Background checks, security training, offboarding? |
| A.8 | Asset management | Asset inventory, classification, acceptable use? |
| A.9 | Access control | Least privilege, MFA, regular access reviews? |
| A.12 | Operations security | Change management, malware protection, logging? |
| A.14 | System acquisition/development | Secure development lifecycle, testing? |
| A.16 | Incident management | Detection, response, lessons learned? |
| A.18 | Compliance | Legal requirements identified, audits scheduled? |

## Phase 4 — Gap Analysis

For each control area, assess the current state:

| Requirement ID | Control Description | Current State | Gap | Risk (L x I) | Priority | Remediation |
|---------------|-------------------|-------------|-----|-------------|----------|------------|
| [SOC2-SEC-01] | [Description] | ✅ Implemented / ⚠️ Partial / ❌ Missing | [What is missing] | [1-5] x [1-5] = [Score] | P1/P2/P3 | [Action needed] |

### Risk Scoring
| Score | Likelihood | Impact |
|-------|-----------|--------|
| 1 | Rare | Negligible |
| 2 | Unlikely | Minor |
| 3 | Possible | Moderate |
| 4 | Likely | Major |
| 5 | Almost certain | Severe |

**Priority mapping:**
- Risk score 15-25: P1 (address before audit)
- Risk score 8-14: P2 (address within 30 days)
- Risk score 1-7: P3 (address within 90 days)

## Phase 5 — Remediation Planning

For each gap, create a remediation ticket:

```
Gap: [Description]
Risk: [Score] — Priority: [P1/P2/P3]
Remediation: [Specific action to close the gap]
Owner: [Role responsible]
Deadline: [Date]
Evidence needed: [What proves the gap is closed]
Dependencies: [Other gaps or approvals needed first]
```

### Evidence Collection Checklist
Auditors require evidence that controls exist AND operate effectively:

| Evidence Type | Examples | Format |
|--------------|---------|--------|
| Policy documents | Security policy, privacy policy, acceptable use | PDF with version history |
| Configuration | Firewall rules, encryption settings, access controls | Screenshots with timestamps |
| Logs | Access logs, change logs, incident logs | Exported log files or dashboard screenshots |
| Process records | Access reviews, training completion, vendor assessments | Dated records with approvals |
| Test results | Penetration test reports, DR test results, backup verification | Third-party reports |

## Output Format

Save to `outputs/compliance-assessment-[standard].md` with:

1. Scope definition table
2. Data inventory with classification
3. Controls assessment by framework area
4. Gap analysis table with risk scores
5. Prioritized remediation plan
6. Evidence inventory (what exists, what is missing)
7. Timeline to audit-readiness

## Do NOT
- Provide legal advice — flag ambiguous items for legal review with specific questions
- Assume that having a tool means having a control — a tool must be configured correctly AND its effectiveness must be demonstrated
- Skip evidence documentation — a control without evidence is the same as no control during an audit
- Assess compliance without a defined scope — scope creep during compliance work wastes effort
- Treat compliance as one-time — controls must operate continuously, and evidence must show ongoing effectiveness

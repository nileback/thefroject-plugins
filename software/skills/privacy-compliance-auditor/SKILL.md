---
name: privacy-compliance-auditor
description: Audit applications and data practices for privacy compliance (GDPR, CCPA, and general best practices). Use before launching features that collect personal data, during periodic compliance reviews, or when entering new markets.
triggers:
  - GDPR audit
  - privacy compliance
  - CCPA compliance
  - data privacy review
  - privacy audit
  - do we comply
allowed-tools: []
---

# Privacy Compliance Auditor

Audit data practices against privacy regulations. Produces a compliance gap analysis with specific remediation steps.

## Writes
- `outputs/privacy-audit-[date].md`

## Step 1: Data Inventory

Map what personal data exists:
- **What data is collected** — name, email, IP, cookies, device info, usage data, payment info
- **How it is collected** — forms, tracking, cookies, third-party SDKs, server logs
- **Where it is stored** — database, analytics service, email provider, CRM, logs
- **Who can access it** — team roles, third-party services, subprocessors
- **How long it is retained** — explicit retention periods or "forever by default"
- **Legal basis** — consent, contract, legitimate interest (GDPR requires one)

## Step 2: GDPR Checklist

| Requirement | Status | Notes |
|---|---|---|
| Privacy policy exists and is accessible | | |
| Legal basis documented for each processing activity | | |
| Consent is freely given, specific, informed, unambiguous | | |
| Consent can be withdrawn as easily as given | | |
| Data Subject Access Requests (DSAR) process exists | | |
| Right to deletion is implemented | | |
| Right to data portability is supported | | |
| Data Processing Agreements (DPA) with all subprocessors | | |
| Data breach notification process defined (72 hours) | | |
| Privacy by design in new features | | |
| DPIA (Data Protection Impact Assessment) for high-risk processing | | |
| Cookie consent banner with granular controls | | |
| No pre-checked consent boxes | | |
| Children's data handling (if applicable) | | |

## Step 3: Technical Controls

- Is personal data encrypted at rest?
- Is data transmitted over HTTPS only?
- Can specific user data be exported on request?
- Can specific user data be deleted on request (including backups)?
- Are access logs maintained for personal data?
- Is data minimization practiced (collecting only what is needed)?
- Are analytics anonymized where possible?

## Step 4: Third-Party Audit

For each third-party service that receives personal data:
- What data do they receive?
- Where are their servers located?
- Do they have a DPA available?
- Are they GDPR/CCPA compliant?
- What is their data retention policy?

## Step 5: Gap Report

For each gap found:
1. **Issue** — what is missing or non-compliant
2. **Risk** — legal exposure (fine, complaint, breach)
3. **Severity** — Critical (legal exposure now), High (compliance gap), Medium (best practice), Low (improvement)
4. **Remediation** — specific fix
5. **Owner** — who should fix it
6. **Timeline** — suggested deadline

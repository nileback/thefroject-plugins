---
name: risk-register-builder
description: Build and maintain an operational risk register with risk identification, assessment, mitigation planning, and monitoring. Use when establishing risk management, preparing for leadership reviews, or responding to emerging risks.
triggers:
  - risk register
  - risk assessment
  - risk management
  - operational risk
---

# Risk Register Builder

Identify and manage risks before they become incidents. A risk register is a living document that turns vague worries into concrete action plans.

## Input Required

1. **Business context** — industry, size, stage, regulatory environment (check `context/business-info.md`)
2. **Strategic priorities** — current goals and initiatives (check `context/strategy.md`)
3. **Previous incidents** — past issues that indicate risk areas
4. **Existing controls** — what risk management is already in place
5. **Stakeholder concerns** — what keeps leadership up at night

## Risk Identification

### Step 1 — Brainstorm by Category

| Category | Risk Areas to Consider |
|----------|----------------------|
| **Strategic** | Market shifts, competitive threats, failed initiatives, M&A risk |
| **Operational** | Process failures, system outages, supply chain, key person dependency |
| **Financial** | Cash flow, credit risk, currency exposure, cost overruns |
| **Compliance** | Regulatory changes, data privacy, labor law, audit findings |
| **Technology** | Security breaches, data loss, system obsolescence, vendor lock-in |
| **People** | Attrition, skills gaps, culture issues, leadership succession |
| **Reputational** | PR crisis, customer complaints, social media, partner failures |
| **External** | Economic downturn, pandemic, natural disaster, geopolitical |

### Step 2 — Risk Assessment Matrix

Score each risk on two dimensions:

**Likelihood (1-5):**
| Score | Definition | Frequency |
|-------|-----------|----------|
| 1 | Rare | Less than once per 5 years |
| 2 | Unlikely | Once per 2-5 years |
| 3 | Possible | Once per 1-2 years |
| 4 | Likely | Multiple times per year |
| 5 | Almost certain | Expected to occur |

**Impact (1-5):**
| Score | Definition | Financial | Operational |
|-------|-----------|----------|------------|
| 1 | Negligible | < $10K | No disruption |
| 2 | Minor | $10K-$50K | Hours of disruption |
| 3 | Moderate | $50K-$250K | Days of disruption |
| 4 | Major | $250K-$1M | Weeks of disruption |
| 5 | Severe | > $1M | Existential threat |

**Risk Score = Likelihood × Impact**

| Risk Score | Level | Action Required |
|-----------|-------|----------------|
| 20-25 | Critical | Immediate executive attention, active mitigation |
| 12-19 | High | Mitigation plan required, monthly review |
| 6-11 | Medium | Monitor and review quarterly |
| 1-5 | Low | Accept and review annually |

### Step 3 — Build the Register

| ID | Risk | Category | Likelihood | Impact | Score | Level | Owner | Mitigation | Status |
|----|------|----------|-----------|--------|-------|-------|-------|-----------|--------|
| R001 | [Description] | [Category] | [1-5] | [1-5] | [L×I] | [Level] | [Name] | [Plan] | [Open/Active/Mitigated] |

### Step 4 — Mitigation Planning

For each High and Critical risk:

| Element | Detail |
|---------|--------|
| **Risk ID** | [R00X] |
| **Risk description** | [Clear statement of what could go wrong] |
| **Root causes** | [What conditions enable this risk] |
| **Current controls** | [What is already in place] |
| **Residual risk** | [Score after current controls] |
| **Additional mitigation** | [What else should be done] |
| **Mitigation cost** | [Time, money, resources required] |
| **Target residual risk** | [Score after additional mitigation] |
| **Timeline** | [When will mitigation be complete] |
| **KRI (Key Risk Indicator)** | [What metric signals this risk is materializing] |

### Step 5 — Monitoring Plan

Define triggers that escalate a risk:

| Risk ID | KRI | Threshold | Current Value | Monitoring Frequency | Escalation Path |
|---------|-----|-----------|-------------|---------------------|----------------|
| R001 | [Metric] | [Trigger value] | [Current] | [Daily/Weekly/Monthly] | [Who to notify] |

## Output Format

Save to `reference/risk-register.md` (updated regularly):

```markdown
# Risk Register
**Last updated:** [Date] | **Next review:** [Date]

## Risk Summary
| Level | Count | Change Since Last Review |
|-------|-------|------------------------|
| Critical | [N] | [+/-] |
| High | [N] | |
| Medium | [N] | |
| Low | [N] | |

## Heat Map
[5x5 grid showing risk distribution]

## Full Register
[Complete table]

## Mitigation Plans (High and Critical)
[Detailed plans for each]

## Changes Since Last Review
[New risks, closed risks, score changes]
```

## Principles

- A risk register that is not reviewed regularly is just a document. Schedule recurring reviews (monthly for high risks, quarterly for all).
- Risk management is not risk elimination. Some risks are accepted. The goal is informed decision-making, not zero risk.
- The most dangerous risks are the ones nobody names. Create psychological safety for people to raise concerns.

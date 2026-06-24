---
name: risk-management-specialist
description: Build and run a cross-functional Enterprise Risk Management (ERM) program. Risk identification, scoring, treatment, monitoring, and reporting. More structured than risk-register-builder. For SOC 2-specific risk work pair with soc2-compliance.
triggers:
  - enterprise risk management
  - erm
  - risk register
  - risk framework
  - risk treatment plan
  - risk monitoring
---

# Risk Management Specialist

Run a cross-functional ERM program. The goal: leadership has a current view of the most material risks to the business and the actions being taken on each.

## Gather context

Ask if not provided:

1. **Org maturity** — first ERM effort, mature program, between iterations?
2. **Driver** — board mandate, audit finding, leadership initiative, certification requirement?
3. **Scope** — single business unit or enterprise-wide?
4. **Cadence** — quarterly is standard; some industries do monthly.
5. **Reporting audience** — board, exec team, regulator, all of the above?

## Risk categories

A working ERM categorizes risks across at least these areas:

### Strategic
- Market shifts.
- Competitive disruption.
- M&A failures.
- Geographic / regulatory expansion risks.

### Operational
- Process failures.
- Vendor / supplier disruption.
- Talent loss.
- Capacity / scaling issues.

### Financial
- Liquidity / runway.
- Currency / interest rate.
- Customer concentration.
- Credit exposure.

### Compliance / regulatory
- Privacy (GDPR, CCPA).
- Security (SOC 2, ISO 27001).
- Industry-specific (HIPAA, PCI, financial services).
- Tax positions.

### Reputational
- Public incidents.
- Customer or employee complaints going public.
- Founder / leadership behavior.
- Crisis communications.

### Cyber
- Breaches.
- Ransomware.
- Phishing / social engineering.
- Third-party data exposure.

Pick the categories relevant to the business and skip ones that don't apply.

## Risk scoring

Each risk gets:
- **Likelihood** (1-5 or low/medium/high).
- **Impact** (1-5 or low/medium/high).
- **Velocity** (how fast it could materialize — slow/medium/fast).
- **Inherent risk score** (likelihood × impact, before controls).
- **Residual risk score** (after current controls).
- **Acceptable threshold** (above which treatment is required).

Score on a heat map for visualization. Anything above the threshold drives action.

## Risk treatment

Four standard responses:
- **Treat** — implement controls to reduce.
- **Tolerate** — accept the risk; document why.
- **Transfer** — insurance, contractual.
- **Terminate** — stop the activity creating the risk.

Each above-threshold risk gets:
- A treatment decision.
- An owner.
- An action plan.
- A deadline.
- A review date.

## Workflow

### Step 1: Build the register
Pull risks from: leadership team interviews, function leaders, audit findings, near-miss / incident logs, peer benchmarks, regulator advisories.

Output: a register typically with 30-100 risks (most orgs).

### Step 2: Score
Apply the scoring framework. Plot on heat map.

### Step 3: Prioritize
Top 10-15 risks (by residual score) get active attention. The rest go to backlog with quarterly review.

### Step 4: Treat
Assign owners and treatment plans for active risks. Document acceptance for tolerated ones.

### Step 5: Monitor
For each active risk: leading indicators, monitoring frequency, escalation path.

### Step 6: Report
Monthly: top-10 risks dashboard for exec team.
Quarterly: full register review with leadership.
Annually: board-level risk summary.

### Step 7: Refresh
Quarterly: re-score active risks, identify new risks, retire resolved ones.

## Output

Save ERM artifacts to `outputs/erm/`:
- `risk-register.md` — complete register with category, score, owner, treatment, dates.
- `heat-map-<quarter>.md` — visualized scoring per quarter.
- `top-10-dashboard.md` — exec-level view.
- `risk-treatment-plans/` — folder of detailed plans for top risks.
- `incident-log.md` — actual incidents that materialized; ties to risks.

For board reporting: `outputs/erm/board-report-<quarter>.md` summarizing position and trend.

## Common mistakes

- Risk register that's mostly aspirational ("data breach"). Real risks are specific to your context.
- One-time exercise. Risk shifts; the register needs to shift too.
- No owner per risk. Unowned risks are unmanaged risks.
- No leading indicators. You only know the risk fired by looking at lagging data.
- Treating risk management as compliance theater. The point is making decisions; the artifact is just documentation.

## Cross-references

For tactical risk register building, use `risk-register-builder`. For SOC 2 risk work, use `soc2-compliance`. For ISO 27001 risk treatment, use `iso27001-isms`. For GDPR-specific privacy risks, use `gdpr-compliance`. For scenario-based stress testing, use `scenario-war-room`. For incident response when risks materialize, use `incident-responder`. For board reporting on risk, use `board-deck-builder` and `board-report-builder`.

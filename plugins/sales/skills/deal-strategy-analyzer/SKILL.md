---
name: deal-strategy-analyzer
description: Analyze active deals to assess health, identify risks, develop advancement strategies, and improve win probability. Use during pipeline reviews, deal coaching sessions, or when a deal is stalled.
triggers:
  - deal strategy
  - deal review
  - pipeline review
  - deal coaching
---

# Deal Strategy Analyzer

Evaluate deals with the same rigor an investor evaluates companies. Surface the risks, challenge the assumptions, and build a plan to win.

## Input Required

1. **Deal details** — company, opportunity value, stage, close date, product
2. **Buyer map** — contacts, roles, influence, sentiment
3. **Deal history** — meetings, emails, proposal status, objections raised
4. **Competitive landscape** — who else is being evaluated
5. **Decision criteria** — what the buyer says matters (check CRM notes)

## Deal Assessment

### Step 1 — MEDDPICC Qualification

| Element | Status | Evidence | Gap |
|---------|--------|---------|-----|
| **Metrics** | [What measurable outcome does the buyer want?] | [Confirmed by whom?] | [What is missing?] |
| **Economic Buyer** | [Name and title of the person who signs] | [Have you met them?] | |
| **Decision Criteria** | [What are they evaluating on?] | [Written or verbal?] | |
| **Decision Process** | [Steps, timeline, approvals required] | [Confirmed by whom?] | |
| **Paper Process** | [Legal, procurement, security review] | [Timeline known?] | |
| **Implicate Pain** | [What happens if they do nothing?] | [Quantified?] | |
| **Champion** | [Name — who is selling internally for you?] | [Have they proven access and influence?] | |
| **Competition** | [Who else is being evaluated?] | [Where do you stand?] | |

### Step 2 — Deal Health Score

| Factor | Score (1-5) | Notes |
|--------|-----------|-------|
| Champion strength | | [Can they mobilize internal support?] |
| Economic buyer access | | [Have you had a direct conversation?] |
| Pain clarity | | [Is the cost of inaction quantified?] |
| Decision timeline | | [Is there a compelling event driving urgency?] |
| Competitive position | | [Are you the front-runner?] |
| Value alignment | | [Does your solution map to their criteria?] |
| Buying process clarity | | [Do you know every step to close?] |
| Risk of no-decision | | [Could they decide to do nothing?] |

**Total: [X/40]**
- 32-40: Strong — execute the plan
- 24-31: Solid — address the gaps
- 16-23: At risk — needs intervention
- Below 16: Unlikely to close — qualify out or reset

### Step 3 — Stakeholder Analysis

| Name | Title | Role in Decision | Sentiment | Power | Last Contact | Next Action |
|------|-------|-----------------|-----------|-------|-------------|-------------|
| | | Champion/Influencer/Blocker/Decision Maker | Positive/Neutral/Negative | High/Med/Low | [Date] | [What to do] |

**Stakeholder coverage gaps:**
- [ ] Economic buyer met and engaged?
- [ ] Technical evaluator satisfied?
- [ ] Legal/procurement requirements known?
- [ ] Any unknown stakeholders who could block the deal?
- [ ] Coach identified (someone giving you inside information)?

### Step 4 — Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|-----------|
| Champion leaves or loses influence | | | |
| Budget gets cut or redirected | | | |
| Competitor undercuts on price | | | |
| Decision timeline slips | | | |
| Technical evaluation fails | | | |
| No-decision (do nothing) | | | |
| Scope changes mid-evaluation | | | |

### Step 5 — Win Plan

| Phase | Actions | Owner | Timeline | Success Criteria |
|-------|---------|-------|---------|-----------------|
| **This week** | | | | |
| **Next 2 weeks** | | | | |
| **Before close date** | | | | |

## Output Format

Save to `outputs/deal-strategy-[company]-[date].md`:

```markdown
# Deal Strategy — [Company]
**Value:** $[Amount] | **Stage:** [Stage] | **Close Date:** [Date] | **Health:** [X/40]

## Qualification Summary (MEDDPICC)
[One-line status for each element]

## Top 3 Risks
1. [Risk + mitigation]

## Win Plan
[Sequenced actions with owners and dates]

## Key Question for Next Meeting
[The single most important thing to learn]

## Forecast Assessment
[Commit / Best Case / Pipeline — with justification]
```

## Principles

- Challenge every assumption. "The champion says we are the front-runner" is not evidence. "The champion shared the internal evaluation scorecard and we lead in 4 of 5 criteria" is evidence.
- The most dangerous deal risk is the one nobody is discussing. Ask "what could kill this deal?" in every review.
- If you cannot articulate the buyer's compelling event, you do not have a timeline. You have a hope.

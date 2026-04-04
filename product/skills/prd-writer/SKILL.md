---
name: prd-writer
description: Write product requirements documents (PRDs) and feature specs. Use when defining new features, writing specs, or documenting product decisions.
triggers:
  - write PRD
  - product requirements
  - feature spec
---

# PRD Writer

Write PRDs that engineering can build from without ambiguity. A good PRD eliminates the need for follow-up clarification meetings.

## Before Writing

Gather these inputs before drafting:

1. **User research** — Check `context/` for user interviews, support tickets, or analytics that demonstrate the problem
2. **Strategic alignment** — How does this feature connect to current OKRs or roadmap themes?
3. **Existing solutions** — What do users do today to solve this problem? What competitors offer alternatives?
4. **Stakeholder input** — Engineering feasibility, design constraints, business priorities

## PRD Structure

### 1. Header
```
Feature: [Clear name]
Author: [Name]
Status: Draft / In Review / Approved
Created: [Date]
Last updated: [Date]
Target release: [Quarter or date]
```

### 2. Problem Statement (half page max)
Answer three questions:
- **What** is the user problem? (Describe the pain, not the solution)
- **Who** experiences it? (Specific persona, not "users")
- **Why now?** (What changed that makes this worth solving now — data, strategy shift, competitive pressure)

**Pattern:** "[Persona] struggles with [problem] when [context], which leads to [negative outcome]. Currently they [workaround]. This affects [X% of users / $Y revenue / Z key accounts]."

### 3. Goals and Non-Goals

**Goals** — Outcomes this feature must achieve. Use measurable language:
- "Reduce time-to-first-value from 14 days to 3 days for new enterprise accounts"
- "Increase self-service resolution rate from 30% to 60%"

**Non-goals** — Explicitly state what this feature will NOT do. Non-goals prevent scope creep during development:
- "This feature does NOT replace the existing admin panel"
- "We will NOT support offline mode in this iteration"

### 4. User Stories and Scenarios

For each persona affected, write stories using this format:
```
As a [persona],
I want to [action],
so that [outcome].

Acceptance criteria:
- Given [context], when [action], then [expected result]
- Given [edge case], when [action], then [graceful handling]
```

Include at minimum:
- The happy path (primary use case)
- 2-3 edge cases (error states, empty states, boundary conditions)
- The "power user" scenario (if applicable)

### 5. Requirements (MoSCoW)

| ID | Requirement | Priority | Acceptance Criteria |
|----|-----------|----------|-------------------|
| R1 | [Specific requirement] | Must | [Testable condition] |
| R2 | [Specific requirement] | Must | [Testable condition] |
| R3 | [Specific requirement] | Should | [Testable condition] |
| R4 | [Specific requirement] | Could | [Testable condition] |

**Priority definitions:**
- **Must** — Feature cannot ship without this. These define the MVP.
- **Should** — Important but can ship without it. Target for the initial release.
- **Could** — Desirable if time permits. Often becomes the fast-follow.
- **Won't (this time)** — Explicitly excluded from this scope. Record here to prevent re-discussion.

### 6. User Experience

Describe key interactions without prescribing visual design:

- **Entry points** — How does the user discover or access this feature?
- **Core flow** — Step-by-step description of the primary interaction
- **State transitions** — Empty state, loading state, success state, error state
- **Navigation** — Where does the user go after completing the action?

Include wireframes or mockups if available. Reference design files by path or link.

### 7. Technical Considerations

Provide context, not implementation decisions:

- **Dependencies** — Other features, services, or teams this depends on
- **Constraints** — Performance requirements, data limits, platform restrictions
- **Data** — New data models, schema changes, migration needs
- **API changes** — New endpoints, breaking changes, versioning implications
- **Security** — Authentication, authorization, data handling requirements
- **Analytics** — Events to track for measuring success metrics

### 8. Success Metrics

| Metric | Baseline | Target | Measurement Method | Timeframe |
|--------|----------|--------|-------------------|-----------|
| [Primary metric] | [Current value] | [Target value] | [How to measure] | [When to evaluate] |
| [Guardrail metric] | [Current value] | [Must not degrade] | [How to measure] | [Ongoing] |

### 9. Open Questions

| Question | Owner | Deadline | Impact if Unresolved |
|----------|-------|----------|---------------------|
| [Specific question] | [Name/Role] | [Date] | [What gets blocked] |

### 10. Launch Plan (brief)

- **Rollout strategy** — Big bang, percentage rollout, beta group?
- **Feature flag** — Yes/No, with kill criteria
- **Communication** — Who needs to know (support, sales, marketing)?
- **Documentation** — What user-facing docs need updating?

## Output Format

Save to `plans/prd-[feature-slug].md` with the full structure above.

## Do NOT
- Prescribe technical implementation — describe what, not how
- Write requirements without acceptance criteria — untestable requirements cause scope disputes
- Skip the non-goals section — this is the most effective tool against scope creep
- List requirements without priority — engineers need to know what to cut if time runs short
- Assume everyone knows the context — write as if the reader joined the team yesterday
- Leave open questions without owners and deadlines — unowned questions never get resolved

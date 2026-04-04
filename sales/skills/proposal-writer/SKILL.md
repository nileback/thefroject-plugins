---
name: proposal-writer
description: Write business proposals, RFP responses, and partnership pitches. Use when responding to opportunities, pitching partnerships, or seeking budget approval.
triggers:
  - write proposal
  - RFP response
  - business proposal
---

# Proposal Writer

Write proposals that win by being clear, specific, and focused entirely on the buyer's problem and desired outcome.

## Before Writing

Gather these inputs:

1. **Discovery notes** — What did the prospect say about their problem? Check `context/` for meeting notes or briefs
2. **Decision criteria** — What will they evaluate on? (price, timeline, expertise, methodology, team)
3. **Competition** — Are they comparing you to others? If so, what is your differentiation?
4. **Budget signal** — Any indication of budget range or approval process?
5. **Decision maker** — Who reads this proposal and who signs it? They may be different people

## Proposal Structure

### 1. Executive Summary (half page max)
This is the only section every stakeholder will read. Structure it as:

- **Sentence 1:** Restate their problem in their own language
- **Sentence 2:** State your proposed solution and the primary outcome
- **Sentence 3:** Timeline and investment range
- **Sentence 4:** Why you are the right partner (one specific proof point)

Write this section last, after the rest of the proposal is complete.

### 2. Understanding of the Problem (1 page)
Demonstrate that you listened. Mirror the language from the discovery call or brief.

**Pattern:**
- Current situation: [What is happening now]
- Impact: [What it costs them — revenue, time, risk, opportunity cost]
- Desired state: [Where they want to be]
- Gap: [What stands between current and desired]

Do NOT list your capabilities here. This section is entirely about them.

### 3. Proposed Solution (1-2 pages)
Describe what you will deliver, not how you will deliver it. Save methodology for the Approach section.

For each deliverable:
| Deliverable | Description | Timeline | Owner |
|------------|-------------|----------|-------|
| [Name] | [What they get] | [When] | [Your team / their team] |

### 4. Approach and Methodology (1-2 pages)
Now describe how you will deliver. Structure in phases:

**Phase 1: [Name]** (Weeks 1-N)
- Activities: [What happens]
- Milestones: [What marks completion]
- Their involvement: [What you need from them]
- Deliverables: [What they receive]

Repeat for each phase. Include a visual timeline if the engagement spans more than 4 weeks.

### 5. Team (half page)
Introduce only the people who will actually do the work. For each:
- Name, role on this project
- One sentence on relevant experience (specific to their problem, not a bio)

### 6. Proof Points (1 page)
Include 2-3 case studies that match their situation. Each case study follows:
- **Client:** [Industry/size, anonymized if needed]
- **Challenge:** [Similar to prospect's problem]
- **Solution:** [What you did]
- **Result:** [Quantified outcome]

### 7. Investment (1 page)
Present pricing with context:

| Component | Scope | Investment |
|-----------|-------|-----------|
| [Phase/Deliverable] | [What's included] | [Amount] |
| **Total** | | **[Amount]** |

**Include:**
- What is in scope and what is out of scope
- Payment terms and schedule
- Assumptions that could change the price
- Optional add-ons (gives them a sense of control)

### 8. Next Steps (half page)
Propose specific actions with dates:
1. "Review this proposal by [date]"
2. "30-minute Q&A call on [proposed date]"
3. "If approved, kickoff on [proposed date]"

Never end with "let us know" — always propose a specific next action.

## Writing Standards

- **Mirror their language** — Use the exact words and phrases from the brief or discovery call
- **Lead with outcomes** — "Reduce customer churn by 15%" not "Implement a retention platform"
- **Specific over vague** — "3-week sprint" not "rapid timeline." "$45,000" not "competitive pricing"
- **Active voice** — "We will deliver" not "The deliverables will be provided"
- **Short paragraphs** — 3-4 sentences max. Use bullet points for lists of 3+ items

## Output Format

Save to `outputs/proposal-[client-slug].md` with the full structure above. Target 5-8 pages total. Anything longer gets skimmed, not read.

## Do NOT
- Lead with company history or credentials — they care about their problem, not your story
- Use superlatives: "industry-leading," "best-in-class," "world-class"
- Present a single price without showing what is included and excluded
- Leave next steps vague — propose specific dates and actions
- Include case studies from unrelated industries when relevant ones exist
- Submit without proofreading the client's name, company name, and specific details — wrong names kill proposals

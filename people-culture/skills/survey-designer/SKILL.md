---
name: survey-designer
description: Design surveys and questionnaires for research, customer feedback, employee engagement, or market research. Covers question types, flow design, bias reduction, and analysis planning.
triggers:
  - design a survey
  - create questionnaire
  - survey questions
  - feedback survey
  - research survey
allowed-tools: []
---

# Survey Designer

Design effective surveys that produce reliable, actionable data. Every question must earn its place.

## Writes
- `outputs/survey-[name].md`

## Step 1: Define Objectives

Before writing questions:
1. **What decision will this data inform?** If you cannot answer this, the survey is premature.
2. **Who is the audience?** Sample size, access method, expected response rate.
3. **What do you already know?** Prior research, hypotheses, assumptions to test.

## Step 2: Question Design Rules

**Question types and when to use them:**

| Type | When | Example |
|---|---|---|
| Multiple choice | Predefined categories, easy analysis | "How did you hear about us?" |
| Likert scale (1-5/1-7) | Attitudes, satisfaction, agreement | "How satisfied are you with..." |
| Open text | Exploratory, "why" questions, quotes | "What would you change?" |
| Ranking | Relative priority among options | "Rank these features by importance" |
| Matrix | Multiple items on same scale | Satisfaction across 5 service areas |
| NPS (0-10) | Loyalty benchmark | "How likely to recommend?" |

**Bias reduction:**
- No leading questions ("Don't you agree that..." is leading)
- No double-barreled questions ("How satisfied are you with our speed and quality?" — split into two)
- Balanced scales (same number of positive and negative options)
- Include "Not applicable" or "Prefer not to answer" where relevant
- Randomize option order for multiple choice where appropriate
- Avoid acquiescence bias by mixing positively and negatively worded statements

## Step 3: Flow Design

1. **Opening** — easy, non-threatening questions (demographics or context)
2. **Core** — the questions that matter most, while attention is highest
3. **Sensitive** — personal or potentially uncomfortable questions later
4. **Closing** — open-ended "anything else?" and thank you

Keep under 15 questions for general surveys. Under 30 for in-depth research. Every question beyond 10 reduces completion rate.

## Step 4: Pre-launch Checklist

- [ ] Every question maps to a research objective
- [ ] No jargon the audience would not understand
- [ ] Mobile-friendly (no wide matrices on phone)
- [ ] Estimated completion time stated upfront
- [ ] Skip logic defined for conditional questions
- [ ] Analysis plan: know how you will use each answer before you ask

## Output

Deliver the complete survey with:
- Introduction text
- Questions numbered with type labels
- Skip logic notes
- Estimated completion time
- Suggested analysis approach for each question

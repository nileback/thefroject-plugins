---
name: employee-survey-analyst
description: Analyze employee engagement and pulse survey results to identify trends, surface insights, and build action plans. Use after running engagement surveys, pulse checks, or when preparing people strategy recommendations.
triggers:
  - survey analysis
  - engagement survey
  - pulse survey
  - employee feedback
---

# Employee Survey Analyst

Turn survey data into insight and action. Raw scores are meaningless without context, and insights are meaningless without follow-through.

## Input Required

1. **Survey results** — scores by question, category, and demographic cuts
2. **Response rate** — overall and by segment
3. **Previous survey results** — for trend comparison (check `outputs/` for prior analyses)
4. **Benchmark data** — industry or company size benchmarks (if available)
5. **Open-ended responses** — free text comments (often the most valuable data)

## Analysis Process

### Step 1 — Response Rate Assessment

| Segment | Invited | Responded | Rate | Concern? |
|---------|---------|----------|------|---------|
| Overall | | | | >70% = good, <50% = problem |
| [Department A] | | | | |
| [Department B] | | | | |
| [Tenure < 1 year] | | | | |
| [Tenure > 5 years] | | | | |
| [Management] | | | | |
| [Individual contributors] | | | | |

Low response rates in specific segments are findings in themselves. Why are people not responding?

### Step 2 — Category Scores

| Category | Score | Benchmark | vs. Last Survey | Trend | Priority |
|----------|-------|----------|----------------|-------|---------|
| Overall engagement | [X/5] | [Benchmark] | [+/-] | [↑/→/↓] | |
| Manager effectiveness | | | | | |
| Career development | | | | | |
| Compensation & benefits | | | | | |
| Work-life balance | | | | | |
| Belonging & inclusion | | | | | |
| Communication & transparency | | | | | |
| Role clarity | | | | | |
| Recognition | | | | | |
| Company direction | | | | | |

### Step 3 — Segment Analysis

Compare scores across meaningful cuts:

**By Department:**
| Department | Engagement | Manager | Career | Belonging | Flag |
|-----------|-----------|---------|--------|----------|------|
| [Dept A] | | | | | |
| [Dept B] | | | | | |

**By Tenure:**
| Tenure | Engagement | Manager | Career | Belonging | Flag |
|--------|-----------|---------|--------|----------|------|
| < 1 year | | | | | |
| 1-3 years | | | | | |
| 3-5 years | | | | | |
| 5+ years | | | | | |

**By Level:**
| Level | Engagement | Manager | Career | Belonging | Flag |
|-------|-----------|---------|--------|----------|------|
| IC | | | | | |
| Manager | | | | | |
| Director+ | | | | | |

Flag any segment where scores are >0.5 points below the company average.

### Step 4 — Driver Analysis

Identify which categories most strongly correlate with overall engagement:

| Category | Correlation with Engagement | Current Score | Priority |
|----------|--------------------------|-------------|---------|
| [Highest correlation] | [Strong/Medium/Weak] | [Score] | [Fix first — biggest ROI] |
| [Next] | | | |
| [Next] | | | |

Focus improvement efforts on categories that are both low-scoring AND high-impact on overall engagement.

### Step 5 — Open-Ended Response Themes

Analyze free text responses by clustering into themes:

| Theme | # Mentions | Sentiment | Representative Quotes | Category Link |
|-------|-----------|-----------|---------------------|-------------|
| [Theme 1] | [Count] | Positive/Mixed/Negative | "[Direct quote]" | [Survey category] |
| [Theme 2] | | | | |

### Step 6 — Action Planning

| Finding | Affected Segment | Root Cause Hypothesis | Action | Owner | Timeline | Success Metric |
|---------|-----------------|---------------------|--------|-------|---------|---------------|
| [Low career development in Dept B] | [Dept B, IC level] | [No clear promotion criteria] | [Document and communicate promotion paths] | [HR + Dept B lead] | [Q2] | [Career score +0.5 next survey] |

## Output Format

Save to `outputs/survey-analysis-[date].md`:

```markdown
# Employee Survey Analysis — [Date]

## Executive Summary
[3-4 sentences: response rate, overall engagement, biggest finding, recommended priority]

## Scorecard
| Category | Score | Trend | vs. Benchmark | Priority |
|----------|-------|-------|-------------|---------|

## Key Findings
1. [Finding + supporting data + impact]
2. [Finding + supporting data + impact]
3. [Finding + supporting data + impact]

## Segment Highlights
[Notable differences by department, tenure, or level]

## Action Plan
| Action | Owner | Timeline | Metric |
|--------|-------|---------|--------|

## Communication Plan
[How and when results will be shared with the organization]
```

## Principles

- Share results transparently, including uncomfortable findings. Employees who take time to respond deserve to see what you learned and what you will do about it.
- Do not survey more often than you can act. If the last survey's action items are not complete, running another survey signals that feedback does not lead to change.
- Scores are not the goal. Behavior change is the goal. A 4.2 that becomes a 4.3 means nothing if the underlying experience has not changed.

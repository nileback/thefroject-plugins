---
name: qualitative-analyst
description: Analyze qualitative data (interviews, open-ended responses, transcripts, notes) using thematic coding and pattern extraction. Use when you have unstructured text data and need to find patterns, themes, and insights.
triggers:
  - analyze qualitative data
  - thematic analysis
  - code these interviews
  - find patterns in responses
  - affinity mapping
allowed-tools: []
---

# Qualitative Analyst

Turn unstructured qualitative data into structured insights through systematic coding and thematic analysis.

## Writes
- `outputs/qualitative-analysis-[topic].md`

## Input

Accept any of:
- Interview transcripts
- Open-ended survey responses
- Field notes or observation logs
- Meeting transcripts
- Customer feedback text
- Forum posts or community discussions

## Step 1: Familiarization

Read all data end to end before coding. Note initial impressions:
- Recurring words or phrases
- Emotional intensity moments
- Surprising or contradictory statements
- Potential themes emerging

## Step 2: Open Coding

Go through the data line by line. Assign a short descriptive code to each meaningful segment. Codes should be:
- **Descriptive** — what is being said ("frustrated with setup process")
- **In vivo** where powerful — use the participant's exact words as the code
- **Granular** — do not merge different concepts into one code yet

Aim for 30-80 initial codes depending on data volume.

## Step 3: Axial Coding

Group related codes into categories. Look for:
- **Clusters** — codes that frequently co-occur
- **Hierarchies** — codes that are subcategories of broader concepts
- **Relationships** — causal, temporal, or conditional links between codes

Reduce to 8-15 categories.

## Step 4: Theme Development

Elevate categories into themes. A theme is a pattern of meaning that captures something important about the data in relation to the research question.

For each theme:
1. **Name** — a descriptive phrase (not a single word)
2. **Definition** — what this theme captures and what it does not
3. **Prevalence** — how many participants or data points reflect this theme
4. **Key quotes** — 2-3 verbatim quotes that best illustrate the theme
5. **Subthemes** — if the theme has meaningful internal variation

## Step 5: Synthesis

Write a narrative that:
- Presents themes in order of importance or logical flow
- Uses quotes to ground each theme in real data
- Notes where themes interact, reinforce, or contradict each other
- Identifies outliers and negative cases (data that does not fit the pattern)
- Connects findings to the original research question

## Output Format

```markdown
# Qualitative Analysis: [Topic]

## Method
[Data sources, sample size, coding approach]

## Themes
### Theme 1: [Name]
[Definition, prevalence, key quotes, subthemes]

### Theme 2: [Name]
...

## Theme Map
[Visual representation of how themes relate]

## Key Insights
[3-5 actionable takeaways]

## Limitations
[Sample size, selection bias, analyst interpretation]
```

---
name: literature-reviewer
description: Conduct structured literature reviews across academic papers, industry reports, and online sources. Use when building an evidence base for a decision, writing a research report, or mapping the state of knowledge on a topic.
triggers:
  - literature review
  - research review
  - systematic review
  - what does the research say
  - evidence review
allowed-tools: []
---

# Literature Reviewer

Conduct a structured review of available literature on a given topic. Produce a synthesis that maps what is known, what is debated, and what is missing.

## Writes
- `outputs/lit-review-[topic].md`

## Context Scan

Check `context/` and `outputs/` for existing research, prior reviews, or relevant background on this topic.

## Step 1: Define the Review Scope

Confirm with the user:
1. **Research question** — what specifically are you trying to answer?
2. **Scope boundaries** — time range, geography, industry, source types
3. **Depth** — rapid scan (10-15 sources) or comprehensive (30+)?

## Step 2: Search Strategy

Define search terms and sources:
- **Primary terms** — core keywords and their synonyms
- **Boolean combinations** — AND/OR groupings to narrow results
- **Sources to search** — academic databases, industry reports, reputable blogs, government publications

Use web search tools if available. If not, work from sources the user provides or general knowledge.

## Step 3: Screen and Categorize

For each source found:
- **Relevance** — does it address the research question directly?
- **Quality** — peer-reviewed > industry report > blog post > opinion
- **Recency** — newer is generally better unless historical context matters
- **Perspective** — note whether findings support, contradict, or add nuance

Categorize into: directly relevant, provides context, methodologically useful, or excluded (with reason).

## Step 4: Synthesize Findings

Organize by theme, not by source. For each theme:
1. **What the evidence says** — consensus view with strongest supporting sources
2. **Where sources disagree** — conflicting findings and possible explanations
3. **Strength of evidence** — strong (multiple quality sources), moderate (limited but credible), weak (anecdotal or single source)

## Step 5: Gap Analysis

Identify:
- Questions the literature does not answer
- Areas where evidence is thin or outdated
- Methodological limitations across studies
- Suggestions for primary research to fill gaps

## Output Format

```markdown
# Literature Review: [Topic]

## Research Question
[The question this review answers]

## Key Findings
[3-5 bullet summary of the most important takeaways]

## Thematic Analysis
### [Theme 1]
[Synthesis of findings, with citations]

### [Theme 2]
...

## Evidence Gaps
[What remains unanswered]

## Sources
[Numbered list with author, title, year, source type, and relevance rating]
```

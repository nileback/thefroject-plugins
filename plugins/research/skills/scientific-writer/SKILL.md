---
name: scientific-writer
description: Write and edit research papers, literature reviews, technical reports, and white papers with academic rigor. Use for research documentation, grant proposals, or technical publications.
triggers:
  - research paper
  - literature review
  - technical report
---

# Scientific Writer

Write research that is rigorous, clear, reproducible, and properly structured. Every claim must be supported by evidence or citation.

## Document Types and Structures

### Research Paper (IMRaD)
| Section | Purpose | Typical Length |
|---------|---------|---------------|
| **Abstract** | Complete summary: problem, method, key findings, implication | 150-300 words |
| **Introduction** | Problem statement, motivation, research question, contribution | 1-2 pages |
| **Related Work** | Positioning within existing research, identifying the gap | 1-3 pages |
| **Methods** | Approach, data, experimental setup (must be reproducible) | 2-4 pages |
| **Results** | Findings with tables, figures, statistical tests | 2-4 pages |
| **Discussion** | Interpretation, limitations, implications, future work | 1-3 pages |
| **Conclusion** | Summary of contributions (no new information) | 0.5-1 page |

### Literature Review
| Section | Purpose |
|---------|---------|
| **Introduction** | Scope, research questions guiding the review, methodology for paper selection |
| **Thematic sections** | Organized by theme (not by paper). Each theme synthesizes findings across multiple sources |
| **Synthesis** | Patterns, contradictions, and gaps across the literature |
| **Research agenda** | Open questions and recommended future directions |

### White Paper / Technical Report
| Section | Purpose |
|---------|---------|
| **Executive summary** | Key findings and recommendations for decision-makers |
| **Problem statement** | What challenge this report addresses |
| **Methodology** | How the investigation was conducted |
| **Findings** | Organized by theme with supporting data |
| **Recommendations** | Actionable next steps with justification |
| **Appendices** | Raw data, detailed methodology, supplementary analysis |

### Grant Proposal
| Section | Purpose | Key Question |
|---------|---------|-------------|
| **Specific aims** | What you will accomplish | "What and why?" |
| **Significance** | Why it matters | "So what?" |
| **Innovation** | What is new | "Why hasn't this been done?" |
| **Approach** | How you will do it | "How, specifically?" |
| **Timeline and budget** | Resources needed | "How much and how long?" |

## Writing Process

### Phase 1 — Outline
Write the outline before any prose. Each section header should be a complete sentence stating the section's argument:

**Bad header:** "Data Collection"
**Good header:** "Survey of 2,400 developers reveals three distinct adoption patterns"

### Phase 2 — Figures and Tables First
Design key figures and tables before writing the text that references them. The paper's argument should be followable from figures and tables alone.

**Table design rules:**
- Every table has a caption that makes it self-contained
- Row and column headers are unambiguous
- Units are included in headers, not repeated in cells
- Bold or highlight the key result
- Include sample sizes (N) for all statistical measures

**Figure design rules:**
- Axes are labeled with units
- Legends are readable at print size
- Color is not the only differentiator (use shapes, patterns for accessibility)
- Error bars or confidence intervals are shown for all measurements

### Phase 3 — First Draft
Write sections in this order (not the order they appear in the paper):
1. Methods (most concrete, easiest to write)
2. Results (describe what you found)
3. Discussion (interpret the results)
4. Introduction (now you know what the paper says)
5. Abstract (now you can summarize it)
6. Related Work (position against what you now cite)

### Phase 4 — Revision

**Clarity checklist:**
- [ ] Every paragraph has one main idea, stated in the first sentence
- [ ] Every claim is supported by evidence (data, citation, or logical argument)
- [ ] Technical terms are defined on first use
- [ ] Abbreviations are spelled out on first use
- [ ] No sentence exceeds 30 words (aim for 15-20 average)
- [ ] Active voice is used where possible: "We measured..." not "Measurements were taken..."

**Rigor checklist:**
- [ ] Statistical tests are appropriate for the data type and distribution
- [ ] Effect sizes are reported alongside p-values
- [ ] Confidence intervals are provided for key measurements
- [ ] Correlation is not presented as causation
- [ ] Limitations are stated honestly and prominently
- [ ] Alternative explanations for findings are acknowledged

## Citation Standards

Default to author-year (APA) style unless the venue specifies otherwise:

**In-text:** (Smith & Jones, 2024) or Smith and Jones (2024) found...
**Reference list:** Smith, A. B., & Jones, C. D. (2024). Title of paper. *Journal Name*, 42(3), 15-28. https://doi.org/10.xxxx

**Citation rules:**
- Every factual claim needs a citation unless it is common knowledge in the field
- Cite primary sources, not summaries or reviews (unless reviewing the review itself)
- Include DOI or stable URL for every reference
- Use "et al." for 3+ authors after first mention
- Distinguish between "Smith (2024) found X" (paraphrase) and "X occurs in Y contexts (Smith, 2024)" (citation support)

## Common Pitfalls

| Pitfall | Example | Fix |
|---------|---------|-----|
| Hedging without reason | "It might possibly suggest..." | State clearly or explain the uncertainty |
| Overclaiming | "This proves that..." | "This provides evidence that..." |
| Correlation as causation | "X causes Y" (from observational data) | "X is associated with Y" |
| Survivorship bias | Studying only successful projects | Acknowledge sample limitations |
| Citation stacking | "(A; B; C; D; E; F; G)" | Cite the most relevant 2-3, note "see also" for others |
| Jargon creep | Using field-specific terms without definition | Define on first use or avoid |

## Output Format

Save to `outputs/[document-type]-[topic-slug].md` with:

- Full document in the appropriate structure
- Inline citation markers using [Author, Year] format
- Reference list at the end with complete bibliographic information
- Figures and tables described in text with `[FIGURE: description]` and `[TABLE: description]` markers for placement

For LaTeX output, wrap content in appropriate environments and use `\cite{}` and `\ref{}` markers.

## Do NOT
- Make claims without evidence — every assertion needs a citation or data point
- Cherry-pick results that support a narrative — report all findings, including null results
- Use unnecessarily complex language — clarity is a virtue, not a weakness
- Skip the limitations section — every study has limitations, and acknowledging them strengthens credibility
- Present exploratory findings as confirmatory — clearly label post-hoc analyses
- Plagiarize — all text must be original. Paraphrase and cite, or quote directly with attribution

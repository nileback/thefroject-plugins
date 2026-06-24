---
name: interview-designer
description: Design structured interview processes with competency-based questions and scorecards.
triggers:
  - design interview
  - interview questions
  - interview loop design
---

# Interview Designer

Design structured interview processes that are fair, consistent, and predictive of on-the-job performance.

## Phase 1 — Competency Mapping

Extract 4-6 competencies directly from the job description and team needs:

1. Read the job description in `outputs/` or ask for the role details
2. Identify the core competencies — skills and behaviors that differentiate top performers in this specific role
3. Classify each competency:
   - **Technical** — Domain skills that can be assessed through exercises or questions
   - **Behavioral** — Past behavior patterns that predict future performance
   - **Cognitive** — Problem-solving approach, learning agility, analytical thinking
   - **Collaboration** — Communication style, conflict resolution, influence

For each competency, define:
| Competency | Weight | Assessment Method | Interview Stage |
|-----------|--------|-------------------|----------------|
| [Name] | [1-5] | Behavioral / Technical / Exercise | [Which round] |

## Phase 2 — Interview Loop Design

Structure the interview as a series of stages, each with a clear purpose:

### Stage Architecture
| Stage | Duration | Format | Assessor | Competencies Covered |
|-------|----------|--------|----------|---------------------|
| Recruiter screen | 30 min | Phone/Video | Recruiter | Role fit, logistics, motivation |
| Hiring manager screen | 45 min | Video | HM | Technical depth, team fit, career goals |
| Technical/functional | 60 min | Exercise + discussion | Domain expert | Core technical competencies |
| Cross-functional | 45 min | Behavioral interview | Peer from adjacent team | Collaboration, communication |
| Leadership (senior roles) | 45 min | Case discussion | Skip-level leader | Strategic thinking, influence |

**Rules for loop design:**
- Each competency must be assessed by at least 2 interviewers across different stages
- No stage should assess more than 3 competencies (focus degrades)
- Total candidate time should not exceed 4 hours across all stages
- Include a break of at least 15 minutes between back-to-back interviews

## Phase 3 — Question Design

For each competency, write questions using the STAR-L framework (Situation, Task, Action, Result, Learning):

### Behavioral Questions (past behavior)
**Pattern:** "Tell me about a time when [specific situation relevant to the competency]."

For each question, prepare:
- **Primary question** — The main prompt
- **Probe 1** — "What was your specific role?" (isolates individual contribution)
- **Probe 2** — "What was the outcome?" (forces concrete results)
- **Probe 3** — "What would you do differently?" (reveals self-awareness)

### Situational Questions (hypothetical)
**Pattern:** "Imagine you're in [realistic scenario for this role]. Walk me through your approach."

Use situational questions only when the candidate may lack directly relevant past experience (career changers, junior roles).

### Technical Questions
- Tie to real work the candidate would do in the first 90 days
- Provide context and constraints, not trick questions
- Allow multiple valid approaches — assess reasoning, not a specific answer

## Phase 4 — Scorecard Design

Build a scorecard for each interview stage:

### Rating Scale (1-4, no middle option to force a lean)
| Rating | Label | Definition |
|--------|-------|-----------|
| 1 | Does not meet | Did not demonstrate the competency. Could not provide relevant examples. |
| 2 | Partially meets | Showed some evidence but with significant gaps or only in simple contexts. |
| 3 | Meets | Clear, specific examples with good outcomes. Would perform well in this role. |
| 4 | Exceeds | Exceptional examples showing leadership, innovation, or outsized impact in this area. |

Each competency on the scorecard includes:
- The competency name and brief description
- The rating scale with role-specific anchors
- Space for evidence notes (interviewers must cite specific candidate statements)
- Red flags to watch for (e.g., cannot describe personal contribution, blames others)

## Phase 5 — Debrief Template

Create a structured debrief format:

1. **Independent scoring** — All interviewers submit scorecards before the debrief meeting
2. **Round-robin** — Each interviewer shares their top-line assessment (2 min each, no interrupting)
3. **Discuss divergences** — Focus on competencies where scores differ by 2+ points
4. **Decision framework** — Hire / No hire / Need more signal. Require majority on each must-have competency
5. **Document the decision** — Record the rationale, not just the outcome

## Output Format

Save to `outputs/interview-design-[role-slug].md` with:

- Competency matrix with weights
- Interview loop structure (stages, timing, assessors)
- Full question bank (2-3 questions per competency with probes)
- Scorecard template for each stage
- Debrief template
- Interviewer prep checklist

## Do NOT
- Use brainteasers or puzzle questions — they measure preparation, not job performance
- Design questions that favor a specific demographic or background
- Allow unstructured "culture fit" conversations — define the behaviors you are actually assessing
- Let interviewers see each other's scores before the debrief
- Assess the same competency in every stage — distribute across the loop
- Skip calibration — train interviewers on the scorecard before they use it

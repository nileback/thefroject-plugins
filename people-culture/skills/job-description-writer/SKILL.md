---
name: job-description-writer
description: Write clear, inclusive job descriptions that attract the right candidates.
triggers:
  - job description
  - write job post
  - write job description
---

# Job Description Writer

Write job posts that attract qualified, diverse candidates and set honest expectations about the role.

## Before Writing

Gather these inputs before drafting:

1. **Hiring manager interview** — What problem does this hire solve? What does "great" look like at 3, 6, and 12 months?
2. **Team context** — Who will this person work with? What's the team's current gap?
3. **Level calibration** — Junior/Mid/Senior/Staff? Map to the company's leveling framework
4. **Compensation band** — Get the approved range before writing. Always include it.
5. **Dealbreakers vs. teachables** — Separate true requirements from skills the person can learn on the job

## Job Description Structure

### 1. Title (1 line)
Use standard industry titles. A candidate should understand the role from the title alone.

**Good:** Senior Backend Engineer, Product Marketing Manager, Customer Success Lead
**Bad:** Marketing Ninja, Code Wizard, Chief Happiness Officer, "Senior" with junior responsibilities

### 2. Opening Hook (2-3 sentences)
Answer: "Why would someone leave their current job for this one?" Lead with the mission or impact, not the company bio.

**Pattern:** [What the team/product does] + [Why this role matters right now] + [What makes it interesting]

### 3. What You Will Do (5-7 bullets)
Each bullet follows the pattern: **[Action verb]** + [what] + [impact/context]

- Start with the highest-impact responsibilities
- Use present tense, active voice
- Describe outcomes, not just activities: "Reduce deploy time by designing CI/CD pipelines" not "Work on CI/CD"
- Include collaboration patterns: "Partner with design to..." tells the candidate about the work style

### 4. What You Bring (two sections)

**Requirements (5 max):**
- Only list genuine dealbreakers — skills the person must have on day one
- Use "X years of experience with Y" sparingly. Prefer demonstrated ability over years
- Avoid credential inflation: do not require a degree unless the role legally requires one

**Nice-to-haves (3-4 max):**
- Skills that accelerate ramp-up but are not required
- Label these clearly so candidates do not self-select out

### 5. What We Offer (4-6 bullets)
- Compensation range (required — omitting it reduces applicant volume by 20-40%)
- Benefits highlights (not the full list — link to a benefits page)
- Growth and learning opportunities specific to this role
- Work arrangement: remote, hybrid, on-site — be explicit

### 6. How to Apply (1-2 sentences)
One clear action. Remove friction: "Apply at [link]" beats "Send your resume, cover letter, three references, and a portfolio to..."

## Inclusive Language Checklist

Run every draft through these checks:

- **Gender** — No gendered pronouns for the candidate. Use "you" and "they." Avoid "he/she"
- **Coded language** — Remove words that research shows skew gendered: "aggressive," "dominant," "nurturing." Use tools like Textio or the Gender Decoder
- **Age bias** — "Digital native," "young and hungry," or "10+ years experience" for a mid-level role all signal age bias
- **Ability bias** — Avoid "must be able to lift 50 lbs" unless physical requirements are genuine and essential
- **Cultural bias** — "Culture fit" is vague. Describe specific values and behaviors instead
- **Jargon** — Avoid internal acronyms and tool-specific jargon unless the tool IS the job

## Output Format

Save to `outputs/jd-[role-slug].md` with:

- The complete job description in the structure above
- A metadata header: role title, level, team, location, compensation range, hiring manager
- Word count target: 400-600 words (shorter posts consistently get more applicants)

## Do NOT
- Use superlatives: "best team," "world-class," "cutting-edge technology"
- List more than 5 hard requirements — every additional requirement reduces the applicant pool, especially among underrepresented groups
- Write a company bio paragraph before the role description — lead with the role
- Use "fast-paced environment" as a selling point without saying what that actually means
- Require cover letters unless someone will actually read them
- Copy-paste from another JD without adapting to this specific role and team

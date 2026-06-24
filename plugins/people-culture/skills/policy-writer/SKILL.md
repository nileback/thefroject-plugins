---
name: policy-writer
description: Draft company policies, employee handbooks, and compliance documentation.
triggers:
  - write policy
  - company policy
  - employee handbook
---

# Policy Writer

Write policies that people actually read, understand, and follow. Prioritize clarity over legal formality.

## Before Writing

Gather these inputs:

1. **Policy trigger** — What event or need prompted this policy? (incident, growth stage, compliance requirement, employee request)
2. **Existing documentation** — Check `context/` and `reference/` for related policies or standards already in place
3. **Stakeholders** — Who needs to review: legal, HR, affected teams, leadership?
4. **Jurisdiction** — Which employment laws or regulations apply? (varies by country, state, and industry)

## Policy Document Structure

### 1. Header Block
```
Policy: [Clear, specific name]
Version: [X.Y]
Effective: [Date]
Last reviewed: [Date]
Owner: [Role, not person name]
Approved by: [Role]
```

### 2. Purpose (2-3 sentences max)
Answer: "Why does this policy exist and what does it protect?" One sentence on the problem, one on the intent.

**Good:** "This policy ensures all employees can take time off to recover from illness without financial penalty. It applies to all full-time and part-time employees."
**Bad:** "In accordance with applicable labor regulations and organizational best practices, the Company hereby establishes the following comprehensive sick leave framework..."

### 3. Scope
Define precisely:
- **Who** — All employees? Specific departments? Contractors? Interns?
- **When** — Always applicable? During specific situations? After a certain tenure?
- **Where** — All locations? Specific jurisdictions? Remote vs. on-site?

### 4. Policy Statement
The actual rules. Use numbered items for sequential requirements, bullets for lists.

**Writing rules for rules:**
- One requirement per sentence
- Use "must" for mandatory items, "should" for recommendations, "may" for permissions
- Define every term that could be ambiguous
- Include the "why" after each rule — people comply more when they understand the reason

### 5. Procedures
For each common scenario, provide step-by-step instructions:

**Pattern:**
| Step | Action | Who | Timeline |
|------|--------|-----|----------|
| 1 | [What to do] | [Role] | [When] |
| 2 | [What to do] | [Role] | [When] |

### 6. Examples
Include 2-3 concrete examples showing how the policy applies in realistic situations. Cover:
- A straightforward case (clear compliance)
- An edge case (where judgment is needed)
- A violation example (what NOT to do and the consequence)

### 7. Exceptions Process
- Who can request an exception
- Who approves exceptions (and the backup approver)
- How to document the exception
- Maximum duration before re-review

### 8. Consequences
State consequences clearly and proportionally. Use progressive discipline where appropriate:
- First occurrence: [action]
- Repeated occurrence: [action]
- Severe violation: [action]

### 9. Related Policies
Link to other policies this one interacts with or depends on.

## Readability Standards

- **Reading level** — Write at a 9th-grade level (Flesch-Kincaid grade 9 or lower). Use Hemingway Editor or similar tool to verify
- **Sentence length** — Average 15-20 words per sentence. Break up anything over 30 words
- **Formatting** — Use headers, bullets, and tables. No wall-of-text paragraphs. Bold key terms on first use
- **Tone** — Authoritative but human. "You must notify your manager within 24 hours" not "Personnel shall be required to provide notification to their direct supervisory authority"

## Review Cycle

Every policy should have a review schedule:
| Policy type | Review frequency | Trigger for ad-hoc review |
|------------|-----------------|--------------------------|
| Employment/HR | Annually | Law change, incident |
| Security | Semi-annually | Breach, new threat |
| Operational | Annually | Process change |
| Financial | Annually | Audit finding |

## Output Format

Save to `outputs/policy-[slug].md` with the full document structure above. Include a changelog section at the bottom tracking version history.

## Do NOT
- Use legal jargon when plain language works — this is a policy, not a contract
- Write rules without stating the consequence of violation
- Create policies for problems that can be solved with a conversation
- Copy policies from other companies without adapting to the actual org context
- Omit the review date — stale policies are worse than no policy
- Mix policy (what) with procedure (how) in the same section — keep them separate

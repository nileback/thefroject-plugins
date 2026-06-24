---
name: sop-writer
description: Create clear standard operating procedures for repeatable business processes.
triggers:
  - write SOP
  - standard operating procedure
  - document process
---

# SOP Writer

Document processes so clearly that a new team member can follow them on their first day without asking questions.

## Before Writing

1. **Observe the process** — Read any existing documentation in `context/` or `reference/`. Ask the process owner to walk through the steps as they actually happen (not as they think they should happen)
2. **Identify the audience** — Who will follow this SOP? What can you assume they already know?
3. **Define the boundary** — Where does this SOP start and end? What processes does it connect to?

## SOP Document Structure

### Header Block
```
SOP: [Clear, specific title]
ID: [SOP-DEPT-NNN]
Version: [X.Y]
Effective: [Date]
Owner: [Role responsible for maintaining this SOP]
Last tested: [Date someone followed it literally]
```

### Purpose (2-3 sentences)
Answer two questions:
- What process does this SOP cover?
- Why does this process matter? (What breaks if it is done wrong?)

### Scope and Triggers
- **When to use:** The specific event or condition that triggers this process
- **When NOT to use:** Common situations that look similar but require a different process
- **Frequency:** How often this process runs (daily, per-event, monthly)

### Prerequisites Checklist
List everything needed before starting. Use a checkbox format:

- [ ] Access to [system/tool] with [permission level]
- [ ] [Input data/document] from [source]
- [ ] [Approval/sign-off] from [role]
- [ ] Estimated time: [X minutes/hours]

### Procedure Steps

Follow these rules for every step:

**One action per step.** If a step contains "and," split it into two steps.

**Step format:**
```
Step [N]: [Action verb] + [what] + [where]
   Expected result: [What you should see after completing this step]
   Note: [Any context that prevents mistakes]
```

**Decision points** — Use clear branching:
```
Step 5: Check [condition]
   → If YES: Continue to Step 6
   → If NO: Go to Step 5a
   Step 5a: [Alternative action]
   → Then continue to Step 6
```

**Verification checkpoints** — Insert a checkpoint after every critical step:
```
✓ CHECKPOINT: [What to verify before proceeding]
```

### Expected Outcome
Describe exactly what "done" looks like:
- What has changed in the system?
- What artifact has been produced?
- Who needs to be notified?
- What is the next process in the chain?

### Troubleshooting Matrix

| Symptom | Likely Cause | Fix | Escalation |
|---------|-------------|-----|-----------|
| [What you see] | [Why it happens] | [How to fix] | [Who to contact if fix fails] |

Include the 3-5 most common issues. Add to this section every time someone encounters a new problem.

### Revision History
| Version | Date | Author | Change |
|---------|------|--------|--------|
| 1.0 | [Date] | [Name] | Initial version |

## Quality Criteria

Before publishing, verify:

1. **The "stranger test"** — Could someone with no context follow every step? If any step requires tribal knowledge, add that knowledge to the SOP
2. **No ambiguity** — Every step uses a specific action verb. "Handle the request" is ambiguous. "Forward the request to the #support channel in Slack" is specific
3. **No assumptions** — If a step requires navigating to a URL, include the URL. If it requires clicking a button, describe where the button is
4. **Escape hatches** — Every decision point has a path for "none of the above" or "I'm not sure"
5. **Tested** — Someone other than the author has followed the SOP literally and confirmed it works

## Output Format

Save to `outputs/sop-[process-slug].md` with the full structure above.

For processes with UI interactions, add a companion section noting where screenshots should be inserted (mark with `[SCREENSHOT: description of what to capture]`).

## Do NOT
- Combine multiple actions into a single step
- Use vague verbs: "handle," "process," "manage," "deal with"
- Assume the reader knows where to find things — include paths, URLs, and navigation instructions
- Skip the troubleshooting section — if a process can fail, document how
- Write the SOP from memory without observing the actual process
- Publish without testing — an untested SOP is worse than no SOP

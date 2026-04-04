---
name: discussion-responder
description: Draft contextual, helpful replies to GitHub issues, discussions, and community questions by reading the thread, checking relevant code and docs, and composing a response. Use when you need to respond to community questions or issues.
triggers:
  - respond to issue
  - draft reply
  - community response
---

# Discussion Responder

Draft a reply to a community discussion, issue, or question. The response must be helpful, specific, and grounded in the actual codebase and documentation.

## Phase 1 — Read the Thread

1. Read the entire conversation thread, not just the latest message.
2. Identify what is being asked or reported:
   - **Bug report:** Specific problem with reproduction steps
   - **Feature request:** Something the user wants to exist
   - **Question:** How to do something or why something works a certain way
   - **Discussion:** Open-ended topic seeking input
3. Note the emotional tone. Is the person frustrated, confused, curious, or enthusiastic?
4. Identify any previous responses and whether they addressed the issue.

## Phase 2 — Research the Answer

Based on the type of discussion:

### For Bug Reports
1. Search the codebase for the relevant code path.
2. Try to reproduce the issue based on the reported steps.
3. Check if the issue exists in the latest version.
4. Look for related issues or PRs that may have already addressed this.
5. Determine: confirmed bug, works as designed, cannot reproduce, or needs more information.

### For Feature Requests
1. Check if the feature already exists (possibly under a different name).
2. Check if there is a related open issue or PR.
3. Review the roadmap or plans/ directory for related planned work.
4. Assess feasibility: quick win, medium effort, or significant undertaking.

### For Questions
1. Find the relevant documentation or code.
2. Check if this is covered in existing docs, FAQ, or past discussions.
3. Prepare a clear answer with code examples if applicable.
4. Link to relevant documentation.

### For Discussions
1. Understand the context and different perspectives shared so far.
2. Check if there are relevant design decisions documented in context/.
3. Prepare a balanced response that acknowledges different viewpoints.

## Phase 3 — Draft the Response

### Structure
1. **Acknowledge.** Show you read and understood the message. One sentence.
2. **Answer.** Provide the substantive response. Be specific.
3. **Evidence.** Link to relevant code, docs, or examples.
4. **Next step.** Tell them what to do next (try this, update to version X, open a PR, etc.).

### Tone Guidelines
- **Helpful, not defensive.** Even if the reporter is wrong, guide them gently.
- **Specific, not generic.** Reference their exact situation, not boilerplate advice.
- **Concise.** Respect their time. Get to the answer quickly.
- **Appreciative.** Thank bug reporters and feature requesters. They are helping.

### Response Templates by Type

**Bug — Confirmed:**
> Thanks for the detailed report. This is a confirmed bug in [component]. The issue is [brief explanation]. A fix is in progress / tracked in #[issue]. As a workaround, you can [workaround].

**Bug — Cannot Reproduce:**
> Thanks for reporting this. I was not able to reproduce the issue with [version/environment]. Could you share [specific missing info]? That will help narrow down the cause.

**Bug — Works as Designed:**
> Thanks for raising this. The current behavior is intentional because [reason]. I understand it may be unexpected. If you have a use case that would benefit from a different behavior, we can discuss it as a feature request.

**Feature — Positive:**
> Great suggestion. This aligns with [planned work / existing direction]. I have added it to [milestone/backlog]. If you are interested in contributing, [entry point for a PR].

**Feature — Needs Discussion:**
> Interesting idea. Before we commit to an approach, it would help to understand [questions about use case, scope, or tradeoffs]. What does your ideal version of this look like?

**Question — Has Answer:**
> Good question. You can do this by [specific steps]. Here is the relevant documentation: [link]. The key concept is [brief explanation].

## Output

Present the draft response with:
1. **Context:** What the thread is about (one line)
2. **Type:** Bug / Feature / Question / Discussion
3. **Draft Response:** The actual text to post
4. **Confidence:** High / Medium / Low (based on how certain the answer is)
5. **References:** Links to code, docs, or issues used

## Do NOT
- Post the response without user review — always present as a draft
- Be dismissive of user reports, even if they seem trivial
- Promise timelines or features without confirming with the team
- Copy-paste generic responses — every reply must reference the specific thread
- Ignore previous responses in the thread — acknowledge and build on them

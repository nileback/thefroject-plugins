---
name: mom-test-interviewer
description: Design and debrief customer validation interviews using Rob Fitzpatrick's Mom Test principles. Use when preparing for discovery calls, evaluating interview notes, or planning customer research.
triggers:
  - mom test
  - customer interview
  - customer validation
  - discovery interview
---

# Mom Test Interviewer

The Mom Test is a set of rules for crafting questions that even your mom cannot lie to you about. The core idea: talk about their life, not your idea. Ask about specifics in the past, not opinions about the future.

## Three Rules of the Mom Test

1. **Talk about their life, not your idea.** Bad: "Would you use a tool that does X?" Good: "How do you currently handle X?"
2. **Ask about specifics in the past, not generics or opinions.** Bad: "How often would you use this?" Good: "When was the last time you dealt with this? Walk me through it."
3. **Talk less, listen more.** You should be listening 80% of the time. If you are pitching, you are not learning.

## Phase 1 — Prepare the Interview Guide

### Define Learning Goals (max 3)
What do you need to learn that you cannot learn from data or observation alone?

| Goal | Why it matters | What would change your plan |
|------|---------------|---------------------------|
| [learning goal] | [decision it informs] | [what you would do differently] |

### Write Questions

Transform each learning goal into questions that follow the Mom Test:

**Good question patterns:**
- "Tell me about the last time you [problem area]..."
- "What happened? Walk me through it."
- "What did you do next?"
- "How are you dealing with this today?"
- "What have you tried? Why did you stop?"
- "How much time/money does this cost you?"
- "Who else should I talk to about this?"

**Bad question patterns (avoid these):**
- "Would you use...?" (hypothetical)
- "Do you think it's a good idea to...?" (opinion)
- "How much would you pay for...?" (fantasy pricing)
- "Would you recommend this to a friend?" (social pressure)
- "What features would you want?" (designing for you)

### Identify Danger Signals

Watch for these during the conversation — they mean you are getting bad data:

| Signal | What it means | What to do |
|--------|--------------|------------|
| Compliments ("That's a great idea!") | Politeness, not validation | Deflect: "Thanks — but tell me how you handle this today" |
| Hypotheticals ("I would definitely...") | Fantasy, not commitment | Anchor: "When was the last time you actually...?" |
| Generic claims ("Everyone hates...") | Vague, unverifiable | Specifics: "Can you give me a concrete example?" |
| Feature requests ("It should also...") | Designing for you | Motivation: "Why? What are you trying to do?" |

## Phase 2 — Debrief the Interview

After the conversation, extract signal:

### Facts (what actually happened)
- Specific behaviors, actions, and events the person described
- Money or time they spent on the problem
- Tools or workarounds they currently use
- Who else is involved in the problem

### Commitments (strongest signal)
Did they offer something concrete?
- Time: "I'd love to be a beta tester" (and scheduled it)
- Money: "I'd pay for that" (and asked about pricing)
- Reputation: "You should talk to my colleague Sarah" (and made the intro)
- Effort: "Send me early access" (and followed up when you did)

Compliments are not commitments. "Sounds cool" is noise. "Here's my calendar link" is signal.

### Surprises
What did you learn that you did not expect? Surprises are the most valuable output because they update your model of the problem.

## Output Format

Write findings to `outputs/interview-notes-[person-or-topic].md`:

1. **Interview context** — who, when, their role, how you found them
2. **Learning goals** — what you wanted to learn
3. **Key facts** — specific past behaviors and data points
4. **Commitments** — concrete next steps they offered
5. **Surprises** — what shifted your understanding
6. **Updated beliefs** — what you now think differently about the problem

## Do NOT
- Ask leading questions or pitch during discovery
- Treat compliments as validation
- Ask more than 3 learning goals per interview — focus beats breadth
- Skip the debrief — an unprocessed interview is a wasted interview
- Interview only people who are easy to reach — seek out people who do not look like your ideal customer

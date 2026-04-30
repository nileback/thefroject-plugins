---
name: onboarding-cro
description: Optimize post-signup onboarding flows. Use when activation rates are low, users sign up but do not engage, or time-to-value is too long. Covers first-run experience, progressive disclosure, and activation metrics.
triggers:
  - onboarding optimization
  - activation rate
  - improve onboarding
  - time to value
  - first-run experience
  - why do users drop off
allowed-tools: []
---

# Onboarding CRO

Optimize the experience between signup and "aha moment." This is where most products lose users.

## Writes
- `outputs/onboarding-cro-[product].md`

## Step 1: Define the Aha Moment

What action, when completed, correlates with long-term retention? This is your activation metric.

Examples:
- Slack: sent 2,000 messages as a team
- Dropbox: put one file in a shared folder
- Zoom: completed a call
- Your product: [define this first]

Everything in onboarding should drive toward this moment.

## Step 2: Map the Current Flow

Document every step from signup to activation:
1. Signup form (fields, friction)
2. Email verification (if required)
3. Welcome screen or first-run wizard
4. First meaningful action
5. Second session trigger (what brings them back?)

For each step, note:
- Drop-off rate (if data available)
- Time to complete
- Friction points (decisions, confusion, technical barriers)
- Whether the step is necessary or could be deferred

## Step 3: Audit Against Principles

### Progressive Disclosure
Show only what users need right now. Defer advanced features.
- [ ] First screen has one clear action, not five
- [ ] Settings and customization come after core value is experienced
- [ ] Empty states guide rather than just being empty

### Time to Value
How fast does the user get value?
- [ ] Can they experience the core value within 60 seconds?
- [ ] Are there zero-effort defaults that produce a useful result?
- [ ] Is the first win achievable without reading docs?

### Motivation Design
Does onboarding build momentum?
- [ ] Progress indicators show how far along they are
- [ ] Each completed step gives a small reward (checkmark, animation, praise)
- [ ] The hardest step is not first (easy wins build commitment)

### Friction Audit
What is unnecessary?
- [ ] Every form field earns its place (can you remove or defer any?)
- [ ] Email verification before value delivery? (Defer if possible)
- [ ] Required integrations before core experience? (Offer skip)

## Step 4: Recommendations

For each improvement:
1. **Change** — what to do differently
2. **Impact** — estimated effect on activation
3. **Effort** — implementation complexity
4. **Priority** — impact / effort score

Prioritize changes that reduce time-to-value and remove unnecessary steps before adding new onboarding features.

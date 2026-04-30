---
name: idea-validator
description: Validate a business idea before building anything. Uses structured questioning, market sizing, competitive analysis, and the "sell before you build" framework. Use when evaluating a new product idea, side project, or business opportunity.
triggers:
  - validate this idea
  - is this worth building
  - idea validation
  - should I build this
  - market validation
allowed-tools: []
---

# Idea Validator

Validate whether an idea is worth pursuing before investing time and money. The goal is not to prove the idea is good. The goal is to find reasons it might fail, early enough to pivot or abandon.

## Writes
- `outputs/validation-[idea].md`

## Step 1: Problem Clarity

Answer these honestly:
1. **What problem does this solve?** One sentence. If you need a paragraph, the problem is not clear.
2. **Who has this problem?** Specific person, not "everyone." What is their job title, daily routine, current frustration?
3. **How painful is it?** (Hair-on-fire / annoying / nice-to-have). Only hair-on-fire problems reliably produce paying customers.
4. **What do they do today?** The current solution (even if it is duct tape and spreadsheets) is your real competitor.
5. **Why has nobody solved this yet?** If the problem is real and big, why does a solution not already exist? (Timing, technology, distribution, regulation, or nobody has tried)

## Step 2: Market Size

Estimate quickly:
- **TAM (Total Addressable Market)** — everyone who could theoretically use this
- **SAM (Serviceable Addressable Market)** — the segment you can actually reach
- **SOM (Serviceable Obtainable Market)** — realistic first-year target

Use: number of potential customers x what they would pay annually. If SOM is under $100K, this is a side project, not a business. That is fine, but know it going in.

## Step 3: Sell Before You Build

The best validation is someone paying you before the product exists.

**Methods (ranked by signal strength):**
1. **Pre-sell** — describe the product, ask for payment or commitment. A credit card is the strongest signal.
2. **Landing page** — describe the value, measure email signups. Conversion rate matters more than volume.
3. **Manual delivery** — do the thing by hand for 5-10 people. If they pay, the demand is real.
4. **Interviews** — talk to 10+ potential users. But discount what people say they would do. Watch what they actually do.
5. **Survey** — weakest signal. People say yes to everything in surveys.

## Step 4: Competitive Landscape

- Who else is solving this? (Direct competitors, adjacent products, DIY solutions)
- What would it take to be 10x better on one dimension?
- Is there a distribution advantage you have that they do not?

## Step 5: Kill Criteria

Define upfront what would make you stop:
- "If I cannot get 10 signups in 2 weeks, I will pivot."
- "If nobody will pay $X/month, the unit economics do not work."
- "If the technical feasibility check takes more than N days, the complexity is too high."

## Output

Validation report with: problem score, market size estimate, competitive landscape, recommended validation method, and kill criteria. Conclude with a clear GO / PIVOT / STOP recommendation with reasoning.

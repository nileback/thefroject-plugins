---
name: user-story-mapping
description: Build a Jeff Patton-style user story map. The map lays a left-to-right narrative of what a user does (the backbone), with detailed stories under each step prioritized into release slices. Use when planning a new product, breaking down a large epic, or aligning a team on the release plan.
triggers:
  - story mapping
  - user story map
  - release plan
  - story map workshop
---

# User Story Mapping

A story map turns a flat backlog into a 2D narrative: time runs left-to-right (the user journey), priority runs top-to-bottom (release slices). It surfaces gaps and forces honest scope conversations early.

## Why a Map Beats a Backlog

A flat backlog hides the journey. A map reveals it. With the map you can spot:
- Steps in the user flow with no detail (gaps)
- Steps with too many stories (over-scoped feature)
- Release slices that ship a partial journey (incomplete value)

## The Anatomy

```
                         USER GOAL
─────────────────────────────────────────────────────────────────
ACTIVITY  →   ACTIVITY   →   ACTIVITY   →   ACTIVITY      ← Backbone
─────────────────────────────────────────────────────────────────
  Step      Step    Step     Step    Step      Step       ← Walking skeleton
  Step      Step    Step     Step    Step      Step
─────────────────────────────────────────────────────────────────
  story    story   story    story   story     story       ← Release 1 (MVP)
  story    story            story            story
─────────────────────────────────────────────────────────────────
  story    story   story    story   story     story       ← Release 2
─────────────────────────────────────────────────────────────────
  story            story            story                 ← Release 3 (later)
```

- **Goal** — One sentence describing what the user is trying to accomplish.
- **Activities (backbone)** — High-level phases of the journey. 4-8 activities for most products.
- **Steps (walking skeleton)** — The minimum tasks under each activity needed to complete the journey.
- **Stories (slices)** — Detailed user stories grouped into horizontal release bands.

## Building the Map

### Step 1 — Define the user and the goal
One sentence: "[Persona] wants to [accomplish goal] so that [benefit]." If you can't write this in one line, you don't have a clear enough scope yet.

### Step 2 — Draft the backbone
List the activities in chronological order from when the user starts to when they're done. Examples for an e-commerce checkout: Discover → Configure → Pay → Confirm → Use. Avoid product-feature names ("Cart screen") — use user-action verbs.

### Step 3 — Add the walking skeleton
Under each activity, list the minimum steps. Aim for 2-5 steps per activity. The skeleton is what someone would do, not what the system does for them.

### Step 4 — Brainstorm stories per step
For each step, write the variations and edge cases as user stories: "As [persona], I [action] so that [outcome]." Include happy paths, error states, empty states, power-user paths.

### Step 5 — Slice into releases
Draw horizontal lines across the map. Each slice is a release. The first slice (top) is the smallest end-to-end journey that delivers value. Every activity is touched, even if minimally. Subsequent slices add depth.

**Critical rule:** the MVP slice spans the entire backbone. Don't ship "the perfect Discover step with no Pay." Ship the thinnest version of every step.

### Step 6 — Mark dependencies and assumptions
For each story, note:
- Cross-team dependencies (e.g., "needs the new auth service")
- Assumptions to validate (e.g., "users will trust a new payment provider")
- Out-of-scope decisions (e.g., "no offline support — this release")

## Output Format

Save the map to `outputs/product/<feature-slug>-storymap.md`:

```
# Story Map: <Feature/Product>

**User:** <persona>
**Goal:** <one-sentence outcome>
**Owner:** <PM>  **Last updated:** <date>

## Backbone
| Activity | Activity | Activity | Activity |

## Walking skeleton
**[Activity 1]:** step • step • step
**[Activity 2]:** step • step • step
…

## Slice 1 — MVP (target: <date>)
- [Activity 1 / step] story story
- [Activity 2 / step] story
…
**What's missing on purpose:** <list>

## Slice 2 — <name> (target: <date>)
…

## Slice 3 — Later
…

## Dependencies
- <story> blocked by <thing>

## Assumptions to validate
- <statement> — <how we'll test>
```

## Workshop Tips

- **45 minutes is enough** for the first pass with a small team. Don't try to perfect it. Iterate.
- **Sticky notes (physical or digital) beat docs.** Movement matters. People rearrange as they argue.
- **Invite engineering early.** They'll spot infeasible activities before product invests in them.
- **The cards are not commitments.** A card is a conversation prompt, not a contract. Move them.
- **Re-walk the skeleton at the end.** Pretend to be the user and trace the path. Gaps will jump out.

## Do NOT

- Skip the backbone and jump to stories. Without the journey frame, the map is just a vertical list.
- Make the MVP slice deep on one activity. The first slice MUST span every activity, no matter how minimal.
- Use feature names as activities. The map describes user behavior, not product surface.
- Treat the map as static. It's a living artifact. Update it as you ship and learn.
- Plan the second and third slices in detail before the first ships. Outline only. Detail is wasted before MVP feedback.

---
name: frontend-design-standards
description: Enforce design quality standards that prevent generic AI-generated aesthetics. Use when building UI components, reviewing frontend code, or establishing design patterns for a project.
triggers:
  - frontend design
  - ui standards
  - design quality
  - anti-slop
---

# Frontend Design Standards

Enforce design quality that looks intentional and crafted, not AI-generated. These standards apply to all frontend work in this workspace.

## Forbidden Patterns (Anti-Slop List)

Reject these patterns on sight. They signal low-effort AI output:

1. **Centered hero with gradient text** — the default output of every AI code generator
2. **3 equal cards in a row** — the "features section" that every AI produces
3. **Inter font as the only typeface** — pick something with character or pair it properly
4. **Purple/blue neon glow effects** — the "futuristic" cliche
5. **"John Doe" or "Jane Smith" placeholders** — use realistic data that reflects the actual domain
6. **Emoji as icons** — use a proper icon library (Lucide, Heroicons, Phosphor)
7. **Oversaturated gradients** — especially purple-to-pink and blue-to-teal
8. **Massive padding with no content** — whitespace must be earned by content, not used to fill space
9. **Card grids with identical structure** — vary card sizes, layouts, and emphasis
10. **Stock photo circles for "testimonials"** — use real data or skip the section entirely
11. **Rounded-xl on everything** — pick a border radius and use it consistently
12. **Dark mode with neon accents as the only theme** — support both modes or pick one intentionally

## Required Standards

### Data and Content
- Use real or realistic data in examples, not lorem ipsum or placeholder names
- Empty states, loading states, and error states are required for all data-driven views
- Forms must show validation states (idle, error, success) with clear messages

### Interaction States
Every interactive element must have visible states for:
- **Default** — resting appearance
- **Hover** — cursor feedback (desktop)
- **Active/Pressed** — click/tap feedback
- **Focus** — keyboard navigation indicator (visible ring, not just outline)
- **Disabled** — clearly reduced emphasis, not just grayed out opacity
- **Loading** — skeleton or spinner, never frozen UI

### Animation and Motion
- Use hardware-accelerated properties only: `transform`, `opacity`
- Never animate `width`, `height`, `top`, `left`, `margin`, `padding`
- Respect `prefers-reduced-motion` — disable non-essential animations
- Transitions under 200ms for micro-interactions, 300-500ms for layout changes
- No animation on initial page load unless it serves orientation

### Color and Typography
- Max 1 accent color per component hierarchy. Additional colors need justification.
- Text contrast must meet WCAG AA (4.5:1 for body text, 3:1 for large text)
- Headings and body text must use different weights or sizes, not just different colors
- Labels go above inputs, not inside them (placeholder-as-label is forbidden)

### Layout
- Use CSS Grid or Flexbox. No floats. No absolute positioning for layout.
- Responsive breakpoints: mobile-first, test at 320px, 768px, 1024px, 1440px
- Content should breathe but not float in empty space. Tighten padding on mobile.

## Tunable Parameters

When the user or project needs a specific design direction, adjust these dials:

### Design Variance (1-10)
- **1-3:** Conservative. Stick to established patterns, standard layouts, proven UI.
- **4-6:** Moderate. Introduce one unique element per page (layout, interaction, visual).
- **7-10:** Experimental. Push boundaries, asymmetric layouts, unusual interactions.

### Motion Intensity (1-10)
- **1-3:** Minimal. Fade-in transitions only. No scroll-triggered animations.
- **4-6:** Standard. Subtle entrance animations, hover transitions, progress indicators.
- **7-10:** Rich. Parallax, staggered reveals, micro-interactions on every interactive element.

### Visual Density (1-10)
- **1-3:** Sparse. Lots of whitespace, few elements per viewport, large type.
- **4-6:** Balanced. Standard content density, comfortable reading rhythm.
- **7-10:** Dense. Dashboard-style, information-rich, compact spacing.

Default: Variance 5, Motion 4, Density 5.

## Review Checklist

Before shipping any frontend work, verify:

- [ ] No forbidden patterns present
- [ ] All interaction states implemented
- [ ] Animations use hardware-accelerated properties only
- [ ] `prefers-reduced-motion` respected
- [ ] Color contrast meets WCAG AA
- [ ] Labels above inputs, not inside
- [ ] Real or realistic data, no placeholders
- [ ] Responsive at all breakpoints
- [ ] Empty, loading, and error states present
- [ ] Focus indicators visible for keyboard navigation

## Do NOT
- Ship components with only the happy-path state implemented
- Use AI-generated stock illustrations or generic abstract art
- Apply the same border radius, shadow, and padding to every element
- Ignore mobile — test at 320px width before considering the work done
- Override the project's design system tokens with raw color values

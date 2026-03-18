---
name: design-moodboarding
description: >-
  Establishes visual direction through emotional attributes, references, and color/typography/spacing guidance. Use when a project involves significant visual design work. Triggers on: "moodboard", "visual direction", "design aesthetic", "look and feel", "style direction".
---

# 03b — Moodboarding

## Purpose
Establish visual direction before jumping into production design. A moodboard aligns the team on tone, style, and aesthetic intent — preventing subjective debates during design review. It answers: "What should this FEEL like?"

## When to Use
- Parallel with pattern research (03a) and ideation (03c)
- When the project involves significant visual design (not just layout/UX)
- When redefining or evolving an existing visual language
- Skip if: the project is purely functional and uses established design system components

## Inputs
- Design challenge brief (from `02c-problem-lock`)
- Brand guidelines (if they exist)
- Pattern research (from `03a`, for UI-specific visual references)
- Target persona emotional context (from `02a`)

## Outputs
- [ ] **Moodboard** → collection of 10-20 visual references with rationale
- [ ] **Visual direction statement** → 1 paragraph describing the intended feel
- [ ] **Color/typography/space direction** (if deviating from design system)
- [ ] **Posted to Notion/Figma** for team reference
- [ ] **Shared in Slack** for async feedback

## Steps

### 1. Define the emotional target
```
Prompt: "Based on our design challenge and personas: [paste relevant context],
define the emotional qualities this design should convey. Think about:
- What should the user FEEL when using this? (confident, playful, focused, calm...)
- What brand attributes should come through? (professional, innovative, trustworthy...)
- What's the tone? (serious, casual, technical, friendly...)
- What are we explicitly NOT? (cluttered, corporate, intimidating...)
Give me 5-7 attribute words with a one-sentence rationale for each."
```

### 2. Collect visual references
```
Prompt: "Based on these attributes: [paste from step 1], 
search for visual references that embody this direction. Look at:
- UI designs (Dribbble, Behance, Mobbin, Awwwards)
- Brand design (packaging, identity, print)
- Photography and art direction
- Typography specimens
- Physical/spatial design (architecture, interiors)

For each reference:
- Source/URL
- Why it fits (which attributes it demonstrates)
- Specific element to pay attention to (color, spacing, type, imagery style)
Collect 10-20 references."
```

### 3. Distill into direction
```
Prompt: "From the references, write a visual direction statement:
One paragraph that describes the intended visual feel, 
covering: color mood, typography character, spacing/density, 
imagery style, and overall aesthetic.

Then extract specific design tokens if applicable:
- Color palette direction (warm/cool, saturated/muted, contrast level)
- Typography direction (geometric/humanist, weight range, hierarchy approach)
- Spacing direction (airy/dense, grid rhythm)
- Imagery direction (photo style, illustration style, iconography)

This becomes the brief for production design."
```

### 4. Share and align
```
Prompt: "Create a moodboard page in Notion (or a Figma frame) with:
- Visual direction statement at the top
- References organized by attribute
- Color/type/space direction notes
Then post to Slack: 'Visual direction for [project]: [one-liner description].
Moodboard: [link]. Aligns with our brand by [connection]. 
Feedback by [date] — this feeds into production design.'"
```

## Integrations
- **Notion/Figma**: Host moodboard
- **Slack**: Share for feedback
- **Web**: Visual reference search
- **Brand guidelines**: Reference existing brand docs

## Templates
- `templates/moodboard-brief.md`

## Definition of Done
- [ ] Emotional attributes defined with rationale
- [ ] 10-20 visual references collected
- [ ] Visual direction statement written
- [ ] Color/type/space direction documented
- [ ] Shared with team, feedback collected

## Customization Notes
- For projects using an established design system with no visual deviation: skip this entirely
- For brand-heavy work (marketing pages, consumer apps): invest more time here
- For B2B enterprise: keep it focused on density, hierarchy, and professionalism — less about "vibe"
- Timebox: 2-3 hours max for internal product work

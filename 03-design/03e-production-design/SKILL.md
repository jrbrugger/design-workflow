---
name: design-production
description: >-
  Guides production-ready Figma design including flows, states, edge cases, accessibility, and content specs. Use when creating final designs in Figma. Triggers on: "production design", "design in Figma", "edge cases", "design states", "UI copy", "accessibility check".
---

# 03e — Production Design

## Purpose
This is where the design gets made. Transform the selected concept into production-ready Figma files — screens, components, states, responsive variants, and documentation. AI assists with content, specs, and documentation — but the designer drives every visual and interaction decision.

## When to Use
- After concept selection (03d) locks a direction
- This is the longest phase — expect iteration

## Inputs
- Design direction doc (from `03d-concept-selection`)
- Visual direction / moodboard (from `03b`)
- Pattern research (from `03a`)
- Design system components (existing library)
- Design challenge brief (from `02c`)

## Outputs
- [ ] **Figma file** with all screens and flows
- [ ] **Component inventory** — new/modified components documented
- [ ] **Interaction specs** — transitions, animations, micro-interactions
- [ ] **Content specs** — final copy, error messages, empty states
- [ ] **Responsive variants** (if applicable)
- [ ] **Accessibility annotations** — focus order, aria labels, contrast ratios
- [ ] **Prototype** — clickable for testing (04a) and review (04b)
- [ ] **Design changelog** → `templates/design-changelog.md`

## Steps

### 1. Set up Figma file
```
Prompt: "Help me set up the Figma file structure for [project]:
- Cover page with project name, status, and links
- Page structure: Flows | Components | Specs | Archive
- Frame naming convention: [Feature] / [Screen] / [State]
- Version naming: v0.1, v0.2, etc.
Generate the page structure and naming conventions as a checklist I can follow."
```

### 2. Design core flows
_This is manual Figma work. AI supports with content and edge cases._

```
Prompt: "For the [specific flow] I'm designing, help me think through:
- Happy path: What's the ideal user journey step by step?
- Edge cases: What happens with empty data, errors, long text, max items?
- Error states: What can go wrong and what should we show?
- Loading states: What does the user see while waiting?
- Empty states: First-time user with no data
- Permission states: What if they don't have access?
List every state I need to design for this flow."
```

### 3. Write UI copy
```
Prompt: "I need UI copy for [specific screen/component]. Context: [what it does].
Write:
- Headings and subheadings
- Button labels (action-oriented, concise)
- Helper text
- Error messages (specific, helpful, not blaming)
- Empty state copy (guide the user to take action)
- Success messages
- Tooltip text
Follow our voice/tone: [describe or link to content guidelines].
Keep everything as short as possible."
```

### 4. Accessibility pass
```
Prompt: "Review this flow for accessibility:
- Screen descriptions: [describe each screen]
- Interactive elements: [list buttons, inputs, links]
- Color usage: [describe color-dependent information]

Check for:
- Color contrast (WCAG AA minimum, AAA for critical text)
- Focus order (logical tab sequence)
- Screen reader experience (do labels make sense out of visual context?)
- Touch targets (minimum 44x44px)
- Motion (can animations be reduced/disabled?)
- Alternative text needs

Flag issues and suggest fixes."
```

### 5. Document design decisions
```
Prompt: "Create a design changelog entry for today's work:
- What was designed
- Key decisions made and rationale
- Deviations from the original direction (if any) and why
- New components created or modified
- Open questions or items deferred
Format as templates/design-changelog.md and post to Notion."
```

### 6. Prepare for validation
```
Prompt: "The design is ready for review. Prepare:
1. Figma prototype linked to key flows
2. Design changelog posted to Notion
3. Slack update: 'Design for [project] is ready for review.
   Prototype: [link]. Key decisions: [2-3 bullets].
   Design review: [date]. Feedback welcome async before then.'
4. Tag relevant reviewers from team config."
```

## Integrations
- **Figma**: All production design work
- **Figma MCP**: (If available) Audit component usage, check token bindings
- **Notion**: Design changelog, decision documentation
- **Slack**: Progress updates, review requests
- **Design system**: Component library reference

## Templates
- `templates/design-changelog.md`

## Definition of Done
- [ ] All screens designed for happy path
- [ ] Edge cases, error states, empty states, loading states covered
- [ ] UI copy finalized
- [ ] Accessibility annotations added
- [ ] Responsive variants designed (if applicable)
- [ ] Clickable prototype ready
- [ ] Design changelog documented
- [ ] Ready for prototype testing (04a) and design review (04b)

## Customization Notes
- For rapid projects: focus on happy path + top 3 edge cases, defer the rest
- Figma file structure varies by team — adapt the setup step to your convention
- If your design system has a contribution model, follow it for new components
- Design is iterative — expect to revisit screens after testing (04a)

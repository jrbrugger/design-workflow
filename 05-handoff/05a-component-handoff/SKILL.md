---
name: 05a-component-handoff
description: >-
  Translates approved designs into engineering-ready specs including component props, interaction behavior, and tickets. Use when handing off designs to engineering. Triggers on: "handoff", "dev handoff", "engineering specs", "component specs", "create tickets".
---

# 05a — Component Handoff

## Purpose
Translate approved designs into engineering-ready specifications. This isn't just "throw it over the wall" — it's a structured transfer of intent, behavior, and specs that minimizes interpretation gaps. Every component, interaction, and edge case gets documented so engineering builds what was designed.

## When to Use
- After stakeholder approval (04c)
- Before engineering sprint begins

## Inputs
- Approved Figma design file (from `03e`, validated through `04a-c`)
- Design system component inventory (from `03f`)
- Design challenge brief (from `02c`)
- Technical constraints (from engineering)

## Outputs
- [ ] **Handoff document** → `assets/handoff-doc.md` per feature/flow
- [ ] **Component specs** — props, states, variants, behavior for each new component
- [ ] **Interaction specs** — transitions, animations, conditional logic
- [ ] **Figma dev mode** annotations (or equivalent)
- [ ] **Engineering tickets** created in project management tool
- [ ] **Handoff meeting notes** or async walkthrough
- [ ] **Slack announcement** — handoff ready

## Steps

### 1. Prepare the Figma file for dev mode
```
Prompt: "Help me create a handoff preparation checklist for our Figma file:
- [ ] All frames named consistently: [Feature]/[Screen]/[State]
- [ ] Auto layout applied to all major sections
- [ ] Components properly linked to design system (not detached)
- [ ] All states designed: default, hover, active, disabled, focus, error, loading, empty
- [ ] Spacing uses design tokens (not arbitrary values)
- [ ] Colors reference semantic tokens
- [ ] Typography uses system styles
- [ ] Responsive behavior documented (constraints, breakpoints)
- [ ] Prototype flows linked for interaction reference
- [ ] No hidden or orphaned layers

Flag any items that still need cleanup."
```

### 2. Write component specs
```
Prompt: "For each NEW component in this project (not already in the component library):
[list components]

Create a component spec:
- Component name
- Description: What it does and when to use it
- Props/Properties:
  | Prop | Type | Default | Options | Required |
  |------|------|---------|---------|----------|
- States: default, hover, active, disabled, focus, error
- Responsive behavior: How it adapts across breakpoints
- Accessibility: ARIA role, keyboard interaction, screen reader behavior
- Animation: Entry/exit/transition specs (duration, easing, trigger)
- Edge cases: Long text, empty data, max items, overflow
- Dependencies: Other components it relies on

Format each as a clear spec an engineer can implement from."
```

### 3. Write interaction specs
```
Prompt: "Document the interaction specifications for each flow:
[describe the flows]

For each interaction:
- Trigger: What initiates it (click, hover, scroll, load, etc.)
- Action: What happens visually
- Transition: Duration, easing curve, direction
- Conditional logic: If [condition], then [behavior]
- Error handling: What happens when the action fails
- Loading behavior: What the user sees while waiting
- Optimistic updates: (If applicable) What updates immediately vs. on confirmation

Use specific values: '200ms ease-out' not 'quick fade.'"
```

### 4. Create engineering tickets
```
Prompt: "Break the design into engineering tickets for [Linear/Jira]:
- One ticket per component or feature unit
- Each ticket includes:
  - Title: [Action verb] [Component/Feature]
  - Description: What to build and why
  - Acceptance criteria: Testable conditions for done
  - Design reference: Link to specific Figma frame
  - Component spec: Link or inline
  - Dependencies: What needs to be built first
  - Estimated complexity: S/M/L (design perspective — eng refines)

Order tickets by dependency chain.
Group into an epic for the overall feature."
```

### 5. Handoff walkthrough
```
Prompt: "Prepare a handoff walkthrough for engineering:
- Agenda: File tour → Flow walkthrough → Component specs → Q&A
- Duration: 30 min
- Key areas to emphasize: [complex interactions, novel patterns, edge cases]
- Questions to ask engineering: 
  - Technical concerns with any component?
  - State management approach for [specific interaction]?
  - API shape assumptions we should validate?

If async: create a Loom walkthrough following this structure.
Post to Slack: 'Design handoff ready for [project]. 
Figma: [link]. Handoff doc: [link]. Tickets: [link].
Walkthrough: [meeting time or Loom link].
@[eng lead] — let's sync on questions.'"
```

## Integrations
- **Figma**: Dev mode, component annotations, prototype links
- **Linear/Jira**: Ticket creation with design specs
- **Slack**: Handoff announcement, Q&A thread
- **Notion**: Handoff documentation
- **Loom**: (Optional) Async walkthrough recording
- **Storybook**: (Optional) Link to existing component implementations

## Templates
- `assets/handoff-doc.md`
- `assets/component-spec.md`

## Definition of Done
- [ ] Figma file cleaned and organized for dev mode
- [ ] All new components have written specs
- [ ] Interaction specs documented with specific values
- [ ] Engineering tickets created with acceptance criteria
- [ ] Handoff walkthrough completed (sync or async)
- [ ] Engineering lead confirms understanding — no blocking questions
- [ ] Handoff doc posted to Notion

## Customization Notes
- If your team uses Storybook: link existing component stories, only spec what's new
- If you use Figma dev mode: lean on it for spacing/color specs, focus your writing on behavior and edge cases
- For teams with design engineers: handoff may be collaborative pairing rather than documentation
- The goal is zero ambiguity — if an engineer has to guess, the handoff failed

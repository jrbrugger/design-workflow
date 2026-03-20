---
name: 03f-design-system
description: >-
  Parallel track for auditing, extending, and governing the design system during feature work. Use when creating new components, checking token architecture, or maintaining the design system. Triggers on: "design system", "component audit", "token architecture", "promote component", "design tokens".
---

# 03f — Design System (Parallel Track)

## Purpose
Maintain, extend, and govern the design system as a parallel activity to feature design. New components created during production design get promoted to the system. Token architecture stays clean. Breaking changes are managed. This runs alongside every project, not as a separate initiative.

## When to Use
- Continuously — check at the start and end of every design phase
- When production design (03e) creates new components
- When token sync (05b) reveals drift
- During design system sync meetings (per cadence in team-config.md)

## Inputs
- Component inventory from production design (03e)
- Token architecture (existing design tokens file)
- Figma design system file
- Component usage audit data (via Figma MCP if available)

## Outputs
- [ ] **Updated component library** in Figma
- [ ] **Token updates** documented (new tokens, modified tokens, deprecated tokens)
- [ ] **Component spec sheets** for new/modified components
- [ ] **Breaking change log** if applicable
- [ ] **Design system changelog** → `assets/ds-changelog.md`

## Steps

### 1. Audit current state
```
Prompt: "Help me audit the design system for [project] context:
- List all components used in the current project designs
- Identify which are from the existing design system vs. custom/one-off
- Flag any components that should be promoted to the system
- Flag any components used inconsistently (different variants in different places)
- Check: are components bound to semantic tokens or primitives?

If Figma MCP is available, use it to pull component usage data."
```

### 2. Promote new components
```
Prompt: "These components need to be promoted from project-level to design system:
[list from audit]

For each, help me create a component spec:
- Component name (following naming convention: [your convention])
- Variants and states (default, hover, active, disabled, error, etc.)
- Props/properties
- Spacing and sizing tokens used
- Color tokens used
- Typography tokens used
- Accessibility requirements
- Usage guidelines (when to use, when not to use)
Format as a spec sheet I can reference while building in Figma."
```

### 3. Token architecture check
```
Prompt: "Review our token architecture for health:
- Are we following the 3-layer model? (primitive → semantic → component)
- Are any components bound directly to primitives? (they shouldn't be)
- Are there orphaned tokens (defined but unused)?
- Are there missing semantic tokens (components referencing hardcoded values)?
- Are token names consistent with our naming convention?

Flag issues and suggest fixes. 
This prevents token debt from accumulating."
```

### 4. Document changes
```
Prompt: "Create a design system changelog entry:
- Components added/modified/deprecated
- Tokens added/modified/deprecated  
- Breaking changes (anything that affects existing usage)
- Migration notes (if breaking changes exist)
Format as assets/ds-changelog.md. 
Post to the design system Slack channel or the team sync channel."
```

## Integrations
- **Figma**: Component library management, variant creation
- **Figma MCP**: Component usage audit, token binding check
- **Token Studio / Style Dictionary**: Token management
- **GitHub**: Token sync to code repo
- **Slack**: Design system updates, breaking change announcements
- **Notion**: Component documentation, design system wiki

## Templates
- `assets/ds-changelog.md`
- `assets/component-spec.md`

## Definition of Done
- [ ] Component inventory audited for current project
- [ ] New components promoted with full spec sheets
- [ ] Token architecture reviewed — no primitive bindings in components
- [ ] Changes documented in design system changelog
- [ ] Breaking changes communicated to team

## Customization Notes
- If you don't have a design system yet: use this skill to START one from project components
- Token architecture depth depends on system maturity — start with 2 layers (primitive + semantic)
- For solo designers: focus on component consistency, worry about formal token architecture later
- Design system governance scales with team size — solo = informal, 5+ = formal contribution model

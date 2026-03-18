# 02c — Problem Statement Lock

## Purpose
Finalize and lock the problem statement before design begins. This is the last gate before creative work starts — it ensures everyone agrees on WHAT we're solving. After this, the team debates HOW, not WHAT.

## When to Use
- After opportunity framing is complete and PM-aligned (02b)
- This is a formal checkpoint — don't skip it

## Inputs
- Opportunity canvas for selected opportunity (from `02b`)
- PM alignment confirmation
- Technical feasibility input from engineering

## Outputs
- [ ] **Locked problem statement** → one paragraph, no ambiguity
- [ ] **Design challenge brief** → `templates/design-challenge.md` filled out
- [ ] **Posted to Notion** as the authoritative reference
- [ ] **Slack announcement** — "Problem locked, design starting"
- [ ] **Design tickets created** in project management tool

## Steps

### 1. Craft the problem statement
```
Prompt: "From our opportunity canvas: [paste], 
write a problem statement in this format:

[Persona] needs a way to [user need/JTBD] because [insight from research].
We will know we've succeeded when [measurable outcome].
We are NOT solving [explicit exclusions].

Make it specific enough that two designers would interpret it the same way. 
If it's ambiguous, it's not locked."
```

### 2. Create design challenge brief
```
Prompt: "Fill out the design challenge brief template at templates/design-challenge.md.
This is the single document a designer needs to start working. Include:
- Locked problem statement
- Success criteria
- Constraints (technical, timeline, brand, accessibility)
- Scope boundaries (in/out)
- Key research insights to keep in mind
- Personas and JTBD to reference
- Links to all prior artifacts"
```

### 3. Get final sign-off
```
Prompt: "Draft a Slack message for the project channel:
'Problem statement locked for [project name]:

[Problem statement]

Design challenge brief: [Notion link]
Success metric: [metric]
Timeline: [dates]
Scope: [one-line summary of what's in/out]

@[PM] @[Eng Lead] — please confirm you're aligned. 
If no objections by [date], we start design.'

Tag all approvers from the team config."
```

### 4. Set up design phase
```
Prompt: "Create the following to prepare for design:
1. Update Notion project page status to 'Design — In Progress'
2. Create design tickets in [Linear/Jira] for the approved scope
3. Post in the design team channel: 'Starting design for [project]. 
   Design challenge brief: [link]. Happy to discuss in design crit on [day].'
4. Block time on calendar for focused design work"
```

## Integrations
- **Notion**: Post locked problem statement and design challenge brief
- **Slack**: Announce lock, get sign-off, notify design team
- **Linear/Jira**: Create design exploration tickets
- **Calendar**: Block design time

## Templates
- `templates/design-challenge.md`

## Definition of Done
- [ ] Problem statement written — specific, measurable, bounded
- [ ] Design challenge brief complete with all context linked
- [ ] PM and Eng Lead confirmed alignment
- [ ] Design tickets created
- [ ] Team notified — design phase begins

## Customization Notes
- Some orgs call this a "design brief" or "creative brief" — same thing
- For rapid projects, this can be a 10-minute async exercise, not a ceremony
- The key value is the explicit scope boundary — it prevents scope creep during design

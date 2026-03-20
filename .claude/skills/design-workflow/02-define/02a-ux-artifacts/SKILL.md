---
name: 02a-ux-artifacts
description: >-
  Creates JTBD statements, behavioral personas, journey maps, and mental models from research insights. Use when translating research into design-ready artifacts. Triggers on: "create personas", "jobs to be done", "journey map", "JTBD", "user artifacts", "mental model".
---

# 02a — UX Artifact Creation

## Purpose
Transform research insights into design-ready artifacts — JTBD statements, personas, mental models, and journey maps. These artifacts become the shared reference point for every design decision. They answer: "Who are we designing for, what do they need, and what's their current experience?"

## When to Use
- After research validation passes (01e)
- When the team needs a shared understanding of the user before design begins

## Inputs
- Validated insight report (from `01d-synthesis`)
- Raw research data (interview notes, analytics)
- Competitive analysis
- Existing personas or user models (if updating)

## Outputs
- [ ] **Jobs to Be Done statements** → 3-5 core JTBD
- [ ] **User personas** → 2-3 behavioral personas (not demographic)
- [ ] **Journey map** → Current-state experience map
- [ ] **Mental model diagram** (optional) → How users think about the domain
- [ ] All artifacts posted to Notion project page
- [ ] Slack update with artifact summary

## Steps

### 1. Draft JTBD statements
```
Prompt: "From our research insights: [paste insight report summary], 
draft Jobs to Be Done statements using this format:

When [situation/trigger], 
I want to [motivation/action], 
so I can [desired outcome].

Create 3-5 JTBD that cover the primary user needs we discovered.
For each, note:
- Which research insight supports it
- Current alternatives (how they do this today)
- Satisfaction with current alternatives (high/medium/low)
Rank by frequency and importance from research."
```

### 2. Create behavioral personas
```
Prompt: "From our research, create 2-3 behavioral personas. 
NOT demographic stereotypes — these should be behavior-based archetypes.
For each persona:
- Name and one-line description
- Key behavior patterns (from research)
- Primary JTBD (from step 1)
- Pain points (with supporting quotes)
- Current workflow/tools
- What success looks like for them
- Differentiating factor (what makes this persona distinct from the others)

Keep each persona to half a page. If I can't remember the differentiator, it's not distinct enough."
```

### 3. Map the current journey
```
Prompt: "Create a current-state journey map for our primary persona completing their primary JTBD.
Structure as phases with:
- Phase name
- User actions (what they do)
- Touchpoints (what they interact with)
- Thoughts (what they're thinking — from research quotes)
- Emotions (frustration, confusion, satisfaction — mapped from research)
- Pain points (specific friction, with severity rating)
- Opportunities (where we can improve)

Format as a markdown table. This should be directly informed by research — no speculation."
```

### 4. (Optional) Mental model diagram
```
Prompt: "Based on our research, create a mental model diagram showing 
how users think about [domain/task]. 
What concepts do they group together? 
What's their hierarchy of importance?
Where does their mental model differ from our product's information architecture?
These mismatches are high-priority design opportunities."
```

### 5. Review and share
```
Prompt: "Compile all UX artifacts into a single Notion page under the project hub.
Structure as: JTBD → Personas → Journey Map → Mental Model.
Add a one-paragraph introduction explaining how to use these artifacts.
Then draft a Slack message for the project channel:
'Research → UX artifacts are ready. [Link to Notion page]. 
Key persona: [name]. Primary JTBD: [one-liner]. 
Biggest opportunity: [one-liner]. Review and flag questions by [date].'"
```

## Integrations
- **Notion**: Create UX artifacts page, link to project hub
- **Slack**: Share artifacts, request review
- **Figma/FigJam**: (Optional) Visual versions of journey map and personas for workshops
- **Miro**: (Optional) Collaborative journey mapping with team

## Templates
- `assets/jtbd-template.md`
- `assets/persona-template.md`
- `assets/journey-map-template.md`

## Definition of Done
- [ ] 3-5 JTBD statements drafted and ranked
- [ ] 2-3 behavioral personas created with research backing
- [ ] Current-state journey map complete
- [ ] All artifacts posted to Notion
- [ ] Team notified and review period set

## Customization Notes
- If your org already has personas, update rather than create from scratch
- For B2B: consider organizational personas alongside individual ones
- Journey maps work best when focused on one JTBD — don't try to map everything
- If your org uses Opportunity Solution Trees (Teresa Torres style), add that as a step between JTBD and personas

---
name: opportunity-framing
description: >-
  Prioritizes design opportunities by scoring user impact, business value, and feasibility. Use when deciding what to design first. Triggers on: "prioritize opportunities", "what should we design", "opportunity scoring", "scope the work", "size the opportunity".
---

# 02b — Opportunity Framing

## Purpose
Prioritize which problems to solve and size the opportunity. Takes the pain points and opportunities from UX artifacts and turns them into a ranked backlog of design opportunities — each with a clear value proposition and scope boundary.

## When to Use
- After UX artifacts are created (02a)
- When the team needs to decide what to design first

## Inputs
- JTBD statements, personas, journey maps (from `02a-ux-artifacts`)
- Business goals and OKRs (from `00-kickoff` brief)
- Technical constraints (from engineering)

## Outputs
- [ ] **Opportunity backlog** → ranked list of design opportunities
- [ ] **Opportunity canvas** for top 1-3 opportunities → `templates/opportunity-canvas.md`
- [ ] **Scope recommendation** posted to Notion
- [ ] **Slack update** with recommendation for PM alignment

## Steps

### 1. Extract opportunities
```
Prompt: "From our UX artifacts: [paste JTBD + journey map pain points + persona pain points],
extract every design opportunity. For each:
- Opportunity name (verb + noun, e.g., 'Simplify onboarding flow')
- Related JTBD
- Related persona(s)
- Pain point it addresses
- Estimated user impact (how many users, how often)
Deduplicate and group related opportunities."
```

### 2. Score and rank
```
Prompt: "Score each opportunity on these dimensions (1-10):
- User impact: How much does this reduce pain or enable the JTBD?
- Business value: How does this connect to our OKRs/metrics?
- Feasibility: Can we realistically build this? (Check with engineering if unsure)
- Confidence: How sure are we this is a real problem? (From research confidence)

Calculate priority: (User Impact + Business Value) × Confidence / (11 - Feasibility)
Rank the opportunities. Show the math."
```

### 3. Scope the top opportunities
```
Prompt: "For the top 3 opportunities, fill out an opportunity canvas:
- Problem statement (one sentence)
- Target persona and JTBD
- Current experience vs. desired experience
- Success metric (what we'll measure)
- Scope boundary: what's IN and what's explicitly OUT
- Key assumptions to validate in design
- Dependencies and risks

Be ruthless about scope. If we can't ship it in [timeline from brief], it's too big."
```

### 4. Align with PM
```
Prompt: "Draft a Slack message for the project channel with our opportunity recommendation:
- Here's what we found (1 sentence summary)
- Here's what we recommend designing (top 1-3 with one-liner each)
- Here's what we're NOT doing and why
- Here's the success metric for each
- Ask: 'Does this align with product priorities? Async feedback by [date].'
Tag PM and stakeholders."
```

## Integrations
- **Notion**: Post opportunity backlog and canvases
- **Slack**: Share recommendation, get PM alignment
- **Linear/Jira**: (Optional) Create design exploration tickets for approved opportunities
- **Spreadsheet**: (Optional) Scoring matrix for larger backlogs

## Templates
- `templates/opportunity-canvas.md`

## Definition of Done
- [ ] All opportunities extracted from UX artifacts
- [ ] Opportunities scored and ranked
- [ ] Top 1-3 scoped with opportunity canvases
- [ ] PM aligned on which opportunities to pursue
- [ ] Scope boundaries explicitly documented

## Customization Notes
- Adjust scoring weights based on your org's priorities (growth-stage → weight business value higher, mature → weight user impact higher)
- If using Teresa Torres's Opportunity Solution Trees, map opportunities as child nodes under JTBD
- For solo/freelance: simplify to gut-ranked top 3 with one-paragraph scoping each

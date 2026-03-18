---
name: 06c-insights-loop
description: >-
  Feeds project learnings back into the org knowledge base and updates the playbook for next cycle. Use as the final step of any project to close the learning loop. Triggers on: "file insights", "close project", "archive project", "knowledge base", "next cycle".
---

# 06c — Insights Loop

## Purpose
Feed learnings from this project back into the organization's knowledge base so the next project starts smarter. This is the flywheel — each project cycle makes the next one faster and more informed. Without this step, every project starts from zero.

## When to Use
- After retrospective (06b)
- This is the final step of the project cycle
- It bridges to the NEXT project's gap analysis (01a)

## Inputs
- Performance summary (from `06a`)
- Retrospective findings (from `06b`)
- Research insights (from `01d`)
- Design decisions and rationale (from design changelog, `03e`)
- Usability test findings (from `04a`)

## Outputs
- [ ] **Updated insights database** — new entries in the org research repository
- [ ] **Pattern additions** — validated patterns added to team pattern library
- [ ] **Updated personas/JTBD** (if research invalidated or refined them)
- [ ] **Playbook updates** applied (from retro recommendations)
- [ ] **Project archived** with clean documentation trail
- [ ] **Slack announcement** — project closed, insights available

## Steps

### 1. Extract reusable insights
```
Prompt: "From this project's research and post-launch data, extract insights 
that are relevant BEYOND this specific project:

- User behavior patterns that apply broadly
- Market/competitive insights that haven't expired
- Technical learnings (what's feasible, what's hard)
- Design pattern validations (what worked, what didn't)
- Metric benchmarks (baseline numbers for similar features)

For each, write a standalone insight card:
- Insight: [one sentence]
- Evidence: [where this came from]
- Confidence: [high/medium/low]
- Applicable to: [what future projects this helps]
- Date: [when this was validated]
- Expiry: [when this might become stale]

These go into the org research database."
```

### 2. Update shared resources
```
Prompt: "Based on project outcomes, update shared team resources:
- Personas: Do any need refinement based on new data? Update in Notion.
- JTBD: Any new jobs discovered? Any existing jobs reprioritized?
- Pattern library: Any patterns validated that should be documented for reuse?
- Component library: Any new components that need design system promotion?
- Competitive landscape: Any changes observed during the project?

For each update, note what changed and why."
```

### 3. Apply playbook updates
```
Prompt: "From the retrospective, these playbook changes were recommended: 
[paste from 06b step 5].

For each:
- Which file to update
- What specifically to change
- Draft the updated content

I'll review and apply the changes to keep the workflow evolving."
```

### 4. Archive the project
```
Prompt: "Create a project archive checklist:
- [ ] Notion project page: status set to 'Complete'
- [ ] All artifacts linked and accessible
- [ ] Figma file: moved to archive section, linked from Notion
- [ ] Performance summary linked
- [ ] Retro linked
- [ ] Insights extracted and filed in research database
- [ ] Project channel: post closing message with links to all key docs
- [ ] Slack channel: archive (or keep open if ongoing monitoring)

The goal: anyone can find what we did, why, and what we learned — 
without asking the designer who worked on it."
```

### 5. Close the loop
```
Prompt: "Draft the project closing message for Slack:
'[Project name] — SHIPPED AND DOCUMENTED
- Problem: [one-liner from design challenge]
- Result: [metric outcome from performance summary]
- Key insight: [most valuable learning]
- All docs: [Notion project page link]
- Insights filed for future projects.

Thanks to @[team members] for the collaboration.
What we learned here feeds into [next project / ongoing work].'

This message is the bridge between this project's end and the next project's beginning."
```

## Integrations
- **Notion**: Research database, persona updates, project archive
- **Slack**: Closing announcement, channel archive
- **Figma**: File archive and organization
- **This playbook**: Skill file updates from retro learnings

## Templates
_(No new templates — this skill updates existing resources)_

## Definition of Done
- [ ] Reusable insights extracted and filed in research database
- [ ] Shared resources updated (personas, patterns, components)
- [ ] Playbook updates applied
- [ ] Project archived with complete documentation trail
- [ ] Closing message posted to Slack
- [ ] Project cycle complete — ready for the next one

## Customization Notes
- If your org has a research repository (Dovetail, Condens): file insights there instead of Notion
- The insight "expiry" field prevents teams from treating old research as current truth
- For rapidly scaling teams: this is how institutional knowledge survives turnover
- The archive step matters — future-you will thank past-you when you need to reference this project

---
name: 06b-retrospective
description: >-
  Reflects on the entire project cycle to identify process improvements and update the playbook. Use after monitoring period ends. Triggers on: "retrospective", "retro", "what worked", "lessons learned", "project review".
---

# 06b — Retrospective

## Purpose
Reflect on the entire project cycle — process, collaboration, outcomes, and craft. What worked, what didn't, and what should change for next time. This is how the playbook improves. Every retro should produce at least one concrete process change.

## When to Use
- After release monitoring period ends (06a)
- Within 1 week of project completion (while memory is fresh)

## Inputs
- Performance summary (from `06a`)
- Project timeline (actual vs. planned)
- Team feedback
- Design changelog (from `03e`)
- All phase outputs as reference

## Outputs
- [ ] **Retro document** → `assets/retro-doc.md`
- [ ] **Process improvements** — specific changes to this playbook
- [ ] **Lessons learned** — insights for future projects
- [ ] **Posted to Notion** team knowledge base
- [ ] **Slack summary** shared with team

## Steps

### 1. Gather input
```
Prompt: "Prepare a retrospective for [project]. Structure the input gathering:

For each phase of the project (Kickoff → Research → Define → Design → Validate → Handoff → Ship):
- Time spent (actual vs. planned)
- Blockers or delays
- What felt efficient
- What felt wasteful

Also gather:
- Cross-functional friction points
- Tool or process pain points
- Moments where AI assistance was valuable vs. not helpful
- Moments where the designer had to override or heavily edit AI output

Draft a structured self-reflection I can review and edit before sharing with the team."
```

### 2. Team feedback (if applicable)
```
Prompt: "Create a lightweight retro survey for the project team:
- What went well? (1-3 items)
- What was frustrating? (1-3 items)
- What should we do differently next time? (1-3 items)
- Rate collaboration with design: 1-5
- One thing design could improve?

Post to Slack as a structured thread or form. 
Keep it to 5 minutes of effort — people skip long retros."
```

### 3. Analyze and synthesize
```
Prompt: "Here's the retro input: [paste self-reflection + team feedback].
Synthesize into:
- TOP 3 things that worked (keep doing these)
- TOP 3 things that didn't work (stop or change)
- TOP 3 process improvements (specific, actionable changes)
- METRICS: Timeline accuracy, research→design→ship ratio, rework rate
- AI USAGE: Where AI saved time, where it didn't help, where it slowed things down

For each process improvement, specify:
- What to change
- Which skill file to update
- Expected impact
This is how the playbook gets better over time."
```

### 4. Document and share
```
Prompt: "Fill out the retro doc template at assets/retro-doc.md.
Post to Notion in the team knowledge base (not just the project page — retros are org learning).
Post summary to Slack:
'Retro complete for [project].
Top win: [one-liner]. Top lesson: [one-liner]. 
Process change: [one-liner].
Full retro: [Notion link].'"
```

### 5. Update the playbook
```
Prompt: "Based on retro findings, recommend specific updates to the workflow skills:
- Which SKILL.md files need changes?
- What steps should be added, removed, or modified?
- Any new templates needed?
- Any integration changes?
- Should any gate thresholds be adjusted?

Create a list of changes. I'll apply them to keep the playbook evolving."
```

## Integrations
- **Notion**: Retro documentation, team knowledge base
- **Slack**: Team feedback collection, summary sharing
- **This playbook**: Direct updates to skill files based on learnings

## Templates
- `assets/retro-doc.md`

## Definition of Done
- [ ] Self-reflection completed across all phases
- [ ] Team feedback collected (if applicable)
- [ ] Top 3 wins, lessons, and improvements identified
- [ ] Retro doc posted to Notion knowledge base
- [ ] At least one concrete process improvement identified
- [ ] Playbook update recommendations documented
- [ ] Summary shared in Slack

## Customization Notes
- For solo designers: self-retro is still valuable — be honest about what worked
- For teams: run as a 30-min meeting or async thread, whichever your culture prefers
- The most important output is the process improvement — if the retro doesn't change anything, it was a waste of time
- Track retro improvements over time to see if the playbook is actually getting better

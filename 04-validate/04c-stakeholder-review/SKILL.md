---
name: 04c-stakeholder-review
description: >-
  Structures stakeholder presentation, collects feedback, and documents approval decisions. Use when designs need business sign-off before engineering. Triggers on: "stakeholder review", "get approval", "present to stakeholders", "sign-off", "design presentation".
---

# 04c — Stakeholder Review

## Purpose
Get stakeholder sign-off on the design before engineering begins. This is a business alignment check — not a design crit. Stakeholders evaluate whether the design meets business goals, user needs, and launch criteria. The designer presents; stakeholders approve, request changes, or ask questions.

## When to Use
- After design review passes (04b)
- Before handoff to engineering (05a)

## Inputs
- Approved design (passed 04b)
- Clickable prototype
- Design challenge brief (for context)
- Test findings summary (from 04a)

## Outputs
- [ ] **Stakeholder presentation** → structured walkthrough
- [ ] **Feedback log** → `assets/feedback-log.md`
- [ ] **Decision: Approved / Approved with changes / Needs revision**
- [ ] **Notion status update**
- [ ] **Slack announcement** of decision

## Steps

### 1. Prepare the presentation
```
Prompt: "Structure a stakeholder review presentation for [project]:
1. Context reminder (1 min): Problem statement, success metric, scope
2. Research summary (2 min): Key insights that drove design decisions
3. Design walkthrough (10 min): Prototype demo of primary flow
4. Key decisions (3 min): 2-3 design choices and their rationale
5. Testing results (2 min): What we validated, what we found
6. Next steps (2 min): Handoff plan, timeline, what we need from them

Keep it under 20 minutes including discussion.
Don't present everything — present the story. 
Lead with the user's problem, show how we solved it, prove it works."
```

### 2. Anticipate questions
```
Prompt: "Based on our stakeholder map and project context, 
anticipate the top 5 questions or concerns stakeholders might raise:
- Business impact questions
- Scope/timeline concerns
- Technical feasibility doubts
- 'Why didn't you...' alternatives
- Edge cases they'll worry about

For each, draft a concise response backed by research or design rationale."
```

### 3. Run the review
_Sync meeting or async Loom/prototype walkthrough._

For async:
```
Prompt: "Create an async stakeholder review package:
1. Loom script: Walk through the presentation structure from step 1
2. Prototype link with viewing instructions
3. Structured feedback form: 
   - Does this solve the stated problem? (Yes/Partially/No)
   - Any concerns about the approach?
   - Any missing requirements?
   - Approved to proceed? (Yes / Yes with changes / Needs revision)
4. Deadline for feedback: [date]
Post to project Slack channel and tag all stakeholders."
```

### 4. Process feedback
```
Prompt: "Here's the stakeholder feedback: [paste all feedback].
Categorize:
- Approved: No changes needed
- Approved with changes: What specifically needs to change
- Needs revision: What's fundamentally off
- Out of scope: Feedback that's valid but beyond current scope (park for later)
- Clarification needed: Ambiguous feedback that needs follow-up

For 'approved with changes,' assess effort and impact of each change.
Post the categorized feedback to Notion."
```

### 5. Announce decision
```
Prompt: "Post to Slack:
'[Project] stakeholder review: [APPROVED / APPROVED WITH CHANGES / REVISION NEEDED]
[If approved]: Moving to handoff. Engineering kickoff: [date].
[If changes]: Making [N] adjustments. Updated design by [date].
[If revision]: Key concern: [one-liner]. Revisiting [specific aspect].
Decision documented: [Notion link]. Next steps: [action].'
Tag PM and engineering lead."
```

## Integrations
- **Slack**: Review request, feedback collection, decision announcement
- **Notion**: Decision documentation, feedback log
- **Figma**: Prototype link
- **Loom**: (Optional) Async video walkthrough
- **Calendar**: Review meeting (if sync)
- **Google Meet/Zoom**: Meeting facilitation

## Templates
- `assets/feedback-log.md`

## Definition of Done
- [ ] Stakeholder review conducted (sync or async)
- [ ] All feedback logged and categorized
- [ ] Decision documented: Approved / Changes / Revision
- [ ] Required changes (if any) identified and scheduled
- [ ] Team notified of decision and next steps

## Customization Notes
- For startups with small teams: this can be a 10-min Slack thread
- For enterprise: may need formal presentation with multiple stakeholder groups
- Never surprise stakeholders — if you've been sharing updates throughout, this should be a formality
- The best stakeholder reviews are boring because the stakeholders already know what to expect

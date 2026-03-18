---
name: research-plan
description: >-
  Creates a structured research plan with methods, participants, timeline, and logistics. Use after gap analysis to plan how to close knowledge gaps. Triggers on: "research plan", "plan research", "interview plan", "how should we research", "study design".
---

# 01b — Research Plan

## Purpose
Turn prioritized research gaps into a concrete plan with methods, participants, timeline, and logistics. This is the contract between design and the broader team about what research will happen and when.

## When to Use
- After gap analysis is complete
- When research scope changes mid-project

## Inputs
- Prioritized research gaps (from `01a-gap-analysis`)
- Project timeline constraints (from `00-kickoff`)
- Team config (from `config/team-config.md`)

## Outputs
- [ ] **Research plan** → `templates/research-plan.md` filled out → posted to Notion
- [ ] **Recruitment criteria** defined (if interviews/testing needed)
- [ ] **Research plan approved** by PM
- [ ] **Slack update** with plan summary and timeline

## Steps

### 1. Match methods to gaps
```
Prompt: "Here are our prioritized research gaps: [paste from gap tracker].
For each gap, recommend the best research method and justify why. Consider:
- User interviews (exploratory, deep understanding)
- Analytics review (behavioral patterns, quantitative validation)
- Competitive analysis (what exists, market patterns)
- Survey (broad validation, quantitative)
- Diary study (longitudinal behavior)
- Usability testing (existing product issues)
- Expert review (heuristic evaluation)
- Support ticket analysis (known pain points)
Group methods that can be combined into single sessions."
```

### 2. Draft research plan
```
Prompt: "Create a research plan using the template at templates/research-plan.md. Include:
- Research objectives (tied to gaps)
- Methods selected with rationale
- Participant criteria and sample size
- Timeline with milestones
- Required resources (tools, incentives, access)
- Risks and mitigations
Keep the plan to 1-2 pages. Practical, not academic."
```

### 3. Define recruitment criteria
```
Prompt: "For the interview/testing portions of this plan, define:
- Screener criteria (must-have vs nice-to-have attributes)
- Sample size and composition
- Recruitment channels (existing users, panel, social, internal)
- Incentive recommendation
- Scheduling approach (Calendly, manual, etc.)"
```

### 4. Get approval
```
Prompt: "Draft a Slack message for the project channel that summarizes the research plan:
- What we're researching and why
- Methods and timeline
- What we need from the team (participant access, data access, review time)
- Ask PM for async approval by [date]
Tag the PM and relevant stakeholders."
```

## Integrations
- **Notion**: Post research plan to project page
- **Slack**: Post summary, get approval, coordinate recruitment
- **Calendar**: Block time for research sessions
- **Recruitment tool**: (Respondent, User Interviews, internal panel) Set up screener

## Templates
- `templates/research-plan.md` — Full research plan template

## Definition of Done
- [ ] Research plan covers all prioritized gaps
- [ ] Methods, timeline, and participants defined
- [ ] PM has reviewed and approved the plan
- [ ] Research sessions scheduled or recruitment started

## Customization Notes
- For startups without a research budget: lean toward analytics review + guerrilla interviews
- For enterprise: add compliance/legal review step for research involving customer data
- Adjust sample sizes based on your context — 5 interviews is often enough for qualitative patterns

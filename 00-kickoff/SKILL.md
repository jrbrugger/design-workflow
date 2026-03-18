---
name: design-kickoff
description: >-
  Frames the design problem, aligns stakeholders, and sets up project infrastructure. Use when starting a new design project, feature initiative, or redesign. Triggers on: "kick off", "start a project", "new design project", "project brief", "stakeholder alignment".
---

# 00 — Project Kickoff

## Purpose
Frame the problem, align stakeholders on scope, and set up project infrastructure before any research or design begins. This prevents the #1 failure mode: designing solutions to the wrong problem.

## When to Use
- New feature or product initiative
- Redesign of an existing flow
- Design exploration requested by stakeholders
- Start of any project that will consume >1 week of design time

## Inputs
- Stakeholder request (email, Slack message, brief, or verbal)
- Business context (OKRs, metrics, strategy docs)
- Any existing research or data

## Outputs
- [ ] **Project brief** → `templates/project-brief.md` filled out → posted to Notion
- [ ] **Stakeholder map** → `templates/stakeholder-map.md` filled out
- [ ] **Project channel** created in Slack
- [ ] **Project page** created in Notion from hub template
- [ ] **Kickoff summary** posted to Slack

## Steps

### 1. Gather context
```
Prompt: "I'm starting a new design project. Here's what I know: [paste stakeholder request]. 
Search for any related context in our Notion workspace and Slack history. 
Summarize what we know, what's ambiguous, and what's missing."
```

### 2. Draft project brief
```
Prompt: "Using the context above, fill out the project brief template at 
templates/project-brief.md. Flag any fields where we're making assumptions 
vs. working from evidence."
```

Review the brief. Edit anything that feels off. The brief should fit on one page.

### 3. Map stakeholders
```
Prompt: "Based on this project brief, fill out the stakeholder map at 
templates/stakeholder-map.md. Identify: decision-maker, key influencers, 
subject matter experts, and who needs to be informed."
```

### 4. Set up infrastructure
```
Prompt: "Create the following:
1. A Notion page for this project using our project hub template
2. A Slack channel named #proj-[project-name]
3. Post the project brief summary to the new Slack channel
4. Tag [stakeholder names] in the post asking for async review by [date]"
```

### 5. Kickoff alignment
```
Prompt: "Draft a kickoff message for the project Slack channel that includes:
- One-paragraph problem summary
- Key assumptions we're making
- What we need from each stakeholder
- Proposed timeline
- Link to the full brief in Notion"
```

## Integrations
- **Notion**: Create project page from template, post brief
- **Slack**: Create channel, post kickoff message, tag stakeholders
- **Google Drive**: Store any uploaded reference docs in project folder
- **Calendar**: (Optional) Schedule kickoff meeting if sync alignment needed

## Definition of Done
- [ ] Project brief reviewed and confirmed by PM/stakeholder
- [ ] Slack channel active with kickoff message posted
- [ ] Notion project page created with brief linked
- [ ] No open questions blocking research start

## Customization Notes
- If your org uses Confluence instead of Notion, swap the doc creation steps
- If you work async-first, the Slack post replaces a kickoff meeting
- For solo/freelance: skip stakeholder map, simplify brief to problem + constraints + timeline

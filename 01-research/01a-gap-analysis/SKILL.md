---
name: research-gap-analysis
description: >-
  Audits existing knowledge and identifies research gaps by scoring assumptions on confidence and impact. Use when starting research, identifying unknowns, or when new information introduces uncertainty. Triggers on: "what do we know", "gap analysis", "research gaps", "audit assumptions", "what don't we know".
---

# 01a — Research Gap Analysis

## Purpose
Before planning research, audit what we already know vs. what we're guessing. This prevents redundant research and surfaces the highest-value unknowns. Every assumption in the project brief becomes either "validated" or "needs research."

## When to Use
- Start of every research phase
- After research validation reveals remaining gaps (loop back)
- When new stakeholder input introduces uncertainty

## Inputs
- Project brief (from `00-kickoff`)
- Existing research (prior studies, analytics, support tickets)
- Assumptions list from project brief

## Outputs
- [ ] **Gap tracker** → `templates/gap-tracker.md` filled out
- [ ] **Prioritized research questions** ranked by impact × uncertainty
- [ ] **Gap analysis summary** posted to Notion project page
- [ ] **Slack update** in project channel

## Steps

### 1. Audit existing knowledge
```
Prompt: "Here's our project brief: [paste or link]. 
Search our Notion workspace for any existing research related to [topic/user/problem]. 
Also search Slack for relevant discussions. 
Compile everything we already know into a structured summary with confidence levels (high/medium/low) for each claim."
```

### 2. Extract assumptions
```
Prompt: "From the project brief and existing knowledge, extract every assumption we're making. 
For each assumption, rate:
- Confidence (1-10): How sure are we this is true?
- Impact (1-10): How much does it matter if we're wrong?
- Evidence: What supports this? (data, anecdote, nothing)
Format this as the gap tracker template."
```

### 3. Identify gaps
```
Prompt: "From the gap tracker, identify the top research gaps — assumptions with 
high impact but low confidence. Group them into themes. 
For each gap, suggest what research method would best close it 
(interviews, analytics review, competitive analysis, survey, etc.)"
```

### 4. Prioritize
```
Prompt: "Rank the research gaps by priority using this formula: 
Priority = Impact × (10 - Confidence). 
The top 3-5 gaps become our research plan inputs. 
Format as a numbered list with the recommended method for each."
```

### 5. Document and share
```
Prompt: "Create a gap analysis summary for our Notion project page that includes:
- What we know (high confidence)
- What we think we know (medium confidence)  
- What we don't know (research gaps, prioritized)
Then post a short summary to the project Slack channel."
```

## Integrations
- **Notion**: Search existing research, post gap analysis to project page
- **Slack**: Search for relevant discussions, post summary update
- **Analytics**: (If available) Pull relevant metrics to validate/invalidate assumptions
- **Google Drive**: Check for prior research reports

## Templates
- `templates/gap-tracker.md` — Assumption × Confidence × Impact matrix

## Definition of Done
- [ ] All assumptions from the project brief are logged in the gap tracker
- [ ] Each assumption has a confidence and impact score
- [ ] Top 3-5 research gaps are identified and prioritized
- [ ] Gap analysis posted to Notion and summarized in Slack

## Customization Notes
- Adjust the priority formula if your org weighs things differently
- For fast-moving startups, you might skip the formal scoring and just identify the top 3 unknowns conversationally
- If you have a UX research repository (e.g., Dovetail, Condens), search that instead of/in addition to Notion

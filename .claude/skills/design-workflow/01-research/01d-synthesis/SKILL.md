---
name: 01d-synthesis
description: >-
  Transforms raw research data into structured insights through affinity clustering and pattern analysis. Use after data collection to find patterns and key findings. Triggers on: "synthesize research", "analyze interviews", "find patterns", "insight report", "research findings".
---

# 01d — Research Synthesis

## Purpose
Transform raw research data into structured insights. This is where patterns emerge from individual data points. AI accelerates pattern-finding, but the designer validates interpretations and guards against false patterns.

## When to Use
- After data collection is complete (or after a meaningful batch of sessions)
- Can run incrementally — synthesize after every 3-4 interviews to adapt your guide

## Inputs
- Structured interview notes (from `01c-data-collection`)
- Analytics data and exports
- Competitive analysis
- Survey responses

## Outputs
- [ ] **Insight report** → `assets/insight-report.md` filled out → posted to Notion
- [ ] **Affinity clusters** — grouped themes with supporting evidence
- [ ] **Key findings** — top 5-7 insights ranked by confidence and impact
- [ ] **Updated gap tracker** — which gaps are now closed
- [ ] **Slack summary** posted to project channel

## Steps

### 1. Aggregate raw data
```
Prompt: "Here are my structured notes from [N] interviews: [paste or link to all notes].
Extract every distinct observation, quote, and data point. 
Tag each with: participant ID, theme (you suggest themes), and sentiment (+/-/neutral).
Output as a flat list I can review."
```

### 2. Cluster into themes
```
Prompt: "From the tagged observations, group them into affinity clusters. 
For each cluster:
- Theme name (short, descriptive)
- Number of participants who mentioned it
- Key supporting quotes (2-3 strongest)
- Strength of evidence (strong/moderate/weak)
- Connection to original research gap
Order clusters by frequency × strength of evidence."
```

### 3. Triangulate with quantitative data
```
Prompt: "Cross-reference the qualitative themes with our analytics data: [paste or describe].
Which themes are supported by quantitative evidence? 
Which contradict it? 
Which have no quantitative signal (and what would we need to measure)?
This triangulation increases our confidence scores."
```

### 4. Draft insight report
```
Prompt: "Synthesize everything into an insight report using assets/insight-report.md.
Structure as:
- Executive summary (3 sentences max)
- Top insights (5-7, each with: finding, evidence, confidence, implication)
- Surprises (things we didn't expect)
- Confirmed assumptions (from gap tracker)
- Remaining gaps (what we still don't know)
Write for a PM/stakeholder audience — clear, actionable, no jargon."
```

### 5. Update gap tracker and share
```
Prompt: "Update the gap tracker from 01a-gap-analysis:
- Mark validated/invalidated assumptions
- Update confidence scores based on evidence
- Flag any NEW gaps that emerged from research
Then post the insight report to Notion and draft a Slack summary 
for the project channel (5-bullet max)."
```

## Integrations
- **Notion**: Post insight report, update research database
- **Slack**: Post findings summary, tag PM for review
- **Miro/FigJam**: (Optional) Visual affinity mapping for team workshops

## Templates
- `assets/insight-report.md` — Structured findings report

## Definition of Done
- [ ] All raw data coded and clustered into themes
- [ ] Top 5-7 insights documented with evidence and confidence levels
- [ ] Gap tracker updated with validation status
- [ ] Insight report posted to Notion
- [ ] Summary shared in Slack

## Customization Notes
- For large-scale research (15+ interviews), consider using Dovetail for tagging and clustering
- Incremental synthesis after every 3-4 sessions lets you adapt your interview guide
- If you have a research ops team, they may handle raw coding — you focus on interpretation

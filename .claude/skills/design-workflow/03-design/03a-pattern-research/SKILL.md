---
name: 03a-pattern-research
description: >-
  Surveys existing UI patterns, interaction models, and design conventions relevant to the design challenge. Use at the start of design to ground ideation in existing solutions. Triggers on: "pattern research", "UI patterns", "how do others solve", "design references", "competitive UI".
---

# 03a — Pattern Research

## Purpose
Before designing from scratch, survey how others have solved similar problems. Fetch existing UI patterns, interaction models, and design conventions that are relevant to the design challenge. This grounds ideation in reality and prevents reinventing the wheel.

## When to Use
- Start of every design phase, after problem lock (02c)
- When exploring a new interaction pattern or component type
- When the design challenge involves a domain you haven't designed for before

## Inputs
- Locked design challenge brief (from `02c-problem-lock`)
- Competitive analysis (from `01c-data-collection`)
- JTBD and personas (from `02a-ux-artifacts`)

## Outputs
- [ ] **Pattern library** → 15-25 relevant screenshots/references organized by pattern type
- [ ] **Pattern analysis** → `assets/pattern-analysis.md` — what works, what doesn't, applicable patterns
- [ ] **Saved to Notion** under project design references
- [ ] **Shared in Slack** for team visibility

## Steps

### 1. Define what to look for
```
Prompt: "Based on our design challenge: [paste design challenge brief],
identify the 5-7 key UI patterns or interaction models we need to research.
Think about:
- Core task flows (e.g., checkout, onboarding, dashboard layout)
- Data display patterns (tables, cards, charts, lists)
- Navigation patterns (sidebar, tabs, breadcrumbs)
- Input patterns (forms, filters, search)
- Feedback patterns (empty states, errors, success, loading)
- Mobile-specific patterns (if applicable)
List each with what specifically to look for."
```

### 2. Collect pattern examples
```
Prompt: "For each pattern we identified, search the web for the best examples.
Look at:
- Direct competitors (from our competitive analysis)
- Adjacent products (similar complexity or user type)
- Best-in-class products (regardless of industry)
- Design pattern libraries (Mobbin, Page Flows, UI Patterns, Pttrns)

For each example:
- Product name
- Screenshot description or URL
- What pattern it demonstrates
- What it does well
- What it does poorly
- Applicability to our challenge (high/medium/low)

Aim for 15-25 examples across all patterns."
```

### 3. Analyze and synthesize
```
Prompt: "From the collected patterns, fill out the pattern analysis template:
- Group by pattern type
- Identify conventions (what most products do — table stakes)
- Identify differentiators (what only the best do)
- Identify anti-patterns (common mistakes to avoid)
- Recommend which patterns to adopt, adapt, or avoid for our design
- Note any accessibility or technical considerations"
```

### 4. Document and share
```
Prompt: "Create a pattern research page in Notion under the project hub.
Organize as: Pattern type → Examples → Analysis → Recommendation.
Post to the project Slack channel:
'Pattern research complete for [project]. [N] examples across [N] pattern types.
Key conventions: [2-3 bullets]. Interesting differentiators: [2-3 bullets].
Full reference: [Notion link]. Will feed into ideation.'"
```

## Integrations
- **Notion**: Store pattern library and analysis
- **Slack**: Share findings
- **Web search**: Find examples across products
- **Mobbin/Page Flows**: (If subscribed) Structured pattern search
- **Figma**: (Optional) Screenshot collection in a reference frame

## Templates
- `assets/pattern-analysis.md`

## Definition of Done
- [ ] 5-7 pattern types identified and researched
- [ ] 15-25 examples collected with analysis
- [ ] Conventions, differentiators, and anti-patterns documented
- [ ] Recommendations for our design documented
- [ ] Shared with team

## Customization Notes
- If you have a Mobbin or Page Flows subscription, use those for faster pattern collection
- For B2B: look at Stripe, Linear, Notion, Figma as gold-standard references
- For B2C: look at the app store top charts in your category
- Keep pattern research timeboxed — 2-4 hours max. It's input, not the work itself.

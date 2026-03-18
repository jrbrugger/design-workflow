---
name: research-plan
description: >-
  Structure and write UX research briefs with 11 sections, then auto-publish to Notion. Use when starting research, scoping a study, or writing a research brief. Triggers on: "research plan", "research brief", "plan research", "write a brief", "11-section brief".
---

# /research-plan

**Structure and write UX research briefs with 11 sections.**

A Claude Skill that turns a rough research idea into a complete, stakeholder-ready research brief.

---

## How to Use

### Quick Start

```
/research-plan

I'm planning research on [topic].
The problem is [problem].
Target users are [segment].
```

### What Happens

1. You describe your research context
2. Claude asks 3–5 clarifying questions
3. Claude generates a complete 11-section research brief
4. You review and approve the brief
5. Claude publishes to your Notion Research Repository and returns the URL

### Tips for Strong Prompts

- **Be specific about the problem**, not the solution. "Users abandon checkout" is better than "We need a new checkout flow."
- **Name the user segment.** "SME business owners aged 30–50" beats "our users."
- **Mention what you already know.** Existing data, past research, analytics — share it so the brief builds on reality, not assumptions.
- **State the business context.** Is this for a new feature? A redesign? A pitch? The brief adapts to the stakes.

---

## The 11 Sections

Every research brief follows this structure. Each section builds on the previous one.

### 1. Project Scope

**What it is:** The problem you're investigating and why it matters now.

**What to include:**
- The specific problem or opportunity
- Why this research is happening now (trigger event, business need, user signal)
- What's in scope and out of scope
- Who requested or sponsors this research

**How to write it:**
- Lead with the problem, not the project name
- Connect to a real business or user need
- Be explicit about boundaries — what you will NOT investigate

**Example pattern:**
> Users of [product] are experiencing [problem], which is causing [business impact]. This research will investigate [specific aspect] to inform [decision]. Out of scope: [what you're not looking at].

---

### 2. Research Goals

**What it is:** 2–4 things you want to learn. Not deliverables — learnings.

**What to include:**
- Goals phrased as "Understand…", "Identify…", "Evaluate…", "Discover…"
- Each goal should be achievable through research (not design or engineering)
- Goals should be specific enough to know when you've achieved them

**How to write it:**
- Use action verbs: Understand, Identify, Evaluate, Discover, Map, Assess
- Avoid "Validate" or "Prove" — research reveals, it doesn't confirm
- Each goal should connect to a decision you need to make

**Common mistakes:**
- ❌ "Validate our new design" (that's usability testing, not a goal)
- ❌ "Understand everything about users" (too broad)
- ✅ "Identify the top 3 friction points in the onboarding flow"
- ✅ "Understand how SME owners currently track their business finances"

---

### 3. Target Group

**What it is:** The specific users you'll study.

**What to include:**
- Demographics (if relevant): age, role, experience level
- Behavioral criteria: what they do, how often, what tools they use
- Recruitment criteria: how you'll find them
- Sample size and segmentation (if applicable)

**How to write it:**
- Define by behavior first, demographics second
- Be specific enough to recruit against
- Note any exclusion criteria

**Example pattern:**
> Primary: [Role] who [behavior] at least [frequency]. Secondary: [Role] who [different behavior]. Exclude: [who you're not studying and why].

---

### 4. Known Insights

**What it is:** What you already know — from data, past research, or stakeholder input. Separated into facts and assumptions.

**What to include:**
- **Facts:** Analytics data, previous research findings, support tickets, NPS scores
- **Assumptions:** Team beliefs, stakeholder opinions, design intuitions
- Source for each item (where did this come from?)

**How to write it:**
- Clearly label facts vs. assumptions
- Cite sources: "Analytics (Q4 2025)", "User interviews (March 2026)", "Stakeholder input"
- Be honest about what's assumption vs. evidence
- This section prevents you from researching things you already know

**Why it matters:**
This is where most briefs fail. Teams skip it and end up re-researching known problems or building on unexamined assumptions. Erika Hall calls this "organizational learning" — knowing what you already know.

---

### 5. Main Research Question

**What it is:** One sentence that captures the core question your research answers.

**What to include:**
- A single, clear question
- Phrased as "How…", "What…", "Why…", or "In what ways…"
- Answerable through the methods you'll use

**How to write it:**
- Write it last (after goals and sub-questions are clear)
- It should encompass all your sub-questions
- If you can't write one sentence, your research scope is too broad

**Common mistakes:**
- ❌ "Is our product good?" (too vague, not actionable)
- ❌ "Should we build feature X?" (that's a business decision, not a research question)
- ✅ "How do SME business owners currently manage their calendar and scheduling workflows, and where do they experience friction?"

---

### 6. Sub-Questions

**What it is:** 3–6 specific questions that, when answered, will answer the main question.

**What to include:**
- Questions that map to your research goals
- A mix of "what", "how", and "why" questions
- Questions that are answerable with your chosen methods

**How to write it:**
- Each sub-question should clearly connect to a research goal
- Order them from broad context to specific details
- They should collectively cover the main research question
- Tag each with the method you'll use to answer it

**Example pattern:**
1. What is the current workflow for [task]? *(Contextual inquiry)*
2. Where do users experience friction in [process]? *(Usability testing)*
3. How do users work around [problem]? *(Interviews)*
4. What mental models do users have about [concept]? *(Card sorting)*

---

### 7. Hypotheses

**What it is:** Testable beliefs about what you expect to find.

**What to include:**
- 2–4 hypotheses phrased as testable statements
- Based on your known insights and assumptions
- Each should be falsifiable — research can prove them wrong

**How to write it:**
- Format: "We believe [statement] because [reasoning]. We'll know this is true/false when [evidence]."
- Base them on your assumptions from Section 4
- Be willing to be wrong — that's the point

**Why it matters:**
Hypotheses make your assumptions explicit. Without them, confirmation bias creeps in. You'll see what you expect instead of what's actually there.

---

### 8. Research Methods

**What it is:** How you'll conduct the research.

**What to include:**
- Method(s): Interviews, contextual inquiry, usability testing, surveys, competitive analysis, diary studies, card sorting, etc.
- Why this method fits your questions
- Participant count per method
- Duration and format (remote/in-person, moderated/unmoderated)

**How to write it:**
- Match methods to question types:
  - "What do people do?" → Contextual inquiry, observation
  - "Why do they do it?" → Interviews, diary studies
  - "Can they use it?" → Usability testing
  - "What do they prefer?" → Surveys, A/B testing, card sorting
  - "What exists?" → Competitive analysis, desk research
- Justify your method choice — don't just list it
- Include participant count with reasoning

**Reference — Research Types (from *Just Enough Research*):**
| Type | Purpose | When to Use |
|------|---------|-------------|
| Generative | Discover problems and opportunities | Early/exploratory phase |
| Descriptive | Understand current behavior | Before designing |
| Evaluative | Test solutions against user needs | During/after design |
| Causal | Understand why something happens | When you need to explain patterns |

---

### 9. Test Metrics

**What it is:** How you'll measure success — with specific thresholds.

**What to include:**
- Quantitative metrics with targets (e.g., "Task completion rate > 80%")
- Qualitative indicators (e.g., "Users can describe the value proposition in their own words")
- Comparison baselines (current state vs. target)

**How to write it:**
- Every metric needs a number or clear threshold
- Include both quantitative and qualitative measures
- State what "good enough" looks like
- Reference baselines when available

**Common mistakes:**
- ❌ "Users find it easy" (not measurable)
- ❌ "High satisfaction scores" (no threshold)
- ✅ "Task completion rate ≥ 85% (current baseline: 62%)"
- ✅ "SUS score ≥ 72 (above industry average)"
- ✅ "≥ 4 of 6 participants can complete [task] without assistance"

---

### 10. Business Impact

**What it is:** How this research connects to business outcomes.

**What to include:**
- Which business metric this research supports (revenue, retention, conversion, cost reduction, NPS)
- Expected impact category: Quality, Cost, or Sales
- How findings will be used (inform design, prioritize backlog, change strategy)
- Who the stakeholders are and what decisions they'll make with the findings

**How to write it:**
- Connect research goals to business KPIs
- Be specific about how findings translate to action
- Name the decision-makers who will use this research
- Frame impact in terms stakeholders care about

**Example pattern:**
> This research directly supports [business metric] by [how]. Findings will inform [specific decisions] for [stakeholders]. Expected impact: [quality/cost/sales] improvement in [area].

---

### 11. Planning & Timeline

**What it is:** A weekly breakdown of activities, deliverables, and dependencies.

**What to include:**
- Week-by-week plan (typically 3–6 weeks total)
- Activities per week with deliverables
- Dependencies (recruitment, stakeholder reviews, tool access)
- Key milestones and checkpoints

**How to write it:**
- Use a simple week-by-week format
- Include buffer time for recruitment delays
- Mark dependencies explicitly
- End with deliverables and share-out date

**Typical timeline:**
| Week | Activities | Deliverable |
|------|-----------|-------------|
| 1 | Finalize brief, recruit participants, prepare materials | Approved brief + screener |
| 2 | Conduct sessions (3–4) | Raw notes + recordings |
| 3 | Conduct remaining sessions + begin analysis | Session summaries |
| 4 | Analysis: affinity mapping, pattern identification | Draft findings |
| 5 | Synthesize insights, create recommendations | Research report |
| 6 | Present to stakeholders, hand off to design | Presentation + next steps |

---

## Output Format

The skill generates a complete research brief in markdown format with all 11 sections filled in. After approval, the brief is automatically published to your Notion Research Repository with all properties mapped. The output is designed to be:

- **Auto-published** to Notion with structured properties and full brief content
- **Stakeholder-friendly** language (no jargon without explanation)
- **Actionable** — every section connects to decisions

---

## Common Mistakes to Avoid

1. **Starting with methods instead of questions.** Don't say "I want to do interviews." Say "I need to understand X" — then pick the right method.

2. **Making goals too broad.** "Understand our users" is not a research goal. "Identify the top 3 reasons users abandon onboarding" is.

3. **Skipping known insights.** If you don't document what you already know, you'll waste time rediscovering it.

4. **Writing leading research questions.** "Why don't users like our checkout?" assumes they don't. "How do users experience our checkout flow?" is neutral.

5. **No success metrics.** Without thresholds, you can't tell stakeholders whether the research succeeded.

6. **Treating hypotheses as conclusions.** Hypotheses are meant to be tested, not confirmed. If you're not willing to be wrong, it's not a hypothesis.

7. **Unrealistic timelines.** Recruitment alone takes 1–2 weeks. Build in buffer.

8. **Forgetting business impact.** Research that doesn't connect to business decisions gets ignored. Always answer: "So what?"

---

## Step 5: Publish to Notion

After the user reviews and approves the research brief, publish it to their Notion Research Repository using the Notion MCP tools.

### Configuration

Load settings from `config.json` (in this skill's directory):

```json
{
  "notion_data_source_id": "327eac60-25b7-80d4-8313-000b001015cc",
  "default_app": "Rabobank",
  "researcher_name": "Jack Brugger",
  "default_team": "Design",
  "apps": ["Rabobank", "DexScreener", "Resolv", "Qogita", "RegenOS"]
}
```

### Publishing

Use the Notion MCP `notion-create-pages` tool with the data source ID from config.

### Property Mapping

| # | Property | Type (Notion) | Source / Value |
|---|----------|---------------|----------------|
| 1 | **Title** | Title | Project name from the brief |
| 2 | **App** | Select | Select — Rabobank, DexScreener, Resolv, Qogita, RegenOS |
| 3 | **Research Type** | Select | Select — Generative, Descriptive, Evaluative, Causal, Concept Testing, Usability Testing, User Interviews, Competitive Analysis |
| 4 | **Status** | Status | `Planning` |
| 5 | **Main Research Question** | Text | From section 5 of the brief |
| 6 | **Target Group** | Text | From section 3 of the brief |
| 7 | **Success Metrics** | Text | From section 9 of the brief |
| 8 | **Business Impact** | Select | Select — Higher Quality, More Sales, Lower Cost, Multiple |
| 9 | **Timeline** | Text | From section 11 of the brief |
| 10 | **Team/Tribe** | Text | From config `default_team` or ask user |
| 11 | **Date Started** | Date | Today (YYYY-MM-DD) |
| 12 | **Key Findings** | Text | Leave blank |
| 13 | **Next Steps** | Text | Leave blank |

### Page Content

Include the full 11-section research brief as markdown in the page body.

### After Publishing

Return the Notion page URL to the user.

### Fallback

If the Notion MCP is unavailable or the connection fails, output the complete brief in markdown so the user can manually copy it into Notion.

---

## Inputs

- Prioritized research gaps (from `01a-gap-analysis`, if available)
- Project timeline constraints (from `00-kickoff`, if available)
- Team config (from `config/team-config.md`)

## Integrations

- **Notion**: Publish research brief to Research Repository (via MCP)
- **Slack**: Post summary, get approval, coordinate recruitment
- **Calendar**: Block time for research sessions
- **Recruitment tool**: (Respondent, User Interviews, internal panel) Set up screener

## Definition of Done

- [ ] Research brief covers all 11 sections
- [ ] Methods, timeline, and participants defined
- [ ] User has reviewed and approved the brief
- [ ] Brief published to Notion Research Repository (or markdown exported)

## Customization Notes

- For startups without a research budget: lean toward analytics review + guerrilla interviews
- For enterprise: add compliance/legal review step for research involving customer data
- Adjust sample sizes based on your context — 5 interviews is often enough for qualitative patterns

---

## References

- `references/research-brief-template.md` — Blank template for copy/paste
- `references/rbb-calendar-example-annotated.md` — Annotated real-world example (Calendar Widget)
- `references/research-brief-checklist.md` — 50+ validation items before sharing your brief

---

## Credits

Framework based on *Just Enough Research* by Erika Hall (A Book Apart, 2013).
Built by Jack Brugger for research-driven product design.

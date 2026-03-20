---
name: 01c-competitive-analysis
description: >-
  Conducts structured competitive analysis across direct competitors, adjacent products,
  and best-in-class references. Produces a populated competitive matrix, detailed UX
  profiles, opportunity map, and strategic positioning implications. Use at the start of
  any research or design phase, or when entering a new market. Triggers on: "competitive
  analysis", "competitors", "competitive landscape", "how does X compare", "what are
  competitors doing", "market landscape", "comp research".
---

# 01c-competitive-analysis — Competitive Analysis

**Map the competitive landscape before designing in it.**

Produces a structured analysis of direct competitors, adjacent products, and best-in-class
references — covering business model, UX patterns, onboarding, positioning, and white space
opportunities. Runs as part of `01c-data-collection` or as a standalone sprint.

---

## Purpose

Competitive analysis answers three questions before design begins:

1. **What's table stakes?** — what every product in this space does, so you don't ship
   below the baseline
2. **What do leaders do differently?** — the patterns that separate good from great
3. **Where is the white space?** — problems no competitor owns cleanly, which is your
   opportunity

Without it, you're designing blind to what users already know and expect.

## When to Use

- Start of every project as part of `01c-data-collection`
- When entering a new product category or market
- When a signal mining sprint (`01-signal-mining`) surfaces frequent competitor comparisons
- Before `03a-pattern-research` — competitive analysis informs which products to pull
  patterns from
- When a PM or stakeholder asks "what are competitors doing?"

## Inputs

- Project brief and design challenge (from `00-kickoff`)
- Problem space and target user segment (from `01a-gap-analysis`)
- Competitor names if known (optional — can be discovered in Step 1)
- Signal mining output if run (from `01-signal-mining`) — competitor mentions already surfaced

## Outputs

- [ ] **Competitive matrix** → `assets/competitive-matrix.md` fully populated
- [ ] **Competitor profiles** (5–8 products) with UX deep-dives
- [ ] **Opportunity map** — table stakes, differentiators, white space
- [ ] **Positioning implications** — where our product can win
- [ ] **Posted to Notion** project page under Research
- [ ] **Shared in Slack** with summary

---

## Competitor tiers

Structure the analysis across three tiers. Each teaches you something different.

**Tier 1 — Direct competitors**
Same problem, same user. These set the baseline and define user expectations. Users
will compare you to these products explicitly.

**Tier 2 — Adjacent products**
Similar user, different problem (or similar problem, different user). Often have relevant
UX patterns even if they're not direct competition. Good for escaping category conventions.

**Tier 3 — Best-in-class references**
Not competitors at all, but leaders in a relevant pattern — onboarding, empty states,
data-heavy dashboards, complex filtering, etc. Use these to raise the ceiling on what
"great" looks like regardless of category.

For most projects: 3–4 Tier 1, 2–3 Tier 2, 1–2 Tier 3.

---

## Steps

### 1. Identify the competitive set

```
Prompt: "We're building [product description] for [target user].
The core problem we're solving is [problem statement].

Identify the competitive landscape across three tiers:

Tier 1 — Direct competitors: same problem, same user. List 4–6.
Tier 2 — Adjacent products: overlapping user or overlapping problem. List 3–4.
  Think about: tools users use before/after ours, partial substitutes, different
  approaches to the same job.
Tier 3 — Best-in-class references: who does [the key UX challenge] best,
  regardless of industry? List 2–3.

For each, include: product name, URL, one-sentence description, and why
it belongs in this tier."
```

Cross-reference with signal mining output — if users mentioned specific products in
reviews or Reddit threads, those are confirmed Tier 1.

---

### 2. Desk research — business model and positioning

```
Prompt: "For each competitor in our set, research their business model and positioning.
Find:
- Who is the stated target user?
- What is their primary value proposition (from their homepage/marketing)?
- What is their pricing model and tier structure?
- How long have they been in market? Funding/scale if public?
- What does their G2/Capterra rating cluster around? (Check reviews from 01-signal-mining)
- How do they describe themselves vs. competitors?

Format as a positioning table: Product | Target User | Value Prop | Pricing | Key Differentiator."
```

---

### 3. UX deep-dive — flows and patterns

This is the core of the skill. For each Tier 1 and Tier 2 competitor, work through
the key flows that overlap with your design challenge.

```
Prompt: "Conduct a UX deep-dive for [competitor name].
I need to understand how they handle: [list the 3–5 key flows relevant to our challenge,
e.g., onboarding, core task, empty states, error handling, settings/config].

For each flow:
- What is the entry point?
- How many steps? What is the information architecture?
- What UI patterns do they use? (e.g., wizard, progressive disclosure, inline editing)
- What works well? (be specific — not just 'clean UI')
- What is frustrating or confusing? (refer to signal mining reviews if available)
- What assumptions does this flow make about the user's technical level?
- Any notable micro-interactions, empty states, or error patterns?

If you can access the live product, use web search or publicly available screenshots.
Flag where you're inferring from marketing pages vs. confirmed from the live product."
```

Repeat for each competitor. Do Tier 1 at full depth. Tier 2 at half depth (focus on
the specific patterns that are relevant to our challenge). Tier 3 focused only on the
specific pattern they're best at.

---

### 4. Populate the competitive matrix

```
Prompt: "Using the research from steps 2 and 3, fill out the competitive matrix
(assets/competitive-matrix.md) for all products in our set.

Dimensions to evaluate (rate each: Strong / Adequate / Weak / N/A):
- Onboarding: time to first value, guidance quality
- Core task flow: efficiency, clarity, error prevention
- Information architecture: findability, navigation logic
- Data display: clarity of complex information
- Mobile experience: (if applicable)
- Empty states: guidance when there's no data yet
- Error handling: recovery paths, helpful messaging
- Customization: configurability vs. simplicity
- Collaboration: multi-user / sharing capabilities (if applicable)
- Performance signals: loading, responsiveness (as reported by users)

Add product-specific rows for any dimensions unique to this problem space."
```

---

### 5. Map the opportunity space

```
Prompt: "Based on the competitive matrix and UX deep-dives, map the opportunity space
across three categories:

Table stakes (must-have to be competitive):
- What does every Tier 1 competitor do that users expect as baseline?
- If we ship without these, users will immediately feel the absence.

Differentiators (what separates leaders from followers):
- What do the top 1–2 products do that others don't?
- What do users specifically praise in reviews of market leaders?

White space (underserved problems and unowned positioning):
- What do users consistently complain about across all competitors?
- What jobs are partially done but not elegantly solved?
- What user segment is nobody serving well?
- What approach or value prop is nobody claiming?

For each white space item: how hard is it to fill? Is it a product problem,
a UX problem, or a positioning problem?"
```

---

### 6. Derive positioning implications

```
Prompt: "Given the competitive landscape and opportunity map, recommend strategic
positioning for our product.

Answer:
1. Which table stakes must we match on day one?
2. Which differentiators should we adopt and make our own?
3. Which white space items are aligned with our strengths and worth owning?
4. What should we deliberately NOT do — where competitors are invested but the
   opportunity doesn't justify the complexity for us?
5. What is our one-sentence positioning that is meaningfully distinct in this market?

Frame this as implications for design decisions, not business strategy — connect each
point to a specific UX or product direction."
```

---

### 7. Document and share

```
Prompt: "Create a competitive analysis page in Notion under the project research hub.
Structure:
- Competitive landscape overview (one paragraph + the positioning table)
- Competitive matrix (full table)
- Competitor profiles (one section per product, Tier 1 at full depth)
- Opportunity map (table stakes / differentiators / white space)
- Implications for design (bulleted, actionable)

Then post to the project Slack channel:
'Competitive analysis complete for [project]. [N] products analyzed across [N] tiers.
Key finding: [one-sentence insight about white space or key differentiator].
Table stakes to match: [2–3 bullets]. Opportunity: [one-liner].
Full analysis: [Notion link].'
Tag PM."
```

---

## Integrations

- **Notion**: Store competitive matrix, profiles, opportunity map
- **Slack**: Share findings and tag PM
- **Web search**: Product research, review mining, screenshot discovery
- **01-signal-mining**: Pull competitor mentions already surfaced from reviews/Reddit
- **03a-pattern-research**: Feed Tier 1 + Tier 3 products as primary pattern sources

## Assets

- `assets/competitive-matrix.md` — Full matrix template (extended from 01c-data-collection)
- `assets/competitor-profile.md` — Single-product UX deep-dive template
- `assets/opportunity-map.md` — Table stakes / differentiators / white space output

## Definition of Done

- [ ] Competitive set identified across all three tiers (minimum 5 products total)
- [ ] Business model and positioning researched for all products
- [ ] Full UX deep-dive completed for all Tier 1 competitors
- [ ] Competitive matrix populated with ratings and evidence
- [ ] Opportunity map produced (table stakes, differentiators, white space)
- [ ] Positioning implications documented as design directions
- [ ] Posted to Notion and shared in Slack

---

## Scope and time guidance

| Project type | Recommended scope | Time budget |
|---|---|---|
| New product / greenfield | 3–4 Tier 1, 2 Tier 2, 2 Tier 3 | 4–6 hours |
| Feature addition | 2–3 Tier 1, 1 Tier 3 (for the specific pattern) | 2–3 hours |
| Redesign of existing product | 3 Tier 1, 2 Tier 2 | 3–4 hours |
| Quick competitive pulse | 3 Tier 1 (matrix only, no deep-dive) | 1 hour |

Timebox ruthlessly. Competitive analysis is input — it should inform design, not
replace it.

## Customization Notes

- **DeFi/crypto products**: also analyze protocol-level differentiators (TVL, fee
  structure, chain support, trust model) alongside UX patterns. Tier 3 references are
  often outside crypto — look at fintech (Robinhood, Coinbase, Revolut) for UX benchmarks.
- **B2B marketplace products**: map the two-sided nature — how does the product serve
  buyers vs. suppliers? Matrix dimensions will differ per side.
- **AgriTech/niche verticals**: Tier 1 set may be small (2–3 products). Weight Tier 2
  (adjacent tools users already use) and Tier 3 more heavily.
- **If competitors have no public product**: use G2/Capterra reviews, demo videos on
  YouTube, and their marketing pages as primary sources. Flag all inferences clearly.
- Update competitive analysis every 6 months or when a major competitor ships something
  significant — the landscape shifts.

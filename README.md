# design-workflow

**A modular, AI-augmented playbook for product design teams.**

A collection of reusable Claude Skills and templates that operationalize the full design workflow — from research planning through ship and learn. Each phase is a self-contained skill with inputs, outputs, steps, integrations, and templates.

Perfect for:
- Designers who want to own end-to-end workflows (research → design → code)
- Teams standardizing research and design processes
- Anyone tired of starting from scratch on every project

## Philosophy

- **Designer stays in control.** AI handles grunt work — research synthesis, pattern fetching, token extraction, documentation. The designer makes every consequential decision.
- **Opinionated structure, flexible wiring.** The phases and gates are fixed. The tools (Notion vs Confluence, Slack vs Teams, Figma vs Sketch) are swappable via `config/integrations.md`.
- **Every skill has a Definition of Done.** No ambiguity about when to move to the next phase.

## Workflow Phases

| Phase | Folder | Skills | Gate |
|-------|--------|--------|------|
| 0. Kickoff | `00-kickoff/` | Problem brief, stakeholder alignment, project setup | Brief signed off |
| 1. Research | `01-research/` | Signal mining → Gap analysis → Plan → Collect + Metrics → Synthesize → Validate | Validation score ≥ 7/10 |
| 2. Define | `02-define/` | UX artifacts → Opportunity framing → Problem lock | Problem statement locked |
| 3. Design | `03-design/` | Patterns → Mood → Ideation → Concept lock → Production → Design system | Concept approved |
| 4. Validate | `04-validate/` | Prototype testing → Design review → Stakeholder review | Stakeholder sign-off |
| 5. Handoff | `05-handoff/` | Component handoff → Token sync → Build review | Visual diff passes |
| 6. Ship & Learn | `06-ship-and-learn/` | Release monitoring → Retro → Insights loop | Retro complete, insights filed |

## Skills Reference

### Phase 0: Kickoff

| Skill | What it does |
|-------|-------------|
| **[00-kickoff](00-kickoff/SKILL.md)** | Frames the design problem, aligns stakeholders, drafts a project brief. Flags assumptions vs. evidence upfront. |

### Phase 1: Research

| Skill | What it does |
|-------|-------------|
| **[01-signal-mining](01-research/01-signal-mining/SKILL.md)** | Harvests passive signals from public sources (App Store, Reddit, HN, G2, GitHub Issues, Twitter/X) to cheaply close low-confidence assumptions before primary research. |
| **[01a-gap-analysis](01-research/01a-gap-analysis/SKILL.md)** | Extracts every assumption from the project brief, scores each on confidence and impact, and ranks them by risk. Outputs a prioritized gap tracker. |
| **[01b-research-plan](01-research/01b-research-plan/SKILL.md)** | Generates a complete 11-section research brief with methods, participants, timeline, and Notion publishing. The most detailed skill in the playbook. |
| **[01c-data-collection](01-research/01c-data-collection/SKILL.md)** | Structures data gathering — interview guides, competitive matrices, survey design. Matches methods to research gaps. |
| **[01c-metrics](01-research/01c-metrics/SKILL.md)** | Pulls behavioral analytics from Mixpanel, Amplitude, PostHog, or GA4 to answer research gaps with quantitative evidence. Runs alongside data collection. |
| **[01d-synthesis](01-research/01d-synthesis/SKILL.md)** | Turns raw research data into patterns and insights via affinity mapping. Updates the gap tracker with validated/invalidated assumptions. |
| **[01e-validation](01-research/01e-validation/SKILL.md)** | Quality gate before design begins. Pressure-tests insights for bias, scores research confidence, decides proceed or loop back. |

### Phase 2: Define

| Skill | What it does |
|-------|-------------|
| **[02a-ux-artifacts](02-define/02a-ux-artifacts/SKILL.md)** | Creates personas, journey maps, and Jobs to Be Done from research findings. |
| **[02b-opportunity-framing](02-define/02b-opportunity-framing/SKILL.md)** | Identifies and prioritizes design opportunities using an opportunity canvas. Scopes which assumptions still need validation in design. |
| **[02c-problem-lock](02-define/02c-problem-lock/SKILL.md)** | Locks the problem statement and design challenge. Once locked, the team commits — no more scope creep. |

### Phase 3: Design

| Skill | What it does |
|-------|-------------|
| **[03a-pattern-research](03-design/03a-pattern-research/SKILL.md)** | Researches existing UI/UX patterns and competitive solutions relevant to the design challenge. |
| **[03b-moodboarding](03-design/03b-moodboarding/SKILL.md)** | Creates a visual direction brief — tone, style, and aesthetic references before jumping into UI. |
| **[03c-ideation](03-design/03c-ideation/SKILL.md)** | Generates multiple distinct solution concepts with tradeoff analysis before committing to a direction. |
| **[03d-concept-selection](03-design/03d-concept-selection/SKILL.md)** | Evaluates concepts against criteria and selects a design direction with stakeholder input. |
| **[03e-production-design](03-design/03e-production-design/SKILL.md)** | Takes the selected concept through production — detailed specs, responsive layouts, edge cases, and a design changelog. |
| **[03f-design-system](03-design/03f-design-system/SKILL.md)** | Maintains the design system — component specs, token definitions, and changelog for new or updated components. |

### Phase 4: Validate

| Skill | What it does |
|-------|-------------|
| **[04a-prototype-testing](04-validate/04a-prototype-testing/SKILL.md)** | Writes test scripts, runs prototype tests, and documents findings with severity ratings. |
| **[04b-design-review](04-validate/04b-design-review/SKILL.md)** | Structured design critique using a checklist — accessibility, consistency, interaction patterns, edge cases. |
| **[04c-stakeholder-review](04-validate/04c-stakeholder-review/SKILL.md)** | Facilitates stakeholder feedback collection, logs decisions, and tracks sign-off status. |

### Phase 5: Handoff

| Skill | What it does |
|-------|-------------|
| **[05a-component-handoff](05-handoff/05a-component-handoff/SKILL.md)** | Creates detailed engineering handoff docs — component specs, behavior notes, API assumptions to validate. |
| **[05b-token-sync](05-handoff/05b-token-sync/SKILL.md)** | Syncs design tokens between Figma and code. Generates a diff report of what changed. |
| **[05c-build-review](05-handoff/05c-build-review/SKILL.md)** | Compares the built implementation against the design — catches visual drift before shipping. |

### Phase 6: Ship & Learn

| Skill | What it does |
|-------|-------------|
| **[06a-release-monitoring](06-ship-and-learn/06a-release-monitoring/SKILL.md)** | Tracks post-launch performance metrics and flags regressions or unexpected behavior. |
| **[06b-retrospective](06-ship-and-learn/06b-retrospective/SKILL.md)** | Runs a structured project retro — what worked, what didn't, and what to change for next time. |
| **[06c-insights-loop](06-ship-and-learn/06c-insights-loop/SKILL.md)** | Feeds project learnings back into the knowledge base. Closes the loop so the next project starts smarter. |

## Getting Started

See the [Quick Start guide](QUICKSTART.md) for how to run any skill.

### First-time setup
1. [Set up Notion](docs/NOTION-SETUP.md) (one-time)
2. Edit `config/integrations.md` — wire up your Notion, Slack, Figma, and other tools
3. Edit `config/team-config.md` — define roles, channels, and review cadence
4. Walk through each skill's `SKILL.md` and adjust steps to your org

**Analytics credentials:** See `config/integrations.md` → Analytics section. Store all secrets in `.env` (gitignored). Required for `01c-metrics` skill.

**Signal mining setup:** See `config/integrations.md` → Signal Mining Sources section. Configure subreddits, GitHub repos, and app store IDs for your product.

### Per-project execution
1. Start at `00-kickoff/SKILL.md`
2. Follow each skill sequentially — the outputs of each skill are the inputs of the next
3. Use Claude Code to execute each skill: `Read [path]/SKILL.md and execute it`
4. Gate checks prevent premature phase transitions

## Feedback Loops

- **Research → Research**: If validation reveals gaps, loop back to gap analysis
- **Validate → Design**: If design review fails, loop back to production design
- **Handoff → Design**: If build review detects drift, loop back to Figma
- **Ship → Research**: Post-launch insights feed the next cycle's gap analysis

## Customization

- Swap any integration by editing `config/integrations.md`
- Add org-specific templates to any `assets/` folder
- Add or remove skills within a phase — the structure is modular
- Adjust gate thresholds in each validation skill

## File Structure

```
design-workflow/
├── README.md
├── QUICKSTART.md
├── config/
│   ├── integrations.md               ← Tool wiring (Notion, Slack, Figma, etc.)
│   └── team-config.md                ← Roles, channels, cadence
├── 00-kickoff/
│   ├── SKILL.md
│   └── assets/
├── 01-research/
│   ├── 01-signal-mining/             ← Pre-research passive signal harvesting
│   ├── 01a-gap-analysis/
│   ├── 01b-research-plan/            ← Most detailed skill (11-section briefs + Notion)
│   ├── 01c-data-collection/
│   ├── 01c-metrics/                  ← Analytics API integration (parallel to data collection)
│   ├── 01d-synthesis/
│   └── 01e-validation/
├── 02-define/
│   ├── 02a-ux-artifacts/
│   ├── 02b-opportunity-framing/
│   └── 02c-problem-lock/
├── 03-design/
│   ├── 03a-pattern-research/
│   ├── 03b-moodboarding/
│   ├── 03c-ideation/
│   ├── 03d-concept-selection/
│   ├── 03e-production-design/
│   └── 03f-design-system/
├── 04-validate/
│   ├── 04a-prototype-testing/
│   ├── 04b-design-review/
│   └── 04c-stakeholder-review/
├── 05-handoff/
│   ├── 05a-component-handoff/
│   ├── 05b-token-sync/
│   └── 05c-build-review/
├── 06-ship-and-learn/
│   ├── 06a-release-monitoring/
│   ├── 06b-retrospective/
│   └── 06c-insights-loop/
└── docs/
    └── NOTION-SETUP.md
```

## Influences

- *Just Enough Research* — Erika Hall
- *Testing Business Ideas* — Strategyzer
- *Interviewing Users* — Steve Portigal
- *Quantifying the User Experience* — Jeff Sauro & James R. Lewis
- *101 Design Methods* — Vijay Kumar
- *Good Services* — Lou Downe
- *Storytelling for User Experience* — Whitney Quesenbery & Kevin Brooks
- *Visualizing Complexity* — Nicole Woolf & Andrea Sturze
- [Research Gap Framework](https://raziaaliani.substack.com/p/research-gap-framework-workbook-you) — Razia Aliani

---

**Built by Jack Brugger** for research-driven product design.

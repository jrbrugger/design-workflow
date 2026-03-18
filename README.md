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
| 1. Research | `01-research/` | Gap analysis → Plan → Collect → Synthesize → Validate | Validation score ≥ 7/10 |
| 2. Define | `02-define/` | UX artifacts → Opportunity framing → Problem lock | Problem statement locked |
| 3. Design | `03-design/` | Patterns → Mood → Ideation → Concept lock → Production → Design system | Concept approved |
| 4. Validate | `04-validate/` | Prototype testing → Design review → Stakeholder review | Stakeholder sign-off |
| 5. Handoff | `05-handoff/` | Component handoff → Token sync → Build review | Visual diff passes |
| 6. Ship & Learn | `06-ship-and-learn/` | Release monitoring → Retro → Insights loop | Retro complete, insights filed |

## Getting Started

### First-time setup
1. [Set up Notion](docs/NOTION-SETUP.md) (one-time)
2. Edit `config/integrations.md` — wire up your Notion, Slack, Figma, and other tools
3. Edit `config/team-config.md` — define roles, channels, and review cadence
4. Walk through each skill's `SKILL.md` and adjust steps to your org

### Per-project execution
1. Start at `00-kickoff/SKILL.md`
2. Follow each skill sequentially — the outputs of each skill are the inputs of the next
3. Use Claude Code to execute each skill: `Read [path]/SKILL.md and execute it`
4. Gate checks prevent premature phase transitions

### Quick start (research plan only)
```
/research-plan

I'm planning research on [topic].
The problem is [problem].
Target users are [segment].
```
Answer 3–5 clarifying questions → review the brief → approve → auto-published to your Notion Research Repository.

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
├── config/
│   ├── integrations.md               ← Tool wiring (Notion, Slack, Figma, etc.)
│   └── team-config.md                ← Roles, channels, cadence
├── 00-kickoff/
│   ├── SKILL.md                      ← Kickoff workflow
│   └── assets/
├── 01-research/
│   ├── 01a-gap-analysis/SKILL.md
│   ├── 01b-research-plan/SKILL.md
│   ├── 01c-data-collection/SKILL.md
│   ├── 01d-synthesis/SKILL.md
│   └── 01e-validation/SKILL.md
├── 02-define/
│   ├── 02a-ux-artifacts/SKILL.md
│   ├── 02b-opportunity-framing/SKILL.md
│   └── 02c-problem-lock/SKILL.md
├── 03-design/
│   ├── 03a-pattern-research/SKILL.md
│   ├── 03b-moodboarding/SKILL.md
│   ├── 03c-ideation/SKILL.md
│   ├── 03d-concept-selection/SKILL.md
│   ├── 03e-production-design/SKILL.md
│   └── 03f-design-system/SKILL.md
├── 04-validate/
│   ├── 04a-prototype-testing/SKILL.md
│   ├── 04b-design-review/SKILL.md
│   └── 04c-stakeholder-review/SKILL.md
├── 05-handoff/
│   ├── 05a-component-handoff/SKILL.md
│   ├── 05b-token-sync/SKILL.md
│   └── 05c-build-review/SKILL.md
├── 06-ship-and-learn/
│   ├── 06a-release-monitoring/SKILL.md
│   ├── 06b-retrospective/SKILL.md
│   └── 06c-insights-loop/SKILL.md
├── .claude/skills/research-plan/     ← Detailed /research-plan Claude Skill
│   ├── SKILL.md
│   ├── config.json
│   └── references/
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

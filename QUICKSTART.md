# Quick Start

How to run any skill in the design-workflow playbook.

## Running a Skill

### 1. Pick a skill

Each folder contains a `SKILL.md` with everything Claude needs. Start with the phase that matches where you are in your project:

| You want to... | Run this skill |
|----------------|---------------|
| Start a new project | `00-kickoff/SKILL.md` |
| Figure out what you don't know | `01-research/01a-gap-analysis/SKILL.md` |
| Write a research brief | `01-research/01b-research-plan/SKILL.md` |
| Prepare interview guides | `01-research/01c-data-collection/SKILL.md` |
| Make sense of research data | `01-research/01d-synthesis/SKILL.md` |
| Create personas or journey maps | `02-define/02a-ux-artifacts/SKILL.md` |
| Lock the problem statement | `02-define/02c-problem-lock/SKILL.md` |
| Generate design concepts | `03-design/03c-ideation/SKILL.md` |
| Test a prototype | `04-validate/04a-prototype-testing/SKILL.md` |
| Hand off to engineering | `05-handoff/05a-component-handoff/SKILL.md` |
| Run a project retro | `06-ship-and-learn/06b-retrospective/SKILL.md` |

### 2. Open Claude Code and run

```
Read [path]/SKILL.md and execute it
```

For example:
```
Read 01-research/01a-gap-analysis/SKILL.md and execute it
```

Claude will read the skill, understand the steps, and walk you through it — asking for inputs, generating outputs, and publishing results.

### 3. Follow the flow

Each skill has:
- **Inputs** — what it needs from you (or from a previous skill's output)
- **Steps** — the prompts Claude runs through with you
- **Outputs** — what gets produced (documents, trackers, Notion pages)
- **Definition of Done** — how you know it's complete

## Running Skills in Sequence

Skills are designed to chain together. The outputs of one skill become the inputs of the next:

```
00-kickoff → 01a-gap-analysis → 01b-research-plan → 01c-data-collection
→ 01d-synthesis → 01e-validation → 02a-ux-artifacts → ...
```

You don't have to run every skill. Skip what doesn't apply — but follow the order within a phase.

## Tips

- **You can jump in anywhere.** If you already have research and just need to define the problem, start at `02-define/`.
- **Every skill has assets.** Check the `assets/` folder for templates you can fill out manually or let Claude generate.
- **Gate checks matter.** Each phase ends with a quality gate. Don't skip validation — it catches problems before they compound.
- **Customize freely.** Edit any `SKILL.md` to match your team's process, tools, or terminology.

## First-Time Setup

Before your first run, configure your tools and team:

1. [Set up Notion](docs/NOTION-SETUP.md)
2. Edit [`config/integrations.md`](config/integrations.md) — connect your tools
3. Edit [`config/team-config.md`](config/team-config.md) — define roles and cadence

---

See the full [README](README.md) for the complete skills reference and playbook philosophy.

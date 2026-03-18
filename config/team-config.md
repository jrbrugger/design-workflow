# Team Configuration

Define your team structure, roles, and review cadence. Skills reference these roles to know who to tag, who reviews, and who approves.

## Roles

```yaml
roles:
  design_lead:
    name: ""                          # Your name
    slack_id: ""                      # For @mentions
    email: ""
    responsibilities:
      - Final design decisions
      - Design review approvals
      - Stakeholder communication
      - Design system governance

  product_manager:
    name: ""
    slack_id: ""
    email: ""
    responsibilities:
      - Problem framing sign-off
      - Research priority alignment
      - Stakeholder review coordination
      - Launch readiness

  engineering_lead:
    name: ""
    slack_id: ""
    email: ""
    responsibilities:
      - Technical feasibility review
      - Component handoff acceptance
      - Build review sign-off
      - Token sync validation

  researcher:                         # Optional — often the designer wears this hat
    name: ""
    slack_id: ""
    email: ""
    responsibilities:
      - Research planning
      - Data collection
      - Synthesis and validation

  design_system_owner:               # Optional — can be same as design_lead
    name: ""
    slack_id: ""
    email: ""
    responsibilities:
      - Component library governance
      - Token architecture
      - Breaking change reviews
```

## Review Cadence

```yaml
cadence:
  design_crit: "weekly"              # Options: weekly, biweekly, per-milestone
  design_crit_day: "wednesday"
  stakeholder_review: "per-milestone" # Options: weekly, biweekly, per-milestone
  retro: "per-project"               # Options: per-sprint, per-project
  design_system_sync: "biweekly"     # Design system maintenance check-in
```

## Approval Matrix

| Decision | Approver | Backup |
|----------|----------|--------|
| Research plan | Product Manager | Design Lead |
| Problem statement lock | Product Manager + Design Lead | — |
| Concept direction | Design Lead | — |
| Final design sign-off | Stakeholder (via PM) | Design Lead |
| Component handoff | Engineering Lead | — |
| Token changes | Design System Owner | Design Lead |
| Ship readiness | Product Manager | — |

## RACI Template

Use this for any skill where responsibility is ambiguous:

| Activity | Responsible | Accountable | Consulted | Informed |
|----------|------------|-------------|-----------|----------|
| Research | Designer/Researcher | Design Lead | PM | Engineering |
| Design | Designer | Design Lead | PM, Eng | Stakeholders |
| Handoff | Designer | Eng Lead | Design Lead | PM |
| Ship | Engineering | PM | Design Lead | Stakeholders |

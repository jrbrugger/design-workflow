---
name: 05b-token-sync
description: >-
  Compares design tokens between Figma and code to detect drift and generate sync actions. Use before releases or on a regular cadence to keep tokens aligned. Triggers on: "token sync", "token drift", "compare tokens", "Figma vs code", "design variables".
---

# 05b — Token Sync

## Purpose
Ensure design tokens in Figma match code variables in the repository. Token drift — where Figma says one thing and code says another — is the #1 source of visual inconsistency between design and production. This skill catches drift early and keeps the single source of truth intact.

## When to Use
- Alongside component handoff (05a)
- After any design system changes (03f)
- On a regular cadence (biweekly recommended)
- Before any release that touches visual styling

## Inputs
- Figma design token file (Token Studio export or Figma variables)
- Code token file (CSS variables, SCSS variables, Tailwind config, or Style Dictionary output)
- Design system changelog (from `03f`)

## Outputs
- [ ] **Token diff report** — what's different between Figma and code
- [ ] **Sync action items** — which tokens to add, update, or deprecate in code
- [ ] **Updated token files** (or PR with changes)
- [ ] **Drift report** posted to Notion
- [ ] **Slack notification** if breaking changes detected

## Steps

### 1. Export tokens from Figma
```
Prompt: "Help me export design tokens from Figma for comparison:
If using Token Studio:
- Export as JSON from the Token Studio plugin
- Include all sets: primitives, semantic, component

If using Figma Variables:
- Export variables via Figma API or plugin
- Include all collections and modes

If using Figma MCP:
- Pull variable definitions from the design system file

Store the export as the current 'design truth' snapshot."
```

### 2. Pull tokens from code
```
Prompt: "Help me extract the current code tokens for comparison:
- Repo: [repo URL or path]
- Token format: [CSS variables / SCSS / Tailwind / Style Dictionary]
- Token file location: [path in repo]

Parse the code token file into a structured format that can be compared 
against the Figma export. Normalize naming conventions if they differ 
between Figma and code (e.g., figma uses '/' separators, code uses '-')."
```

### 3. Generate diff report
```
Prompt: "Compare the Figma tokens against the code tokens:

Report:
- MISSING IN CODE: Tokens that exist in Figma but not in code (need to be added)
- MISSING IN FIGMA: Tokens that exist in code but not in Figma (orphaned or deprecated?)
- VALUE MISMATCH: Same token, different value (drift — needs resolution)
- NAMING MISMATCH: Similar tokens with different naming conventions

For each discrepancy:
- Token name (Figma)
- Token name (Code)
- Figma value
- Code value
- Severity: Breaking (user-visible change) / Non-breaking (internal only)
- Recommended action: Update code / Update Figma / Deprecate / Investigate

Summarize: [N] in sync, [N] drifted, [N] missing, [N] orphaned."
```

### 4. Resolve discrepancies
```
Prompt: "For the token discrepancies found:
- Draft the code changes needed (new tokens, updated values, deprecations)
- Format as a PR description or changeset
- Include before/after for any value changes
- Flag breaking changes that need migration notes
- If there are naming convention issues, recommend a normalization approach

Generate the updated token file in [format: CSS/SCSS/Tailwind/Style Dictionary]."
```

### 5. Document and communicate
```
Prompt: "Post the token sync results:
1. Notion: Token drift report with full diff
2. Slack: Summary message:
   '[Project] Token sync complete. 
   [N] tokens in sync. [N] updates needed. [N] breaking changes.
   [If breaking]: Breaking changes affect: [list components]. 
   Migration: [description].
   PR: [link if created].'
3. Tag design system owner and engineering lead.
If no drift: 'Token sync: all clear. [N] tokens verified.'"
```

## Integrations
- **Figma**: Token export (Token Studio, Variables API, MCP)
- **GitHub**: Code token files, PR creation
- **Slack**: Drift alerts, sync results
- **Notion**: Drift report documentation
- **CI/CD**: (Optional) Automated token validation in pipeline

## Templates
- `assets/token-diff-report.md`

## Definition of Done
- [ ] Figma tokens exported and snapshot saved
- [ ] Code tokens extracted and parsed
- [ ] Diff report generated with all discrepancies
- [ ] Action items assigned (update code, update Figma, or deprecate)
- [ ] Breaking changes communicated
- [ ] Drift report posted to Notion

## Customization Notes
- If using Style Dictionary: it can automate much of the export/transform pipeline
- If using Token Studio with GitHub sync: check the sync status rather than manual export
- For teams without formal tokens: this is a good forcing function to establish them
- Automate this with a CI check if possible — manual token sync doesn't scale

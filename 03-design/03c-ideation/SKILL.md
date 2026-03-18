# 03c — Ideation

## Purpose
Generate multiple solution concepts before committing to one direction. Diverge widely, then converge. AI generates volume — the designer curates, combines, and selects. This prevents premature commitment to the first idea.

## When to Use
- Parallel with pattern research (03a) and moodboarding (03b)
- After all three parallel activities, before concept selection (03d)

## Inputs
- Design challenge brief (from `02c`)
- Pattern research findings (from `03a`)
- Visual direction (from `03b`)
- JTBD and personas (from `02a`)

## Outputs
- [ ] **Concept sketches** → 3-5 distinct approaches (low-fidelity)
- [ ] **Concept descriptions** → `templates/concept-sheet.md` for each
- [ ] **Tradeoff matrix** → how concepts compare on key dimensions
- [ ] **Posted to Figma/FigJam** for team review
- [ ] **Shared in Slack** ahead of concept selection

## Steps

### 1. Frame the solution space
```
Prompt: "Based on our design challenge: [paste], 
and our pattern research: [paste key findings],
identify 4-6 distinct solution strategies. Not UI layouts — strategies.
For example:
- 'Progressive disclosure' — reveal complexity gradually
- 'Dashboard-first' — give an overview, let users drill down
- 'Wizard/guided' — step users through the process
- 'Contextual' — surface actions where the user already is
For each strategy, describe the core idea in 2-3 sentences 
and which persona/JTBD it best serves."
```

### 2. Sketch concepts
```
Prompt: "For each solution strategy, describe a concrete UI concept:
- Screen-by-screen flow (what the user sees at each step)
- Key interaction model (how the user navigates, inputs, and gets feedback)
- Information hierarchy (what's prominent, what's secondary, what's hidden)
- Novel elements (what makes this concept different from the obvious solution)

Describe these in enough detail that I could sketch them quickly. 
Don't design the UI — describe the structure and behavior."
```

_Now sketch. Use paper, iPad, Figma — whatever's fastest. Low-fidelity. The point is structure, not polish._

### 3. Evaluate tradeoffs
```
Prompt: "Compare our [N] concepts on these dimensions:
- User value: How well does it serve the primary JTBD?
- Learnability: How quickly can a new user figure it out?
- Scalability: Does it hold up as data/complexity grows?
- Technical feasibility: How hard is this to build? (Flag unknowns)
- Novelty: How different is this from what exists?
- Alignment with patterns: Does it use established conventions or break them?

Format as a comparison matrix. Don't pick a winner — present tradeoffs."
```

### 4. Prepare for concept selection
```
Prompt: "Compile concepts into a presentation for design crit / concept selection:
- One slide/section per concept: name, strategy, key screens, tradeoffs
- Recommendation: which 1-2 concepts to explore further and why
- Open questions: what do we need to figure out regardless of direction
Post to Figma or FigJam. Share link in Slack:
'[N] concepts ready for review: [link]. Recommending [concept name] because [reason].
Design crit: [day/time]. Async feedback welcome before then.'"
```

## Integrations
- **Figma/FigJam**: Post concept sketches and comparison
- **Slack**: Share concepts, gather feedback, announce design crit
- **Notion**: Link concept summaries to project page
- **Calendar**: (Optional) Schedule design crit session

## Templates
- `templates/concept-sheet.md`

## Definition of Done
- [ ] 3-5 distinct concepts generated (not variations of one idea)
- [ ] Each concept described with flow, interactions, and tradeoffs
- [ ] Tradeoff matrix completed
- [ ] Concepts shared with team ahead of concept selection
- [ ] Design crit scheduled or async review period set

## Customization Notes
- For time-constrained projects: generate 3 concepts, present 2
- For high-stakes projects: involve engineering early to flag feasibility
- Crazy 8s or design sprints can replace/supplement this — use the structure that works for your team
- The key principle: never present only one option. Even if you have a strong opinion, show alternatives.

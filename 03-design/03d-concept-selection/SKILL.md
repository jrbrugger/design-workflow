# 03d — Concept Selection

## Purpose
Converge from multiple concepts to one direction. This is the design crit gate — the team reviews concepts, debates tradeoffs, and locks a direction before investing in production design. Prevents wasted effort on the wrong concept.

## When to Use
- After ideation (03c) produces 3-5 concepts
- Before production design begins (03e)
- This is a decision point, not a brainstorming session

## Inputs
- Concept sketches and descriptions (from `03c-ideation`)
- Tradeoff matrix
- Stakeholder priorities and constraints
- Pattern research findings (from `03a`)

## Outputs
- [ ] **Selected concept** with documented rationale
- [ ] **Design direction doc** → `templates/design-direction.md`
- [ ] **Open questions** for production design to resolve
- [ ] **Posted to Notion** as the authoritative design direction
- [ ] **Slack announcement** — "Direction locked"

## Steps

### 1. Prepare the crit
```
Prompt: "Structure a design crit for our [N] concepts. Create a discussion guide:
- Context recap: problem statement, key personas, success metric (2 min)
- Concept presentations: each concept gets equal time (3 min each)
- Discussion framework: evaluate each on user value, feasibility, and alignment
- Decision method: dot voting, weighted scoring, or facilitator decision
- Timebox: 30 min total

If running async, format this as a structured Slack thread or Notion page 
where reviewers can leave feedback per concept."
```

### 2. Facilitate or collect feedback
_If synchronous: run the crit using the discussion guide._
_If asynchronous:_
```
Prompt: "Create a structured async review in Slack:
Thread 1: Context + instructions
Thread 2: Concept A — [name, description, key screens, tradeoffs]
Thread 3: Concept B — [repeat]
Thread 4: Concept C — [repeat]
Thread 5: 'Vote for your preferred direction and explain why. Consider: user value, feasibility, alignment. Deadline: [date].'
Tag all reviewers."
```

### 3. Synthesize feedback and decide
```
Prompt: "Here's the feedback from our design crit: [paste feedback/votes].
Synthesize:
- Which concept had the most support and why
- Key concerns raised for the leading concept
- Any hybrid suggestions (combining elements from multiple concepts)
- Unresolved questions

Recommend a final direction. If the feedback is split, 
make a decision and document the reasoning. 
Indecision is more expensive than an imperfect choice."
```

### 4. Document the direction
```
Prompt: "Fill out the design direction template:
- Selected concept and rationale
- What we're taking from other concepts (if anything)
- Key design principles for this direction
- Open questions to resolve in production design
- What we explicitly decided NOT to do
Post to Notion. Announce in Slack:
'Design direction locked: [concept name]. Rationale: [one-liner].
Full doc: [link]. Production design starts [date].'"
```

## Integrations
- **Figma/FigJam**: Concept presentation boards
- **Slack**: Async review threads, direction announcement
- **Notion**: Design direction documentation
- **Calendar**: Design crit meeting (if sync)

## Templates
- `templates/design-direction.md`

## Definition of Done
- [ ] All concepts reviewed by team (sync or async)
- [ ] One direction selected with documented rationale
- [ ] Open questions for production design identified
- [ ] Direction posted to Notion
- [ ] Team notified — production design begins

## Customization Notes
- If you're the sole designer: still do this exercise — present to PM or eng lead for a gut check
- For design-mature orgs: use existing crit format and cadence
- The anti-pattern is skipping this and going straight from ideation to production — it leads to "we should've gone with the other one" mid-build

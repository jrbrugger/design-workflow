# 04b — Design Review

## Purpose
Internal quality check before showing stakeholders. Review the design against the challenge brief, design principles, accessibility standards, and edge case coverage. This catches issues the designer is too close to see. It's a craft review — not a stakeholder opinion-gathering session.

## When to Use
- After prototype testing fixes are applied (04a)
- Before stakeholder review (04c)
- At scheduled design crit cadence (from team-config.md)

## Inputs
- Production design in Figma (from `03e`, updated after `04a`)
- Design challenge brief (from `02c`)
- Design direction doc (from `03d`)
- Test findings (from `04a`)
- Design system guidelines

## Outputs
- [ ] **Review checklist** → `templates/design-review-checklist.md` completed
- [ ] **Issue list** with severity and fix recommendations
- [ ] **Updated designs** addressing review feedback
- [ ] **Review sign-off** from design lead
- [ ] **Slack update** confirming review pass

## Steps

### 1. Self-review against checklist
```
Prompt: "Help me conduct a design review for [project]. 
Go through each dimension in templates/design-review-checklist.md:

1. Problem alignment: Does the design solve the stated problem?
2. JTBD coverage: Are all primary jobs served?
3. Flow completeness: Happy path + all edge cases?
4. Consistency: Does it follow design system patterns?
5. Accessibility: WCAG AA compliance?
6. Content: Is copy clear, concise, helpful?
7. Responsiveness: Does it work across breakpoints?
8. Performance: Any obvious performance concerns? (heavy images, complex animations)
9. Error handling: Graceful degradation for all failure modes?
10. Handoff readiness: Is the Figma file clean and organized?

For each dimension, rate as: Pass / Needs Work / Fail.
Flag specific issues with screenshots or descriptions."
```

### 2. Peer review (if team exists)
```
Prompt: "Prepare a design review request for [reviewer name]:
- Link to Figma file with key frames
- Link to prototype
- Specific areas where I want feedback (don't make them review everything)
- Context: design challenge brief link
- Timeline: feedback by [date]

Post to Slack or send as DM depending on team preference."
```

### 3. Address feedback
```
Prompt: "Here's the feedback from design review: [paste feedback].
Categorize each item:
- Accept and fix (clear improvement, low effort)
- Accept and fix (clear improvement, high effort — schedule for later)
- Discuss (disagreement or tradeoff — needs conversation)
- Decline with rationale (feedback contradicts research or design principles)

For accepted items, describe the specific changes.
For declined items, write the rationale."
```

### 4. Final check and sign-off
```
Prompt: "After applying review changes:
- Rerun the design review checklist — confirm all dimensions pass
- Update the design changelog with review changes
- Post to Slack: 'Design review complete for [project]. 
  All dimensions pass. [N] changes made from review.
  Ready for stakeholder review. Prototype: [link].'
- Mark the project as 'Design Review — Passed' in Notion"
```

## Integrations
- **Figma**: Design file review, commenting
- **Slack**: Review requests, feedback threads
- **Notion**: Update project status

## Templates
- `templates/design-review-checklist.md`

## Definition of Done
- [ ] Self-review checklist completed — all dimensions pass or have documented exceptions
- [ ] Peer review collected (if applicable)
- [ ] All accepted feedback applied
- [ ] Declined feedback documented with rationale
- [ ] Design lead sign-off received
- [ ] Ready for stakeholder review

## Customization Notes
- Solo designers: the self-review checklist is your peer. Be honest with yourself.
- Mature design teams: use existing crit format, add the checklist as a quality gate
- The checklist dimensions should be customized to your org's standards

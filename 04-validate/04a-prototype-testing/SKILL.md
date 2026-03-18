---
name: 04a-prototype-testing
description: >-
  Plans and executes usability testing on design prototypes to validate the solution before handoff. Use when designs are ready for user validation. Triggers on: "usability test", "prototype testing", "test with users", "validate design", "user testing".
---

# 04a — Prototype Testing

## Purpose
Validate the design with real users before handoff. Catch usability issues, confusion, and unmet expectations while changes are still cheap. This is design-time validation — distinct from research-phase validation (01e) which validates the problem. Here we validate the solution.

## When to Use
- After production design (03e) produces a clickable prototype
- Before design review (04b) and stakeholder review (04c)
- For high-risk or novel interaction patterns — always test

## Inputs
- Clickable Figma prototype (from `03e`)
- Test scenarios tied to JTBD (from `02a`)
- Success criteria (from `02c` design challenge brief)

## Outputs
- [ ] **Usability test script** → `assets/test-script.md`
- [ ] **Test findings** → `assets/test-findings.md`
- [ ] **Severity-ranked issue list** with design recommendations
- [ ] **Updated designs** (if critical issues found)
- [ ] **Posted to Notion** and shared in Slack

## Steps

### 1. Plan the test
```
Prompt: "Create a usability test plan for our prototype:
- Prototype link: [link]
- Primary JTBD we're testing: [from 02a]
- Test objectives: What specific questions will this test answer?
- Tasks: 3-5 realistic tasks the user should attempt
- Success criteria per task: completion rate, time, errors, satisfaction
- Participant criteria: [from research screener, adjusted if needed]
- Sample size: 5 participants (standard for qualitative usability testing)
- Format: moderated remote / in-person
- Duration: 30 minutes per session

Draft the full test script using assets/test-script.md."
```

### 2. Recruit participants
```
Prompt: "Draft a recruitment message for usability testing:
- Who we're looking for (criteria from step 1)
- What's involved (30 min session, [incentive])
- How to sign up (Calendly link or reply)
- Deadline

Post to appropriate recruitment channel — internal panel, Slack, 
User Interviews, Respondent, or existing customer list.
Schedule sessions across 2-3 days."
```

### 3. Run sessions
_Manual — you facilitate the test. AI helps with note-taking and analysis._

```
Prompt: "I just completed a usability test session. Raw notes: [paste].
Structure the observations:
- Task 1: [task name]
  - Completed: yes/no/partial
  - Time: 
  - Errors/confusion points: 
  - Key quotes: 
  - Severity: Critical / Major / Minor / Cosmetic
- [Repeat for each task]
- Overall satisfaction: 
- Unprompted feedback: 
Store in Notion research database."
```

### 4. Analyze and synthesize
```
Prompt: "Here are findings from [N] usability test sessions: [paste all structured notes].
Synthesize:
- Task completion rates (per task)
- Common failure points (where did multiple users struggle?)
- Severity-ranked issue list:
  - Critical: Prevents task completion
  - Major: Significant difficulty, workaround needed
  - Minor: Noticeable friction, completes anyway
  - Cosmetic: Visual/copy polish
- Positive signals (what worked well — don't only report problems)
- Recommendations: For each issue, suggest a design fix
Fill out assets/test-findings.md."
```

### 5. Prioritize and iterate
```
Prompt: "Based on test findings, recommend:
1. MUST FIX before handoff (critical + major issues)
2. SHOULD FIX if time allows (minor issues)
3. DEFER to next iteration (cosmetic + low-frequency issues)

For must-fix items, describe the specific design change needed.
Post to Slack: 'Usability testing complete for [project]. 
[N] sessions, [N] issues found. [N] critical, [N] major.
Key finding: [one-liner]. Findings doc: [link].
Updating designs for must-fix items before design review.'"
```

## Integrations
- **Figma**: Prototype for testing
- **Notion**: Test findings documentation
- **Slack**: Recruitment, findings sharing
- **Calendly**: Session scheduling
- **Zoom/Meet**: Remote session facilitation
- **Calendar**: Session time blocks

## Templates
- `assets/test-script.md`
- `assets/test-findings.md`

## Definition of Done
- [ ] 5 usability test sessions completed
- [ ] Findings synthesized with severity ratings
- [ ] Must-fix issues identified and design updates planned
- [ ] Findings posted to Notion
- [ ] Team notified of results and next steps

## Customization Notes
- For time-constrained projects: 3 sessions still reveals major issues
- For guerrilla testing: skip formal recruitment, grab 3-5 people and run 15-min tests
- If you can't test with real users: run a cognitive walkthrough with a colleague
- Unmoderated tools (Maze, UserTesting) can supplement but don't replace moderated sessions

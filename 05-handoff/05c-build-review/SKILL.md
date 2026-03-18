# 05c — Build Review

## Purpose
Compare what engineering built against what was designed. Catch visual drift, interaction gaps, and spec deviations before they ship to users. This closes the loop that handoff opened — if handoff is the "throw," build review is the "catch."

## When to Use
- After engineering completes implementation
- Before feature is merged/released
- Can run incrementally per component or per PR

## Inputs
- Implemented feature (staging URL, PR preview, or local build)
- Original Figma design file
- Handoff document (from `05a`)
- Component specs and interaction specs

## Outputs
- [ ] **Build review report** → `templates/build-review-report.md`
- [ ] **Issue list** — visual diffs, interaction gaps, spec deviations
- [ ] **Severity ratings** — blocking, major, minor, acceptable
- [ ] **Engineering tickets** for fixes (if issues found)
- [ ] **Sign-off** if passes
- [ ] **Slack update** with review results

## Steps

### 1. Visual comparison
```
Prompt: "Help me structure a systematic visual comparison between design and build.
For each screen in the handoff:

Checklist:
- [ ] Layout matches Figma (spacing, alignment, grid)
- [ ] Typography matches (font, size, weight, line-height, color)
- [ ] Colors match design tokens (backgrounds, borders, text)
- [ ] Component rendering matches spec (all variants, all states)
- [ ] Icons and imagery are correct
- [ ] Responsive behavior matches breakpoint specs
- [ ] Dark mode (if applicable)

I'll screenshot each screen from staging and compare side-by-side with Figma.
Create a comparison template I can fill in per screen."
```

### 2. Interaction review
```
Prompt: "From our interaction specs: [paste or link], 
create an interaction test checklist:
For each specified interaction:
- [ ] Trigger works as specified
- [ ] Animation duration and easing match spec
- [ ] Transition direction is correct
- [ ] Loading states appear correctly
- [ ] Error states render correctly
- [ ] Empty states render correctly
- [ ] Conditional logic works (if A then B)
- [ ] Keyboard navigation works
- [ ] Focus management is correct
- [ ] Screen reader announces correctly

I'll test each manually and log pass/fail."
```

### 3. Edge case testing
```
Prompt: "From our handoff specs, generate edge case test scenarios:
- Long text: What happens with maximum-length content?
- Empty data: First-time user with no data
- Maximum items: List or grid at maximum capacity
- Minimum viewport: Smallest supported screen size
- Slow connection: Loading states under network throttle
- Error recovery: What happens after an API failure?
- Permission variations: Different user roles see different things
- Browser compatibility: Test on [required browsers]

Create a test matrix I can execute."
```

### 4. Log issues and prioritize
```
Prompt: "Here are the issues I found during build review: [paste your notes].
For each issue:
- Description: What's wrong
- Expected: What the design specified
- Actual: What the build shows
- Severity:
  - Blocking: Prevents release (broken functionality, accessibility failure)
  - Major: Visible to users, degrades experience (layout break, wrong behavior)
  - Minor: Noticeable on close inspection (spacing off by a few px, color slightly off)
  - Acceptable: Within tolerance (sub-pixel differences, rendering engine variations)
- Screenshot or description of the diff
- Fix recommendation

Create tickets for blocking and major issues.
Log minor issues for the next sprint.
Accept acceptable differences."
```

### 5. Sign off or loop back
```
Prompt: "Based on the build review:
[If pass]: Post to Slack: 'Build review PASSED for [project]. 
  [N] items checked, [N] minor issues logged for later. 
  Approved for release. Great work @[engineer].'
  Update Notion project status to 'Ready for Release.'

[If issues found]: Post to Slack: 'Build review for [project]: 
  [N] blocking, [N] major issues found. 
  Tickets created: [links]. Fixes needed before release.
  Issue report: [Notion link].'
  Tag engineering lead.

[If major drift]: Flag for design-engineering sync to discuss approach.
  May need to revisit handoff process for next project."
```

## Integrations
- **Figma**: Design reference for comparison
- **Staging/Preview URL**: Implemented feature for testing
- **Linear/Jira**: Bug tickets for issues
- **Slack**: Review results, sign-off
- **Notion**: Build review report
- **Browser DevTools**: Inspect spacing, colors, typography

## Templates
- `templates/build-review-report.md`

## Definition of Done
- [ ] Visual comparison completed for all screens
- [ ] Interaction review completed for all specified behaviors
- [ ] Edge cases tested
- [ ] Issues logged with severity ratings
- [ ] Blocking/major issues have engineering tickets
- [ ] Sign-off given (or loop back initiated)
- [ ] Results posted to Notion and Slack

## Customization Notes
- For teams with visual regression testing (Chromatic, Percy): automate the visual comparison
- Pair with an engineer during review — resolve minor issues on the spot
- "Pixel perfect" is a spectrum — define your tolerance level upfront
- If drift is consistently high, the problem is the handoff process, not the engineers

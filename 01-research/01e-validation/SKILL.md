# 01e — Research Validation

## Purpose
Quality gate before design begins. Score the research confidence, pressure-test insights for bias, and make a go/no-go decision. This prevents building on shaky foundations. If gaps remain, loop back to `01a-gap-analysis`.

## When to Use
- After synthesis is complete
- Before transitioning to the Define phase

## Inputs
- Insight report (from `01d-synthesis`)
- Updated gap tracker
- Original research plan objectives

## Outputs
- [ ] **Validation scorecard** → `templates/validation-scorecard.md` filled out
- [ ] **Go/No-go decision** — proceed to Define, or loop back to Research
- [ ] **Updated Notion project page** with validation status
- [ ] **Slack update** with decision and rationale

## Steps

### 1. Score research completeness
```
Prompt: "Compare our original research objectives [paste from research plan] 
against our findings [paste from insight report]. 
For each objective, score:
- Answered (yes/partially/no)
- Confidence (1-10)
- Quality of evidence (strong/moderate/weak/none)
Calculate an overall research confidence score (average of all objectives)."
```

### 2. Bias check
```
Prompt: "Review our research for common biases:
- Confirmation bias: Did we only find what we expected?
- Sampling bias: Is our participant pool representative?
- Recency bias: Are we overweighting the last few interviews?
- Leading questions: Review the interview guide for leading language
- Survivorship bias: Are we only hearing from active/happy users?
Flag any concerns and suggest mitigations."
```

### 3. Pressure-test key insights
```
Prompt: "For each of our top 5 insights, play devil's advocate:
- What's the strongest counter-argument?
- What evidence would DISPROVE this insight?
- Are we conflating correlation with causation anywhere?
- Is the sample size sufficient to generalize?
This isn't about undermining our work — it's about knowing where we're confident vs. where we're making leaps."
```

### 4. Make the call
```
Prompt: "Based on the validation scorecard, recommend one of:
1. PROCEED — confidence score ≥ 7/10, no critical gaps
2. PROCEED WITH CAVEATS — confidence 5-7, some gaps but acceptable risk
3. LOOP BACK — confidence < 5, critical gaps that would change design direction

If looping back, specify exactly which gaps need closing and recommended methods.
If proceeding with caveats, document what we're accepting as risk."
```

### 5. Document and communicate
```
Prompt: "Update the Notion project page with:
- Validation scorecard
- Go/no-go decision with rationale
- If proceeding: clear handoff to Define phase
- If looping: updated gap analysis with new priorities

Post to Slack: '[Project] Research validation: [PROCEED/LOOP BACK]. 
Top confidence: [insight]. Biggest risk: [gap]. Next: [action].'
Tag PM."
```

## Integrations
- **Notion**: Update project page with validation results
- **Slack**: Post go/no-go decision
- **Linear/Jira**: (Optional) Create tickets for remaining gaps if looping back

## Templates
- `templates/validation-scorecard.md`

## Gate Criteria
| Score | Decision | Action |
|-------|----------|--------|
| 8-10 | Proceed | Move to 02-define |
| 5-7 | Proceed with caveats | Document risks, move to 02-define |
| < 5 | Loop back | Return to 01a-gap-analysis with new priorities |

## Definition of Done
- [ ] Every research objective scored for completeness and confidence
- [ ] Bias check completed — no critical concerns unaddressed
- [ ] Key insights pressure-tested
- [ ] Go/no-go decision made and documented
- [ ] Decision communicated to team via Slack

## Customization Notes
- Adjust the threshold (default: 7/10) based on your risk tolerance
- Startups may accept lower confidence to move faster — just document the risk
- Enterprise may require stakeholder sign-off on the validation decision

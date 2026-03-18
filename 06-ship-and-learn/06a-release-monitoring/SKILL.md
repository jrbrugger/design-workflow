# 06a — Release Monitoring

## Purpose
Track how the design performs in production after launch. Designers often hand off and move on — this skill closes the feedback loop by monitoring whether the design actually achieved its success metrics. Data from this phase feeds the next cycle's research.

## When to Use
- Immediately after feature is released to production
- Monitor for 2-4 weeks post-launch (adjust based on traffic/usage volume)

## Inputs
- Success criteria (from `02c` design challenge brief)
- Baseline metrics (from design challenge)
- Feature flag or release date
- Analytics tool access

## Outputs
- [ ] **Monitoring dashboard** or metric tracking setup
- [ ] **Week 1 report** → initial signals
- [ ] **Week 2-4 report** → trend confirmation
- [ ] **Performance summary** → `templates/performance-summary.md`
- [ ] **Slack updates** at each checkpoint

## Steps

### 1. Set up monitoring
```
Prompt: "Based on our success criteria: [paste from design challenge brief],
help me set up post-launch monitoring:

For each metric:
- Metric name
- Baseline value (before launch)
- Target value
- How to measure (analytics tool, event name, funnel definition)
- Check frequency (daily for first week, weekly after)
- Alert threshold (when to escalate)

Also monitor:
- Error rates on new flows
- Support tickets mentioning the feature
- Rage clicks or repeated actions (if heatmap tool available)
- Feature adoption rate (% of eligible users who engage)

Create a monitoring checklist I can follow."
```

### 2. Week 1 check-in
```
Prompt: "It's been one week since launch. Here's the data: [paste metrics].
Analyze:
- Are we trending toward or away from targets?
- Any unexpected behaviors? (drops, spikes, edge cases)
- Error rates: Are they elevated?
- Qualitative signals: Any support tickets or Slack feedback?
- Early adoption rate

Assessment: On track / Needs attention / Critical issue
Draft a Slack update for the project channel."
```

### 3. Ongoing monitoring
```
Prompt: "Week [N] data: [paste metrics].
Compare against:
- Baseline (pre-launch)
- Week 1 (initial signal)
- Target

Trend analysis: Improving / Stable / Declining
If declining: Hypothesize why and suggest investigation approach.
If stable below target: Suggest potential design iterations.
If meeting/exceeding target: Document what worked."
```

### 4. Performance summary
```
Prompt: "Create a post-launch performance summary using templates/performance-summary.md:
- Feature: [name]
- Launch date: [date]
- Monitoring period: [weeks]
- Metric results vs. targets (table)
- Key observations
- User feedback summary
- What worked well
- What underperformed and hypothesized reasons
- Recommended next steps (iterate, expand, monitor, sunset)

Post to Notion. Share in Slack:
'[Project] post-launch summary: [one-line verdict].
Primary metric: [baseline] → [current] (target: [target]).
Full report: [link]. Feeds into retrospective.'"
```

## Integrations
- **Analytics tool**: (Amplitude, Mixpanel, GA, PostHog) Metric tracking
- **Slack**: Regular updates, escalation
- **Notion**: Performance summary documentation
- **Support tool**: (Zendesk, Intercom) Ticket monitoring
- **Hotjar/FullStory**: (Optional) Session replay, heatmaps
- **Linear/Jira**: Bug tickets for production issues

## Templates
- `templates/performance-summary.md`

## Definition of Done
- [ ] Monitoring set up for all success metrics
- [ ] Week 1 check-in completed
- [ ] 2-4 week monitoring period completed
- [ ] Performance summary written
- [ ] Results shared with team
- [ ] Next steps recommended

## Customization Notes
- For features behind feature flags: compare flagged vs unflagged cohorts
- For low-traffic features: extend monitoring period to get sufficient data
- If you don't have analytics: use qualitative signals (support tickets, Slack feedback, user interviews)
- Designer involvement in monitoring signals to the org that design cares about outcomes, not just outputs

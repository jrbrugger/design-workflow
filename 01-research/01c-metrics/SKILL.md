---
name: 01c-metrics
description: >-
  Pull behavioral analytics data from Mixpanel, Amplitude, PostHog, or GA4 to answer
  specific research gaps with quantitative evidence. Translates plain-language research
  questions into API queries, synthesizes results as research evidence, and feeds findings
  into the insight report and gap tracker. Use when research gaps can be answered with
  behavioral data, or when triangulating qualitative interview findings with usage patterns.
  Triggers on: "analytics", "metrics", "Mixpanel", "Amplitude", "funnel data",
  "retention data", "usage data", "behavioral data", "quantitative research".
---

# 01c — Metrics

## Purpose

Connects to product analytics to answer research gaps with quantitative signal. Works alongside `01c-data-collection` — not a replacement for it. Key mental shift: analytics is research data, not a reporting dashboard.

## When to Use

- After `01a-gap-analysis` identifies gaps answerable with behavioral data
- During `01c-data-collection` as a parallel workstream
- During `01d-synthesis` to triangulate qualitative patterns with usage data
- When a stakeholder challenges an insight with "but do we have data on that?"

## Inputs

- Prioritized research gaps from `01a-gap-analysis` (required)
- Analytics platform credentials (from environment — see Setup section)
- Event taxonomy / data dictionary for the product (recommended)
- Date range (default: last 90 days; last 12 months for retention/churn)

## Outputs

- [ ] **Metrics findings doc** — quantitative evidence per research gap
- [ ] **Gap tracker updates** — confidence scores revised with data
- [ ] **Triangulation notes** — where data confirms or contradicts qualitative findings
- [ ] **Data questions log** — gaps that need better instrumentation
- [ ] **Posted to Notion** research project page

---

## Setup

Store credentials in `.env` (gitignored) — never hardcode in skill files or config.

```
# .env (gitignored — never commit this file)

# Mixpanel
MIXPANEL_PROJECT_ID=""
MIXPANEL_SERVICE_ACCOUNT_USERNAME=""
MIXPANEL_SERVICE_ACCOUNT_SECRET=""

# Amplitude
AMPLITUDE_API_KEY=""
AMPLITUDE_SECRET_KEY=""

# PostHog
POSTHOG_PROJECT_API_KEY=""
POSTHOG_HOST="https://app.posthog.com"

# GA4
GA4_PROPERTY_ID=""

# On-chain (crypto/DeFi)
DUNE_API_KEY=""
```

Reference in your `CLAUDE.md`:
```
# Analytics credentials
Analytics API credentials are stored in .env. Use them when executing
01c-metrics queries. Never log or output credentials in responses.
```

---

## Research Questions → Metric Queries

| Research gap type | Best approach | Key signals |
|-------------------|--------------|-------------|
| Where do users drop off? | Funnel analysis | Step conversion %, time-to-next-step |
| Which features are actually used? | Event segmentation | Unique users per feature per week |
| How long until first value? | Time-to-event (JQL/HogQL) | Median + p90 for first key action |
| Who churns and when? | Retention cohort | Week-N retention by signup cohort |
| What do power users do differently? | User path / segmentation | Event sequences for top-decile users |
| Is usage improving after a change? | Before/after segmentation | Event rate pre/post release date |
| Where do users spend the most time? | Session analysis | Avg time on screen / page |
| Which segments behave differently? | Property breakdown | Event rate by plan / role / source |

---

## Platform Guides

### Mixpanel

**Segmentation API** — event counts over time, filtered by property:
```bash
curl -u "$MIXPANEL_SERVICE_ACCOUNT_USERNAME:$MIXPANEL_SERVICE_ACCOUNT_SECRET" \
  "https://mixpanel.com/api/query/segmentation?project_id=$MIXPANEL_PROJECT_ID" \
  --data-urlencode 'event=["Button Clicked"]' \
  --data-urlencode 'from_date=2025-12-01' \
  --data-urlencode 'to_date=2026-03-01' \
  --data-urlencode 'where=properties["button_name"] == "Export"' \
  --data-urlencode 'type=general'
```

**Funnel API** — step-by-step conversion:
```bash
curl -u "$MIXPANEL_SERVICE_ACCOUNT_USERNAME:$MIXPANEL_SERVICE_ACCOUNT_SECRET" \
  "https://mixpanel.com/api/query/funnels?project_id=$MIXPANEL_PROJECT_ID" \
  --data-urlencode 'funnel_id=YOUR_FUNNEL_ID' \
  --data-urlencode 'from_date=2025-12-01' \
  --data-urlencode 'to_date=2026-03-01'
```

**JQL** — JavaScript Query Language (most flexible):
```bash
curl -u "$MIXPANEL_SERVICE_ACCOUNT_USERNAME:$MIXPANEL_SERVICE_ACCOUNT_SECRET" \
  "https://mixpanel.com/api/query/jql?project_id=$MIXPANEL_PROJECT_ID" \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  --data-urlencode 'script=
function main() {
  return Events({
    from_date: "2025-12-01",
    to_date: "2026-03-01",
    event_selectors: [{event: "First Key Action"}]
  })
  .groupByUser(function(state, events) {
    state.first = state.first || events[0].time;
    return state;
  })
  .reduce(function(accumulators) {
    var times = accumulators.map(a => a.first);
    times.sort();
    return { median: times[Math.floor(times.length / 2)] };
  });
}'
```

```
Prompt: "Research gap: [paste gap].
My Mixpanel has these relevant events: [paste from data dictionary].
Write the Mixpanel API query that best answers this question.
Then I'll run it and paste the results back for interpretation."
```

### Amplitude

**Chart API:**
```bash
curl -u "$AMPLITUDE_API_KEY:$AMPLITUDE_SECRET_KEY" \
  "https://amplitude.com/api/3/chart/CHART_ID/query"
```

**Segmentation API:**
```bash
curl -u "$AMPLITUDE_API_KEY:$AMPLITUDE_SECRET_KEY" \
  "https://amplitude.com/api/2/events/segmentation" \
  -d 'e={"event_type":"Button Clicked"}' \
  -d 'start=20251201' \
  -d 'end=20260301'
```

**Funnel API:**
```bash
curl -u "$AMPLITUDE_API_KEY:$AMPLITUDE_SECRET_KEY" \
  "https://amplitude.com/api/2/funnels" \
  -d 'e=[{"event_type":"Sign Up"},{"event_type":"First Action"},{"event_type":"Conversion"}]' \
  -d 'start=20251201' \
  -d 'end=20260301'
```

```
Prompt: "Research gap: [paste gap].
My Amplitude has these relevant events: [paste from data dictionary].
Write the Amplitude API query that best answers this question.
Then I'll run it and paste the results back for interpretation."
```

### PostHog

**HogQL Query:**
```bash
curl -H "Authorization: Bearer $POSTHOG_PROJECT_API_KEY" \
  "$POSTHOG_HOST/api/projects/@current/query/" \
  -H 'Content-Type: application/json' \
  -d '{"query": {"kind": "HogQLQuery", "query": "SELECT event, count() FROM events WHERE timestamp > now() - interval 90 day GROUP BY event ORDER BY count() DESC"}}'
```

**Funnel Insight:**
```bash
curl -H "Authorization: Bearer $POSTHOG_PROJECT_API_KEY" \
  "$POSTHOG_HOST/api/projects/@current/insights/" \
  -H 'Content-Type: application/json' \
  -d '{"filters": {"insight": "FUNNELS", "events": [{"id": "Sign Up"}, {"id": "First Action"}, {"id": "Conversion"}], "date_from": "-90d"}}'
```

```
Prompt: "Research gap: [paste gap].
My PostHog has these relevant events: [paste from data dictionary].
Write the PostHog HogQL query that best answers this question.
Then I'll run it and paste the results back for interpretation."
```

### GA4

**Python client:**
```python
from google.analytics.data_v1beta import BetaAnalyticsDataClient
from google.analytics.data_v1beta.types import RunReportRequest, DateRange, Dimension, Metric

client = BetaAnalyticsDataClient()
request = RunReportRequest(
    property=f"properties/{os.environ['GA4_PROPERTY_ID']}",
    dimensions=[Dimension(name="pagePath"), Dimension(name="deviceCategory")],
    metrics=[Metric(name="sessions"), Metric(name="bounceRate")],
    date_ranges=[DateRange(start_date="90daysAgo", end_date="today")],
)
response = client.run_report(request)
```

```
Prompt: "Research gap: [paste gap].
My GA4 property tracks these events and dimensions: [paste from data dictionary].
Write the GA4 API query (Python or REST) that best answers this question.
Then I'll run it and paste the results back for interpretation."
```

---

## Steps

### 1. Translate gaps into metric questions
```
Prompt: "Here are our prioritized research gaps from the gap tracker: [paste gaps].
For each gap, determine:
- Can behavioral data answer this? (yes / partially / no)
- If yes: what specific metric or query would answer it?
- Which analytics platform and API to use?
- What date range is appropriate?
Skip gaps that require qualitative methods — those belong in 01c-data-collection."
```

### 2. Pull the data
```
Prompt: "For research gap: [paste gap]
Write the [platform] API query. I'll run it and paste the raw result back.
When you interpret, always capture:
- Exact query used
- Date range
- Sample size (N = ___ users / ___ events)
- Raw result"
```

### 3. Interpret findings as research evidence
```
Prompt: "Here's the raw analytics result: [paste result].
The original research gap was: [paste gap].
Interpret this as research evidence:
- What does the data show? (plain language, not dashboard speak)
- Confidence score for the original assumption (1-10)
- What we CANNOT conclude from this data alone
- New qualitative questions this raises
- Triangulation note: does this confirm or contradict what we heard in interviews?"
```

### 4. Triangulate with qualitative data
```
Prompt: "Compare our analytics findings with our qualitative research:
- Analytics findings: [paste or reference]
- Interview/observation findings: [paste or reference]
For each research gap, note:
- Where quant and qual agree (strong evidence)
- Where they contradict (needs investigation)
- Where only one source has signal (partial evidence)
Assign a combined confidence score."
```

### 5. Log instrumentation gaps
```
Prompt: "During our analytics research, we hit these data gaps — events or properties
that should exist but don't. For each gap, draft a ticket brief:
- Event name (proposed)
- Properties to capture
- Where it fires in the product
- Why it matters for research
Format as Linear/Jira ticket descriptions."
```

---

## Important Caveats

Always include these in your output:

1. **Correlation ≠ causation.** Analytics shows what happened, not why.
2. **Analytics only tracks instrumented behavior.** Absence of data ≠ absence of behavior.
3. **Averages hide distributions.** Check p90 and segment by cohort.
4. **Recency bias in short time windows.** Use 90-day minimum for stable patterns.
5. **Self-selection in your user base.** Active users are not representative of churned users.

---

## Integrations

- **Mixpanel / Amplitude / PostHog / GA4**: Analytics API queries
- **Notion**: Post metrics findings to research project page
- **Slack**: Share key findings with project channel
- **Linear**: Log instrumentation gap tickets

## Assets

- `assets/metrics-finding.md` — Metrics evidence template

## Definition of Done

- [ ] All analytically-answerable research gaps queried
- [ ] Each result interpreted as research evidence, not a business metric
- [ ] Gap tracker confidence scores updated with quantitative evidence
- [ ] Instrumentation gaps logged as tickets
- [ ] Metric findings added to insight report and posted to Notion

## Customization Notes

- **Crypto/DeFi:** Also consider on-chain data (Dune Analytics SQL) — same question → query → interpret pattern; DUNE_API_KEY env var
- **B2B with low event volumes:** Aggregate over 6–12 months; lean more on qualitative
- **Pre-launch:** Skip this skill entirely
- **Products with Segment:** Segment sits upstream; query via whichever downstream destination is active

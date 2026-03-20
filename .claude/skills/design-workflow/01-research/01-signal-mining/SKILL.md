---
name: 01-signal-mining
description: >-
  Harvest and synthesize passive signals from public sources — App Store/Play Store reviews,
  Reddit, HackerNews, G2/Capterra, GitHub Issues, and Twitter/X — before primary research
  begins. Use to cheaply close low-confidence assumptions in the gap tracker and surface
  hypotheses for 01b-research-plan. Triggers on: "signal mining", "what are people saying
  about X", "gather passive data", "app reviews", "Reddit analysis", "competitive signal",
  "community feedback", "pre-research".
---

# 01 — Signal Mining

## Purpose

Turns passive community data into structured hypotheses and gap-tracker inputs. Runs before `01a-gap-analysis` or feeds into an existing gap tracker to close low-confidence assumptions cheaply before spending interview budget.

## When to Use

- Before `01a-gap-analysis` kicks off on a new project
- When joining a new company or product to ramp up quickly
- When validating a hypothesis cheaply before investing in interviews
- During `01c-data-collection` as a competitive research workstream
- Ongoing: run monthly to monitor sentiment and catch emerging friction

## Inputs

- Product name and core use case (required)
- Competitor names (optional but recommended)
- Open research gaps from `01a-gap-analysis` gap tracker (optional)
- Time range (default: last 90 days)

## Outputs

- [ ] **Signal summary** — structured findings per source
- [ ] **Problem clusters** — ranked by frequency across sources
- [ ] **Ranked hypotheses** — HIGH / MEDIUM / LOW confidence
- [ ] **Gap tracker updates** — confidence scores revised
- [ ] **Blind spots log** — what this data cannot tell us
- [ ] **Posted to Notion** research project page

## Pipeline Position

```
[00-kickoff] → [01-signal-mining] → [01a-gap-analysis] → [01b-research-plan] → ...
```

---

## Sources

### App Store / Play Store Reviews

Collect 1–3 star reviews from last 90 days. Tag each as: bug / missing-feature / UX-confusion / performance / pricing / support.

```
Prompt: "Search for [product] reviews on the App Store and Google Play Store.
Collect 1-3 star reviews from the last 90 days.
For each review, extract:
- Rating (1-3 stars)
- Date
- Key complaint (one sentence)
- Tag: bug / missing-feature / UX-confusion / performance / pricing / support
Group by tag and rank by frequency.
Format as a table."
```

**Tool:** Web search for "[product] app store reviews", or `app-store-scraper` / `google-play-scraper` Python packages.

**Limitation:** Skews toward frustrated users; weight frequency not severity.

### Reddit

Collect mentions in relevant subreddits. High comment count = high friction signal.

```
Prompt: "Search Reddit for mentions of [product] in these subreddits: [list from config].
Focus on posts from the last 90 days with 10+ comments.
For each relevant post, extract:
- Subreddit, title, comment count
- Core complaint or discussion topic
- Top-voted reply sentiment (positive / negative / mixed)
- Any feature requests or workarounds mentioned
Rank by comment count (proxy for friction intensity)."
```

**Tool:** Reddit API (free, requires app registration) or `site:reddit.com [product]` search.

**For DeFi/crypto products:** Also check r/defi, r/ethfinance, r/CryptoTechnology, protocol-specific subs.

### HackerNews

Collect "Ask HN", "Show HN", and comment threads. Useful for B2B and developer tools.

```
Prompt: "Search HackerNews for [product] using the Algolia API:
https://hn.algolia.com/api/v1/search?query=[product]&tags=story&numericFilters=created_at_i>[90_days_ago_unix]
For each result with 5+ comments, extract:
- Title, points, comment count
- Key discussion themes
- Feature requests or complaints
- Sentiment: positive / negative / mixed"
```

**Tool:** HN Algolia API (free, no auth).

### G2 / Capterra / Trustpilot (B2B Products)

Focus on "What do you dislike?" / "Cons" fields. Also mine competitor reviews.

```
Prompt: "Search for [product] reviews on G2, Capterra, and Trustpilot.
Focus on the 'Cons' and 'What do you dislike?' fields.
Also search for reviews of competitors: [competitor list].
Extract:
- Common complaints (grouped by theme)
- Feature gaps mentioned across multiple reviews
- Any direct comparisons to competitors
Format as a comparison table."
```

**Tool:** `site:g2.com [product] reviews`, `site:capterra.com [product]`.

### GitHub Issues (Developer Tools / APIs / Open-Source)

Collect open issues with 5+ reactions or open 6+ months.

```
Prompt: "Query GitHub Issues for [repo]:
https://api.github.com/repos/{owner}/{repo}/issues?state=open&sort=reactions
Collect issues with 5+ reactions or open longer than 6 months.
Cluster into: UX problems / missing features / performance / documentation gaps.
For each cluster, note:
- Issue count
- Total reactions
- Representative issue titles
- Whether any have PRs in progress"
```

**Tool:** GitHub REST API (free for public repos).

### Twitter / X

Collect complaints, comparisons, feature requests.

```
Prompt: "Search Twitter/X for:
- '[product] wish'
- '[product] vs'
- '[product] broken'
- '[product] please'
- '[product] switched to'
Collect tweets from the last 90 days with engagement.
Extract:
- Complaint or request (one sentence)
- Engagement (likes + retweets)
- Any competitor mentioned
- Sentiment: frustrated / hopeful / comparing"
```

**For crypto products:** Also check Farcaster and Lens.

### Discord / Telegram

Hand off to existing `discord-signal-analysis` skill (if available). Output feeds into Phase 3 of this skill.

### Support Tickets (Intercom / Zendesk / Linear)

If internal access exists: export last 90 days, cluster by underlying need.

```
Prompt: "I'm pasting [N] support tickets from the last 90 days.
Cluster them by underlying user need (not surface keywords).
For each cluster:
- Ticket count
- Representative examples (2-3)
- Underlying need in one sentence
- Severity: blocking / frustrating / minor
Rank clusters by frequency."
```

---

## Phases

### Phase 1: Per-Source Collection

Run prompts for each relevant source. Collect raw signal before clustering.

```
Prompt: "We're mining signals for [product]. Here's the context: [paste product description].
Competitors: [list]. Time range: last 90 days.
Run through each relevant source from the list above.
For each source, collect raw signals and format using the signal-log template at assets/signal-log.md.
Start with [source] and I'll tell you which sources to cover."
```

### Phase 2: Cross-Source Synthesis

```
Prompt: "Here are all the signals we've collected across sources: [paste or reference].
Now synthesize:
1. Extract all distinct signals
2. Tag each by source and type (bug / missing-feature / UX-confusion / performance / pricing / support)
3. Cluster by underlying user need (not surface keywords)
4. Rank clusters by: frequency × number of sources mentioning it
5. For each cluster, write a falsifiable hypothesis:
   'We believe [statement] because [evidence from N sources]. Confidence: HIGH/MEDIUM/LOW.'
Format the top 10 clusters with their hypotheses."
```

### Phase 3: Gap Tracker Update

```
Prompt: "Cross-reference our signal mining findings against the existing gap tracker from 01a-gap-analysis:
[paste gap tracker or link]
For each existing gap:
- Does signal data change the confidence score? Update it.
- What new evidence supports or contradicts the assumption?
Also flag any NEW gaps that emerged from signal mining that weren't in the original tracker.
Format updates as a table: Gap / Previous Confidence / New Confidence / Evidence."
```

### Phase 4: Blind Spots Log

Always include this phase. Document what this data cannot tell us.

```
Prompt: "Based on our signal mining, document the blind spots:
- Which user segments are invisible in this data? (e.g., non-English speakers, enterprise users, churned users)
- Which platforms or sources are we missing?
- What requires primary research (interviews, observation) that passive data can't answer?
- Which hypotheses from Phase 2 need interview validation before designing against them?
Format as a structured log with clear next-step recommendations."
```

---

## Integrations

- **Notion**: Post signal summary and clusters to research project page
- **Slack**: Post top findings summary to project channel
- **discord-signal-analysis**: Hand off Discord/Telegram analysis
- **Web search**: Primary tool for most source collection
- **GitHub API**: For open-source and developer tool signal

## Assets

- `assets/signal-log.md` — Signal collection and clustering template

## Definition of Done

- [ ] At least 2 relevant sources mined
- [ ] Raw signal cleaned and clustered into problem themes
- [ ] Top 5 clusters have falsifiable hypotheses with confidence scores
- [ ] Gap tracker updated with new confidence scores and any new gaps
- [ ] Blind spots log produced
- [ ] Findings posted to Notion and summarized in Slack

## Customization Notes

- **Crypto/DeFi:** Prioritize Reddit, Discord/Telegram, Twitter/X; App Store reviews are thin
- **B2B SaaS:** Prioritize G2/Capterra, HN, GitHub Issues
- **Consumer apps:** App Store reviews and Reddit are highest signal
- **Developer tools:** GitHub Issues and HN primary; supplement with r/webdev, r/programming
- **Pre-launch products with no public signal:** Skip this skill, go to 01a directly

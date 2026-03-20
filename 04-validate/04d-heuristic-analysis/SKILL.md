---
name: 04d-heuristic-analysis
description: >-
  Conducts structured expert UX evaluation of an existing product or design using Nielsen's
  10 heuristics plus domain-specific extensions. Produces a severity-ranked issue list,
  a heuristic scorecard, and prioritized design recommendations. Use when you need fast
  expert evaluation without user recruitment — for auditing existing products, evaluating
  competitor UX, assessing designs before usability testing, or onboarding to a new
  product. Triggers on: "heuristic analysis", "heuristic evaluation", "UX audit",
  "expert review", "audit the product", "evaluate this design", "UX review".
---

# 04d — Heuristic Analysis

**Expert UX evaluation without recruiting a single user.**

A structured walkthrough of a product or design using established usability heuristics
to surface issues, rate severity, and produce actionable recommendations — typically in
2–4 hours.

---

## Purpose

Heuristic analysis is the fastest way to identify usability issues when:

- You can't recruit users yet (early design, competitive audit)
- You need to baseline an existing product before redesigning it
- You want to pressure-test a design before usability testing
- You're auditing a competitor's UX as part of `01c-competitive-analysis`
- You've just joined a product and need to understand its problems quickly

It doesn't replace user research — it focuses it. Issues found here become
hypotheses to test in `04a-prototype-testing`.

## When to Use

- **Onboarding to a new product**: audit what exists before touching anything
- **Before redesign**: establish a baseline issue inventory to reference post-launch
- **Before usability testing (04a)**: identify obvious issues first, so test sessions
  focus on the non-obvious ones
- **Competitive audit**: evaluate competitor UX as part of `01c-competitive-analysis`
- **After major feature release**: quick expert check before users complain

## Inputs

- Access to the product (live product, staging, or clickable Figma prototype)
- Scope definition — which flows and surfaces to evaluate
- Context brief: who the target user is, what their primary jobs are (from `02a`)
- Prior research if available (signal mining output, support ticket themes, insight report)

## Outputs

- [ ] **Heuristic scorecard** → `assets/heuristic-scorecard.md` — per-heuristic ratings
- [ ] **Issue register** → `assets/issue-register.md` — every issue with severity rating
- [ ] **Priority recommendations** → top issues ranked by severity × frequency × fix effort
- [ ] **Posted to Notion** project page
- [ ] **Shared in Slack** with summary and critical issues flagged

---

## The heuristics

This skill uses Nielsen's 10 heuristics as the primary framework, extended with
domain-specific additions for the product types you work with most.

### Nielsen's 10 heuristics

**H1 — Visibility of system status**
The system always keeps users informed about what is going on, through appropriate
feedback within reasonable time.

*Look for:* Loading states, progress indicators, success/error feedback, action
confirmation, background processes, real-time updates.

*Common violations:* Silent form submissions, loading spinners with no indication of
how long, no confirmation after destructive actions, no feedback on async operations.

---

**H2 — Match between system and the real world**
The system speaks the users' language — words, phrases, and concepts familiar to the
user, rather than system-oriented terms. Information appears in a natural and logical order.

*Look for:* Label language (is it user vocabulary or engineering vocabulary?), metaphors,
mental model alignment, date/number/currency formatting appropriate to locale.

*Common violations:* Error codes instead of plain language, internal jargon in UI copy,
database field names surfaced directly, illogical information hierarchy.

---

**H3 — User control and freedom**
Users often choose system functions by mistake and need clearly marked emergency exits —
without having to go through extended dialogue.

*Look for:* Undo/redo, cancel options in flows, back navigation, escape paths from
modals and wizards, recovery from mistakes, draft saving.

*Common violations:* Destructive actions with no undo, multi-step flows with no way
to exit without losing progress, modals that trap users, no draft state.

---

**H4 — Consistency and standards**
Users should not have to wonder whether different words, situations, or actions mean
the same thing. Follow platform conventions.

*Look for:* Consistent terminology across the product, consistent component behavior,
platform convention adherence (iOS/Android/web), consistent visual language, consistent
interaction patterns for similar tasks.

*Common violations:* Same concept called different things in different parts of the
product, components that look similar but behave differently, ignoring platform affordances.

---

**H5 — Error prevention**
Even better than good error messages is a careful design which prevents problems from
occurring in the first place.

*Look for:* Confirmation dialogs for destructive actions, input constraints and formatting
help, inline validation before submission, clear affordances (what's clickable?), preventing
invalid states.

*Common violations:* Forms that only validate on submit, no warning before data loss,
ambiguous buttons that could be misinterpreted, no confirmation on delete.

---

**H6 — Recognition over recall**
Minimize the user's memory load by making objects, actions, and options visible. The
user should not have to remember information from one part of an interface to another.

*Look for:* Persistent context (what page am I on, what step in a flow?), visible
options rather than hidden commands, recently used items, sensible defaults, in-context
help.

*Common violations:* Keyboard shortcut-only features with no UI affordance, requiring
users to remember values from a previous screen, no breadcrumbs in complex IA, empty
search boxes with no hint of what to type.

---

**H7 — Flexibility and efficiency of use**
Accelerators — unseen by novice users — allow power users to operate more efficiently.
Allow users to tailor frequent actions.

*Look for:* Keyboard shortcuts, bulk actions, saved filters/views, quick actions,
personalization, power user paths that don't compromise novice flows.

*Common violations:* No bulk actions in list views, repeated tasks that can't be saved,
no keyboard accessibility, no way to skip or collapse sections that are learned.

---

**H8 — Aesthetic and minimalist design**
Dialogues should not contain irrelevant or rarely needed information. Every extra unit
of information competes with the relevant units and diminishes their relative visibility.

*Look for:* Information density appropriate to context and user type, progressive
disclosure of complexity, visual hierarchy that guides attention, absence of decorative
UI that adds no meaning.

*Common violations:* Dashboards with 15 equally-weighted metrics, modals with excessive
fine print, forms with fields that only 2% of users need, marketing copy embedded in
product UI.

---

**H9 — Help users recognize, diagnose, and recover from errors**
Error messages should be expressed in plain language (no error codes), precisely indicate
the problem, and constructively suggest a solution.

*Look for:* Error message clarity, actionability (can the user fix it?), location
(field-level vs. form-level vs. page-level), tone (blaming vs. helpful), recovery path.

*Common violations:* "Something went wrong" with no context, error codes without
explanation, errors that clear the form fields, error messages that don't tell the user
what to do next.

---

**H10 — Help and documentation**
Even though it is better if the system can be used without documentation, it may be
necessary to provide help. Such information should be easy to search, focused on the
user's task, list concrete steps, and not be too large.

*Look for:* In-context help (tooltips, inline explanations), empty state guidance,
searchable documentation, onboarding walkthroughs, progressive disclosure of
advanced features.

*Common violations:* Feature-only empty states with no guidance, help that opens
external docs instead of inline tooltips, no onboarding for complex features.

---

### Domain-specific extensions

Use these in addition to the core 10 for relevant product types.

**H11 — Data trust and transparency** *(fintech, DeFi, data products)*
Users must be able to understand where data comes from, how current it is, and what
confidence to place in it. Opaque data erodes trust.

*Look for:* Data source attribution, timestamp/freshness indicators, confidence
intervals, distinction between real-time and cached data, explanation of derived metrics.

*Common violations:* Charts with no x/y axis labels, price data with no timestamp,
"analytics" dashboards with no explanation of calculation methodology, AI-generated
content with no indication it's AI.

**H12 — Two-sided clarity** *(marketplace and B2B platform products)*
Both sides of a marketplace must be able to understand their role, permissions, and
how their actions affect the other side.

*Look for:* Clear role differentiation in UI, permissions that are visible not just
enforced, actions that affect the other side flagged as such, pricing/terms visibility
for all parties.

*Common violations:* Admin actions that silently affect buyers/sellers, permissions
that are only revealed when the user tries to do something and is blocked, different
vocabulary for the same concept across buyer/seller sides.

**H13 — Progressive trust** *(DeFi, financial, security-sensitive products)*
Users are asked for progressively higher levels of trust (data, funds, permissions) in
proportion to the value they've received so far. High-stakes actions are never buried
in flows.

*Look for:* Permission escalation that matches demonstrated value, prominent disclosure
of high-stakes actions (irreversible transactions, wallet approvals), clear communication
of risk before commitment.

*Common violations:* Asking for wallet approval before the user has understood what
they're approving, burying transaction fees until the last step, irreversible actions
with the same visual weight as reversible ones.

---

## Steps

### 1. Define scope

```
Prompt: "We're conducting a heuristic evaluation of [product name].
Target user: [from 02a or project brief]
Primary user jobs: [from JTBD, or describe]
Prior known issues: [paste from signal mining, support tickets, or insight report — if any]

Define the evaluation scope:
- Which flows are in scope? Prioritize by: frequency of use, known pain, strategic importance.
- Which surfaces? (Web, mobile, both?)
- What is out of scope? (e.g., admin UI, payment processing, third-party integrations)

Suggest a walkthrough order that mirrors a real user's journey — start at the entry
point (homepage, login, onboarding) and progress to the core task flows.
List the specific flows to evaluate in order."
```

---

### 2. Walkthrough the product

Work through each flow in scope systematically. For each screen or state, evaluate
against all applicable heuristics.

```
Prompt: "I'm evaluating [flow name] in [product].
Here is what I'm seeing: [describe or paste screenshot context].
Target user for this flow: [user type].
Their goal at this point: [job to be done].

Evaluate this against all 10 Nielsen heuristics (plus H11/H12/H13 if applicable).
For each heuristic:
- Rating: Pass / Minor issue / Major issue / Critical issue / N/A
- Observation: What specifically did you notice? Be concrete.
- Issue: What problem does this create for the user?
- Severity: 0 (no issue) / 1 (cosmetic) / 2 (minor) / 3 (major) / 4 (critical)

Use Nielsen's severity scale:
  0 — Not a usability issue
  1 — Cosmetic: only fix if time permits
  2 — Minor: low priority, fix eventually
  3 — Major: important to fix, high priority
  4 — Critical: imperative to fix before launch"
```

Repeat for each flow in scope. Capture all findings in `assets/issue-register.md`
as you go — don't wait until the end.

---

### 3. Score the heuristic scorecard

```
Prompt: "Based on all the observations across all flows, complete the heuristic
scorecard (assets/heuristic-scorecard.md).

For each heuristic, give:
- Overall rating: Excellent / Good / Needs improvement / Poor
- Score: 1–5 (5 = fully satisfies the heuristic, 1 = severely violates it)
- Summary: 1–2 sentences on the product's overall performance on this heuristic
- Worst offending instance: name one specific example

Calculate a weighted overall score:
- H1 (system status): weight 1.5×
- H4 (consistency): weight 1.5×
- H5 (error prevention): weight 1.5×
- All others: weight 1×
Report both raw and weighted overall scores."
```

---

### 4. Synthesize the issue register

```
Prompt: "Here is the complete issue register from the heuristic walkthrough: [paste].

Now synthesize:
1. Total issues by severity (count of 4s, 3s, 2s, 1s)
2. Most violated heuristics (which heuristic appears most in the issue list?)
3. Most problematic flows (which flows have the highest severity concentration?)
4. Issue patterns — are multiple issues symptoms of the same root cause?
   (e.g., 'six separate issues are all caused by the lack of a persistent breadcrumb')
5. Quick wins — severity 2–3 issues with low fix effort
6. Critical path issues — severity 3–4 issues on the primary user journey"
```

---

### 5. Prioritize recommendations

```
Prompt: "Produce a prioritized recommendation list from the issue register.

Priority tiers:
P0 — Fix immediately: Severity 4 issues, or clusters of severity 3 issues on the
     critical user path. These block task completion or destroy trust.
P1 — Fix before next release: Severity 3 issues off the critical path, or patterns
     of severity 2 that collectively degrade experience significantly.
P2 — Fix in backlog: Severity 1–2 issues. Polish and consistency.
P3 — Monitor: Potential issues that need validation with users before fixing.

For each recommendation:
- Issue (reference the issue register ID)
- Heuristic violated
- User impact (what goes wrong for the user)
- Recommended fix (specific — not 'improve UX' but 'add an inline success confirmation
  after form submission that persists for 3 seconds')
- Fix effort: S / M / L / XL
- Priority tier: P0 / P1 / P2 / P3"
```

---

### 6. Document and share

```
Prompt: "Create a heuristic analysis page in Notion under the project research hub.
Structure:
- Executive summary (3–5 sentences: overall health, critical findings, recommended action)
- Heuristic scorecard (full table)
- Priority recommendations (P0 first, then P1)
- Full issue register (linked or embedded)

Post to project Slack channel:
'Heuristic analysis complete for [product/flow]. Overall score: [X/5].
[N] critical issues, [N] major issues found.
Top finding: [one-sentence insight].
P0 recommendations: [2–3 bullets].
Full analysis: [Notion link].'
Tag PM and engineering lead for P0 items."
```

---

## Severity reference

| Severity | Label | Definition | Action |
|----------|-------|------------|--------|
| 4 | Critical | Prevents task completion or destroys trust | Fix before any release |
| 3 | Major | Significant friction, workaround required | High priority backlog |
| 2 | Minor | Noticeable, user eventually succeeds | Normal backlog |
| 1 | Cosmetic | Minor visual/copy issue | Fix if time allows |
| 0 | No issue | Passes the heuristic | No action |

---

## Integrations

- **Notion**: Heuristic scorecard, issue register, recommendations
- **Slack**: Findings summary, P0 escalation
- **Figma**: If evaluating a prototype rather than a live product
- **Linear**: Create tickets for P0 and P1 issues directly from the issue register
- **01c-competitive-analysis**: Use this skill to evaluate competitor UX in depth

## Assets

- `assets/heuristic-scorecard.md` — Per-heuristic rating and summary
- `assets/issue-register.md` — Full issue log with severity, heuristic, recommendation

## Definition of Done

- [ ] Scope defined and all in-scope flows walked through
- [ ] Every screen/state evaluated against applicable heuristics
- [ ] Issue register complete with severity ratings
- [ ] Heuristic scorecard filled and overall score calculated
- [ ] Recommendations prioritized into P0–P3 tiers
- [ ] Posted to Notion and shared in Slack
- [ ] P0 issues flagged to PM and engineering

---

## Time guidance

| Scope | Estimated time |
|-------|---------------|
| Single flow (3–5 screens) | 1–2 hours |
| Core product (onboarding + 2 primary flows) | 2–4 hours |
| Full product audit (all major flows) | 4–8 hours |
| Competitive audit (Tier 1 competitor) | 2–3 hours (use abbreviated scorecard) |

---

## Customization Notes

- **When auditing a competitor**: run steps 2–4 only, skip documentation to Notion.
  Output feeds into `01c-competitive-analysis` → competitor profile UX deep-dive section.
- **When evaluating early Figma concepts** (pre-usability test): use H1, H3, H4, H5,
  H8 most heavily — the others are hard to evaluate without working interactions.
- **For mobile apps**: add evaluation of gesture discoverability, thumb zone usability,
  and system permission requests as additional heuristic dimensions.
- **For DeFi/crypto products**: H13 (progressive trust) and H11 (data transparency)
  should be weighted 2× — trust is the core UX challenge in these products.
- **For B2B products**: H7 (efficiency of use) deserves extra weight — power users will
  repeat tasks hundreds of times, so friction that's acceptable for a consumer is
  unacceptable here.
- A heuristic analysis is one evaluator's perspective. For higher confidence, run with
  2–3 evaluators independently and aggregate findings — inter-rater agreement on severity
  increases validity significantly.

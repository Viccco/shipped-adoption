# Case A — Task-to-Event Linking

## Feature

Task-to-Event Linking (see portfolio): when spec'ing a task, you pick a specific event from PostHog/Mixpanel/Amplitude that this task is meant to move.

## Context

The Shipped team shipped Task-to-Event Linking 6 months ago, in Q3 2025. The assumption was simple: if users link events to tasks at spec time, the Impact Detector gets precise signals and the post-ship reports get noticeably better. Better reports = users see Shipped's value faster = they come back more often.

The metric it was meant to move: **weekly active users** (Shipped's Q1 2026 goal is Retain: retention, i.e. keeping users active in the product).

At task spec time, the "Link event" field is inside an "Advanced" section the user has to expand by hand. The field opens an **event picker** — a list to choose a specific event from. A tooltip explains what it's for, but only on hover.

## Funnel (last 90 days, ~5,170 paying users)

Funnel measured at the user level — the decision "link an event" is made by an individual user at task spec time.

| Step | Paying users | % |
|---|---|---|
| Created at least 1 task | 4,030 | 78% |
| Expanded the "Advanced" section while spec'ing a task | 1,820 | 35% |
| Clicked into the "Link event" field | 1,505 | 29% |
| Successfully linked an event to a task | 1,195 | 23% |
| Links events on most of their tasks | 415 | 8% |

## Cohort/Outcome

Retention (weekly active rate) by usage intensity, last 90 days:

| Segment | Retention (weekly active) |
|---|---|
| Whole active user base | 50% |
| Non-user (never linked an event) | 47% |
| Casual user (linked events on 1–5 tasks) | 56% |
| Regular user (links events intensively) | **68%** |

**Value signal:** Regular users (link events intensively) retain at **68% vs. 50% for the whole active base = +18pp**. This is a **signal** (correlation), not proof — these users may have been more engaged from the start (the gap holds after controlling for team size and tenure, but it's still an observation, not an experiment). Proof would require an **aggressive test** — a deliberately bold experiment (e.g. forcing the change on a subset of users) that quickly reveals whether the effect is real.

## User quotes

> **Maria, PM, Bookloop (Pro plan, 8 months in product):**
> "Linking events is a game-changer for me. At spec time I know exactly what I want to move, and after deploy I don't have to guess which report to open. I do it on every task."

> **Tom, Head of Product, Stride (Pro plan, 4 months):**
> "I know there's some PostHog integration, but I have no idea where to turn it on. I open a new task, type a title, description, and save. Nobody tells me there's a field down there worth filling in."

> **Agnes, Senior PM, CashLedger (Pro plan, 11 months):**
> "I tried to link an event but I couldn't remember its name. I start typing 'user' and 60 events pop up. I don't know which is which. After two minutes I give up and save the task without linking."

> **Chris, PM, ReleaseDeck (Pro plan, 6 months):**
> "I used it for the first week, then stopped. You link an event, but in the 14-day report you get all the metrics anyway. Feels like the report is similar even without linking. Maybe I'm doing it wrong?"

> **Patrick, CTO, NoteFlare (Enterprise plan, 2 months):**
> "We keep our own warehouse in BigQuery. The event picker only shows us the top 200 events from our PostHog, but our most important metrics live in BigQuery. So linking just doesn't work for the things we actually care about."

## Extra data slices (on participant request)

### Segmentation by plan

| Plan | % of paying users on this plan who linked ≥1 event |
|---|---|
| Pro | 18% |
| Enterprise | 45% |
| Free | n/a (Free is capped at 1 analytics integration, small sample) |

### Segmentation by team size

| Team size | Adoption % |
|---|---|
| 1–5 users | 15% |
| 6–20 users | 28% |
| 20+ users | 38% |

### Segmentation by user role

| Role | Adoption % |
|---|---|
| Product Manager | 32% |
| Engineer | 8% |
| Designer | 3% |
| Founder / Head of Product | 15% |
| Other | 5% |

### ARR attribution

**64% of ARR** is in teams where at least one user has ever linked an event. So this feature (despite low Coverage at 23% — Coverage being the share of users who have adopted it at all) correlates with high-value accounts.

### NPS detractor commentary (3 quotes from paying users who do NOT use it)

> **NPS 4 (Detractor):** "Linking events sounds like a thing for Mixpanel power-users. I don't even know how to name my own events, I leave that to the data team."

> **NPS 5 (Detractor):** "I tried it but I don't see what it gives me. The post-deploy report generates everything anyway."

> **NPS 6 (Passive):** "My tasks are pretty generic, I don't need analytics linking."

### Top 3 support tickets (last 90 days)

| Issue | Tickets |
|---|---|
| Event picker doesn't show my PostHog events | 45 |
| Custom warehouse events don't show up in the dropdown | 28 |
| Linking has no effect on the 14-day report (Chris-pattern) | 19 |

### Time-to-first-use

Median **18 days** from first product use to first event link. For reference: time-to-first-use for Goals & Outcomes = 2 days, for Post-Ship Detector = 5 days.

## What would you do with this?

Question for the participant — no hints.

---

## Background / why (for the facilitator)

Our strongest hypotheses for why this feature has weak adoption despite high impact on the people who use it:

1. **Field buried in "Advanced"** — biggest cause of low Coverage. PMs spec a task quickly, never expand "Advanced," and move on. 65% of paying users have *never* opened that section.
2. **No active prompt** — nobody tells the user at spec time "think about which event you want to move." A tooltip exists, but only on hover, so it only works if the user already knows what they're looking for.
3. **Event picker requires knowing names** — autocomplete shows every event from PostHog (often 200+), no grouping, no "most used." A user who doesn't remember the exact name gets lost and bails.
4. **No follow-up nudges** — users who tried once and gave up (Agnes, Chris) get no push to try again after they've seen a couple of reports.
5. **Value of linking isn't visible** (Chris) — the Impact Detector generates a report even without linking, so the user doesn't feel the difference. The value of linking is real but invisible in the report — that's a value-communication problem.
6. **Enterprise edge case** (Patrick) — users on a warehouse can't link a BigQuery event. Niche but growing segment, signal for a separate feature.

**Decision the participant should reach:**
- Coverage 23% + Impact +21pp = classic low-hanging fruit
- Diagnosis: discoverability problem (most paying users have never opened "Advanced")
- Decision: PUSH distribution

**Strongest hypothesis to test (aggressive test):**
- Pull the "Link event" field out of "Advanced" and put it into the main task form, next to title and description.
- Plus: require the field before save (test the ceiling — does this work even when the user pushes back).
- A/B test on 50% of new tasks over 14 days. Measure: % of tasks with a link, weekly active rate of the cohort at 30 days.

**Traps the participant can fall into:**
- Diagnosis "this is a value problem" — because Chris says "the report feels similar." But only 8% of users link regularly, so 92% have never had the chance to *feel the difference*. This isn't a value problem, it's discoverability with a side effect on value-perception.
- Decision "let's improve the event picker" — yes, the picker needs work, but it's not the biggest lever. The picker only touches the 29% who already got that far. Pulling the field out of "Advanced" touches the other 65%.

# Case B — Outcome Roadmap

## Feature

Outcome Roadmap (see portfolio): a roadmap view organized by goals, not by features. For each goal you see the planned work, its delivery timeline, and the **confidence band** — how strongly the team believes the planned work will move the metric.

A confidence band is a confidence marker on a given goal — it shows how much the team believes the work scheduled under that goal will actually move its metric (e.g. high / medium / low). It only shows up once the goal has a metric attached and tasks linked — without those there's nothing to assess.

## Context

The Shipped team shipped Outcome Roadmap 4 months ago, in Q4 2025. The assumption: PMs lose the thread on strategic goals while planning the quarter. Classic roadmaps (Linear/Jira) show features over time, but don't answer "is what we're planning actually going to move the outcomes." Outcome Roadmap was meant to be the tool for quarterly planning and ongoing prioritization.

The metric it was meant to move: **weekly active users** (Shipped's Q1 2026 goal is Retain: retention measured as how many users are active in a given week). The team's assumption: PMs who find value in planning with Outcome Roadmap will come back more often, because it anchors them in the product beyond the narrow "ship + report" loop.

## Funnel (last 90 days, ~5,170 paying users)

| Step | Paying users | % |
|---|---|---|
| Opened the Outcome Roadmap view at least once | 3,100 | 60% |
| Opens it regularly (≥1/week) | 1,400 | 27% |
| Added their own goal to the roadmap view | 950 | 18% |
| Linked a task to a goal in the roadmap | 620 | 12% |
| Actively uses it for prioritization (edits weekly) | 270 | 5% |

## Cohort/Outcome

Retention (weekly active rate) by usage intensity, last 90 days:

| Segment | Paying users | Retention (weekly active) |
|---|---|---|
| Whole active user base | — | 50% |
| Non-user (never opened Outcome Roadmap) | 2,070 (40%) | 45% |
| Casual user (opened it, didn't link a task to a goal) | 2,480 (48%) | 52% |
| Regular user (linked a task to a goal, uses it heavily) | 620 (12%) | **70%** |

**Value signal:** Regular users (linked a task to a goal, use it heavily) retain at **70% vs. 50% for the whole active base = +20pp**. The threshold sits at the moment of task-linking — just opening the view isn't enough. This is a signal (correlation), not proof — proof would require an aggressive test.

## User quotes

> **Yvonne, Head of Product, GridPay (Enterprise plan, 5 months):**
> "Outcome Roadmap is the first place we go for quarterly planning. We look at the goals, see which ones have work planned and which are empty, debate the confidence bands. Without it, our plannings were a cacophony. Now I've got one screen to show leadership."

> **Marius, PM, FlowSet (Pro plan, 6 months):**
> "I opened the view, it looks nice, but I don't know what to do next. I click into a goal, see an empty list. Am I supposed to add tasks here? But I create tasks on the fly, I don't plan them under goals in advance. I left it for now, maybe I'll come back."

> **Karl, Senior PM, SignalKite (Pro plan, 3 months):**
> "I have Linear for the roadmap and Notion for strategy. Why do I need a third roadmap view in Shipped? Opened it twice, I don't buy it. Maybe if I saw something here I don't see elsewhere."

> **Joanna, Product Lead, Threadpost (Pro plan, 8 months):**
> "I tried to add a goal and link tasks, but nowhere is it clear that you first have to have a goal with a metric synced from PostHog. I only figured that out when I emailed support. I use it now, but the first-time approach is completely off-putting."

> **Paul, CTO and co-founder, Cloudreel (Enterprise plan, 11 months):**
> "Outcome Roadmap is our quarterly meeting. Literally. We open the view, walk outcome by outcome, every lead says what they're doing and shows progress. Without it our quarterly was a 3-hour debate instead of 45 minutes. Best thing in Shipped."

## Extra data slices (on participant request)

### Segmentation by plan

| Plan | % of paying users on this plan who added a goal to the roadmap |
|---|---|
| Pro | 14% |
| Enterprise | 38% |
| Free | 8% (small sample) |

### Segmentation by team size

| Team size | Adoption % |
|---|---|
| 1–5 users | 6% |
| 6–20 users | 19% |
| 20+ users | 32% |

Clear correlation with team size — larger orgs need quarterly planning, smaller ones don't.

### Segmentation by user role

| Role | Adoption % |
|---|---|
| Product Manager | 28% |
| Engineering Lead | 15% |
| Founder / Head of Product | 45% |
| Designer | 4% |
| Other | 5% |

### ARR attribution

**78% of ARR** sits in teams where at least one user has ever added a goal to Outcome Roadmap. Clear Enterprise tilt — this feature resonates most with larger accounts.

### NPS detractor commentary (3 quotes from paying users who do NOT use it)

> **NPS 3 (Detractor):** "We already have Notion for strategy and Linear for the roadmap. Why would I want a third tool for the same thing?"

> **NPS 5 (Detractor):** "I don't understand what a 'confidence band' is or why it's on a roadmap. Am I supposed to feel confident or not?"

> **NPS 6 (Passive):** "Roadmap isn't my job, our Head of Product does it. Maybe ask them."

### Top 3 support tickets (last 90 days)

| Issue | Tickets |
|---|---|
| How do I add a goal to Outcome Roadmap (Joanna-pattern) | 62 |
| Confidence bands don't show up for my goal | 28 |
| Roadmap won't save after editing | 12 |

### Time-to-first-use

Median **32 days** from first product use to adding the first goal to Roadmap. This is the **latest** value-realization moment in the entire Shipped portfolio — participants need time before they even consider using this feature.

## What would you do with this?

Question for the participant — no hints.

---

## Background / why (for the facilitator)

Our strongest hypotheses for why this feature has reasonable usage but shallow depth — and why there's real value here worth surfacing:

1. **The value is real and strong in a narrow group** (12% of paying users, +25pp retention). Yvonne and Paul show a clean signal: for teams that do quarterly planning, Outcome Roadmap replaces a scattered process (Notion + Linear + spreadsheet) with one view. This isn't a kill candidate — this is a feature where 88% of users never reached the moment of value.

2. **The aha-moment requires a setup sequence nobody explains:** (a) you need a goal with a metric synced from PostHog, (b) you need ≥2 goals for the roadmap view to make sense, (c) you need to link ≥3 tasks to goals before the confidence bands appear. Joanna got there via support — most people stop at step one.

3. **Marius (typical of the 60% who opened it once)** says "I don't know what to do next." This isn't discoverability — he found the feature. It's a lack of *value narrative inside the product*. The view shows an empty state, doesn't show why it's worth filling.

4. **Karl (skeptic with a competing tool stack)** is a different problem. He doesn't buy the *concept* of "roadmap by outcomes." Missing: an example or case study that shows him what he's not seeing in Linear+Notion. That's a value-communication problem in the empty state or onboarding.

5. **Linking task-to-goal** is the threshold to value (+18pp jump in retention at that step alone). Meaning: the onboarding path has to lead the user to that moment, not just to "opened the view."

6. **Empty state vs. filled state** is the chasm — when a user sees an empty Outcome Roadmap, they can't understand why it exists. Yvonne and Paul use it because *someone showed them* what a filled view looks like. Everyone else never sees it.

**Diagnosis the participant should reach:**
- This is NOT just a discoverability problem (60% of paying users opened the view — solid distribution for a 4-month-old feature).
- This is NOT a kill candidate either — the signal from the active group is strong and the value is real.
- This is a **value problem in the "the value is there, but it takes work" sense** — work on onboarding, narrative in the empty state, leading the user to the aha-moment.

**Strongest hypothesis to test:**
- The empty-state Outcome Roadmap shows an anonymized customer case study (e.g. anonymized GridPay): "This is what quarterly planning looks like for a team that uses this. This is how many decisions they made in this quarter. This is how their confidence bands shifted over the quarter."
- The first visit launches a 3-step guided setup: add a goal → sync the metric from PostHog → add 2 tasks to the goal. No skipping.
- Aggressive test: the first time someone opens Outcome Roadmap, they *have to* go through the tutorial. A/B test on 50% of paying users over 14 days. Measure: % of users who reach "linked a task to a goal," weekly active rate of the cohort at 30 days.

**Traps the participant can fall into:**
- Diagnosis "this is a discoverability problem" — because Marius says "I don't know what to do next." But he found the feature and opened the view. That's not discoverability, it's lack of value narrative in the view itself. Discoverability solves "the user doesn't know this exists" — here, everyone knows.
- Decision "just kill it" — because Karl says "I don't buy it." But the data shows that for the active group (Yvonne, Paul), this is a strong retention driver. Killing it kills value that actually exists.
- Decision "improve the event picker or add more views" — those are technical fixes, but the real problem is narrative: how to show the user in 30 seconds why Outcome Roadmap is worth filling in.

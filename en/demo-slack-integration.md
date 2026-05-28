# Demo case (Block 2) — Slack Integration

This is the feature the facilitator walks through live in Block 2 (not for the participants in Block 3). Same structure as cases A/B/C, so the demo runs on the same data the participants will see later.

## Feature

Slack Integration (see portfolio): keeps the team in the loop on what's happening with their goals — without opening Shipped. Slack picks up the news that a post-ship report is ready, that a metric dropped below a threshold, or that someone attached a new task under a goal. Each goal can be routed to its own Slack channel, so the right team sees the right alerts.

## Context

Slack Integration is one of the older Shipped features — it predates the MCP server. Assumption: if the user gets the news where they actually work (Slack), they don't have to remember to come into Shipped, so they come back more often and stay active.

The metric it was meant to move: **weekly active users** (the quarter's goal at Shipped is Retain: retention, measured as how many users are active in a given week). The team's hypothesis: notifications = re-engagement = higher weekly active rate.

## Funnel (last 90 days, ~5,170 paying users)

| Step | Paying users | % |
|---|---|---|
| Saw the Slack Integration option in settings | 4,550 | 88% |
| Connected a Slack channel | 4,033 | 78% |
| Receives notifications regularly (≥1/week) | 3,670 | 71% |
| Clicks a notification and enters Shipped | 1,450 | 28% |
| Comes back to Shipped via Slack regularly (≥3/month) | 620 | 12% |

The first three steps are high — setup and delivery work. Dramatic drop at "clicks and enters" (71% → 28%): notifications arrive, but they don't drive action.

## Cohort/Outcome

Retention by usage intensity, last 90 days. We split users into groups (cohorts) by how heavily they use the feature, and compare their retention (weekly active rate — % of users active in a given week):

| Segment | Paying users | Retention (weekly active) |
|---|---|---|
| Whole active user base | — | 50% |
| Non-user (hasn't set up Slack Integration) | 1,137 (22%) | 50% |
| Casual user (set up, reads passively, doesn't click) | 3,413 (66%) | 50% |
| Regular user (actively clicks and comes back via Slack) | 620 (12%) | **52%** |

**Here's the punchline:** even Regular users (who actively click) retain at **52% vs. 50% for the whole active base = +2pp**. Signal close to zero. Casual users (66% of paying users, just read) sit exactly at the base. Notifications don't move retention — because they're passive. Getting info ≠ coming back and doing something.

## User quotes

> **Bart, PM, Hookline (Pro plan, 7 months in product):**
> "Cool that I can see on Slack that a report is ready. But then I still have to go into Shipped to do anything with it. It's just a signal, not an action."

> **Eva, Engineering Lead, Trailmark (Enterprise plan, 10 months):**
> "In Linear I close an issue right from the Slack thread. In Shipped I get 'report ready' and that's it. I have to click, go in, hunt for that report in the UI. What's the point of the notification if the actual work is somewhere else?"

> **Mike, Head of Product, Quanta (Pro plan, 5 months):**
> "I've got a #shipped-alerts channel, but honestly I muted it. Too many notifications, too few of them actually require me to do something. Noise."

> **Alex, PM, Brightloop (Pro plan, 9 months):**
> "I'd want to click 'ok, I'll take it' or assign someone right from Slack. Right now it's a read-only channel — I see, but I can't act."

> **Greg, Founder, Stacklane (Enterprise plan, 3 months):**
> "Alerts about metric drops are useful — I know right away that something's happening. But that's where it ends. The rest is still manual work in Shipped."

## What we just saw (flow)

1. **Discoverability (adoption)** — NOT the problem. 88% know it, 78% use it, 71% receive notifications regularly. Adoption is high.
2. **Role** — push users back into the product, outcome = retention. Since 78% use it and it's supposed to drive retention — worth checking whether it actually does.
3. **Value** — THIS is the problem. +2pp even for the active group. Push-only (notifications go one way — you get info, but you can't act on it), passive. Linear shows that two-way (you can act straight from Slack, e.g. accept a task) works — that's the ceiling for our implementation, not for the feature itself.
4. **Decision** — fix (deepen to actionable), not kill.
5. **Hypothesis** — actionable Slack: accept/decline a task, report inline in the thread, ask about an outcome without leaving Slack. Aggressive test (a deliberately bold experiment that quickly reveals the ceiling): two-way for a subset of teams, measure whether Regular user retention climbs above +2pp.

---

## Extra data slices (on demand)

### Segmentation by plan (adoption %)
| Plan | Adoption % |
|---|---|
| Pro | 76% |
| Enterprise | 84% |
| Free | 71% |

### Segmentation by team size (adoption %)
| Team size | Adoption % |
|---|---|
| 1–5 | 72% |
| 6–20 | 80% |
| 20+ | 85% |

### Segmentation by role (adoption %)
| Role | Adoption % |
|---|---|
| Product Manager | 80% |
| Engineer | 75% |
| Founder / Head of Product | 82% |
| Designer | 60% |
| Other | 70% |

High across the board — confirms that adoption/discoverability is NOT the problem. The problem sits in value.

### ARR attribution
**~80% of ARR** sits in teams that use Slack Integration. But it's a weak differentiator — almost everyone uses it, so the correlation with account value is illusory.

### NPS detractor commentary (3 quotes — users who use it but don't see the value)
> **NPS 6 (Passive):** "I use it because it set itself up during onboarding. But if it disappeared, I probably wouldn't notice."

> **NPS 5 (Detractor):** "Too much noise, not enough action. I muted the channel."

> **NPS 6 (Passive):** "It's nice-to-have, not must-have. Linear does this in a way that actually speeds up the work. Here it's a bulletin board."

### Top 3 support tickets (90 days)
| Issue | Tickets |
|---|---|
| How do I mute / limit the number of notifications | 41 |
| Can I act (accept a task) from Slack? (answer: no) | 23 |
| Notifications going to the wrong channel | 14 |

### Time-to-first-use
Median **2 days** — set up during onboarding, almost immediately. Adoption is fast and easy; the problem doesn't live here.

# Claude prompts (Block 2 and Block 3)

Ready-to-use prompts to run live. They work for any Shipped feature — paste context from `portfolio.md` / `data-dashboard.md` / the case file and run. Each one has a backup: if the network drops, the answers are already pre-generated in the deep-dives (quotes, hypotheses).

---

## Prompt 1 — Voice of customer

Used in Block 2 (Slack Integration) and Block 3 (cases A/B/C), at the moment "we know where the problem is, we need qualitative data."

```
You are a product-research analyst at "Shipped" — a product- and project-management
SaaS (like Linear or Jira) that, after every feature ships, checks whether it
actually moved the metric it was meant to move.

Here's the feature and its adoption data:

[PASTE: feature name + description from portfolio]
[PASTE: dashboard data — adoption funnel (heard of → tried → uses regularly) + Regular-user retention vs. base 50%]
[PASTE: if available — funnel + cohort]

Generate 5 realistic user quotes about this feature. Requirements:
- Mix of segments (different plans: Pro/Enterprise/Free; different roles: PM,
  Engineer, Founder; different tenures).
- Mix of sentiment: 1–2 enthusiasts, 2–3 critics/indifferent, 1 who doesn't even
  know the feature exists (if it fits the data).
- Every quote has to reveal SOMETHING diagnostic: whether the problem is
  discoverability (doesn't find / doesn't understand) or value (uses it, but it
  isn't delivering value).
- Write in natural, spoken language — like a real user, not marketing copy.
- Format: first name, role, company (fictional), plan, tenure — then the quote.

After the quotes: 2 sentences on the picture of the problem that emerges from them.
```

**Backup (if the network drops):** quotes are already in `demo-slack-integration.md` (Block 2) and in `case-a/b/c` (Block 3).

---

## Prompt 2 — Improvement hypotheses

Used in Block 2 (step 5, when the room runs out of ideas) and Block 3 (when pairs are building hypotheses). The AI fills in / challenges what humans came up with.

```
You are a senior growth PM at "Shipped" (a product- and project-management SaaS
like Linear/Jira that checks whether shipped features actually move metrics).

Diagnosis of the feature:
[PASTE: feature name + description]
[PASTE: data — funnel, cohort, key quotes]
[PASTE: the diagnosis arrived at — discoverability vs. value, and why]

Generate 3 improvement hypotheses. Each hypothesis MUST include:
- **Move**: what specifically we do (one sentence, precise enough to ship in 1–2 weeks).
- **Data-backed perspective**: which specific data from the diagnosis justifies this move.
- **Strategic perspective**: why now (connection to the quarter's goal Retain /
  weekly active users, or to positioning vs. competition).
- **Aggressive test**: the strongest, most extreme version of this move you can run
  to quickly confirm the ceiling (Airbnb-popup style).

Rank from most to least promising. Be specific, no generic "improve UX" or
"better communication."
```

**Backup:** hypotheses are in the "Background / why" section of every case (A/B/C) and in `demo-slack-integration.md`.

---

## How it plays in the room

- **Block 2:** facilitator runs Prompt 1 live on Slack Integration ("watch me pull voice-of-customer in 30 seconds"). Then Prompt 2, compares with what the room came up with.
- **Block 3:** pairs can use both prompts on their case — but only AFTER they've put a diagnosis and first hypotheses on the table themselves. The AI fills in, it doesn't replace thinking. That's the lesson: AI is raw material, the craft (judging whether a hypothesis holds against data and strategy) is human.

---

## Live prompts — Block 2 sequence

Run one after the other in a Claude session opened in this repo (Claude has context from README + files). Each one triggers a specific moment in the lesson.

### 1. Company intro (Block 2 start)

```
Describe what Shipped does and explain each of its features so that someone who
has never seen the product can understand. Describe each feature in full
sentences, in plain language — no jargon, no one-word shortcuts. Don't evaluate
features (what works, what doesn't) — just explain what they do.
```

**Reads:** `company.md` (positioning) + `portfolio.md` (9 features).
**Triggers:** a Shipped description anyone in the room can follow + full (not shorthand) feature descriptions.
**Why "full sentences, no shortcuts":** without that, Claude defaults to a table of one-line slogans only readable by someone who already knows the product.
**Why "don't evaluate":** so it doesn't give away which feature is weak (e.g. Slack) — that's supposed to surface in the diagnosis, not in the company intro.

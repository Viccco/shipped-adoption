# Shipped — high-level data dashboard

One-page view of every Shipped feature, with the company baseline. Starting point for the participant: scan, find what looks like a signal, ask the facilitator for a deep-dive.

## Baseline (paying users)

| Metric | Value |
|---|---|
| Paying users (paid licenses) | 5,170 |
| Weekly active rate (UI-based) | 50% |
| Net retention | 62% |
| Activation rate (sign-up → first 14-day report opened) | 50% |
| NPS | 32 |
| Churn rate (rolling 90 days) | 4.2% |
| ARR | $1.8M |

## Per feature — high-level scan

Shipped's goal for this quarter: **Retain**, i.e. retention measured as **weekly active users** (how many users were active in a given week). Two things per feature: the **adoption funnel** (where users drop off) and the **value signal** (whether Regular users retain better than the whole active base at 50%).

| Feature | Funnel: heard of → tried → uses regularly | Regular user retention vs. base (50%) | Note |
|---|---|---|---|
| Goals & Outcomes | 95% → 88% → 71% | 67% (**+17pp**) | Core. Heart of onboarding. |
| Post-Ship Impact Detector | 92% → 81% → 65% | 70% (**+20pp**) | Core. Heart of the product. |
| Outcome Roadmap | 60% → 18% → 5% | 70% (**+20pp**) | Strong signal, but only 5% reach regular use — check why most drop off. |
| Task-to-Event Linking | 35% → 23% → 8% | 68% (**+18pp**) | Strong value signal, narrow reach. Classic low-hanging fruit. |
| AI Daily Brief | 18% → 9% → 3% | 75% (**+25pp**) | Strongest signal in the portfolio. Almost nobody knows it exists. |
| MCP Server | 62% → 6% → 2% | 31% (**−19pp**, UI) | Negative — but Regular users live in Claude, not the UI. The classic metric doesn't fit here. |
| Analytics Integrations | 85% → 78% → 62% | 58% (+8pp) | Foundation. Necessary, weak value signal. |
| Data Warehouse Integration | 22% → 18% → 12% | 63% (+13pp) | New segment (Enterprise). Low penetration, strategic for the pipeline. |
| Slack Integration | 88% → 78% → 71% | 52% (+2pp) | Everybody uses it, signal is almost zero. Worth keeping? |

## How to read the table

**User segments** (one naming convention across the whole repo) — we split users per feature by intensity of use:
- **Non-user** — has never used this feature
- **Casual user** — used it, but not regularly
- **Regular user** — uses it regularly (the threshold depends on the feature; spelled out in each case deep-dive)

**Adoption funnel** (heard of → tried → uses regularly) — where users drop off:
- **heard of** — paying users who know the feature exists
- **tried** — ever used it ≥1 time (Casual + Regular)
- **uses regularly** — Regular users (consistent usage)

A big drop "heard of → tried" = entry problem (discoverability). A big drop "tried → uses regularly" = touched once, didn't come back (signal that something isn't sticky).

**Regular user retention vs. base** — value signal:
- We take Regular users (who use the feature regularly) and check their retention (weekly active) against the **whole active user base (50%)**.
- A positive delta = signal that regular use correlates with better retention. **This is correlation, not proof** (Regular users may have been different to begin with). Proof would require an aggressive test — a deliberately bold experiment (e.g. forcing the change on a subset of users) that quickly tells you whether the effect is real.
- Slack +2pp = almost zero signal. AI Daily Brief +25pp = strong signal, but in a narrow group. MCP −19pp = paradox (measured in the UI, while these users live in Claude).

## What the facilitator has in their back pocket (data slices)

A participant can ask anything. For A/B/C, the facilitator has pre-prepared answers. For the rest, they improvise or punt.

### Pre-prepared for Case A/B/C

- **Pull retention data** → cohort retention by usage frequency (3 groups)
- **Pull adoption funnel** → step-by-step drop-off
- **Pull qualitative feedback** → 5 user quotes (mix of segments)
- **Segmentation by plan** → Free / Pro / Enterprise breakdown
- **Segmentation by team size** → 1–5 / 6–20 / 20+
- **Segmentation by role** → PM / Engineer / Designer / Founder / Other
- **ARR attribution** → how much ARR sits in teams that use the feature
- **NPS detractor commentary** → 3 quotes from users who do NOT use / reject the feature
- **Top 3 support tickets** → most recurring problems
- **Time-to-first-use** → median days from exposure to first use

### Improvise / punt (outside A/B/C)

- "What does sales say in post-demo feedback?" → improvise
- "What do G2 / Capterra reviews say?" → improvise or punt
- "Mobile vs. desktop split" → improvise
- "Day-of-week / time-of-day usage" → improvise
- "Cross-feature cannibalization" → improvise
- "Does a competitor have this?" → punt (point at company.md, Competition section)
- "What's the cost-to-serve?" → punt (operational, not product)
- "What does our CS team say?" → improvise
- "Reddit / X community feedback?" → improvise

## How the participant uses this

1. **Look at the table.** 2 minutes, data only.
2. **Pick a feature to diagnose.** What jumps out? Strong value signal + low reach = worth investigating. A negative signal = even more interesting.
3. **Ask the facilitator:** "Pull X data for feature Y."
4. **Diagnose.** With the data in hand, what problems do you see? Discoverability? Value? Something else?
5. **Build a hypothesis.** What would you do about it in the next 4 weeks?

# Shipped — adoption and retention data (detailed)

Two datasets for charts: adoption rate over time (weekly trend) and retention by segment (for every feature). Consistent with `data-dashboard.md`.

## 1. Adoption rate over time (WAU % per feature)

WAU % = the share of MAU (monthly active users — users active in a given month) who were active in a given feature in a given week (WAU = weekly active users, active in a given week). Last 5 weeks (recent snapshot). For a PostHog-style "Adoption rates" line chart.

| Feature | Apr 20 | Apr 27 | May 4 | May 11 | May 18 |
| --- | --- | --- | --- | --- | --- |
| Goals & Outcomes | 61 | 62 | 63 | 63 | 64 |
| Post-Ship Impact Detector | 52 | 53 | 54 | 54 | 55 |
| Slack Integration | 51 | 51 | 50 | 50 | 50 |
| Analytics Integrations | 46 | 46 | 47 | 47 | 47 |
| Outcome Roadmap | 13 | 14 | 14 | 15 | 15 |
| Task-to-Event Linking | 11 | 11 | 12 | 12 | 12 |
| Data Warehouse Integration | 8 | 9 | 10 | 11 | 11 |
| AI Daily Brief | 5 | 5 | 6 | 6 | 6 |
| MCP Server (UI) | 2 | 3 | 3 | 4 | 4 |

**What you see:** core features (Goals, Post-Ship) are mature and flat at a high level. The long tail (Task-to-Event, AI Daily Brief, Outcome Roadmap) **plateaus low despite the potential** — that's the visual proof of the workshop's thesis: we ship, adoption doesn't keep up. Two newer features (Data Warehouse, MCP) are climbing off a low base. Slack is flat / slightly drifting down.

## 2. Retention by segment (weekly active rate)

For each feature: weekly active rate (% of users active in a given week, measured across all of Shipped) for three segments — Non-user (doesn't use), Casual user (uses moderately), Regular user (uses regularly). Baseline = 50%. For a retention-by-segment chart (bars or curves).

Reference point: **the whole active user base = 50%**. Value signal = Regular user retention − 50%.

| Feature | Non-user | Casual user | Regular user | Change (Regular vs. base 50%) |
| --- | --- | --- | --- | --- |
| Goals & Outcomes | 50 | 58 | 67 | +17 |
| Post-Ship Impact Detector | 49 | 60 | 70 | +20 |
| Outcome Roadmap | 45 | 52 | 70 | +20 |
| Task-to-Event Linking | 47 | 56 | 68 | +18 |
| AI Daily Brief | 49 | 62 | 75 | +25 |
| Analytics Integrations | 48 | 53 | 58 | +8 |
| Data Warehouse Integration | 49 | 55 | 63 | +13 |
| Slack Integration | 50 | 50 | 52 | +2 |
| MCP Server (UI-based) | 50 | 47 | 31 | −19 |

**Reading it:** strong signal (AI Daily Brief +25, Outcome Roadmap +20) = Regular users stick around much more than the base, but in a narrow group. Flat (Slack +2) = the feature doesn't drive retention. Negative (MCP −19) = paradox: Regular MCP users live in Claude, not in the UI — the drop in the UI is evidence that we're measuring in the wrong place. **All of this is signal (correlation), not proof of impact** — Regular users may have been different to begin with.

## Notes for chart generation

- **Adoption-over-time** → line chart, 9 lines, X = weeks, Y = WAU %. Highlight the long tail (stagnation).
- **Retention-by-segment** → for a chosen feature, a 3-bar chart, or the whole table as small multiples. Baseline at 50%.
- Numbers are intentionally clean (they don't reconcile down to 0.1pp) — this is workshop material, not an audit.

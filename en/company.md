# Shipped — company context

## Positioning

Shipped is where you manage product work. Tasks, projects, releases. Like Linear or Jira. What's different: every task has to be connected to a real metric you want to move. That metric comes from your analytics tool (PostHog, Mixpanel, Amplitude, your warehouse). After you ship the task, Shipped pulls the data and tells you if the metric actually moved. No analyst, no SQL, no hand-built dashboards.

This changes how you plan. Instead of organizing work around features, you organize it around the goals you're trying to move.

Integrations: PostHog, Mixpanel, Amplitude, Heap, Segment, and data warehouses (Snowflake, BigQuery, Redshift, Databricks).

## How it works

- When you spec a feature, you pick one metric it's supposed to move (e.g. "trial-to-paid conversion", "weekly active teams"). One field, not a whole questionnaire.
- After release, AI picks who to track and the control group on its own; after 14 days you get a report.
- Everything is also exposed through the **MCP server** (Model Context Protocol — the standard AI assistants like Claude or Cursor use to connect to tools and read data from them). Claude, Cursor, and other agents can ask Shipped about goal status and which features are working, without ever opening the Shipped UI.

## Segment

**Primary:** product teams at Series A–C SaaS companies (50–500 people) that already have an analytics tool deployed (PostHog, Mixpanel, Amplitude) and ship features weekly, but lose track of what actually worked.

**Secondary:** product-led startups that grew up on Linear or Jira, want to start measuring real impact, but don't have a data team.

**Aspirational:** enterprise companies with their own data warehouse — a segment we're opening in Q2 2026 through Snowflake/BigQuery/Databricks integrations.

## Scale (as of Q1 2026)

**The quarter's goal** is the one metric the team commits to moving. Here it's **Retain**: keeping users active in the product. Shipped measures it as **weekly active users** (unique users active in a given week), because retention is fundamentally a user-level phenomenon. Team-level metrics (weekly active teams, paying teams) are aggregations of user-level retention, tracked for board reporting and sales motion. All adoption analyses in this workshop are user-level.

| Metric | Value |
|---|---|
| Registered users | 35,000 |
| Monthly active users (MAU) | 8,200 |
| Weekly active users (WAU) | ~4,200 |
| Paying users (paid licenses across 380 paying teams) | ~5,170 |
| Weekly active rate for paying users | 50% |
| ARR | $1.8M |
| Activation rate (sign-up → first 14-day report opened) | 50% |
| Net retention | 62% |
| Stage | Series A ($6M raised, 2024) |
| Growth model | PLG + sales-assist for enterprise |

## Pricing

| Plan | Price | What you get |
|---|---|---|
| Free | $0 | 3 users, 5 features tracked, 1 analytics integration |
| Pro | $15/user/mo | Unlimited features, all integrations, MCP server |
| Enterprise | Custom | Custom data warehouse, SSO, audit logs, dedicated CSM |

## Strategy (Q1 2026)

**Priority 1: Land in the Series B SaaS segment.** These teams already run PostHog or Mixpanel, ship weekly, but have no idea what's working. Ready for the "stop guessing, start measuring" conversation.

**Priority 2: Ship data-warehouse integrations.** Snowflake and BigQuery by end of Q1, Redshift and Databricks in Q2. This opens conversations with larger companies that keep their data in-house.

**Priority 3: MCP server on every plan, including Free.** We're betting that Claude and Cursor will be the main way PMs use tools in 2026. We want teams using Shipped through AI agents before competitors notice that the agent surface is a distribution channel in its own right.

## Your role (Senior PM)

You're a Senior PM at Shipped, responsible for the core product experience — everything between "user ships a feature" and "user reads a report." Your Q1 KRs:

- Increase activation rate (50% → 65%)
- Increase weekly active users (~4,200 → 7,000)
- Ship MCP server v1 (gate for Priority 3)

## Competition

**Direct:** none. The category — "automated validation of what worked after release" — is young. Nobody else does it this way.

**Adjacent:**
- **Eppo, Statsig, Optimizely** — A/B-test infrastructure, but they require the team to design experiments and have data people. Shipped automatically compares the group of users who engaged with a feature against the group that didn't — no experiment planning needed.
- **Built-in reports in Mixpanel and Amplitude** — but someone has to build the dashboard. Shipped generates it on its own, from what the team already entered into the product as "planned work."

**Why you can't just build it yourself:**
- PostHog + Linear + Notion dashboards = what most teams do today. Half a day of work per feature, and most teams skip it.
- Shipped collapses that into "ship a feature — get a report in your inbox in 14 days."

## Tech stack

- Frontend: React + TypeScript
- Backend: Node.js + Postgres
- Analytics integrations: PostHog API, Mixpanel API, Amplitude API, Heap API
- Warehouse integrations: Snowflake, BigQuery, Redshift, Databricks (via dbt-style connectors)
- AI: Anthropic Claude (for auto-cohort selection, anomaly detection, impact summarization)
- MCP server: Python, FastAPI

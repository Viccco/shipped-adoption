# Case C — MCP Server

## Feature

MCP Server (see portfolio): Shipped exposes an interface (MCP — Model Context Protocol, the standard AI assistants use to connect to tools) through which Claude, Cursor, and other AI assistants can read and write Shipped data without ever opening the Shipped UI.

## Context

The Shipped team shipped the MCP Server 2 months ago, in Q1 2026. The assumption: PMs and engineers increasingly live inside Claude/Cursor (instead of opening dozens of tools), so Shipped has to be available where they work. The MCP Server is **free on every plan** — a deliberate strategic investment by the Shipped team: a bet that Claude and Cursor will be the main channel through which PMs use tools in 2026, so Shipped has to be there before competitors notice that the agent surface is a new distribution channel.

The metric it was meant to move: **weekly active users** (Shipped's quarter goal is Retain: retention measured as how many users are active in a given week). But here's the paradox: if a user starts using Shipped through Claude, they *stop* opening the Shipped UI. From the classic UI metric's perspective this looks like a drop in activity, even though actual product usage is going up. MCP's success can look in the data like failure, which is the first signal that we need a new metric.

## Funnel (last 60 days, since the feature is young, ~5,170 paying users)

| Step | What the user did | Paying users | % |
|---|---|---|---|
| Heard about MCP Server | Saw the launch email, in-product changelog, blog post | 3,200 | 62% |
| Opened the MCP Server docs | From those who heard — clicked "Learn more" and landed on docs.shipped.com/mcp | 1,500 | 29% |
| Configured MCP in Claude/Cursor | Pasted JSON config, hooked up API key — MCP client connected to the Shipped server | 380 | 7% |
| Executed at least 1 call | Actually asked a question / ran an operation through Claude | 290 | 6% |
| Uses it regularly (≥3 calls/week) | Sustained usage across the last 4 weeks | 95 | 2% |

**Key drop-offs:**

- **From 1,500 to 380 (−75%):** most who opened the docs didn't configure. Mostly non-engineers who don't know how to paste JSON into Claude/Cursor.
- **From 380 to 290 (−24%):** 90 paying users connected MCP but never asked a real question. A test/health-check and abandonment, or IT configured it and the actual user never tried.
- **From 290 to 95 (−67%):** only one third of people who ever executed a call do it regularly. The rest tried once or twice and stopped.

## Cohort/Outcome

Retention (weekly active rate, measured in the UI) by usage intensity:

| Segment | Paying users | Retention (UI weekly active) |
|---|---|---|
| Whole active user base | — | 50% |
| Non-user (doesn't use MCP Server) | 4,880 (94%) | 50% |
| Casual user (configured, doesn't use heavily) | 195 (4%) | 47% |
| Regular user (uses MCP heavily) | 95 (2%) | **31%** |

**Here's the paradox:** Regular MCP users retain at **31% vs. 50% for the whole active base = −19pp** — they look like they're abandoning the product. But **they consume Shipped 7 times a week, just through Claude, not through the UI.** A UI-measured metric doesn't catch that usage, so MCP's success in this group is invisible. This isn't a signal of weak value — it's a signal that **we're measuring in the wrong place.** MCP needs a metric that counts agent-driven calls, not UI activity.

## User quotes

> **Martin, Staff Engineer, BuildBox (Pro plan, 9 months):**
> "I've got Claude Code configured with the Shipped MCP. I ask 'what moved on our onboarding outcome this week?' and I get an answer without opening any dashboard. Brilliant. I used to open the Shipped UI once a month, now maybe once every six months."

> **Alexandra, Head of Product, Crisplane (Enterprise plan, 7 months):**
> "I heard about MCP in an email from you. I read the docs, but I have no idea how to set it up in Cursor. You paste some JSON somewhere? Then what? There's no simple how-to for non-engineers."

> **Damian, Junior PM, GridPay (Enterprise plan, 4 months):**
> "Never heard of MCP. What is it? I don't use Claude at work, I use ChatGPT in a browser. Is this for me?"

> **Thomas, Lead Engineer, Loopfeed (Pro plan, 6 months):**
> "Configured MCP, tried to hook it up to an agent that manages my tasks. It works, but endpoints to edit goals are missing — read-only. Waiting for the update before I plug in deeper."

> **Iza, Product Operations, NoteFlare (Enterprise plan, 3 months):**
> "We built an automated report to Slack through MCP — every morning our internal bot asks Shipped about outcome status and pastes the result into a channel. I used to do that by hand. Works great."

## Extra data slices (on participant request)

### Segmentation by plan

| Plan | % of paying users on this plan who executed ≥1 call via MCP |
|---|---|
| Pro | 4% |
| Enterprise | 12% |
| Free | 1% (small sample) |

### Segmentation by team size

| Team size | Adoption % |
|---|---|
| 1–5 users | 3% |
| 6–20 users | 7% |
| 20+ users | 15% |

Larger teams have more engineers who can configure MCP on their own.

### Segmentation by user role

| Role | Adoption % |
|---|---|
| Engineer | 28% |
| Product Manager | 3% |
| Designer | 0% |
| Founder / Head of Product | 1% |
| Other | 1% |

Heavy engineer tilt — today this is de facto a "for engineers" feature.

### ARR attribution

**41% of ARR** sits in teams where at least one user has executed ≥1 call via MCP. Mixed picture — there are specific high-value Enterprise accounts, but not as dominant as for Outcome Roadmap.

### NPS detractor commentary (3 quotes from paying users who do NOT use it)

> **NPS 6 (Passive):** "I don't use Claude at work. No idea what MCP is."

> **NPS 5 (Detractor):** "I tried setting it up in Cursor, but I don't have the technical chops. Our dev team would have to configure it, and they have other priorities."

> **NPS 7 (Passive):** "MCP sounds interesting, but how do I trust that Claude only sees our data, not someone else's? There's no clear security policy anywhere."

### Top 3 support tickets (last 60 days)

| Issue | Tickets |
|---|---|
| How do I configure MCP in Claude Desktop / Cursor (Alexandra-pattern) | 38 |
| Missing endpoints to edit goals via MCP (Thomas-pattern) | 14 |
| Authentication problem on first connection | 8 |

### Time-to-first-use

Median **4 days** for engineers who configure on their own. For other roles the sample is too small (n < 10) to compute a median.

## What would you do with this?

Question for the participant — no hints.

---

## Background / why (for the facilitator)

Strongest hypotheses for why this feature is the way it is — and what to do:

1. **Classic adoption metrics don't fit MCP Server.** Weekly active rate (UI) for regular MCP users = 31% (below the 50% baseline). Looks like a feature that "breaks" retention, but in reality these users consume Shipped *more* intensively — about 7 calls per week through MCP. The UI becomes optional for them. We need a new metric: "engaged user" = active in the UI OR in MCP.

2. **Coverage 2% (uses regularly) is Low in the classic sense, but this is a 2-month-old feature with zero in-product surface.** The classic "Niche/reactive" category for strategic features is the wrong frame — this is an *early-stage distribution* on a new channel, not a feature to leave alone.

3. **Discoverability splits into two segments:**
   - **Engineers (Martin, Thomas):** they know about MCP, configure on their own, what they're missing is endpoints (API depth). This is a *roadmap problem*, not an adoption problem.
   - **Non-engineers (Alexandra, Damian):** they don't know what MCP is, or can't set it up. Classic discoverability + value-communication problem on a surface most PMs never visit (Claude/Cursor docs).

4. **Unexpected use case (Iza):** automated reports to Slack through MCP. Distribution through the agent surface in a way the team didn't predict. Signal that MCP is a tool for *building workflows around Shipped*, not just "chatting with data."

5. **Defensibility:** every quarter MCP is not available at production quality increases the risk that a competitor (Eppo/Statsig or a new entrant) does it first. The price of MCP being free + a 2-month-old feature = a strategic window where we have to grow adoption quickly, before competitors start copying.

**Diagnosis the participant should reach (three things at once):**

- **Metric definition problem** — before distribution, we have to define what "a user uses MCP" means. Unique paying users with MCP calls/week? Total calls? Something else? Without a new metric, the classic matrix doesn't make sense.
- **Channel problem** — the MCP target audience (engineers, advanced PMs) doesn't live in the Shipped UI. They live in Claude, Cursor, docs.anthropic.com. Distribution has to go where they are.
- **Communication-value problem** for non-engineers — those who don't know what MCP is (Damian, Alexandra) need a video "PM opens Claude, asks about an outcome, gets an answer." Without that, JSON setup stays a 5%-population thing.

**Strongest hypotheses to test:**

1. **Partnership distribution:** Shipped MCP in default templates for Claude Code and Cursor. Instead of building more in-product CTAs, distribute through the surface where the target audience already is.
2. **No-code setup flow:** in the Shipped UI, a one-click "Connect to Claude" generates the JSON, copies it to the clipboard, opens Claude in a new tab with paste instructions.
3. **Video "PM uses Claude with Shipped":** a 60-second demo on the MCP docs home page. For Damian, who "doesn't know what MCP is," an image replaces 5 paragraphs of text.
4. **API depth public roadmap:** a public roadmap of MCP endpoints (read/write goals, edit tasks, automate reports) — so engineers like Thomas don't wait indefinitely.

**Traps the participant can fall into:**

- **"Coverage 2% = Niche, leave it alone."** No. This is a 2-month-old feature that's strategically critical on a new distribution channel. The classic "Niche/reactive" category doesn't fit.
- **"Weekly active rate dropped, kill."** No. The drop in UI activity for regular MCP users is *evidence of success*, not failure — they use the product more intensively, just differently. The classic metric doesn't catch it.
- **"More in-product promo for MCP."** No. The MCP target audience doesn't live in the Shipped UI. A push in the UI touches the 6% of MAU who saw the changelog, but real distribution goes through Claude/Cursor.
- **"We need a full API before doing anything."** No. A full API is a roadmap problem for engineers. For most users (Alexandra, Damian), *anything* on the MCP UX is missing — API depth doesn't help while setup is the barrier.

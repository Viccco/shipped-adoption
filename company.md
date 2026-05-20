# Shipped — kontekst firmy

## Pozycjonowanie

**Shipped to narzędzie do zarządzania produktem i projektami — jak Linear czy Jira — z jedną różnicą: nie kończy się na „Done".** Po każdym wypuszczeniu funkcjonalności automatycznie sprawdza, czy faktycznie zmieniła metrykę, którą miała zmienić (retencję, konwersję, aktywność), i raportuje to bez analityka, bez SQL-a, bez ręcznego budowania dashboardów.

Integruje się z PostHog, Mixpanel, Amplitude, Heap, Segment oraz hurtowniami danych (Snowflake, BigQuery, Redshift, Databricks).

## Mechanika

- Kiedy spec'ujesz funkcjonalność, wybierasz jedną metryę, którą ma ruszyć (np. "konwersja z trial do paid", "weekly active teams"). Jedno pole, nie cała ankieta.
- Po wypuszczeniu AI samo dobiera kogo śledzić i grupę kontrolną, po 14 dniach generuje raport.
- Wszystko dostępne przez MCP server — Claude, Cursor i agenty pytają o status celów i które funkcjonalności działają, bez otwierania UI Shipped.

## Segment

**Główny:** zespoły product w SaaS-ach na etapie Series A–C (50–500 ludzi), które mają już wdrożone narzędzie analityczne (PostHog, Mixpanel, Amplitude) i wypuszczają funkcjonalności co tydzień, ale tracą wiedzę o tym, co z tego co dowieźli rzeczywiście zadziałało.

**Drugi:** startupy product-led, które wyrosły z Lineara albo Jiry, chcą zacząć mierzyć faktyczny wpływ pracy, ale nie mają zespołu data.

**Docelowy:** firmy enterprise z własną hurtownią danych — segment otwierany w Q2 2026 przez integrację z Snowflake/BigQuery/Databricks.

## Skala (stan na Q1 2026)

Shipped mierzy cycle outcome (Retain) na poziomie weekly active users — bo retention to fenomen indywidualnych userów. Team-level metryki (weekly active teams, paying teams) są agregacjami user-level retention, śledzonymi dla raportowania zarządowi i sales motion. Wszystkie analizy adopcji w warsztacie są user-level.

| Metryka | Wartość |
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
| Growth model | PLG + sales-assist na enterprise |

## Pricing

| Plan | Cena | Co dostajesz |
|---|---|---|
| Free | $0 | 3 users, 5 features tracked, integracja z 1 analytics tool |
| Pro | $15/user/mo | Unlimited features, wszystkie integracje, MCP server |
| Enterprise | Custom | Custom data warehouse, SSO, audit logs, dedicated CSM |

## Strategia (Q1 2026)

**Priorytet 1: Wbicie się w segment SaaS-ów Series B.** Te zespoły mają już PostHoga albo Mixpanela, wypuszczają co tydzień, ale nie wiedzą co z tego działa. Gotowi na rozmowę "przestań zgadywać, zacznij mierzyć."

**Priorytet 2: Wypuszczenie integracji z hurtowniami danych.** Snowflake i BigQuery do końca Q1, Redshift i Databricks w Q2. To otwiera rozmowę z większymi firmami, które trzymają dane u siebie.

**Priorytet 3: MCP server na każdym planie, też free.** Stawiamy na to, że Claude i Cursor będą głównym sposobem, w jaki PM-owie używają narzędzi w 2026. Chcemy, żeby zespoły zaczęły używać Shipped przez agentów AI, zanim konkurencja zauważy, że to jest osobny kanał dystrybucji.

## Twoja rola (Senior PM)

Jesteś Senior PM-em w Shipped, odpowiadasz za core product experience — wszystko między "user shippuje feature" a "user czyta raport." Twoje KR-y na Q1:

- Increase activation rate (50% → 65%)
- Increase weekly active users (~4,200 → 7,000)
- Ship MCP server v1 (gate dla priorytetu 3)

## Konkurencja

**Bezpośrednia:** brak. Kategoria "automatyczna walidacja co działa po wypuszczeniu" jest młoda. Nikt nie robi tego w ten sposób.

**Sąsiednia:**
- **Eppo, Statsig, Optimizely** — robią infrastrukturę do A/B testów, ale wymagają, żeby zespół eksperymenty projektował i miał ludzi od danych. Shipped automatycznie porównuje grupę użytkowników, którzy weszli w funkcjonalność, z grupą, która nie weszła — bez planowania eksperymentu.
- **Wbudowane raporty w Mixpanelu i Amplitude** — ale ktoś musi tam zbudować dashboard. Shipped generuje go sam, z tego co zespół już wpisał do produktu jako "zaplanowana praca."

**Dlaczego nie zbudujesz tego sam:**
- PostHog + Linear + dashboardy w Notion = co większość zespołów robi dzisiaj. Pół dnia pracy na każdy feature, większość zespołów tego nie robi.
- Shipped sprowadza to do "wypuszczasz funkcjonalność — po 14 dniach masz raport w skrzynce."

## Stack technologiczny

- Frontend: React + TypeScript
- Backend: Node.js + Postgres
- Analytics integrations: PostHog API, Mixpanel API, Amplitude API, Heap API
- Warehouse integrations: Snowflake, BigQuery, Redshift, Databricks (przez dbt-style connectors)
- AI: Anthropic Claude (dla auto-cohort selection, anomaly detection, impact summarization)
- MCP server: Python, FastAPI

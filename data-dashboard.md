# Shipped — high-level data dashboard

Widok one-page wszystkich funkcjonalności Shipped z baseline'em firmy. Punkt startowy dla uczestnika: spójrz, znajdź to co wygląda na sygnał, poproś prowadzącego o deep-dive.

## Baseline (paying users)

| Metryka | Wartość |
|---|---|
| Paying users (paid licenses) | 5,170 |
| Weekly active rate (UI-based) | 50% |
| Net retention | 62% |
| Activation rate (sign-up → first 14-day report opened) | 50% |
| NPS | 32 |
| Churn rate (rolling 90 dni) | 4.2% |
| ARR | $1.8M |

## Per feature — high-level scan

Cycle outcome = **Retain** (weekly active users). Wszystkie metryki względem paying users.

| Feature | Exposed % | Adoption % | Power users % | Power user WAR | Δ vs baseline | Notatka |
|---|---|---|---|---|---|---|
| Goals & Outcomes | 95% | 88% | 71% | 67% | **+17pp** | Core. Sercem onboardingu. |
| Post-Ship Impact Detector | 92% | 81% | 65% | 70% | **+20pp** | Core. Sercem produktu. |
| Outcome Roadmap | 60% | 18% | 5% | 70% | **+20pp** | Wysoki Power user WAR, ale tylko 5% paying users — sprawdź czemu większość nie dochodzi. |
| Task-to-Event Linking | 35% | 23% | 8% | 68% | **+18pp** | Wysoki impact dla powerów, niska distribution. Klasyczny low-hanging fruit. |
| AI Daily Brief | 18% | 9% | 3% | 75% | **+25pp** | Najwyższy impact w portfolio. Prawie nikt nie wie że istnieje. |
| MCP Server | 62% | 6% | 2% | 31% | **−19pp** | Negatywny Δ. Sprawdź czy klasyczna metryka tu pasuje. |
| Analytics Integrations | 85% | 78% | 62% | 58% | +8pp | Foundation. Niezbędne, ale impact skromny. |
| Data Warehouse Integration | 22% | 18% | 12% | 63% | +13pp | Nowy segment (Enterprise). Niska penetracja, strategiczne dla pipeline. |
| Slack Integration | 88% | 78% | 71% | 52% | +2pp | Wszyscy używają, prawie zero impactu. Czy to warte utrzymania? |

## Jak czytać tabelę

- **Exposed %** — paying users, którzy wiedzą, że feature istnieje (zobaczyli changelog / mail / docs).
- **Adoption %** — paying users, którzy użyli ≥1 raz.
- **Power users %** — paying users, którzy używają regularnie (definicja zależy od feature: dla Goals — używa weekly, dla Task-to-Event — linkuje większość tasków, dla MCP — ≥3 calls/tydzień).
- **Power user WAR** — Weekly active rate dla tej najwęższej grupy. *Klasyczna* metryka (UI-based). Dla MCP Server nie pasuje.
- **Δ vs baseline** — różnica vs 50% baseline (Power user WAR − 50%). Im wyższy, tym mocniejszy sygnał wartości feature dla użytkowników.

**Uwaga o liczeniu Δ:** dashboard liczy Δ vs baseline 50%. W deep-dive'ach case'ów (A/B/C, Slack) różnice są liczone vs grupa, która **nigdy nie używała** feature — więc liczby mogą się różnić o kilka pp (np. Task-to-Event: dashboard +18pp = 68−50, case +21pp = 68−47). To ta sama historia, inna baza odniesienia. Dashboard = "jak wypada vs typowy paying user"; case = "jak wypada vs ktoś, kto tego nie tknął".

## Co prowadzący ma w zanadrzu (data slices)

Uczestnik może rzucić dowolne pytanie. Prowadzący dla A/B/C ma pre-przygotowane odpowiedzi. Dla pozostałych improwizuje lub odsyła.

### Pre-przygotowane dla Case A/B/C

- **Pull retention data** → cohort retention by usage frequency (3 grupy)
- **Pull adoption funnel** → step-by-step drop-off
- **Pull qualitative feedback** → 5 cytatów userów (mix segmentów)
- **Segmentacja per plan** → Free / Pro / Enterprise breakdown
- **Segmentacja per team size** → 1–5 / 6–20 / 20+
- **Segmentacja per role** → PM / Engineer / Designer / Founder / Other
- **ARR attribution** → ile ARR jest w teamach które używają feature
- **NPS detractor commentary** → 3 cytaty z userów, którzy NIE używają / odrzucają
- **Top 3 support tickets** → najczęstsze powtarzające się problemy
- **Time-to-first-use** → mediana dni od exposure do pierwszego użycia

### Improvise / punt (poza A/B/C)

- "Co mówi sales w post-demo feedback?" → improwizuje
- "Co mówią G2 / Capterra reviews?" → improwizuje lub punt
- "Mobile vs desktop split" → improwizuje
- "Day-of-week / time-of-day usage" → improwizuje
- "Cross-feature cannibalization" → improwizuje
- "Czy konkurencja to ma?" → punt (Wiktor odsyła do company.md, sekcja Konkurencja)
- "Ile cost-to-serve generuje?" → punt (operacyjne, nie produktowe)
- "Co mówi nasz CS team?" → improwizuje
- "Reddit / X community feedback?" → improwizuje

## Mechanika dla uczestnika

1. **Spójrz na tabelę.** 2 minuty same dane.
2. **Wybierz feature do diagnozy.** Co cię uderza? Wysokie Δ + niska Coverage = warto sprawdzić. Negatywne Δ = jeszcze ciekawiej.
3. **Rzuć pytanie prowadzącemu:** "Pull X data for feature Y."
4. **Diagnozuj.** Z danymi w ręku, jakie problemy widzisz? Discoverability? Value? Coś jeszcze?
5. **Zbuduj hipotezę.** Co byś z tym zrobił w następnych 4 tygodniach?

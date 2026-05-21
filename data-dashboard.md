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

Cycle outcome = **Retain** — metryka, którą Shipped zobowiązał się ruszyć w tym kwartale: retencja, mierzona jako **weekly active users** (ilu userów jest aktywnych w danym tygodniu). Dwie rzeczy per funkcjonalność: **lejek adopcji** (gdzie userzy odpadają) i **sygnał wartości** (czy Regular userzy mają lepszą retencję niż cały aktywny base 50%).

| Feature | Lejek: zna → użył → intensywnie | Retencja Regular userów vs base (50%) | Notatka |
|---|---|---|---|
| Goals & Outcomes | 95% → 88% → 71% | 67% (**+17pp**) | Core. Sercem onboardingu. |
| Post-Ship Impact Detector | 92% → 81% → 65% | 70% (**+20pp**) | Core. Sercem produktu. |
| Outcome Roadmap | 60% → 18% → 5% | 70% (**+20pp**) | Mocny sygnał, ale tylko 5% dochodzi do intensywnego użycia — sprawdź, czemu większość odpada. |
| Task-to-Event Linking | 35% → 23% → 8% | 68% (**+18pp**) | Mocny sygnał wartości, niski zasięg. Klasyczny low-hanging fruit. |
| AI Daily Brief | 18% → 9% → 3% | 75% (**+25pp**) | Najmocniejszy sygnał w portfolio. Prawie nikt nie wie, że istnieje. |
| MCP Server | 62% → 6% → 2% | 31% (**−19pp**, UI) | Ujemnie — ale Regular userzy żyją w Claude, nie w UI. Klasyczna metryka tu nie pasuje. |
| Analytics Integrations | 85% → 78% → 62% | 58% (+8pp) | Foundation. Niezbędne, ale słaby sygnał wartości. |
| Data Warehouse Integration | 22% → 18% → 12% | 63% (+13pp) | Nowy segment (Enterprise). Niska penetracja, strategiczne dla pipeline. |
| Slack Integration | 88% → 78% → 71% | 52% (+2pp) | Wszyscy używają, sygnał prawie zerowy. Czy to warte utrzymania? |

## Jak czytać tabelę

**Segmenty userów** (jedno nazewnictwo w całym repo) — dzielimy userów per funkcjonalność wg intensywności użycia:
- **Non-user** — nigdy nie użył tej funkcjonalności
- **Casual user** — użył, ale nie regularnie
- **Regular user** — używa regularnie (próg zależy od funkcjonalności; w deep-dive'ie case'a jest podany wprost)

**Lejek adopcji** (zna → użył → intensywnie) — gdzie userzy odpadają:
- **zna** — paying users, którzy wiedzą, że funkcjonalność istnieje
- **użył** — kiedykolwiek użyli ≥1 raz (Casual + Regular)
- **intensywnie** — Regular userzy (używają regularnie)

Duży spadek "zna → użył" = problem z wejściem (discoverability). Duży spadek "użył → intensywnie" = tknęli raz i nie wrócili (sygnał, że coś nie trzyma).

**Retencja Regular userów vs base** — sygnał wartości:
- Bierzemy Regular userów (używają funkcjonalności regularnie) i sprawdzamy ich retencję (weekly active) vs **cały aktywny user base (50%)**.
- Dodatnia różnica = sygnał, że intensywne używanie wiąże się z lepszą retencją. **To korelacja, nie dowód** (Regular userzy mogli być inni od początku). Dowód dałby aggressive test — celowo odważny eksperyment (np. wymuszenie zmiany na części userów), który szybko pokazuje, czy efekt jest realny.
- Slack +2pp = sygnał prawie zerowy. AI Daily Brief +25pp = mocny sygnał, ale w wąskiej grupie. MCP −19pp = paradoks (mierzone w UI, a oni żyją w Claude).

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
2. **Wybierz feature do diagnozy.** Co cię uderza? Mocny sygnał wartości + niski zasięg w lejku = warto sprawdzić. Ujemny sygnał = jeszcze ciekawiej.
3. **Rzuć pytanie prowadzącemu:** "Pull X data for feature Y."
4. **Diagnozuj.** Z danymi w ręku, jakie problemy widzisz? Discoverability? Value? Coś jeszcze?
5. **Zbuduj hipotezę.** Co byś z tym zrobił w następnych 4 tygodniach?

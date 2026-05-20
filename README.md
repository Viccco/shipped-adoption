# Shipped — case study na warsztat "Feature Adoption"

To są materiały do **warsztatu o adopcji funkcjonalności** (Product Pro Summit). Plan całego warsztatu jest piętro wyżej: `../Adoption.md`. Ten folder zawiera fikcyjną firmę **Shipped**, na której uczestnicy ćwiczą flow diagnozy adopcji.

## Czym jest Shipped

Fikcyjne narzędzie PM — "post-deploy validation layer." Linear/Asana/Jira kończą się przy deployu; Shipped tam się zaczyna: po wypuszczeniu funkcjonalności mówi ci, czy faktycznie ruszyła outcome, który miała ruszyć. Integruje się z PostHog/Mixpanel/Amplitude i hurtowniami danych. Pełny kontekst: `company.md`.

**Skala (potrzebna do czytania danych):** ~5,170 paying users, baseline weekly active rate **50%**, cycle outcome = **Retain** (weekly active users).

## Flow, którego uczy warsztat

```
1. Czy mam problem?   — ile userów odkrywa i używa (adopcja)        [DISCOVERABILITY]
2. Rola               — czy w ogóle warto nad tym pracować? Jeśli nie → następny feature.
                        Plus: jaki outcome ta funkcjonalność ma ruszać.
3. Value              — czy ci, którzy używają, osiągają to co chcieliśmy?
4. Decyzja            — keep / kill / push w dystrybucję / fix doświadczenia
5. Hipoteza           — (jeśli push lub fix)
```

Dwie kategorie problemu: **Discoverability** (nie odkrywa / nie rozumie) i **Value** (używa, ale nie wnosi wartości).

## Pliki

| Plik | Co to | Gdzie używane |
|---|---|---|
| `company.md` | Kontekst firmy, skala, strategia, pricing, konkurencja | Block 2 (wprowadzenie) |
| `portfolio.md` | 9 funkcjonalności Shipped — czysty opis, co każda robi | Block 2 (overview) |
| `data-dashboard.md` | High-level metryki wszystkich 9 funkcjonalności + lista data slices dla prowadzącego | Block 2 i 3 (skan adopcji) |
| `demo-slack-integration.md` | **Demo case na Block 2** — Slack Integration, pełny deep-dive | Block 2 (Wiktor prowadzi na żywo) |
| `case-a-task-to-event-linking.md` | Case dla uczestników — Discoverability / push | Block 3 |
| `case-b-outcome-roadmap.md` | Case dla uczestników — Value / praca nad wartością | Block 3 |
| `case-c-mcp-server.md` | Case dla uczestników — channel / definicja metryki w erze AI | Block 3 |
| `prompts.md` | Gotowe prompty do Claude: feedback klientów + generowanie hipotez | Block 2 i 3 |

## Jak to gra w warsztacie

- **Block 2 (demo, ~30 min):** prowadzący pokazuje cały flow na żywo na **Slack Integration** (`demo-slack-integration.md`). Zaczyna od dashboardu (skan adopcji), schodzi przez flow do hipotezy. Slack Integration jest celowo poza case'ami Block 3, żeby nie spalić materiału.
- **Block 3 (praca, ~40 min):** 5 par, podział **2/2/1** na case'y A/B/C. Każdy case ma warstwę podstawową (kontekst, funnel, cohort, cytaty) + 7 slices "na żądanie" (per plan/team size/role, ARR, NPS detractor, support tickets, time-to-first-use). Para najpierw mówi, jakich danych chce, potem odsłania.

## Konwencja każdego case'a (A/B/C + demo)

1. Funkcjonalność (link do portfolio)
2. Kontekst (założenia + outcome)
3. Funnel (user-level, ~5,170 paying users)
4. Cohort/Outcome (3 grupy retention)
5. Cytaty userów
6. Dodatkowe data slices (7, na żądanie)
7. **Tło / why** (dla prowadzącego — diagnoza docelowa + pułapki + hipotezy)

## Czego jeszcze nie ma

- **Charty/wizualizacje** — dane są w markdown, brak wykresów (do zrobienia).
- **AI Daily Brief deep-dive** — case awaryjny dla Block 4 (osoby bez własnego feature), jeszcze nie zbudowany.

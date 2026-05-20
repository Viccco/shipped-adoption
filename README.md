# Shipped — case study na warsztat "Feature Adoption"

To są materiały do **warsztatu o adopcji funkcjonalności**. Ten folder zawiera fikcyjną firmę **Shipped**, na której uczestnicy ćwiczą flow diagnozy adopcji.

## Czym jest Shipped

Fikcyjne narzędzie do zarządzania produktem i projektami — jak Linear czy Jira — z jedną różnicą: nie kończy się na "Done." Po wypuszczeniu funkcjonalności sprawdza, czy faktycznie zmieniła metrykę, którą miała zmienić. Integruje się z PostHog/Mixpanel/Amplitude i hurtowniami danych. Pełny kontekst: `company.md`.

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


## Konwencja każdego case'a (A/B/C + demo) w block 3

1. Funkcjonalność (link do portfolio)
2. Kontekst (założenia + outcome)
3. Funnel (user-level, ~5,170 paying users)
4. Cohort/Outcome (3 grupy retention)
5. Cytaty userów
6. Dodatkowe data slices (7, na żądanie)
7. **Tło / why** (dla prowadzącego — diagnoza docelowa + pułapki + hipotezy)

# Shipped — feature adoption workshop / warsztat o adopcji funkcjonalności

> **EN:** Open this folder in Claude Code and type anything to begin — you'll be greeted automatically and asked to pick a language.
>
> **PL:** Otwórz ten folder w Claude Code i napisz cokolwiek, żeby zacząć — Claude przywita Cię automatycznie i poprosi o wybór języka.

---

## English

This is the material for a **feature-adoption workshop**. It contains a fictional company called **Shipped** on which participants practice the adoption-diagnosis flow. Each participant works through it in a Claude Code session opened in this folder.

### How to start

Open Claude Code in this folder and type anything — `hi`, `start`, even your actual question. On the very first message in a new session, Claude greets you bilingually and asks you to pick a language (PL or EN). After you pick, you get a short intro and a clear next step. From then on, all content lives in `en/` (or `pl/`) and Claude operates only in your chosen language.

If you're assigned a specific case (A, B, or C), once you've picked your language just type `start case A` (or `B` / `C`) and Claude will walk you through it.

### What Shipped is

A fictional product- and project-management tool — like Linear or Jira — with one difference: it doesn't end at "Done." After every feature ships, Shipped automatically checks whether the metric that feature was meant to move actually moved. Full context: `en/company.md`.

### Workshop flow

```
1. Do I have a problem?  — how many users discover and use it (adoption)    [DISCOVERABILITY]
2. Role                  — is it worth it? If not → next feature. + what outcome.
3. Value                 — do users who use it get what we wanted them to get?
4. Decision              — keep / kill / push (distribution) / fix (experience)
5. Hypothesis            — (if push or fix)
```

Two problem categories: **Discoverability** (doesn't find / doesn't understand) and **Value** (uses it, but it isn't delivering value).

### Files (English)

All under `en/`:

| File | What it is | Used in |
|---|---|---|
| `CLAUDE.md` | Operating instructions (Claude reads after EN pick) | Every session |
| `company.md` | Company context, scale, strategy, pricing, competition | Block 2 (intro) |
| `portfolio.md` | The 9 Shipped features — clean description of what each does | Block 2 (overview) |
| `data-dashboard.md` | High-level metrics for all 9 features + facilitator data slices | Block 2 and 3 (adoption scan) |
| `adoption-retention.md` | Adoption rate over time + retention by segment for all 9 features | Anywhere a retention question comes up |
| `demo-slack-integration.md` | **Block 2 demo case** — Slack Integration, full deep-dive | Block 2 (facilitator walks live) |
| `case-a-task-to-event-linking.md` | Participant case — Discoverability / push | Block 3 |
| `case-b-outcome-roadmap.md` | Participant case — Value / work on value | Block 3 |
| `case-c-mcp-server.md` | Participant case — channel / metric definition in the AI era | Block 3 |
| `prompts.md` | Ready-made Claude prompts: voice-of-customer + hypothesis generation | Block 2 and 3 |
| `Case A - Add task _standalone_.html` | Interactive UI mockup for Case A | Block 3 |
| `Case B - Outcome Roadmap _standalone_.html` | Interactive UI mockup for Case B | Block 3 |
| `retention-curve.html` | Standalone retention charts | Optional visual |

### Case convention (A / B / C + Slack demo) in Block 3

1. Feature (link to portfolio)
2. Context (assumptions + outcome)
3. Funnel (user-level, ~5,170 paying users)
4. Cohort/Outcome (3 retention groups)
5. User quotes
6. Extra data slices (7, on request)
7. **Background / why** (for the facilitator — target diagnosis + traps + hypotheses)

---

## Polski

To są materiały do **warsztatu o adopcji funkcjonalności**. Zawierają fikcyjną firmę **Shipped**, na której uczestnicy ćwiczą flow diagnozy adopcji. Każdy uczestnik przerabia go w sesji Claude Code otwartej w tym folderze.

### Jak zacząć

Otwórz Claude Code w tym folderze i napisz cokolwiek — `cześć`, `start`, albo od razu Twoje pytanie. Na pierwszą wypowiedź w nowej sesji Claude wita bilingual i pyta o język (PL albo EN). Po wyborze dostajesz krótkie wprowadzenie i jasny next step. Od tego momentu cała treść siedzi w `pl/` (albo `en/`), a Claude operuje wyłącznie w wybranym przez Ciebie języku.

Jeśli masz przypisany konkretny case (A, B albo C), po wyborze języka po prostu napisz `start case A` (albo `B` / `C`) — Claude poprowadzi Cię przez flow.

### Czym jest Shipped

Fikcyjne narzędzie do zarządzania produktem i projektami — jak Linear czy Jira — z jedną różnicą: nie kończy się na „Done." Po wypuszczeniu funkcjonalności sprawdza, czy faktycznie zmieniła metrykę, którą miała zmienić. Pełny kontekst: `pl/company.md`.

### Flow, którego uczy warsztat

```
1. Czy mam problem?   — ile userów odkrywa i używa (adopcja)        [DISCOVERABILITY]
2. Rola               — czy w ogóle warto nad tym pracować? Jeśli nie → następny feature.
                        Plus: jaki outcome ta funkcjonalność ma ruszać.
3. Value              — czy ci, którzy używają, osiągają to co chcieliśmy?
4. Decyzja            — keep / kill / push w dystrybucję / fix doświadczenia
5. Hipoteza           — (jeśli push lub fix)
```

Dwie kategorie problemu: **Discoverability** (nie odkrywa / nie rozumie) i **Value** (używa, ale nie wnosi wartości).

### Pliki (po polsku)

Wszystko w folderze `pl/`:

| Plik | Co to | Gdzie używane |
|---|---|---|
| `CLAUDE.md` | Instrukcje operacyjne (Claude czyta po wyborze PL) | Każda sesja |
| `company.md` | Kontekst firmy, skala, strategia, pricing, konkurencja | Block 2 (wprowadzenie) |
| `portfolio.md` | 9 funkcjonalności Shipped — czysty opis, co każda robi | Block 2 (overview) |
| `data-dashboard.md` | High-level metryki wszystkich 9 funkcjonalności + lista data slices dla prowadzącego | Block 2 i 3 (skan adopcji) |
| `adoption-retention.md` | Adoption rate over time + retencja per segment dla wszystkich 9 funkcjonalności | Wszędzie, gdzie pojawi się pytanie o retencję |
| `demo-slack-integration.md` | **Demo case na Block 2** — Slack Integration, pełny deep-dive | Block 2 (Wiktor prowadzi na żywo) |
| `case-a-task-to-event-linking.md` | Case dla uczestników — Discoverability / push | Block 3 |
| `case-b-outcome-roadmap.md` | Case dla uczestników — Value / praca nad wartością | Block 3 |
| `case-c-mcp-server.md` | Case dla uczestników — channel / definicja metryki w erze AI | Block 3 |
| `prompts.md` | Gotowe prompty do Claude: feedback klientów + generowanie hipotez | Block 2 i 3 |
| `Case A - Add task _standalone_.html` | Interaktywna makieta UI dla Case A | Block 3 |
| `Case B - Outcome Roadmap _standalone_.html` | Interaktywna makieta UI dla Case B | Block 3 |
| `retention-curve.html` | Standalone wykresy retencji | Materiał poglądowy |

### Konwencja każdego case'a (A/B/C + demo) w Block 3

1. Funkcjonalność (link do portfolio)
2. Kontekst (założenia + outcome)
3. Funnel (user-level, ~5,170 paying users)
4. Cohort/Outcome (3 grupy retention)
5. Cytaty userów
6. Dodatkowe data slices (7, na żądanie)
7. **Tło / why** (dla prowadzącego — diagnoza docelowa + pułapki + hipotezy)

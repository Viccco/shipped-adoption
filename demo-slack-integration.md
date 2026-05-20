# Demo case (Block 2) — Slack Integration

To jest funkcjonalność, którą Wiktor prowadzi na żywo w Block 2 (nie dla uczestników w Block 3). Struktura jak case'y A/B/C, żeby demo miało te same dane, co potem dostaną uczestnicy.

## Funkcjonalność

Slack Integration (patrz portfolio): jednostronne (push-only) powiadomienia do Slacka — liczby po release, alerty gdy metryka spadła, zdarzenia jak dopisany task. Brak two-way: nie zaakceptujesz taska ani nie otworzysz raportu z poziomu Slacka.

## Kontekst

Slack Integration to jedna ze starszych funkcjonalności Shipped — powstała, zanim był MCP Server. Założenie: jeśli user dostaje info tam, gdzie pracuje (na Slacku), nie musi pamiętać o wchodzeniu do Shipped, więc wraca częściej i zostaje aktywny.

Outcome który miała ruszyć: **weekly active users** (cycle outcome Retain). Hipoteza zespołu: powiadomienia = re-engagement = wyższy weekly active rate.

## Funnel (ostatnie 90 dni, ~5,170 paying users)

| Krok | Liczba paying users | % |
|---|---|---|
| Zobaczył opcję Slack Integration w ustawieniach | 4,550 | 88% |
| Połączył kanał Slack | 4,033 | 78% |
| Dostaje powiadomienia regularnie (≥1/tydzień) | 3,670 | 71% |
| Klika w powiadomienie i wchodzi do Shipped | 1,450 | 28% |
| Wraca do Shipped przez Slack regularnie (≥3/mies.) | 620 | 12% |

Pierwsze trzy kroki wysokie — konfiguracja i odbiór działają. Dramatyczny spadek przy "klika i wchodzi" (71% → 28%): powiadomienia docierają, ale nie napędzają akcji.

## Cohort/Outcome

Retencja (weekly active rate) wg intensywności użycia, ostatnie 90 dni:

| Grupa | Liczba paying users | Retencja (weekly active) |
|---|---|---|
| Cały aktywny user base | — | 50% |
| Nie skonfigurował Slack Integration | 1,137 (22%) | 50% |
| Skonfigurował, czyta pasywnie (nie klika) | 3,413 (66%) | 50% |
| Aktywnie klika i wraca przez Slack | 620 (12%) | **52%** |

**Tu jest pointa:** nawet grupa, która aktywnie klika, ma retencję **52% vs 50% całego aktywnego base = +2pp**. Sygnał prawie zerowy. Ci, którzy tylko czytają (66% paying users), są dokładnie na poziomie base. Powiadomienia nie ruszają retencji — bo są pasywne. Dostać info ≠ wrócić i coś zrobić.

## Cytaty userów

> **Bartek, PM, Hookline (Pro plan, 7 miesięcy):**
> "Fajnie, że widzę na Slacku, że raport jest gotowy. Ale i tak potem muszę wejść do Shipped, żeby cokolwiek z tym zrobić. To tylko sygnał, nie akcja."

> **Ewa, Engineering Lead, Trailmark (Enterprise plan, 10 miesięcy):**
> "W Linearze zamykam issue prosto z wątku na Slacku. W Shipped dostaję 'raport gotowy' i tyle. Muszę klikać, wchodzić, szukać tego raportu w UI. Po co mi to powiadomienie, skoro i tak cała robota jest gdzie indziej?"

> **Michał, Head of Product, Quanta (Pro plan, 5 miesięcy):**
> "Mam kanał #shipped-alerts, ale szczerze go zmutowałem. Za dużo notyfikacji, za mało takich, które naprawdę wymagają, żebym coś zrobił. Szum."

> **Aleksandra, PM, Brightloop (Pro plan, 9 miesięcy):**
> "Chciałabym móc kliknąć 'ok, zajmę się tym' albo przypisać do kogoś prosto ze Slacka. Teraz to read-only kanał — widzę, ale nie działam."

> **Grzegorz, Founder, Stacklane (Enterprise plan, 3 miesiące):**
> "Alerty o spadku metryki są przydatne — od razu wiem, że coś się dzieje. Ale na tym się kończy. Reszta to i tak ręczna robota w Shipped."

## Co właśnie zobaczyliśmy (flow)

1. **Discoverability (adopcja)** — NIE problem. 88% zna, 78% używa, 71% dostaje regularnie. Adopcja wysoka.
2. **Rola** — push z powrotem do produktu, outcome = retention. Skoro 78% używa, a ma napędzać retention — warto sprawdzić, czy faktycznie napędza.
3. **Value** — TO problem. +2pp nawet u aktywnych. Push-only, pasywne. Linear pokazuje, że two-way (actionable) działa — to sufit naszej implementacji, nie funkcjonalności.
4. **Decyzja** — fix (pogłębić do actionable), nie kill.
5. **Hipoteza** — actionable Slack: akceptuj/odrzuć task, raport inline w wątku, zapytaj o outcome bez wchodzenia do Shipped. Aggressive test: two-way dla części teamów, mierzymy czy WAR rośnie powyżej +2pp.

---

## Dodatkowe data slices (na żądanie sali)

### Segmentacja per plan (adoption %)
| Plan | Adoption % |
|---|---|
| Pro | 76% |
| Enterprise | 84% |
| Free | 71% |

### Segmentacja per team size (adoption %)
| Team size | Adoption % |
|---|---|
| 1–5 | 72% |
| 6–20 | 80% |
| 20+ | 85% |

### Segmentacja per role (adoption %)
| Role | Adoption % |
|---|---|
| Product Manager | 80% |
| Engineer | 75% |
| Founder / Head of Product | 82% |
| Designer | 60% |
| Other | 70% |

Wszędzie wysoko — to potwierdza, że adoption/discoverability NIE jest problemem. Problem siedzi w value.

### ARR attribution
**~80% ARR** firmy jest w teamach, które używają Slack Integration. Ale to słaby differentiator — prawie wszyscy używają, więc korelacja z wartością konta jest pozorna.

### NPS detractor commentary (3 cytaty — userzy, którzy używają, ale nie widzą wartości)
> **NPS 6 (Passive):** "Używam, bo się samo skonfigurowało przy onboardingu. Ale gdyby zniknęło, chyba bym nie zauważył."

> **NPS 5 (Detractor):** "Za dużo szumu, za mało akcji. Zmutowałem kanał."

> **NPS 6 (Passive):** "To jest 'nice to have', nie 'must have'. Linear robi to tak, że faktycznie przyspiesza pracę. U was to tablica ogłoszeń."

### Top 3 support ticketów (90 dni)
| Problem | Liczba ticketów |
|---|---|
| Jak wyciszyć / ograniczyć liczbę powiadomień | 41 |
| Czy mogę działać (akceptować task) ze Slacka? (odpowiedź: nie) | 23 |
| Powiadomienia idą do złego kanału | 14 |

### Time-to-first-use
Mediana **2 dni** — konfiguruje się przy onboardingu, niemal natychmiast. Adoption jest szybkie i łatwe; to nie tu leży problem.

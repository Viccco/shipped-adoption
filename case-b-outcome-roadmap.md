# Case B — Outcome Roadmap

## Funkcjonalność

Outcome Roadmap (patrz portfolio): widok roadmapy zorganizowany po celach, nie po funkcjonalnościach. Dla każdego celu widzisz zaplanowaną pracę, termin realizacji i poziom pewności, że ruszy metryę.

## Kontekst

Zespół Shipped wypuścił Outcome Roadmap 4 miesiące temu, w Q4 2025. Założenie: PM-owie tracą wątek z celów strategicznych przy planowaniu kwartału. Klasyczne roadmapy (Linear/Jira) pokazują features w czasie, ale nie odpowiadają na "czy to co planujemy faktycznie pociągnie outcome'y." Outcome Roadmap miała być narzędziem do kwartalnego planningu i bieżącej priorytetyzacji.

Outcome który miał ruszyć: **weekly active users** (cycle outcome Shipped na Q1 2026 = Retain) — założenie zespołu było takie, że PM-owie, którzy znajdą wartość w planningu z Outcome Roadmap, będą wracać częściej, bo to ich kotwiczy w produkcie poza wąskim "ship + raport" loop.

## Funnel (ostatnie 90 dni, ~5,170 paying users)

| Krok | Liczba paying users | % |
|---|---|---|
| Otworzył widok Outcome Roadmap przynajmniej raz | 3,100 | 60% |
| Otwiera regularnie (≥1 raz w tygodniu) | 1,400 | 27% |
| Dodał własny goal do widoku roadmapy | 950 | 18% |
| Zlinkował task do goala w roadmapie | 620 | 12% |
| Aktywnie używa do priorytetyzacji (edytuje co tydzień) | 270 | 5% |

## Cohort/Outcome

Retencja (weekly active rate) wg intensywności użycia, ostatnie 90 dni:

| Segment | Liczba paying users | Retencja (weekly active) |
|---|---|---|
| Cały aktywny user base | — | 50% |
| Non-user (nigdy nie otworzył Outcome Roadmap) | 2,070 (40%) | 45% |
| Casual user (otworzył, nie zlinkował tasku do goala) | 2,480 (48%) | 52% |
| Regular user (zlinkował task do goala, używa intensywnie) | 620 (12%) | **70%** |

**Sygnał wartości:** Regular userzy (zlinkowali task do goala, używają intensywnie) mają retencję **70% vs 50% całego aktywnego base = +20pp**. Próg jest w momencie linkowania taska — samo otwarcie widoku nie wystarcza. To sygnał (korelacja), nie dowód — dowód dałby aggressive test.

## Cytaty userów

> **Iwona, Head of Product, GridPay (Enterprise plan, 5 miesięcy):**
> "Outcome Roadmap to nasze pierwsze miejsce na quarterly planning. Patrzymy na cele, widzimy które mają zaplanowaną pracę a które są puste, debatujemy nad confidence-bands. Bez tego nasze plannings to była kakofonia. Teraz mam jeden screen do pokazania zarządowi."

> **Mariusz, PM, FlowSet (Pro plan, 6 miesięcy):**
> "Otworzyłem ten widok, wygląda fajnie, ale nie wiem co mam dalej robić. Klikam w cel, widzę pustą listę. Mam tam dodać taski? Ale ja taski tworzę na bieżąco, nie planuję ich pod cele z wyprzedzeniem. Zostawiłem na razie, może wrócę kiedyś."

> **Karol, Senior PM, SignalKite (Pro plan, 3 miesiące):**
> "Mam Linear do roadmapy i Notion do strategii. Czemu mam mieć trzeci widok roadmapy w Shipped? Otwierałem dwa razy, nie kupuję. Może gdybym widział tu coś czego nie widzę gdzie indziej."

> **Joanna, Product Lead, Threadpost (Pro plan, 8 miesięcy):**
> "Próbowałam dodać goal i zlinkować taski, ale nigdzie nie jest jasne że trzeba *najpierw* mieć goal z metryką w PostHogu zsynced. Doszłam do tego dopiero jak pisałam do supportu. Teraz używam, ale podejście pierwszy raz totalnie odbija."

> **Paweł, CTO i co-founder, Cloudreel (Enterprise plan, 11 miesięcy):**
> "Outcome Roadmap to nasz quarterly meeting. Dosłownie. Otwieramy widok, przechodzimy outcome po outcome, każdy lead mówi co robi i pokazuje progress. Bez tego nasz quarterly był 3-godzinną debatą zamiast 45 minut. Najlepsza rzecz w Shipped."

## Dodatkowe data slices (na żądanie uczestnika)

### Segmentacja per plan

| Plan | % paying users w tym planie którzy dodali goal do roadmapy |
|---|---|
| Pro | 14% |
| Enterprise | 38% |
| Free | 8% (mała próba) |

### Segmentacja per team size

| Team size | Adoption % |
|---|---|
| 1–5 userów | 6% |
| 6–20 userów | 19% |
| 20+ userów | 32% |

Wyraźna korelacja z rozmiarem zespołu — większe organizacje potrzebują kwartalnego planowania, mniejsze nie.

### Segmentacja per role usera

| Role | Adoption % |
|---|---|
| Product Manager | 28% |
| Engineering Lead | 15% |
| Founder / Head of Product | 45% |
| Designer | 4% |
| Other | 5% |

### ARR attribution

**78% ARR** firmy jest w teamach, w których przynajmniej jeden user kiedykolwiek dodał goal do Outcome Roadmap. Wyraźny tilt Enterprise — ta funkcjonalność najsilniej rezonuje z większymi kontami.

### NPS detractor commentary (3 cytaty z paying users, którzy NIE używają)

> **NPS 3 (Detractor):** "Mamy już Notion do strategii i Linear do roadmapy. Czemu mam mieć trzeci tool dla tego samego?"

> **NPS 5 (Detractor):** "Nie rozumiem co to jest 'confidence band' i czemu to jest na roadmapie. Mam czuć się pewny czy nie?"

> **NPS 6 (Passive):** "Roadmap to nie moje zadanie, to robi nasz Head of Product. Może on by to ocenił."

### Top 3 support ticketów (ostatnie 90 dni)

| Problem | Liczba ticketów |
|---|---|
| Jak dodać goal do Outcome Roadmap (Joanna-pattern) | 62 |
| Confidence bands nie wyświetlają się dla mojego goala | 28 |
| Roadmap się nie zapisuje po edycji | 12 |

### Time-to-first-use

Mediana **32 dni** od pierwszego użycia produktu do dodania pierwszego goala do Roadmap. To **najpóźniejszy** moment value-realization w całym portfolio Shipped — uczestnicy potrzebują czasu, żeby w ogóle rozważyć użycie tej funkcjonalności.

## Co zrobiłbyś z tym?

Pytanie do uczestnika — bez podpowiedzi.

---

## Tło / why (dla prowadzącego)

Nasze najmocniejsze hipotezy dlaczego ta funkcjonalność ma rozsądny usage, ale niską głębokość — i dlaczego mimo to *jest tu realna wartość*, którą warto wydobyć:

1. **Wartość jest realna i mocna w wąskiej grupie** (12% paying users, +25pp retention). Iwona i Paweł pokazują czysty sygnał: dla zespołów, które robią quarterly planning, Outcome Roadmap zastępuje rozproszony proces (Notion + Linear + spreadsheet) jednym widokiem. To nie jest feature do zabicia — to feature, gdzie 88% userów nigdy nie doszło do momentu wartości.

2. **Aha-moment wymaga sekwencji setupu**, której nikt nie tłumaczy: (a) musisz mieć dodany goal z metryką zsynced z PostHogiem, (b) musisz mieć ≥2 goals żeby widok roadmapy miał sens, (c) musisz zlinkować ≥3 taski do goali żeby zobaczyć confidence-bands. Joanna doszła do tego przez support, większość zatrzymuje się na pierwszym kroku.

3. **Mariusz (typowy reprezentant 60% userów którzy raz otworzyli)** mówi "nie wiem co mam dalej robić." To nie discoverability — funkcjonalność znalazł. To brak *narracji wartości w produkcie*. Widok pokazuje pusty stan, nie pokazuje czemu warto go wypełnić.

4. **Karol (sceptyk z konkurencyjnym tooling stackiem)** to inny problem. On nie kupuje *koncepcji* "roadmapa po outcome'ach." Brakuje przykładu/case study, który by mu pokazał czego nie widzi w Linear+Notion. To problem komunikacji wartości w empty state albo onboardingu.

5. **Linkowanie task-do-goala** jest progiem do wartości (+18pp wzrostu retention w samym tym kroku). Co znaczy, że ścieżka onboardingowa musi prowadzić usera do tego momentu, nie tylko do "otwarł widok."

6. **Empty state vs filled state** to przepaść — gdy user widzi pusty Outcome Roadmap, nie ma jak zrozumieć po co on jest. Iwona i Paweł używają, bo *ktoś im pokazał*, jak ma wyglądać wypełniony widok. Reszta nigdy go nie zobaczyła.

**Diagnoza, do której uczestnik powinien dojść:**
- To NIE jest tylko problem discoverability (60% paying users otworzyło widok — to spora dystrybucja jak na 4-miesięczny feature).
- To NIE jest też problem do killa — sygnał z grupy aktywnych userów jest mocny i wartość jest realna.
- To jest **value problem w sensie "wartość jest, ale wymaga pracy"** — pracy nad onboardingiem, narracją w empty state, prowadzeniem usera do momentu Aha.

**Najmocniejsza hipoteza do testowania:**
- Empty-state Outcome Roadmap pokazuje case study konkretnego klienta (np. zanonimizowane GridPay): "Tak wygląda quarterly planning u zespołu który używa. Tyle decyzji podjęli w tym kwartale. Tak ich confidence-band zmieniał się przez kwartał."
- Pierwsza wizyta uruchamia 3-step guided setup: dodaj goal → zsynchroniuj metryę z PostHoga → dodaj 2 taski do goala. Bez przeskakiwania.
- Aggressive test: pierwsze otwarcie Outcome Roadmap *wymaga* przejścia tutoriala. A/B test na 50% paying users przez 14 dni. Mierzymy: % userów którzy dochodzą do "zlinkował task do goala," weekly active rate cohortu w 30 dni.

**Pułapki, w które uczestnik może wpaść:**
- Diagnoza "to jest discoverability problem" — bo Mariusz mówi "nie wiem co dalej robić." Ale on znalazł funkcjonalność i otworzył widok. To nie discoverability, to brak narracji wartości w samym widoku. Discoverability rozwiązuje "user nie wie że to istnieje" — tu wszyscy wiedzą.
- Decyzja "po prostu kill" — bo Karol mówi "nie kupuję." Ale dane pokazują, że dla grupy aktywnej (Iwona, Paweł) to jest mocny driver retention. Killowanie zabija wartość, która faktycznie jest.
- Decyzja "ulepszmy event picker albo dodajmy więcej widoków" — to są fixy techniczne, ale realny problem jest narracyjny: jak pokazać userowi w ciągu 30 sekund, czemu Outcome Roadmap jest warta wypełnienia.

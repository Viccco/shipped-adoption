# Case A — Task-to-Event Linking

## Funkcjonalność

Task-to-Event Linking (patrz portfolio): przy spec'u taska wybierasz konkretne zdarzenie z PostHoga/Mixpanela/Amplitude, które ten task ma ruszyć.

## Kontekst

Zespół Shipped wypuścił Task-to-Event Linking 6 miesięcy temu, w Q3 2025. Założenie było proste: jeśli userzy będą linkować eventy do tasków przy spec'u, Impact Detector dostanie precyzyjne sygnały i raporty po wypuszczeniu będą znacznie lepsze. Lepsze raporty = userzy widzą wartość Shipped szybciej = wracają częściej.

Outcome który miał ruszyć: **weekly active teams** (cycle outcome Shipped na Q1 2026 = Retain — metryka, którą zespół zobowiązał się ruszyć w tym kwartale: retencja, czyli utrzymanie userów aktywnych w produkcie).

Przy spec'u taska pole "Linkuj event" znajduje się w sekcji "Advanced," którą user musi rozwinąć ręcznie. Pole otwiera **event picker** — listę, z której wybierasz konkretne zdarzenie (event) do podpięcia. Tooltip wyjaśnia o co chodzi, ale tylko przy hoverze.

## Funnel (ostatnie 90 dni, ~5,170 paying users)

Funnel mierzony na poziomie usera — decyzja "linkuj event" jest podejmowana przez konkretnego usera w momencie spec'u taska.

| Krok | Liczba paying users | % |
|---|---|---|
| Stworzył przynajmniej 1 task | 4,030 | 78% |
| Rozwinął sekcję "Advanced" przy spec'u taska | 1,820 | 35% |
| Kliknął w pole "Linkuj event" | 1,505 | 29% |
| Skutecznie zlinkował event do taska | 1,195 | 23% |
| Linkuje event do większości swoich tasków | 415 | 8% |

## Cohort/Outcome

Retencja (weekly active rate) wg intensywności użycia, ostatnie 90 dni:

| Segment | Retencja (weekly active) |
|---|---|
| Cały aktywny user base | 50% |
| Non-user (nigdy nie zlinkował eventu) | 47% |
| Casual user (zlinkował 1–5 tasków) | 56% |
| Regular user (linkuje intensywnie) | **68%** |

**Sygnał wartości:** Regular userzy (linkują eventy intensywnie) mają retencję **68% vs 50% całego aktywnego base = +18pp**. To **sygnał** (korelacja), nie dowód — ci userzy mogli być bardziej zaangażowani od początku (różnica utrzymuje się po kontroli na rozmiar zespołu i staż, ale to wciąż obserwacja, nie eksperyment). Dowód dałby dopiero **aggressive test** — celowo odważny eksperyment (np. wymuszenie zmiany na części userów), który szybko pokazuje, czy efekt jest realny.

## Cytaty userów

> **Marta, PM, Bookloop (Pro plan, 8 miesięcy w produkcie):**
> "Linkowanie eventów to dla mnie game-changer. Wiem przy spec'u co dokładnie chcę ruszyć, i po deploy nie muszę zgadywać który raport otworzyć. Robię to przy każdym tasku."

> **Tomek, Head of Product, Stride (Pro plan, 4 miesiące):**
> "Wiem że jest jakaś integracja z PostHogiem, ale nie wiem gdzie ją włączyć. Otwieram nowy task, wpisuję tytuł, opis, i save. Nikt mi nie mówi że gdzieś tam jest pole które warto wypełnić."

> **Agnieszka, Senior PM, CashLedger (Pro plan, 11 miesięcy):**
> "Próbowałam zlinkować event, ale nie pamiętałam jak się nazywa. Zaczynam pisać 'user' i wyskakuje 60 eventów. Nie wiem który jest który. Po dwóch minutach poddaję się i zapisuję task bez linkowania."

> **Krzysiek, PM, ReleaseDeck (Pro plan, 6 miesięcy):**
> "Używałem przez pierwszy tydzień, potem przestałem. Linkujesz event, ale w raporcie 14-day i tak dostajesz wszystkie metryki naraz. Czuję że nawet bez linkowania raport jest podobny. Może coś robię źle?"

> **Patryk, CTO, NoteFlare (Enterprise plan, 2 miesiące):**
> "Mamy własny warehouse w BigQuery. Event picker pokazuje nam tylko top 200 eventów z naszego PostHoga, a my najważniejsze metryki trzymamy w BigQuery. Czyli linkowanie u nas nie działa na to co naprawdę nas obchodzi."

## Dodatkowe data slices (na żądanie uczestnika)

### Segmentacja per plan

| Plan | % paying users w tym planie którzy zlinkowali ≥1 event |
|---|---|
| Pro | 18% |
| Enterprise | 45% |
| Free | n/a (Free ma limit 1 analytics integration, mała próba) |

### Segmentacja per team size

| Team size | Adoption % |
|---|---|
| 1–5 userów | 15% |
| 6–20 userów | 28% |
| 20+ userów | 38% |

### Segmentacja per role usera

| Role | Adoption % |
|---|---|
| Product Manager | 32% |
| Engineer | 8% |
| Designer | 3% |
| Founder / Head of Product | 15% |
| Other | 5% |

### ARR attribution

**64% ARR** firmy jest w teamach, w których przynajmniej jeden user kiedykolwiek zlinkował event. Czyli ta funkcjonalność (mimo niskiej Coverage 23% — Coverage to odsetek userów, którzy w ogóle zaadoptowali funkcjonalność) koreluje z wysokowartościowymi kontami.

### NPS detractor commentary (3 cytaty z paying users, którzy NIE używają)

> **NPS 4 (Detractor):** "Linkowanie events brzmi jak coś dla Mixpanel power-userów. Ja nie wiem nawet jak nazywać swoje events, zostawiam to data team."

> **NPS 5 (Detractor):** "Próbowałem, ale nie widzę co mi to daje. Raport po deploy i tak generuje wszystko."

> **NPS 6 (Passive):** "Mam takie standardowe taski, nie potrzebuję analytics linkowania."

### Top 3 support ticketów (ostatnie 90 dni)

| Problem | Liczba ticketów |
|---|---|
| Event picker nie pokazuje moich eventów PostHog | 45 |
| Custom warehouse events nie pojawiają się w dropdownie | 28 |
| Linkowanie nie ma wpływu na raport 14-day (Krzysiek-pattern) | 19 |

### Time-to-first-use

Mediana **18 dni** od pierwszego użycia produktu do pierwszego zlinkowania eventu. Dla porównania: time-to-first-use dla Goals & Outcomes = 2 dni, dla Post-Ship Detector = 5 dni.

## Co zrobiłbyś z tym?

Pytanie do uczestnika — bez podpowiedzi.

---

## Tło / why (dla prowadzącego)

Nasze najmocniejsze hipotezy dlaczego ta funkcjonalność ma słabą adopcję mimo wysokiego impactu na tych, którzy jej używają:

1. **Pole schowane w "Advanced"** — to największa przyczyna niskiej Coverage. PM-owie szybko spec'ują task, nie rozwijają "Advanced," idą dalej. 65% paying users *nigdy* nie rozwinęło tej sekcji.
2. **Brak aktywnego prompta** — nikt nie mówi userowi w momencie spec'u "pomyśl jaki event chcesz ruszyć." Tooltip jest, ale dopiero po hoverze, więc działa tylko jeśli user już wie czego szuka.
3. **Event picker wymaga znania nazw** — autocomplete pokazuje wszystkie eventy z PostHoga (często 200+), bez grupowania, bez "najczęściej używane." User który nie pamięta dokładnej nazwy się gubi i porzuca.
4. **Brak follow-up nudge'ów** — userzy, którzy raz spróbowali i zrezygnowali (Agnieszka, Krzysiek), nie dostają żadnego push'a żeby spróbować ponownie po tym jak dostali dwa raporty.
5. **Niezrozumienie wartości linkowania** (Krzysiek) — Impact Detector generuje raport nawet bez linkowania, więc user nie czuje różnicy. Wartość linkowania jest realna ale niewidoczna w raporcie — to problem komunikacji wartości.
6. **Enterprise edge case** (Patryk) — userzy z warehouse'em nie mogą zlinkować eventu z BigQuery. To niszowy ale rosnący segment, sygnał na osobny feature.

**Decyzja, do której uczestnik powinien dojść:**
- Coverage 23% + Impact +21pp = klasyczny low-hanging fruit
- Diagnoza: problem discoverability (większość paying users nigdy nie weszła w "Advanced")
- Decyzja: PUSH distribution

**Najmocniejsza hipoteza do testowania (aggressive test):**
- Wyciągnięcie pola "Linkuj event" z "Advanced" do głównego formularza taska, na poziomie tytułu i opisu.
- Dodatkowo: wymóg wypełnienia pola przed zapisem (test ceiling — czy to działa nawet wtedy, kiedy user się broni).
- A/B test na 50% nowych tasków przez 14 dni. Mierzymy: % tasków z linkiem, weekly active rate cohortu w 30 dni.

**Pułapki, w które uczestnik może wpaść:**
- Diagnoza "to jest value problem" — bo Krzysiek mówi "czuję że raport jest podobny." Ale tylko 8% userów regularnie linkuje, więc 92% nigdy nie miało okazji *poczuć różnicy*. To nie value problem, to discoverability ze skutkiem ubocznym na value-perception.
- Decyzja "ulepszmy event picker" — tak, picker wymaga pracy, ale to nie jest największy lever. Picker dotyka tylko tych 29% userów, którzy już do niego dotarli. Wyciągnięcie pola z "Advanced" dotyka pozostałych 65%.

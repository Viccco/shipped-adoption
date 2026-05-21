# Case C — MCP Server

## Funkcjonalność

MCP Server (patrz portfolio): Shipped wystawia interfejs (MCP — Model Context Protocol, standard, którym asystenci AI łączą się z narzędziami) przez który Claude, Cursor i inne asystenty AI mogą czytać i pisać dane bez otwierania UI Shipped.

## Kontekst

Zespół Shipped wypuścił MCP Server 2 miesiące temu, w Q1 2026. Założenie: PM-owie i engineerzy żyją coraz więcej w Claude/Cursor (zamiast otwierać dziesiątek toolów), więc Shipped musi być dostępne tam, gdzie pracują. MCP Server jest **free na każdym planie** — to świadoma strategiczna inwestycja zespołu Shipped: zakład, że Claude i Cursor będą głównym kanałem, przez który PM-owie używają toolów w 2026, więc Shipped musi tam być, zanim konkurencja zauważy, że agent surface to nowy kanał dystrybucji.

Outcome który miał ruszyć: **weekly active users** (cycle outcome Retain — metryka, którą zespół zobowiązał się ruszyć w tym kwartale: retencja, mierzona jako ilu userów jest aktywnych w danym tygodniu). Ale tu pojawia się paradoks: jeśli user zaczyna używać Shipped przez Claude, *przestaje* otwierać UI Shipped. Z perspektywy klasycznej metryki UI wygląda to jak spadek aktywności, mimo że realne zużycie produktu rośnie. Sukces MCP może wyglądać w danych jak porażka — to pierwszy sygnał, że trzeba nowej metryki.

## Funnel (ostatnie 60 dni, bo feature młody, ~5,170 paying users)

| Krok | Co user zrobił | Liczba paying users | % |
|---|---|---|---|
| Dowiedział się o MCP Server | Zobaczył mail z anonsem, in-product changelog, blog post | 3,200 | 62% |
| Otworzył docs MCP Server | Z dowiedzionych — kliknął "Dowiedz się więcej" i trafił na docs.shipped.com/mcp | 1,500 | 29% |
| Skonfigurował MCP w Claude/Cursor | Wkleił config JSON, podpiął API key — MCP klient podłączony do serwera Shipped | 380 | 7% |
| Wykonał przynajmniej 1 call | Faktycznie zadał pytanie / wykonał operację przez Claude | 290 | 6% |
| Wykonuje regularnie (≥3 calls/tydzień) | Powtarza się nieprzerwanie w ostatnich 4 tygodniach | 95 | 2% |

**Kluczowe spadki:**

- **Z 1,500 do 380 (−75%):** większość, która otwarła docs, nie skonfigurowała. Przeważnie nie-engineerzy, którzy nie umieją wkleić JSON-a do Claude'a/Cursora.
- **Z 380 do 290 (−24%):** 90 paying users podłączyło MCP, ale nigdy nie zadało prawdziwego pytania. Test/health-check i porzucenie, albo skonfigurował zespół IT a faktyczny user nigdy nie spróbował.
- **Z 290 do 95 (−67%):** tylko 1/3 osób, które kiedykolwiek wykonały call, robi to regularnie. Reszta spróbowała raz-dwa i przestała.

## Cohort/Outcome

Retencja (weekly active rate, mierzona w UI) wg intensywności użycia:

| Segment | Liczba paying users | Retencja (weekly active w UI) |
|---|---|---|
| Cały aktywny user base | — | 50% |
| Non-user (nie używa MCP Server) | 4,880 (94%) | 50% |
| Casual user (skonfigurował, nie używa intensywnie) | 195 (4%) | 47% |
| Regular user (używa MCP intensywnie) | 95 (2%) | **31%** |

**Tu jest paradoks:** Regular userzy MCP mają retencję **31% vs 50% całego aktywnego base = −19pp** — wyglądają, jakby porzucali produkt. Ale **konsumują Shipped 7 razy w tygodniu, tylko przez Claude, nie przez UI.** Metryka mierzona w UI nie łapie tego użycia, więc sukces MCP w tej grupie jest niewidoczny. To nie jest sygnał słabej wartości — to sygnał, że **mierzymy nie tam, gdzie trzeba.** Dla MCP potrzeba metryki liczącej wywołania przez agentów, nie aktywność w UI.

## Cytaty userów

> **Marcin, Staff Engineer, BuildBox (Pro plan, 9 miesięcy):**
> "Mam Claude Code skonfigurowany ze Shipped MCP. Pytam 'co się ruszyło w naszym onboarding outcome w tym tygodniu' i dostaję odpowiedź bez otwierania jakiegokolwiek dashboardu. Genialne. Otwierałem Shipped UI raz w miesiącu wcześniej, teraz może raz na pół roku."

> **Aleksandra, Head of Product, Crisplane (Enterprise plan, 7 miesięcy):**
> "Słyszałam o MCP w mailu od was. Czytam docs, ale nie wiem jak to skonfigurować w Cursorze. Wkleja się gdzieś jakiś JSON? Co dalej? Brak prostego how-to dla nie-engineerów."

> **Damian, Junior PM, GridPay (Enterprise plan, 4 miesiące):**
> "Nigdy nie słyszałem o MCP. Co to jest? Nie używam Claude w pracy, używam ChatGPT przez przeglądarkę. To dla mnie?"

> **Tomasz, Lead Engineer, Loopfeed (Pro plan, 6 miesięcy):**
> "Skonfigurowałem MCP, próbowałem podpiąć do agenta który zarządza moimi taskami. Działa, ale brakuje endpointów do edycji goali — tylko read. Czekam na update i wtedy podepnę pełniej."

> **Iza, Product Operations, NoteFlare (Enterprise plan, 3 miesiące):**
> "Zbudowaliśmy automatyczny raport do Slacka przez MCP — codziennie rano nasz wewnętrzny bot pyta Shipped o status outcomes i wkleja do kanału. Wcześniej ja robiłam to ręcznie. Działa świetnie."

## Dodatkowe data slices (na żądanie uczestnika)

### Segmentacja per plan

| Plan | % paying users w tym planie którzy wykonali ≥1 call przez MCP |
|---|---|
| Pro | 4% |
| Enterprise | 12% |
| Free | 1% (mała próba) |

### Segmentacja per team size

| Team size | Adoption % |
|---|---|
| 1–5 userów | 3% |
| 6–20 userów | 7% |
| 20+ userów | 15% |

Większe teamy mają więcej engineerów, którzy potrafią skonfigurować MCP samodzielnie.

### Segmentacja per role usera

| Role | Adoption % |
|---|---|
| Engineer | 28% |
| Product Manager | 3% |
| Designer | 0% |
| Founder / Head of Product | 1% |
| Other | 1% |

Bardzo wyraźny engineer tilt — funkcjonalność de facto dziś jest "for engineers."

### ARR attribution

**41% ARR** firmy jest w teamach, w których przynajmniej jeden user wykonał ≥1 call przez MCP. Mieszany obraz — są konkretne high-value Enterprise konta, ale nie tak dominujące jak w Outcome Roadmap.

### NPS detractor commentary (3 cytaty z paying users, którzy NIE używają)

> **NPS 6 (Passive):** "Nie używam Claude w pracy. Nie wiem co to MCP."

> **NPS 5 (Detractor):** "Próbowałem podpiąć w Cursorze, ale brak ekspertyzy technicznej. Nasz dev team musiałby to skonfigurować, a oni mają inne priorytety."

> **NPS 7 (Passive):** "MCP brzmi interesująco, ale jak mam zaufać, że Claude widzi tylko nasze dane, a nie cudze? Nigdzie nie ma jasnej polityki bezpieczeństwa."

### Top 3 support ticketów (ostatnie 60 dni)

| Problem | Liczba ticketów |
|---|---|
| Jak skonfigurować MCP w Claude Desktop / Cursor (Aleksandra-pattern) | 38 |
| Brak endpointów do edycji goali przez MCP (Tomasz-pattern) | 14 |
| Authentication problem przy first connection | 8 |

### Time-to-first-use

Mediana **4 dni** dla engineerów, którzy konfigurują samodzielnie. Dla pozostałych roli próba zbyt mała (n < 10), żeby liczyć medianę.

## Co zrobiłbyś z tym?

Pytanie do uczestnika — bez podpowiedzi.

---

## Tło / why (dla prowadzącego)

Najmocniejsze hipotezy, dlaczego ta funkcjonalność jest taka, jaka jest — i co z tym zrobić:

1. **Klasyczne metryki adopcji nie pasują do MCP Server.** Weekly active rate (UI) regularnych MCP userów = 31% (poniżej baseline 50%). Wygląda jak feature, który "psuje" retention, ale realnie te osoby konsumują Shipped *intensywniej* — średnio 7 calls przez MCP tygodniowo. UI staje się dla nich opcjonalny. Trzeba zdefiniować nową metryę: "engaged user" = active w UI LUB MCP.

2. **Coverage 2% (regularnie używa) to Low w klasycznym sensie, ale to jest 2-miesięczna funkcjonalność z zero in-product surface.** Klasyczna kategoria "Niche/reactive" dla featurów strategicznych jest niewłaściwa — to jest *wczesna faza dystrybucji* na nowym kanale, nie funkcjonalność do zostawienia w spokoju.

3. **Discoverability rozbita na dwa segmenty:**
   - **Engineers (Marcin, Tomasz):** wiedzą o MCP, konfigurują samodzielnie, brakuje im endpointów (depth API). To jest *roadmap problem*, nie adopcyjny.
   - **Nie-engineerzy (Aleksandra, Damian):** nie wiedzą, czym MCP jest, albo nie umieją skonfigurować. To klasyczny discoverability + value-communication problem na surface, której większość PM-ów nawet nie odwiedza (Claude/Cursor docs).

4. **Unexpected use case (Iza):** automatyczne raporty do Slacka przez MCP. To dystrybucja przez agent surface w sposób, którego zespół nie przewidział. Sygnał, że MCP jest narzędziem do *budowania workflow'ów wokół Shipped*, nie tylko "chatting with data."

5. **Defensibility:** każdy kwartał, w którym MCP jest niedostępne na produkcyjnym poziomie, zwiększa ryzyko, że konkurencja (Eppo/Statsig albo nowy entrant) zrobi to pierwsza. Cena tego, że MCP jest free + 2-miesięczna funkcjonalność = okno strategiczne, w którym trzeba szybko zwiększyć adoption, zanim konkurencja zacznie kopiować.

**Diagnoza, do której uczestnik powinien dojść (3 rzeczy naraz):**

- **Metric definition problem** — przed dystrybucją trzeba zdefiniować, co znaczy "user używa MCP." Czy unique paying users z MCP calls/week? Total calls? Coś jeszcze? Bez nowej metryki klasyczny matrix nie ma sensu.
- **Channel problem** — target audience MCP (engineers, advanced PM-owie) nie żyje w UI Shipped. Żyje w Claude, Cursor, docs.anthropic.com. Dystrybucja musi iść tam, gdzie oni są.
- **Communication value problem** dla nie-engineerów — ci, co nie wiedzą czym MCP jest (Damian, Aleksandra), potrzebują video "PM otwiera Claude, pyta o outcome, dostaje odpowiedź." Bez tego setupowanie JSON-a zostaje dla 5% populacji.

**Najmocniejsze hipotezy do testowania:**

1. **Partnership distribution:** Shipped MCP w defaultowych templates dla Claude Code i Cursora. Zamiast budować więcej in-product CTA, dystrybuować przez surface, na której target audience jest.
2. **No-code setup flow:** w Shipped UI, jeden klik "Połącz z Claude" generuje JSON, kopiuje do schowka, otwiera Claude w nowej karcie z instrukcją wklejenia.
3. **Video "PM uses Claude with Shipped":** 60-sekundowy demo na home page docs MCP. Dla Damiana, który "nie wie co to MCP," obraz zastępuje 5 paragrafów tekstu.
4. **API depth roadmap public:** publiczna roadmapa MCP endpoints (read/write goals, edit tasks, automate reports) — żeby engineerzy jak Tomasz nie czekali bezterminowo.

**Pułapki, w które uczestnik może wpaść:**

- **"Coverage 2% = Niche, zostawić w spokoju."** Nie. To jest 2-miesięczna funkcjonalność strategicznie kluczowa, na nowym kanale dystrybucji. Klasyczna kategoria "Niche/reactive" nie pasuje.
- **"Weekly active rate spadł, kill."** Nie. Spadek aktywności w UI dla regularnych MCP userów to *świadectwo sukcesu*, nie porażki — oni używają produktu intensywniej, tylko inaczej. Klasyczna metryka nie łapie.
- **"Więcej in-product promo dla MCP."** Nie. Target audience MCP nie żyje w UI Shipped. Push w UI dotyka 6% MAU którzy widzieli changelog, ale prawdziwa dystrybucja idzie przez Claude/Cursor.
- **"Trzeba pełnego API zanim cokolwiek robimy."** Nie. Pełne API to roadmap problem dla engineerów. Dla większości userów (Aleksandra, Damian) brakuje *czegokolwiek* w UX MCP — depth API nie pomoże, dopóki setup zostaje barierą.

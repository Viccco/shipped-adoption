# Intro module — playbook (PL)

To jest 12-krokowy skrypt prowadzonej lekcji wprowadzającej do flow diagnozy adopcji. Wczytujesz ten plik, gdy uczestnik w `../CLAUDE.md` wybrał ścieżkę **„intro"**. Twoja rola: prowadzisz uczestnika za rękę przez cały flow, używając Slack Integration jako przykładu.

## Zasady prowadzenia (obowiązują w całym intro)

- **Każdy twój turn kończy się jasną sugestią, co user ma zrobić dalej.** Najczęściej: konkretny prompt do wpisania (w cudzysłowie, dosłownie). Czasem: pytanie, na które ma odpowiedzieć.
- **Zwięźle.** 2–5 zdań na turę, nie ściana tekstu. Wyjątek: kroki 2, 5, 7 gdzie pokazujesz dane — wtedy oczywiście tyle ile trzeba.
- **Nie wyprzedzaj.** Nie pokazuj danych, których user jeszcze nie poprosił. Nie wyciągaj diagnozy, dopóki user sam nie spróbuje.
- **Jeśli user wyjdzie poza skrypt** (zada pytanie spoza scenariusza), odpowiedz krótko, potem łagodnie wróć do kolejnego kroku scenariusza.
- **Dane Slack Integration** czytasz z `demo-slack-integration.md` — to jest źródło dla funnelu, cytatów i kontekstu strategicznego. Dane portfolio z `portfolio.md` i `data-dashboard.md`.
- **Po skończeniu kroku 11** wracasz do reguł `CLAUDE.md` (sekcja „Wejście w konkretny case").

---

## Krok 1 — Powitanie i opowieść o procesie

Wyświetl uczestnikowi:

> Lecimy. Pokażę ci, jak diagnozować adopcję funkcjonalności — proces, który powtarzasz przy każdym ficzerze w swoim portfolio. Pięć kroków:
>
> 1. **Czy mam problem?** — sprawdzasz adopcję (ile userów odkrywa i używa).
> 2. **Rola** — czy ta funkcjonalność w ogóle ma sens biznesowy. Jaki outcome miała ruszyć.
> 3. **Value** — czy ci, którzy używają, dostają wartość.
> 4. **Decyzja** — keep, kill, push (dystrybucja) albo fix (doświadczenie).
> 5. **Hipoteza** — jeśli push lub fix, co konkretnie testujesz.
>
> Przejdziemy przez to razem na konkretnym przykładzie — Slack Integration. Ale najpierw musisz poznać firmę.
>
> Wpisz: **„Czym zajmuje się firma i jakie funkcjonalności ma produkt?"**

Zatrzymaj się i czekaj, aż user wpisze ten (lub bardzo podobny) prompt.

---

## Krok 2 — Wprowadzenie do firmy Shipped

[Trigger: user wpisał prompt z kroku 1]

Odpowiedz zgodnie z regułami w `CLAUDE.md` sekcja „Jak odpowiadać, gdy ktoś pyta o firmę lub funkcjonalności". Czyli: jedno zdanie czym jest Shipped + tabela wszystkich 9 funkcjonalności (pełne zdania, korzyść-not-mechanizm, neutralnie) + krótki kontekst firmy (skala, kogo obsługuje, cel kwartału, twoja rola, strategia).

Na końcu odpowiedzi dodaj:

> ---
>
> OK, znasz firmę. Teraz patrzymy z perspektywy PM-a. Masz 9 funkcjonalności, a twój cel kwartału to **Retain**: utrzymanie userów aktywnych. Zanim spojrzysz w dane: **jak myślisz, jakich danych potrzebujesz, żeby zrozumieć, która z tych 9 funkcjonalności ma problem?** Napisz mi, od czego byś zaczął.

Czekaj na odpowiedź.

---

## Krok 3 — User sam się zastanawia

[Trigger: user odpowiedział na pytanie z kroku 2]

Cel: pozwól userowi pomyśleć samemu. **Nie podawaj odpowiedzi.** Twoja reakcja zależy od tego, co napisał:

- **Trafił** (wspomniał o adoption rate, lejku, weekly active users, retencji, segmentach userów) → **„Dobry trop. Sprawdźmy to."** + przejdź do kroku 4.
- **Pobocznie** (mówi o NPS, supporcie, salesie, feedbacku bez wspomnienia adoption) → **„To też ważne, ale zaczynamy od czegoś prostszego: ilu userów w ogóle dotyka tych funkcjonalności. To pierwsza warstwa diagnozy."** + przejdź do kroku 4.
- **Nie wie** → **„OK, ja prowadzę. Pierwsza warstwa diagnozy to adopcja — ilu userów wie, że feature istnieje, i ilu faktycznie go używa."** + krok 4.

Nigdy nie oceniaj odpowiedzi krytycznie. Krótkie potwierdzenie + ruch dalej.

---

## Krok 4 — Pokazanie danych adopcji

Wyświetl:

> Spójrzmy na to z lotu ptaka. Wpisz: **„pokaż dane adopcji dla wszystkich funkcjonalności"**

Czekaj. Gdy user wpisze (lub coś podobnego), pokaż mu tabelę z `data-dashboard.md` (sekcja „Per feature — high-level scan", cała tabela z lejkiem i sygnałem wartości dla 9 funkcjonalności). Wytłumacz krótko, jak ją czytać (lejek + sygnał wartości — 2 zdania).

Po tabeli zwróć jego uwagę na **Slack Integration**:

> ---
>
> Weźmy na tapet **Slack Integration**. Tutaj jest ciekawe: lejek wygląda zdrowo (88% wie, 78% używa, 71% regularnie), ale sygnał wartości to tylko **+2pp** przy pozostałych +18, +20, +25pp w portfolio. Dużo osób używa, a prawie zero wpływu na retencję. Właśnie ten kontrast jest pierwszym sygnałem, że warto pokopać głębiej.
>
> Wpisz: **„Ilu użytkowników włączyło Slack Integration, a ilu z nich faktycznie ją używa?"**

Czekaj.

---

## Krok 5 — Slack Integration: funnel

[Trigger: user wpisał prompt z kroku 4]

Pokaż funnel ze `demo-slack-integration.md` (sekcja „Funnel" — tabela z 5 krokami od „zobaczył opcję" do „wraca przez Slack regularnie"). Bez dodatkowego komentarza. Sama tabela.

Po tabeli dodaj:

> ---
>
> Powiedz mi: **co tu widzisz problematycznego?** Patrz na liczby, nie na nazwy kroków.

Czekaj na odpowiedź.

---

## Krok 6 — User diagnozuje sam

[Trigger: user odpowiedział]

User powinien zauważyć: **71% dostaje regularnie powiadomienia, ale tylko 28% klika i wraca do produktu.** To dramatyczny spadek na końcu funnelu — sygnał, że powiadomienia docierają, ale nie napędzają akcji.

Reaguj na to, co napisał:

- **Zauważył spadek 71% → 28%** → **„Tak. Patrzysz tam, gdzie trzeba. 71% → 28% to nie jest problem dystrybucji — wszyscy dostają. To pytanie, czy te powiadomienia w ogóle coś robią. Sprawdźmy."** + krok 7.
- **Nie zauważył spadku** → **„Spójrz na ostatnie dwa kroki funnelu: 71% userów dostaje notyfikacje regularnie, ale tylko 28% klika i wraca do Shipped. To dramatyczna różnica — info dochodzi, ale nie napędza akcji."** + krok 7.
- **Diagnoza „discoverability"** → **„Zauważ, że 78% userów już to skonfigurowało. Discoverability nie jest problemem — tu ludzie wiedzą i używają. Pytanie jest gdzie indziej."** + krok 7.

---

## Krok 7 — Strategiczny kontekst + voice of customer

Wyświetl:

> Cofnijmy się o krok. Zanim zdecydujesz, co z tym zrobić, musisz wiedzieć: **po co w ogóle tę funkcjonalność wypuszczono, jakie były założenia, i co o niej mówią użytkownicy.**
>
> Wpisz: **„Jak działa Slack Integration, jakie są założenia strategiczne i co mówią o tym użytkownicy?"**

Czekaj. Gdy user wpisze, pokaż:
- **Kontekst** i założenie zespołu (z `demo-slack-integration.md` sekcja „Kontekst" — co miała ruszyć, co zakładał zespół)
- **Cohort/Outcome** (sekcja „Cohort/Outcome" — retencja Regular userów +2pp vs base 50%)
- **Cytaty userów** (wszystkie 5 z sekcji „Cytaty userów")

Po tym dodaj:

> ---
>
> Założenie zespołu było: **powiadomienia → re-engagement → wyższa retencja.** Wszyscy konfigurują. A retencja Regular userów = 52% vs cały aktywny base 50%. **Sygnał wartości +2pp — czyli prawie zero.**
>
> Cytaty pokazują jeden wzór: Bart, Eva, Mike, Alex, Greg — wszyscy mówią to samo. **„Dostajesz info, ale nie możesz nic z nim zrobić."** Powiadomienia są push-only — w jedną stronę.
>
> Czas na decyzję. **Co robisz z tą funkcjonalnością? Keep, kill, push czy fix?**

Czekaj na odpowiedź.

---

## Krok 8 — User podejmuje decyzję

[Trigger: user odpowiedział z decyzją]

Twoja reakcja zależy od tego, co user wybrał. **Cel: doprowadzić go do FIX**, ale przez argument, nie nakaz. Jeśli user trafia gdzie indziej, pokaż mu czemu to nie pasuje, i daj jeszcze szansę:

- **Keep** → „Hmm. Slack ma sygnał wartości +2pp w portfolio, gdzie inne ficzery dają +18, +20, +25. To znaczy, że feature istnieje, ale praktycznie nie pracuje na cel kwartału. Keep = nie ruszamy. Czy na pewno tego chcesz? **Spróbuj jeszcze raz.**"
- **Kill** → „Możliwe, ale 78% userów to konfiguruje, więc to nie jest funkcjonalność, która nikogo nie obchodzi. Killem stracisz powierzchnię, na którą user zwraca uwagę. I cytaty pokazują, że userzy chcą czegoś więcej, nie mniej. **Spróbuj jeszcze raz.**"
- **Push** → „Push to dystrybucja, pchamy więcej userów do funkcjonalności. Ale tu 78% już używa, lejek dystrybucji nie jest problemem. Czego brakuje? **Spróbuj jeszcze raz.**"
- **Fix** → patrz niżej.

### Po wyborze Fix (od razu albo po naprowadzeniu)

Wyświetl:

> Tak. Dystrybucja jest dobra, ale wartość płaska. Linear pokazuje, że można robić to lepiej, two-way Slack (akceptujesz task prosto z wątku, raport inline w wiadomości). To jest sufit, do którego można pchnąć. Idziemy w fix.
>
> Teraz konkret: **jak byś to naprawił?** Opisz pomysły własnymi słowami, nie szlifuj, po prostu rzuć co ci wpada do głowy.

Zatrzymaj się i **czekaj na pomysły usera**. Nie ruszaj dalej, nawet jeśli user milczy chwilę. Dopiero jak user coś rzuci (albo napisze „nie wiem" / „pokaż twoje"), przechodzisz do kroku 9.

### Jeśli po raz drugi user nie wybiera Fix

Nie szarżuj. Przyjmij jego decyzję, ale zaznacz, że w lekcji idziemy ścieżką Fix: „OK, twoja decyzja. W tej lekcji idziemy dalej ścieżką fix, bo na niej widać najwięcej o budowaniu hipotez. Wrócimy do twojej drogi przy case'ach." Potem wykonaj sekcję „Po wyborze Fix" powyżej.

---

## Krok 9 — Twoje hipotezy

[Trigger: user opisał własne pomysły, albo powiedział „nie wiem" / „pokaż twoje"]

**Najpierw zareaguj na to, co user powiedział** (1–2 zdania, zauważ, co dobre, nie krytykuj). Jeśli user nic konkretnego nie podał, zacznij od „OK, idziemy z naszymi pomysłami."

Potem wyświetl nasze hipotezy:

> ---
>
> Dorzucam nasze. Wszystkie idą w jednym kierunku: **z push-only zrób two-way.** Powiadomienie ma być akcją, nie tablicą ogłoszeń.
>
> 1. **Akcje prosto ze Slacka:** przyciski „Zajmę się", „Przypisz do" pod każdym alertem. User decyduje bez wchodzenia do UI.
> 2. **Raport inline w wątku:** gdy raport po wypuszczeniu funkcjonalności jest gotowy, wstaw kluczowe metryki bezpośrednio w wiadomości Slacka, nie tylko link „kliknij, żeby zobaczyć".
> 3. **Slash commands:** `/shipped outcome <nazwa>` żeby zapytać o status outcome bez wychodzenia z kanału.
>
> **Aggressive test** (eksperyment celowo skrajny, żeby szybko pokazać sufit, czyli jak wysoko można podbić metrykę, gdy idziemy całą siłą): two-way Slack dla 30% teamów przez 30 dni. Mierzymy retencję Regular userów Slack Integration, czy z +2pp wystrzeli powyżej +10pp.

Po tym dodaj:

> ---
>
> **Od której hipotezy zacząłbyś?** Powiedz, którą wybierasz i dlaczego.

Czekaj.

---

## Krok 10 — User wybiera, od czego zaczyna

[Trigger: user wybrał hipotezę]

Krótko (2–3 zdania) zareaguj na jego wybór. Pochwal logikę, jeśli jest. Zaznacz tradeoff, jeśli warto. **Nie wyciągaj „tej jedynej słusznej" odpowiedzi**, wszystkie 3 hipotezy są obronialne, każda inny tradeoff (akcje = największa zmiana UX, raport inline = najszybciej, slash commands = najwęższe użycie, ale dla power-userów).

Potem przejdź do kroku 11.

---

## Krok 11 — Koniec intro, przejście do case'ów

Wyświetl:

> ---
>
> To koniec wprowadzenia. Mamy za sobą cały flow: **adopcja → rola → wartość → decyzja → hipoteza.** Pamiętaj — to powtarzasz dla każdego ficzera w swoim portfolio. Teraz pora zrobić to samemu.
>
> Mam dla ciebie 3 case'y. Każdy bierze inną funkcjonalność Shipped i każdy ma inny problem niż Slack:
>
> - **Case A — Task-to-Event Linking** — funkcjonalność, w której przy spec'u taska user linkuje konkretne zdarzenie analityczne (z PostHog/Mixpanel/Amplitude) które ten task ma ruszyć.
> - **Case B — Outcome Roadmap** — widok roadmapy zorganizowany po celach (outcome'ach), nie po featurach.
> - **Case C — MCP Server** — interfejs (MCP — Model Context Protocol), przez który Claude/Cursor i inne agenty AI mogą czytać i pisać dane Shipped bez otwierania UI.
>
> **Napisz „start case A", „start case B" albo „start case C", żeby wejść w jeden z nich.**

Czekaj. Gdy user wybierze case → wejdź w niego zgodnie z regułami w `CLAUDE.md` sekcja **„Wejście w konkretny case"**. To koniec intro module — od tego momentu kierujesz się standardowymi regułami operacyjnymi.

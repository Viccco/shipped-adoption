# CLAUDE.md — instrukcje dla Claude w tym repo

To repo to materiały do warsztatu o adopcji funkcjonalności. Zawiera fikcyjną firmę **Shipped**, na której uczestnicy ćwiczą diagnozę adopcji. Pełny przewodnik dla człowieka: `README.md`. Plan warsztatu: `../Adoption.md`.

## Czym jest Shipped (mów zawsze tak)

Shipped to **narzędzie do zarządzania produktem i projektami — jak Linear czy Jira** — które dodatkowo, po każdym wypuszczeniu funkcjonalności, sprawdza, czy faktycznie zmieniła metrykę, którą miała zmienić. Źródło prawdy: `company.md`.

**Nigdy** nie opisuj Shipped jako "warstwy walidacji", "post-deploy validation layer", "eval-setów" ani żadnego żargonu inżynierskiego. To narzędzie PM, nie narzędzie DevOps/QA.

## Jak odpowiadać, gdy ktoś pyta o firmę lub funkcjonalności

Te konwencje obowiązują, nawet jeśli prompt jest krótki (np. "co robi firma i jakie ma funkcjonalności"):

1. **Zacznij od jednego zdania, czym Shipped JEST** (narzędzie PM jak Linear/Jira + ta jedna różnica). Zrozumiałego dla kogoś, kto nigdy nie widział produktu.
2. **Funkcjonalności podawaj ZAWSZE w tabeli**, nie w bulletach. Wymień **wszystkie 9** z `portfolio.md` — nigdy nie skracaj listy.
3. **Opisuj KORZYŚĆ dla użytkownika — co dzięki funkcjonalności zyskuje — nie techniczny mechanizm.** Nie pisz "anomaly detection", "auto-dobór cohortów", "pisze raporty" jako osobnych ficzerów. To są bebechy. Pisz, co user z tego ma (np. zamiast "anomaly detection" → "dowiesz się, że coś się psuje, zanim będzie za późno").
4. **Pełnymi zdaniami, prostym językiem, bez żargonu i jednowyrazowych skrótów.**
5. **Nie oceniaj funkcjonalności** (która działa, która jest słaba) przy opisie firmy. To, że któraś ma problem z adopcją, jest ćwiczeniem dla uczestników w Block 2/3 — nie zdradzaj tego z góry. Slack Integration opisuj neutralnie (powiadomienia do Slacka), bez wspominania, że jest push-only/płytka.
6. **Zakończ skalą firmy w kilku bulletach** (z `company.md`), np.:
   - 35 000 zarejestrowanych użytkowników, 8,2k MAU, ~4,2k WAU
   - ~5 170 paying users, $1,8M ARR
   - Net retention 62%, activation 50%
   - Etap: Series A, model PLG + sales-assist na enterprise

## Model metryk (jak liczyć — obowiązuje wszędzie)

**Segmenty userów** (jedno nazewnictwo wszędzie — nie wymyślaj synonimów): per funkcjonalność dzielimy userów na **Non-user** (nigdy nie użył), **Casual user** (użył, nie regularnie), **Regular user** (używa regularnie). Konkret per funkcjonalność podawaj w nawiasie, np. "Regular user (linkuje event intensywnie)".

Per funkcjonalność **dwie rzeczy**, nic więcej:

1. **Lejek adopcji** — zna % → użył % → intensywnie % (Regular user). Pokazuje, gdzie userzy odpadają (np. tknął raz i nie wraca — materiał do dyskusji).
2. **Sygnał wartości** — retencja **Regular userów** vs retencja **całego aktywnego user base** (50%). Różnica = **sygnał** (korelacja), nie dowód impactu. Dowód dałby dopiero aggressive test.

**Zakazane** (konceptualnie słabe): "Power user WAR", porównania do arbitralnego "baseline", podawanie korelacji jako impactu, mnożenie metryk (Exposed/Adoption/Power users jako osobne kolumny — to jeden lejek). Zawsze "vs cały aktywny base", zawsze nazywaj różnicę sygnałem.

## Flow, którego uczy warsztat

```
1. Czy mam problem?  — ile userów odkrywa i używa (adopcja)   [DISCOVERABILITY]
2. Rola              — czy warto? Jeśli nie → następny feature. + jaki outcome
3. Value             — czy używający osiągają to, co chcieliśmy
4. Decyzja           — keep / kill / push / fix
5. Hipoteza          — (jeśli push lub fix)
```

## Pliki

`company.md` (firma), `portfolio.md` (9 funkcjonalności), `data-dashboard.md` (metryki snapshot + data slices), `adoption-retention.md` (adoption rate over time + retencja per segment — **dla wszystkich 9 funkcjonalności**), `demo-slack-integration.md` (demo Block 2), `case-a/b/c` (Block 3), `prompts.md` (prompty na żywo). Szczegóły w `README.md`.

Gdy ktoś pyta o **retencję lub adopcję dowolnej funkcjonalności** (także spoza case'ów), dane są w `adoption-retention.md` — nie mów, że "tylko 4 mają dane". Case'y A/B/C i demo Slack mają dodatkowo pełny funnel + cytaty.

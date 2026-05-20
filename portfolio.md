# Shipped — portfolio funkcjonalności

| Funkcjonalność | Co robi |
|---|---|
| **Goals & Outcomes** | Definiujesz cele firmy. Goal = nazwa + konkretna metryka z twojego narzędzia analitycznego + target + termin. Np. "Weekly active teams do 1000, koniec Q1." Każdy goal ma widok z aktualną wartością metryki, historią zmian, i listą tasków/projektów które są pod ten cel zaplanowane. |
| **Post-Ship Impact Detector** | Kiedy taski przypisane do goala oznaczasz jako wypuszczone, Shipped przez 14 dni zbiera dane: kto użył tej funkcjonalności, jak się zachowywał, jak zmieniła się metryka tego goala u nich vs u userów którzy z tej funkcjonalności nie korzystali. Po 14 dniach masz w mailu raport: "ta zmiana ruszyła metryę o X% w grupie która jej używała vs grupa kontrolna." |
| **Outcome Roadmap** | Widok roadmapy zorganizowany po celach, nie po funkcjonalnościach. Dla każdego celu widzisz: ile pracy jest pod niego zaplanowane, kiedy konkretne rzeczy trafiają na produkcję, ile zespół daje sobie pewności że ta praca faktycznie ruszy metryę. |
| **Task-to-Event Linking** | Kiedy spec'ujesz task, wybierasz konkretne zdarzenie z PostHogu/Mixpanela/Amplitude które ten task ma ruszyć. Np. task "Dodaj video w onboardingu" linkujesz do zdarzenia "user_completed_onboarding." Później Shipped używa tego linku żeby wiedzieć którą metryę obserwować po wypuszczeniu tej konkretnej zmiany. |
| **AI Daily Brief** | Rano dostajesz wiadomość (mail albo Slack) z podsumowaniem: gdzie outcome'y idą zgodnie z planem, gdzie coś poszło źle, jakie taski warto teraz spriorytetyzować bo dane sugerują że poruszają najwięcej. Generowane przez AI z twoich danych. |
| **MCP Server** | Shipped wystawia interfejs przez który Claude, Cursor i inne asystenty AI mogą czytać i pisać dane bez otwierania UI Shipped. User pisze w Claude "co się dzieje z naszym goal weekly active teams?" i Claude pobiera odpowiedź ze Shipped. Może też tworzyć taski, czytać raporty, sprawdzać status goali. |
| **Analytics Integrations** | Wbudowane połączenia z popularnymi narzędziami: PostHog, Mixpanel, Amplitude, Heap, Segment. Shipped czyta z nich zdarzenia i metryki, używa do liczenia goal-progress i Impact Detectora. Idzie też w drugą stronę: grupa userów których dotyczy task w Shipped może powstać jako cohort w PostHogu. |
| **Data Warehouse Integration** | Łączysz Shipped bezpośrednio z hurtownią danych firmy (Snowflake, BigQuery, Redshift, Databricks). Wskazujesz które tabele zawierają zdarzenia, których userów, jakie wymiary biznesowe. Cała reszta funkcjonalności (Goals, Impact Detector) działa tak samo, tylko że na twoich własnych danych. |
| **Slack Integration** | Jednostronne (push-only) powiadomienia do Slacka, kiedy coś się dzieje z twoimi celami: raport po wypuszczeniu jest gotowy, metryka spadła poniżej progu, ktoś przypisał nowy task pod twój cel. Każdy goal można kierować do innego kanału. Nie da się działać z poziomu Slacka — tylko czytać powiadomienia (brak two-way: nie zaakceptujesz taska, nie otworzysz raportu inline). |

## Podstawowe rzeczy w produkcie

Funkcjonalności wymagane do konkurowania z Linearem / Asaną / Jirą, ale nie będące wyróżnikiem Shipped:

- Tasks, Projects, Cycles
- Komentarze, mentions
- Powiadomienia in-app i mailowe
- Wyszukiwarka
- Szablony
- API + Webhooks

# Shipped — dane adopcji i retencji (szczegółowe)

Dwa zestawy danych pod charty: adoption rate over time (trend tygodniowy) i retencja per segment (dla każdej funkcjonalności). Spójne z `data-dashboard.md` — power-user endpoint w tabeli retencji = Power user WAR z dashboardu.

## 1. Adoption rate over time (WAU % per funkcjonalność)

WAU % = jaki % MAU był aktywny w danej funkcjonalności w danym tygodniu. Ostatnie 5 tygodni (świeży snapshot). Pod wykres liniowy w stylu PostHog ("Adoption rates").

| Funkcjonalność | Apr 20 | Apr 27 | May 4 | May 11 | May 18 |
| --- | --- | --- | --- | --- | --- |
| Goals & Outcomes | 61 | 62 | 63 | 63 | 64 |
| Post-Ship Impact Detector | 52 | 53 | 54 | 54 | 55 |
| Slack Integration | 51 | 51 | 50 | 50 | 50 |
| Analytics Integrations | 46 | 46 | 47 | 47 | 47 |
| Outcome Roadmap | 13 | 14 | 14 | 15 | 15 |
| Task-to-Event Linking | 11 | 11 | 12 | 12 | 12 |
| Data Warehouse Integration | 8 | 9 | 10 | 11 | 11 |
| AI Daily Brief | 5 | 5 | 6 | 6 | 6 |
| MCP Server (UI) | 2 | 3 | 3 | 4 | 4 |

**Co widać:** core (Goals, Post-Ship) dojrzały i płaski na wysoko. Długi ogon (Task-to-Event, AI Daily Brief, Outcome Roadmap) **stagnuje na nisko mimo potencjału** — to wizualny dowód tezy warsztatu: shippujemy, adopcja nie nadąża. Dwa nowe (Data Warehouse, MCP) rosną z niskiej bazy. Slack płaski/lekko w dół.

## 2. Retencja per segment (weekly active rate)

Dla każdej funkcjonalności: weekly active rate (w całym Shipped) trzech segmentów — kto jej nie używa, kto używa średnio, kto regularnie (power user). Baseline = 50%. Power-user endpoint zgadza się z Power user WAR z dashboardu. Pod wykres retention-by-segment (bar lub curve).

Punkt odniesienia: **cały aktywny user base = 50%**. Sygnał wartości = retencja intensywnych userów − 50%.

| Funkcjonalność | Non-user | Casual user | Regular user | Change (Regular vs base 50%) |
| --- | --- | --- | --- | --- |
| Goals & Outcomes | 50 | 58 | 67 | +17 |
| Post-Ship Impact Detector | 49 | 60 | 70 | +20 |
| Outcome Roadmap | 45 | 52 | 70 | +20 |
| Task-to-Event Linking | 47 | 56 | 68 | +18 |
| AI Daily Brief | 49 | 62 | 75 | +25 |
| Analytics Integrations | 48 | 53 | 58 | +8 |
| Data Warehouse Integration | 49 | 55 | 63 | +13 |
| Slack Integration | 50 | 50 | 52 | +2 |
| MCP Server (UI-based) | 50 | 47 | 31 | −19 |

**Czytanie:** mocny sygnał (AI Daily Brief +25, Outcome Roadmap +20) = intensywni userzy zostają dużo bardziej niż base, ale w wąskiej grupie. Płasko (Slack +2) = funkcjonalność nie napędza retencji. Ujemnie (MCP −19) = paradoks: intensywni userzy MCP żyją w Claude, nie w UI — spadek w UI to dowód, że mierzymy nie tam, gdzie trzeba. **Wszystko to sygnał (korelacja), nie dowód impactu** — intensywni userzy mogli być inni od początku.

## Uwaga dla generowania chartów

- **Adoption-over-time** → wykres liniowy, 9 linii, oś X = tygodnie, oś Y = WAU %. Wyróżnić długi ogon (stagnacja).
- **Retention-by-segment** → dla wybranej funkcjonalności bar chart (3 słupki) albo cała tabela jako small-multiples. Linia baseline 50%.
- Liczby celowo proste (nie sumują się co do 0,1pp) — to materiał dydaktyczny, nie audyt.

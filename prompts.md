# Prompty do Claude (Block 2 i 3)

Gotowe prompty do użycia na żywo. Działają dla dowolnej funkcjonalności Shipped — wklejasz kontekst z `portfolio.md` / dashboardu / case'a i odpalasz. Każdy ma backup: jeśli internet siada, masz już wygenerowane odpowiedzi w deep-dive'ach (cytaty, hipotezy).

---

## Prompt 1 — Feedback klientów (voice of customer)

Używany w Block 2 (Slack Integration) i Block 3 (case'y A/B/C), w momencie "wiemy gdzie jest problem, potrzebujemy danych jakościowych."

```
Jesteś analitykiem product research w SaaS-ie "Shipped" — narzędziu do
zarządzania produktem i projektami (jak Linear czy Jira), które po każdym
wypuszczeniu funkcjonalności sprawdza, czy faktycznie zmieniła metrykę,
którą miała zmienić.

Oto funkcjonalność i jej dane adopcji:

[WKLEJ: nazwa + opis funkcjonalności z portfolio]
[WKLEJ: dane z dashboardu — lejek adopcji (zna → użył → intensywnie) + retencja Regular userów vs base 50%]
[WKLEJ: jeśli jest — funnel + cohort]

Wygeneruj 5 realistycznych cytatów od użytkowników na temat tej
funkcjonalności. Wymagania:
- Mix segmentów (różne plany: Pro/Enterprise/Free; różne role: PM, Engineer,
  Founder; różny staż).
- Mix sentymentu: 1–2 entuzjastów, 2–3 krytyków/obojętnych, 1 który nie wie
  że funkcjonalność istnieje (jeśli pasuje do danych).
- Każdy cytat ma ujawniać COŚ diagnostycznego: czy problem to discoverability
  (nie odkrywa / nie rozumie) czy value (używa, ale nie wnosi wartości).
- Pisz naturalnym, mówionym językiem — jak realny user, nie marketing.
- Format: imię, rola, firma (fikcyjna), plan, staż — potem cytat.

Po cytatach: 2 zdania, jaki obraz problemu się z nich wyłania.
```

**Backup (jeśli net siada):** cytaty są już w `demo-slack-integration.md` (Block 2) i w `case-a/b/c` (Block 3).

---

## Prompt 2 — Hipotezy poprawy

Używany w Block 2 (krok 5, gdy sala da mało pomysłów) i Block 3 (gdy pary budują hipotezy). AI dopełnia / challenge'uje to, co wymyślili ludzie.

```
Jesteś senior growth PM-em w SaaS-ie "Shipped" (narzędzie do zarządzania produktem i projektami jak Linear/Jira, które sprawdza, czy wypuszczone funkcjonalności zmieniają metryki).

Diagnoza funkcjonalności:
[WKLEJ: nazwa + opis]
[WKLEJ: dane — funnel, cohort, kluczowe cytaty]
[WKLEJ: postawiona diagnoza — discoverability czy value, i dlaczego]

Wygeneruj 3 hipotezy poprawy. Każda hipoteza MUSI mieć:
- **Ruch**: co konkretnie robimy (jedno zdanie, na tyle precyzyjne, że da się
  to wdrożyć w 1–2 tygodnie).
- **Data-backed perspektywa**: które konkretne dane z diagnozy uzasadniają
  ten ruch.
- **Strategiczna perspektywa**: dlaczego warto to zrobić teraz (związek z
  cycle outcome = Retain / weekly active users, albo z pozycją vs konkurencja).
- **Aggressive test**: najmocniejsza, najbardziej skrajna wersja tego ruchu,
  którą można odpalić, żeby szybko potwierdzić sufit (Airbnb-popup style).

Uszereguj od najbardziej do najmniej obiecującej. Bądź konkretny, bez ogólników
typu "popraw UX" czy "lepsza komunikacja".
```

**Backup:** hipotezy są w sekcji "Tło / why" każdego case'a (A/B/C) i w `demo-slack-integration.md`.

---

## Jak to gra w sali

- **Block 2:** Wiktor odpala Prompt 1 na żywo na Slack Integration ("zobaczcie, jak w 30 sekund wyciągam głos klienta"). Potem Prompt 2, porównuje z pomysłami sali.
- **Block 3:** pary mogą użyć obu promptów na swoim case'ie — ale dopiero PO tym, jak same postawią diagnozę i pierwsze hipotezy. AI dopełnia, nie zastępuje myślenia. To jest lekcja: AI to surowy materiał, craft (ocena czy hipoteza trzyma się danych i strategii) jest człowieka.

---

## Prompty na żywo — sekwencja Block 2

Odpalane po kolei w sesji Claude otwartej w tym repo (Claude ma kontekst z README + plików). Każdy wywołuje konkretny moment lekcji.

### 1. Wprowadzenie firmy (start Block 2)

```
Opisz, co robi firma Shipped i wyjaśnij każdą jej funkcjonalność tak, żeby
zrozumiała osoba, która nigdy nie widziała produktu. Każdą funkcjonalność
opisz pełnym zdaniem, prostym językiem — bez żargonu, bez jednowyrazowych
skrótów. Nie oceniaj funkcjonalności (co działa, co nie) — tylko wyjaśnij,
co robią.
```

**Czyta:** `company.md` (pozycjonowanie) + `portfolio.md` (9 funkcjonalności).
**Wywołuje:** zrozumiały dla wszystkich opis Shipped + pełne (nie skrótowe) opisy funkcjonalności.
**Dlaczego "pełnym zdaniem, bez skrótów":** bez tego Claude robi tabelę jednolinijkowych haseł, jasnych tylko dla kogoś, kto już zna produkt.
**Dlaczego "nie oceniaj":** żeby nie zdradził, która funkcjonalność jest słaba (np. Slack) — to ma wyjść dopiero w diagnozie, nie przy wprowadzeniu firmy.

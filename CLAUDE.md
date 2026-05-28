# CLAUDE.md — language gate (read first, every session)

This is the **welcome + language gate** for the Shipped feature-adoption workshop. To repo to materiały do warsztatu o adopcji funkcjonalności firmy Shipped.

Detailed operating instructions live in `pl/CLAUDE.md` (Polish session) and `en/CLAUDE.md` (English session). **You only load one of those — after the participant has picked a language.**

---

## Hard rule — first user turn in every new session

On the **very first user message** of any session, regardless of its content (even if it looks like a concrete question such as "show case A data" or "co robi Shipped?"), you **MUST NOT** answer the question yet. Instead, display the bilingual welcome below and wait for a language choice.

This is non-negotiable. It guarantees that every participant — including someone who cloned the repo and has no idea what it is — gets the same automatic, oriented entry into the workshop.

### Exceptions (skip the welcome, jump straight to intro)

- The first message is a **clear language pick**: `PL`, `pl`, `polski`, `po polsku`, `EN`, `en`, `english`, `po angielsku`, `🇵🇱`, `🇬🇧`, `🇺🇸`. Accept it, skip the welcome, show the intro in the chosen language.

### What about a non-language opener (e.g. "cześć", "hi", "start case A", "what does Shipped do?")

Still show the bilingual welcome. **Do not** infer language from the opener — the participant must consciously pick. The welcome itself is bilingual (both PL and EN side by side), so neither language is at a disadvantage.

### After they pick a language

1. Show the intro text for that language (verbatim block below).
2. From that point on, **load and follow the operating rules from `pl/CLAUDE.md` or `en/CLAUDE.md`** — you must `Read` that file once at this point so its rules are in your context for the rest of the session.
3. Operate in the chosen language for the rest of the session (responses, file lookups all from `pl/` or `en/`).

### Mid-session language switch

If the participant later asks to switch ("teraz po angielsku" / "switch to Polish"), confirm in one short line and switch. **Do not** repeat the full intro — they're already oriented. Load the other language's `CLAUDE.md` for the rest of the session.

---

## Welcome message (display verbatim, bilingual — English block first, then Polish)

When the first-turn rule fires, output exactly this text — no preamble, no extras:

```
Hi 👋

This is a workshop repo on feature adoption (fictional company "Shipped").

Which language do you want to use?
  • EN — English
  • PL — polski

Type "EN" or "PL" to begin.

Hi, I'm Wiktor, the author of this workshop. I'd love to hear what you think of it. If you have questions or feedback, write to me: www.linkedin.com/in/wiktorsobolak

---

Cześć 👋

To repo do warsztatu o adopcji funkcjonalności (fikcyjna firma Shipped).

W jakim języku chcesz pracować?
  • EN — English
  • PL — polski

Napisz „EN" lub „PL", żeby zacząć.

Cześć, jestem Wiktor, autor tego warsztatu. Chętnie dowiem się, co o nim myślisz. Jeśli masz pytania lub feedback, napisz do mnie: www.linkedin.com/in/wiktorsobolak
```

After printing this, stop and wait. Do not preempt with extra text.

---

## Intro after `EN` is chosen (display verbatim)

```
Great — we'll work in English.

Quick context: this is a workshop on feature adoption. You'll play the role of a Senior PM at a fictional SaaS called Shipped, and your job is to diagnose where the product has an adoption problem and what to do about it.

You've got two paths:
  • **Intro mode** — I'll walk you through the full adoption-diagnosis flow step by step, using one specific feature (Slack Integration) as the worked example. Recommended if it's your first time. → type: "intro"
  • **Case mode** — jump straight to diagnosing your own case. I'll give you a quick company overview and the 3 available cases, then you pick which one to work on. → type: "case"

Which one?
```

After printing this, immediately read `en/CLAUDE.md` so its operating rules are loaded. Then wait for the participant's choice (`intro` or `case`).

---

## Intro after `PL` is chosen (display verbatim)

```
Świetnie — lecimy po polsku.

Krótko, o co chodzi: to warsztat o adopcji funkcjonalności. Wcielasz się w Senior PM-a fikcyjnej firmy Shipped, a twoim zadaniem jest zdiagnozować, gdzie produkt ma problem z adopcją i co z tym zrobić.

Masz dwie ścieżki:
  • **Intro mode** — przeprowadzę cię krok po kroku przez cały flow diagnozy, na przykładzie jednej funkcjonalności (Slack Integration). Polecane, jeśli pierwszy raz to robisz. → napisz: „intro"
  • **Case mode** — przeskakujesz od razu do diagnozy własnego case'a. Pokażę ci szybko firmę i 3 dostępne case'y, ty wybierasz, na którym pracujesz. → napisz: „case"

Co wybierasz?
```

After printing this, immediately read `pl/CLAUDE.md` so its operating rules are loaded. Then wait for the participant's choice (`intro` lub `case`).

---

## What goes in `<lang>/CLAUDE.md` (not here)

Everything else — how to introduce the company, how to enter a specific case, the metrics model, the workshop flow, the "never reveal Background/why" rule, the jargon-glossary rule — lives in the language-specific CLAUDE.md. Keep this root file focused on **welcoming and routing**. Do not duplicate operating rules here.

# AgencyHires — Challenge 1: Build a Funnel for Volley

A funnel strategy response for **Volley**, a $99/month AI + human language-coaching app
([getvolley.ai](https://getvolley.ai)).

> *"Pretend I just handed you the account. What would you change, and how would you prove it works?"*

## Deliverables

| # | Deliverable | Location |
|---|-------------|----------|
| 1 | **Landing page variant** — actual coded build | [`landing-page-variant/index.html`](landing-page-variant/index.html) |
| 2 | **3 Meta ad angles** + creative direction | In the deck → Section 02 |
| 3 | **1-page testing plan** | In the deck → Section 03 |
| — | **Presentation deck** (prints to PDF) | [`deck/index.html`](deck/index.html) |

## The strategic call

The current page (`getvolley.ai/lp3`) has a strong premium aesthetic, good "show-don't-tell"
mockups, and objection-handling FAQ — all worth preserving. But it has **two high-leverage gaps**:

1. **Price is invisible.** At 7× Duolingo's price, `$99/mo` appears nowhere on the page — visitors
   complete a 2-minute placement test before seeing any cost. Likely drives funnel drop-off *and*
   early cancellation.
2. **The sharpest hook is buried.** "App dropout survivors" (people who tried apps and quit) is
   Volley's strongest wedge, but it sits two-thirds down the page while the hero opens with a
   generic outcome statement.

The variant tests **one focused lever** — pain-first entry framing + price transparency — rather
than rebuilding the page.

## Landing page variant — features

- **Asymmetric editorial hero** with a floating, rotated in-app phone mockup
- **Interactive "Sound familiar?" checklist** — visitors self-diagnose their app-dropout pattern
- **Price-anchor microcopy** near every CTA (`Private tutors: $200+/mo · Volley: $99/mo`)
- **Animated "weekly loop" diagram** — the core product mechanic cycles continuously
- **Monospace data-typography** reinforcing "this product tracks your progress"
- **Message-match via `?ang=` URL param** — hero copy mirrors the ad angle that earned the click:
  - [`?ang=dropout`](landing-page-variant/index.html?ang=dropout) — App Dropout Survivors
  - [`?ang=pro`](landing-page-variant/index.html?ang=pro) — Busy Professional / 15 Minutes
  - [`?ang=compare`](landing-page-variant/index.html?ang=compare) — Not Another App

## Running it

Both are static HTML — just open in a browser:

```
landing-page-variant/index.html   # the LP variant
deck/index.html                   # the strategy deck (File → Print → Save as PDF)
```

## Stack

Plain HTML + CSS + vanilla JS. No build step, no dependencies. Fonts: Fraunces (display serif),
Inter (body), JetBrains Mono (data). Palette mirrors Volley's brand (cream / navy / coral).

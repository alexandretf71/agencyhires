# AgencyHires — CLAUDE.md

## Project purpose
Response to **AgencyHires Challenge 1**: "Build a Funnel for Volley."  
Volley is a $99/month AI + human language-coaching app (getvolley.ai).  
The brief asks for: a landing page variant, 3 Meta ad angles, and a 1-page testing plan.  
Author: **Alexandre Toda Faitarone** — https://www.linkedin.com/in/alexandre-toda-faitarone-0992871/

---

## File structure

```
AgencyHires/
├── index.html                        # Portal homepage — links to LP variant + deck
├── landing-page-variant/
│   ├── index.html                    # Deliverable 1: coded LP variant
│   └── styles.css                    # All styles for the LP variant
├── deck/
│   └── index.html                    # Deliverable 2+3: strategy deck (ad angles + test plan)
├── render.yaml                       # Render.com static site config
├── .gitignore
└── README.md
```

---

## Hosting & deployment

- **GitHub repo**: https://github.com/alexandretf71/agencyhires
- **Deployed on**: Render.com (free Static Site tier)
- **Deploy trigger**: every `git push` to `main` auto-deploys via Render's GitHub integration
- **Render config** (`render.yaml`): type=static, publish dir=`.`, no build command

---

## Tech stack

Pure static HTML + CSS + vanilla JS. No framework, no build step, no dependencies.

| Asset | Detail |
|-------|--------|
| Fonts | Fraunces (serif display), Inter (body), JetBrains Mono (data labels) — Google Fonts CDN |
| Palette | Cream `#F4F0E6` · Navy `#151622` · Coral `#E8623D` · Teal `#2D6E6A` |
| Breakpoint | Single-column grid at `max-width: 720px` |

---

## Landing page variant — key features

- **Pain-first hero**: leads with "You've downloaded the apps. You still can't order a coffee in French." (vs. the original generic outcome headline)
- **Message-match via `?ang=` URL param** (vanilla JS, cross-fade transition):
  - `?ang=dropout` → App Dropout Survivors angle
  - `?ang=pro` → Busy Professional / 15-min angle
  - `?ang=compare` → Not Another App / tutor differentiation angle
- **Interactive "Sound familiar?" checklist**: 4 self-recognition statements, dynamic response copy
- **Price-anchor microcopy** near every CTA: "Private tutors $200+/mo · Volley: $99/mo · cancel anytime"
- **Animated weekly-loop diagram**: 3 steps cycle through an active state via `setInterval` JS
- **JetBrains Mono** used for all data-flavored labels (retention %, streaks, session counts)
- **Asymmetric editorial hero**: oversized serif headline + floating rotated phone mockup (CSS)

---

## Deck — structure

| Section | Content |
|---------|---------|
| Cover | Brief summary + strategic diagnosis |
| 01 — LP Variant | Page audit (keep vs. fix), hypothesis, 4 concrete changes, design rationale, browser mockup |
| 02 — Ad Angles | 2026 Meta framing (Advantage+, creative velocity), 3 angles with full copy + creative direction + `?ang=` param mapping |
| 03 — Testing Plan | Sequencing logic, metrics by phase (CAPI + incrementality), kill criteria in priority order |
| Closing | Summary chips + author signature |

The deck is **print-to-PDF ready** — open in browser → File → Print → Save as PDF.

---

## Strategic rationale (key decisions)

1. **One lever, not a full rebuild** — variant targets the two highest-leverage gaps on lp3: hidden price and buried hook. This is the instinct to demonstrate (don't change five things and learn nothing).
2. **Ad angles = creative buckets, not 3 final ads** — each angle should spawn 4–6 hook variants fed into broad Advantage+ campaigns; the algorithm finds audiences, we find what message resonates.
3. **Measurement layer** — plan includes Conversions API (server-side) + holdout/incrementality test because Meta's in-platform attribution is unreliable post-tracking deprecation.
4. **Kill criteria order** — creative first (cheapest), then LP framing, then funnel mechanics, price/packaging last. The order reflects cost-to-change, not importance.

---

## Known issues fixed

- **Nested `<a>` in `<a>` bug**: portal Card 1 was originally an `<a>` containing `<a>` links (invalid HTML). Browser DOM repair broke the CSS grid for cards 2 and 3 (appeared blank). Fixed by converting Card 1 to `<div onclick>`.
- **Transparent card backgrounds**: `rgba(255,255,255,0.04)` rendered as invisible in some deployed environments. Fixed with opaque colors (`#1c1f35`, `#1a3533`).

---

## Git identity (local override)

This repo has a local git identity set to avoid the machine's global `RAG-SaaS Team` identity:
```
git config user.name "alexandretf71"
git config user.email "alexandretf@hotmail.com"
```

---

## How to run locally

```bash
# Option 1 — any static server
npx serve .

# Option 2 — Python
python -m http.server 8080

# Then open http://localhost:8080
```

Preview tool is configured in `.claude/launch.json` (uses `npx serve` on port 4321).

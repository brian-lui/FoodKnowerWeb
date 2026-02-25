# FoodKnowerWeb — Website Brief

Use this file as the `CLAUDE.md` for the FoodKnowerWeb project.

---

## What is FoodKnower?

An Android app that identifies food from photos and scores it on two axes:

1. **Food Integrity** (0–100) — How far the food has been industrially processed. Based on NOVA classification, additive burden, industrial markers, and engineered subsystem stacking.
2. **Portion Control / Overeating Risk** (0–100) — How engineered the food is to override your satiety signals. Based on Fazzino et al. (2019) hyperpalatable nutrient clusters and ingredient-level formulation analysis.

Users photograph any food — packaged, restaurant, or home-cooked — and get both scores plus a full nutrition breakdown.

### Key Features

- AI-powered food photo identification (Claude API by Anthropic)
- Matches packaged foods against the Open Food Facts database (~85 MB bundled, works offline)
- Full nutrition breakdown per 100g (energy, fat, protein, carbs, sugars, sodium)
- Scan history (up to 100 entries with thumbnails)
- Offline queued scans — pending entries saved with photo, retried on tap
- "Wrong food?" manual correction via product search
- Shareable score card image
- Basic (fast) and Premium (most accurate) analysis modes
- Google Sign-In authentication

---

## Website Purpose

A simple, fast, static single-page landing site with a separate privacy policy page.

### Pages

1. **Landing page** — app pitch, screenshots, feature highlights, Play Store link, contact info
2. **Privacy policy** — full privacy policy (see data details below)
3. **Terms of service** — [TBC]

---

## Brand Colors

### Primary Palette

| Role               | Hex       |
| ------------------- | --------- |
| Primary (green)     | `#388E3C` |
| Primary light       | `#C8E6C9` |
| Secondary (orange)  | `#FF9800` |
| Background          | `#F9FAF5` |
| Surface             | `#FFFFFF` |
| Text                | `#1A1A1A` |

### Score Colors (for any score visualizations)

| Meaning  | Hex       | Threshold        |
| -------- | --------- | ----------------- |
| Healthy  | `#4CAF50` | Score >= 66       |
| Warning  | `#FF9800` | Score 36–65       |
| Danger   | `#F44336` | Score <= 35       |

---

## Landing Page Copy

### Pitch (from in-app onboarding)

**Hook:** "Fast, healthy weight loss without hunger. No energy crash after meals. No cravings. Better sleep."

**Problem:** "By identifying the silent killers of your healthy eating plan. Foods that look 'healthy', but are secretly keeping you hungry. Ultra-processed, industrial junk food. Food that's engineered to make you eat more and more."

**Solution:** "FoodKnower helps. Point your phone at the food, take a picture. We'll tell you exactly how good it is for you."

**CTA:** "Take back control."

### Score Labels (for feature explanation)

**Food Integrity:**
- &gt;= 75: "Minimally processed"
- 50–74: "Lightly processed"
- 25–49: "Heavily processed"
- &lt; 25: "Ultra-processed"

**Overeating Risk:**
- &gt;= 65: "High risk"
- 35–64: "Moderate risk"
- &lt; 35: "Low risk"

---

## Scoring Explanation (for a "How it works" section)

### Food Integrity Score

Based on the NOVA food classification system (Monteiro et al.), extended with:
- **Additive burden** — classifies E-number additives (emulsifiers, sweeteners, flavour enhancers, colours, preservatives, etc.) and scores by count and type
- **Industrial markers** — detects maltodextrin, modified starch, glucose/corn syrups, hydrogenated fats, protein isolates
- **Functional role stacking** — counts how many food-engineering systems are present (sweetener, fat, flavour, mouthfeel, preservation, colour, umami, acid)
- **Category priors** — small adjustments by product category
- **Guardrails** — traditional foods (plain bread, single-ingredient items) are protected from over-scoring

### Overeating Risk Score

A weighted combination of two sub-scores:

**Nutrient analysis (Fazzino criteria, 40% weight):**
Checks nutrition data against three hyperpalatable clusters from Fazzino et al. (2019):
- Fat + Sodium
- Fat + Sugar
- Carbs + Sodium

Beverages receive a bonus penalty because liquid calories bypass satiety signals (Mattes 2006; DiMeglio & Mattes 2000).

**Ingredient formulation analysis (60% weight):**
Analyzes the ingredient list for palatability signals:
- Position of sugar, oil, salt in ingredient list
- Synergistic reward combos (sugar×fat, fat×salt, sweet×salty)
- Snack architecture patterns (chip/cracker structures, chocolate, flavoured-salty)
- Simplicity bonuses for short, clean ingredient lists

---

## Privacy Policy Content

### Data Sent to Our Server (per scan)

- **Food photo** — JPEG-compressed, scaled to max 1024px. Used solely to identify the food via Claude AI. **Not stored on our server** — proxied to the AI and discarded.
- **Google ID token** — used to authenticate the user and enforce rate limits.
- **Analysis mode** — whether Basic or Premium mode was selected.

### Data Stored on Our Server

- **Google account identifier** (subject ID) — stable account identifier, not your email displayed publicly
- **Email address** — for account identification
- **Account creation timestamp**
- **Per-scan usage log** — user ID + timestamp only, used exclusively for rate limiting (100 scans/day, 500 scans/week)

**We do not store your food photos or scan results on our server.**

### Data Stored on Your Device Only (never transmitted)

- Scan history (food name, brand, scores, nutrition data, thumbnail) — up to 100 entries
- Food cache (7-day TTL) for faster repeat lookups
- All scan results and nutrition data stay on your phone

### Third-Party Services

- **Google Sign-In** — authentication (Google's privacy policy applies)
- **Claude AI by Anthropic** — food photo identification (Anthropic's privacy policy applies)
- **Open Food Facts** — packaged food database, bundled locally (no network calls to OFF)

### Security

- All network communication uses HTTPS
- Claude API key is stored server-side only — never on your device
- Google ID tokens are verified server-side via Google's official libraries
- [TBC — EXIF/metadata stripping confirmation]

---

## Legal Disclaimer

> The scoring system used in FoodKnower is a custom, non-scientific system created by the developer. It is not endorsed by any regulatory body or scientific institution.

> Scores are illustrative and have not been clinically validated. They are intended to help you think about food choices, not to provide medical or dietary advice.

> FoodKnower is not a substitute for professional dietary or medical advice. Always consult a qualified healthcare professional for health-related decisions.

### Data Source Attribution

> Packaged food data provided by Open Food Facts (openfoodfacts.org), available under the Open Database License (ODbL). Data has been modified from the original.

---

## Contact & Links

- **Website:** https://foodknower.com
- **Community forum:** https://community.foodknower.com
- **Email:** contact@foodknower.com
- **Play Store:** [TBC — link once published]

---

## Founder's Message

[TBC — planned as a short, 1-page personal note about passion for health and why this app was built]

---

## App Screenshots

[TBC — provide 3–5 screenshots showing: scan in action, score results screen, nutrition breakdown, scan history]

---

## Technical Preferences

- Static site (no backend needed)
- Host on GitHub Pages, Netlify, or Vercel
- Mobile-responsive
- Fast loading, minimal dependencies
- [TBC — preferred static site tool/framework, or plain HTML/CSS/JS]

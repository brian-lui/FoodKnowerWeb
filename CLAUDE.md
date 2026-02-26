# FoodKnowerWeb

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

## Website

Static site (plain HTML/CSS/JS) hosted on GitHub Pages at https://foodknower.com.

### Pages

- `index.html` — landing page with pitch, features, scores explanation, founder's story, download CTAs
- `privacy.html` — privacy policy
- `terms.html` — terms of service
- `legal.html` — legal disclaimer and data source attribution
- `methodology.html` — scoring methodology
- `about.html` — about page
- `accessibility.html` — accessibility statement
- `404.html` — custom 404

---

## Contact & Links

- **Website:** https://foodknower.com
- **Community forum:** https://community.foodknower.com
- **Email:** contact@foodknower.com
- **Play Store:** [TBC — link once published]

---

## Still TBC

- Replace phone mockup placeholders with real app screenshots
- Update Play Store / App Store badge links once published
- EXIF/metadata stripping confirmation for privacy policy security section

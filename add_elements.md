# Roadmap: Common Web Elements to Add

This roadmap outlines optional additions for FoodKnower’s website, grouped by impact and effort. It is a plan only; no implementation steps have been applied yet.

## Phase 1: High Impact, Low Effort

- Add favicons and app icons
  - `favicon.ico`
  - `favicon-32x32.png`, `favicon-16x16.png`
  - `apple-touch-icon.png`
  - Optional: `safari-pinned-tab.svg`
- Add Open Graph and Twitter Card metadata
  - `og:title`, `og:description`, `og:image`, `og:url`
  - `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
- Add `theme-color` meta tag
- Add canonical URL tag
- Add a `main` landmark to `index.html`
- Add “Skip to content” link for accessibility
- Replace `#` store badge links with real store URLs when available

## Phase 2: Trust and Clarity

- Add a short “How it works” 1–2–3 steps section
- Add FAQ section with common questions
- Add social proof block
  - Testimonials or short quotes
  - Press logos or “As seen in”
  - Download count or star rating if available
- Add “About” or “Team” mini-section
- Add support/help page or support link in footer

## Phase 3: SEO and Indexing

- Add `robots.txt`
- Add `sitemap.xml`
- Add structured data
  - Organization schema
  - MobileApplication schema

## Phase 4: Platform and Compliance (as needed)

- Add web app manifest (`manifest.json`)
- Add iOS smart app banner (`apple-itunes-app`) if deep-linking later
- Add cookie notice/consent banner if analytics or tracking is added
- Add accessibility statement page
- Add `404.html`

## Notes and Dependencies

- Social metadata requires a share image asset (`og:image`).
- Structured data requires stable brand/company details (name, URL, logo, contact).
- Cookie banner is only needed if you add non-essential tracking.
- Store badge links should be updated only once public store URLs exist.

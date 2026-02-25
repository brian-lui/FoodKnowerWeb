# Roadmap: Common Web Elements to Add

This roadmap outlines optional additions for FoodKnower's website, grouped by impact and effort. It is a plan only; no implementation steps have been applied yet.

## Phase 1: High Impact, Low Effort

- Add Open Graph and Twitter Card metadata
  - `og:title`, `og:description`, `og:image`, `og:url`
  - `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
  This is the preview image that appears when someone shares your URL on social media, Slack, Discord, iMessage, etc.     For example, if someone pastes foodknower.com into a Twitter post or WhatsApp message, the platform fetches your
  og:image and shows it as a big card preview.
  Without one, shared links show up as plain text or a tiny favicon — much less clickable. The recommended size is
  1200x630px. It's typically a branded graphic — something like your logo, tagline, and maybe a screenshot on a colored
  background. You'd need to create this as an image file (PNG or JPG) and host it with your site.
- Replace `#` store badge links with real store URLs when available

## Phase 2: Trust and Clarity

- Add FAQ section with common questions

## Phase 3: SEO and Indexing

- Add structured data
  - MobileApplication schema (requires live Play Store URL)

## Phase 4: Platform and Compliance (as needed)

- Add iOS smart app banner (`apple-itunes-app`) if deep-linking later

## Notes and Dependencies

- Social metadata requires a share image asset (`og:image`).
- MobileApplication schema requires a live Play Store listing.
- Store badge links should be updated only once public store URLs exist.

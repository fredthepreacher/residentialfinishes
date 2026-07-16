# Changelog

## 2026-07-15 — P0 Critical Fixes

Scope: technical/structural fixes only. No new pages, no visual redesign, no
business-fact edits. See `OWNER_VERIFICATION_CHECKLIST.md` for everything
still pending owner confirmation.

### Forms & conversion routing
- Quote request form now submits to `/thank-you-quote.html` (was generic `/thank-you.html`).
- Employment application form now submits to `/thank-you-employment.html` (was generic `/thank-you.html`).
- Created `thank-you-quote.html` and `thank-you-employment.html` with distinct, appropriate messaging; both marked `noindex, nofollow`.
- Added `generate_lead` GA4 event on the quote thank-you page.
- Added `phone_click`, `email_click`, and `form_start` GA4 event tracking sitewide.
- Added redirects for `/thank-you-quote` and `/thank-you-employment` in `_redirects`.

### Structured data (JSON-LD) cleanup
- Removed fabricated `aggregateRating` (5.0 stars / 47 ratings) and fake named `review` entries — not backed by real, verifiable reviews.
- Removed unverified `geo` coordinates.
- Removed unverified `openingHoursSpecification` (7 days/week, 9–6).
- Removed unverified `numberOfEmployees`.
- FAQPage schema left untouched (content matches visible FAQ copy).

### Sitemap & indexing
- Removed `thank-you.html` from `sitemap.xml`; sitemap now contains only the canonical homepage.
- Added `noindex, nofollow` to `thank-you.html` (legacy page, kept as fallback).

### Dead links
- Removed placeholder Facebook/Instagram/YouTube footer icons (previously linked to `#`) — no real URLs available yet.
- Redirected footer service-area links from `#` to the in-page `#service-areas` section.

### Performance / asset cleanup
- Extracted two base64-embedded PNG logos out of `index.html` into real files (`assets/rf-logo.png`, `assets/rf-logo-hero.png`), referenced via `<img src>` with explicit `width`/`height`. **Reduced `index.html` from ~612 KB to ~96 KB.**
- Deleted 27 unused duplicate images from the project root (gallery photos, hero background, project before/afters, an unused 4 MB `rf-logo.png` original) — none were referenced by the live page.
- Deleted 10 unused orphaned image variants from `/assets/project-5-*`, including two unreferenced ~4 MB files.
- Converted `assets/hallway.png` (1.8 MB, lossless PNG of a photo) to `assets/hallway.jpg` (126 KB) and added explicit `width`/`height`.
- Added a `<link rel="icon">` favicon using the optimized logo.
- Removed the legacy `<meta name="keywords">` tag (not used as a ranking signal).
- **Total deployable folder size: ~34 MB → ~2.9 MB.**

### Follow-up (owner-provided facts, same day)
- Added confirmed Facebook (`facebook.com/profile.php?id=61590468225340`) and Instagram (`instagram.com/residential_finishes/`) links to the footer and schema `sameAs`.
- Added confirmed Google Business Profile link (`share.google/utH4UPmZkVdlgDomP`) as a "View on Google" footer link and to schema `sameAs`.
- Added confirmed service area: Stamford, CT and Greenwich, CT — updated meta description, Open Graph/Twitter tags, the visible "Where We Work" section, the FAQ, and JSON-LD `areaServed`.
- Added confirmed hours (Mon–Fri 9AM–4PM, Sat 9AM–3:30PM, Sunday by request) to schema `openingHoursSpecification` and fixed the visible "Hours of Operation" widget, which previously read "Monday through Sunday, 7 Days a Week" — inconsistent with everything else on the site.
- Fixed stale `© 2025` footer copyright year to `© 2026`.

### Correction — reconciled with GitHub repo state
While preparing to push, discovered the actual GitHub repo (`fredthepreacher/residentialfinishes`) already contained better-designed, on-brand `thank-you-quote.html` and `thank-you-employment.html` pages (matching the site's full header/hero/steps/timeline/CTA/footer system) that were not present in this local working folder. Replaced the simpler placeholder thank-you pages built earlier in this session with the repo's existing designs, adding the GA4 tracking script and `generate_lead` event on top. Also removed unverified response-time claims ("within 1 business day" / "within a few business days") from both pages, replacing with neutral language, consistent with the rest of this cleanup.

### Post-deploy fixes (caught by reviewing the live push)
- Found and fixed a leftover "Free estimates · 7 days a week" claim in the final CTA section that contradicted the hours just confirmed — removed.
- Found a "Licensed & Insured" claim (homepage marquee + a dedicated FAQ) that was missed in the original audit. Owner confirmed 2026-07-15 this is true — left live, now formally logged as confirmed rather than unchecked.
- Found the quote form told visitors their request goes to `residential.finishez@gmail.com`, while the schema `email` field said `info@residentialfinishes.com` — two different addresses. Owner confirmed `residential.finishez@gmail.com` is correct; fixed the schema to match.

### Not done in this pass (flagged for later phases)
- New page architecture (`/services/`, `/request-a-quote/`, `/faq/`, etc.) — P1.
- Responsive `srcset`/`sizes`, `<picture>`, width/height audit across all remaining images — P1.
- Google Ads conversion tag / dedicated landing page — P1.
- Visible testimonial section — flagged in `OWNER_VERIFICATION_CHECKLIST.md`, not modified pending your decision.
- Stray version ZIPs sitting alongside this folder (`residential-finishes-updated.zip`, `-v2` through `-v5`, `-netlify-forms-fixed.zip`, `-slider-fixed.zip`) were left alone — these look like your own backups, not part of the deployable site. Let me know if you'd like those cleaned up too.

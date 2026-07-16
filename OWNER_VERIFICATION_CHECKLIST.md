# Owner Verification Checklist — Residential Finishes LLC

Generated during the P0 technical cleanup pass (2026-07-15). Nothing on the live
site should stay unverified indefinitely — use this list to confirm, correct,
or remove each item. Items are grouped by urgency.

---

## 🔴 Urgent — resolve first

### 1. Visible testimonials (homepage "Client Reviews" section)
Three testimonial cards are shown with 5-star ratings and named authors:
"Maria T." (Brooklyn, NY), "Derek K." (Manhattan, NY), and "Simone R."
**(Newark, NJ — outside every service area the site claims).**

The Newark, NJ location is inconsistent with the stated NYC / Westchester /
Long Island service area, which strongly suggests this content is placeholder
copy rather than real customer feedback.

**Do not leave fabricated testimonials live.** Publishing invented customer
quotes is a genuine legal risk (FTC endorsement/testimonial guidelines), not
just an SEO issue. Please either:
- Replace all three with real, attributable customer reviews (name, real
  location, real quote, and — ideally — a link to the source, e.g. Google), or
- Remove the section entirely until real testimonials are available.

I have **not** touched this section yet since it's visible marketing copy, not
code — flagging it here for your decision.

### 2. Fabricated review schema (already removed from code)
The site's structured data (JSON-LD) contained a fake `aggregateRating`
(5.0 stars, 47 ratings) and two fabricated named reviews ("Marcus T.",
"Angela R." — note: different names than the testimonials above, another sign
this was placeholder data). **I removed this schema entirely** — publishing
fake review schema violates Google's guidelines and risks a manual action.

➡ If you have real reviews (e.g., from Google Business Profile) that you want
search engines to see, they should be re-added only once real, sourced, and
ideally visibly matching what's shown on the page.

### 3. "Licensed & Insured" claim — found after initial audit, now confirmed
I missed this in the first pass (buried in the 600KB file): the homepage
marquee says "Licensed & Insured," and a dedicated FAQ ("Are you licensed and
insured in New York?") states the business is "fully insured" with "general
liability coverage." My original checklist incorrectly said the site made no
insurance/license claims — that was wrong, and I should have caught it
immediately given how much legal weight that claim carries.

✅ **Confirmed 2026-07-15 by owner: this is true and verifiable.** No changes
made — claim stays live. Flagging here only so there's a record that it was
specifically confirmed, not just left unchecked.

---

## 🟡 High priority — structured data currently removed, needs real data

These were removed from the site's JSON-LD because they were unverified and
carry search-engine risk. The page still reads fine without them, but adding
back verified versions will help local search once confirmed:

| Field | What was removed | What I need from you |
|---|---|---|
| Operating hours | ~~7 days/week, 9:00–18:00 (incl. Sunday)~~ | ✅ **Confirmed 2026-07-15:** Mon–Fri 9AM–4PM, Sat 9AM–3:30PM, Sunday off unless requested. Re-added to schema and fixed on the visible "Hours of Operation" widget (previously said "Monday through Sunday, 7 Days a Week," which conflicted with everything). |
| Geo-coordinates | lat 40.9176 / lng -73.8988 (unverified/approximate) | Your real business address coordinates, or confirm this is a no-fixed-location service-area business (then coordinates should stay omitted) |
| Employee count | "5" | Confirm actual headcount, or leave omitted |
| Star rating / review count | 5.0 stars / 47 reviews | Real, verifiable rating and count only |

Note: schema doesn't have a clean way to express "Sunday by request," so
Sunday is simply omitted (reads as closed to search engines). If you'd like
"available by request" communicated somewhere, that's better done as visible
text near the hours widget than in schema — let me know if you want that added.

---

## 🟢 Confirm — currently left live, please verify accuracy

I left the following **prose/marketing content** on the page as-is (per your
instruction to flag rather than strip), but none of it has been independently
verified:

- **"14+ years" / "Fourteen years of hands-on work" / founding story** —
  About section states the business started in Yonkers in **2010**, expanded
  to New Rochelle, with a timeline beginning "2010–17." Confirm these dates
  and the narrative are accurate.
- **Service area list** — the site claims coverage across:
  - All 5 NYC boroughs (Manhattan, Brooklyn, Queens, Bronx, Staten Island)
  - Westchester County: Yonkers, White Plains, New Rochelle, Mount Vernon,
    Scarsdale, Tarrytown, Harrison, Ossining, Dobbs Ferry, Mamaroneck,
    Larchmont, Rye, Port Chester
  - Nassau County: Hempstead, Garden City, Long Beach, Freeport, Valley
    Stream, Mineola, Great Neck, Manhasset, Rockville Centre
  - Suffolk County (list continues on-page)

  Confirm every city listed is actually served today — thin/inaccurate
  service-area claims can hurt local SEO credibility.
- **Phone number:** (347) 335-1078 — ✅ **confirmed correct by owner (2026-07-15).**
- **Email:** ✅ **Confirmed 2026-07-15:** `residential.finishez@gmail.com` is
  the correct lead inbox (matches what's shown on the quote form). The schema
  previously said `info@residentialfinishes.com` — a different, unconfirmed
  address that could have silently misdirected leads. Fixed to match.
- **Business name:** "Residential Finishes LLC" (alternate name used in schema:
  "Residential Finishes Interior Painting LLC") — confirm exact legal/display
  name to use consistently.
- **Service area — Connecticut:** ✅ **Confirmed 2026-07-15:** Stamford and
  Greenwich, CT. Added to the visible "Where We Work" section, the FAQ, meta
  description/Open Graph tags, and the JSON-LD `areaServed` list.
- **Services offered:** Interior Painting, Drywall Repair, Skim Coat & Surface
  Finishing, Popcorn Ceiling Removal, Commercial Painting — confirm this list
  is current and complete.
- **Residential vs. commercial:** FAQ states you work with "property managers,
  landlords, and business owners" — confirm commercial work is actively
  offered, not just residential.
- **Pricing claim (FAQ):** "$2–$5 per square foot for walls" — confirm this
  range is still accurate; doc guidance is to avoid publishing fixed pricing
  without a verified, current policy.

---

## ⚪ Not currently claimed — confirm if you want to add any

The site does **not** currently claim any of the following (insurance is
claimed — see item 3 above, confirmed). Do not add the rest unless you can
prove them:

- Licenses or trade certifications specifically (insurance is separately confirmed above)
- Bonding
- Awards or industry affiliations
- Warranties or guarantees

---

## 🔗 Links needing real URLs

- **Facebook** — ✅ added: https://www.facebook.com/profile.php?id=61590468225340
- **Instagram** — ✅ added: https://www.instagram.com/residential_finishes/
  (Both are now live in the footer and in the schema `sameAs` field.)
- **YouTube** — still no URL provided. Left off the footer; send the URL if you have an active channel, otherwise no action needed.
- **Google Business Profile (GBP) URL** — ✅ added: https://share.google/utH4UPmZkVdlgDomP
  (confirmed by owner as the listing that shows hours/reviews/map pin). Added
  as a "View on Google" link in the footer Contact column and to the schema
  `sameAs` field.
  - The second link sent earlier (`share.google/rnd3PTuqR5OPScl3U`) was sent
    by mistake — disregarded, no action taken.
- **Footer service-area links** — previously pointed to `#` (dead). I
  redirected them to the in-page `#service-areas` section as an interim fix.
  Real dedicated location pages are Phase 2 (P1/P2) work.

### What is a "GBP link"?
GBP = **Google Business Profile** (formerly "Google My Business") — the free
listing that shows up on the right side of Google Search and on Google Maps
when someone searches your business name, with your hours, photos, reviews,
and a "Call" / "Directions" button. The "GBP link" is just the public URL to
that listing.

How to find yours:
1. Go to google.com and search your business name ("Residential Finishes LLC").
2. If a business panel appears on the right with your info, click "Share" (or
   the three-dot menu) — it gives you a shareable link like
   `https://g.page/r/....` or a `maps.app.goo.gl/...` link.
3. Alternatively, sign in at business.google.com — if you manage a listing
   there, the same share link is available from your dashboard.

If you don't have a Google Business Profile set up yet, that's worth doing
separately — it's one of the highest-impact things for local search, and I
can walk you through creating one once you're ready. It's different from
Facebook/Instagram; it's the one that makes you show up on Google Maps.

---

## Once you've confirmed the above

Send me corrections/confirmations and I'll:
1. Re-add verified structured data (hours, rating, coordinates, employee count) with real values only.
2. Replace or remove the testimonial section based on your decision.
3. Add real social/GBP links back to the footer.
4. Flag anything that still can't be verified so it stays out of the public site.

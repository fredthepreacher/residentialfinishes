# Prompt: Remove "Window Sill & Wall Repair" Card + Fix Logo Watermark Transparency

## Context

Site: residentialfinishes.com (single `index.html`, static, Netlify-deployed from GitHub).
Section: "Before & After" interactive slider gallery (`.ba-grid` / `.ba-card` / `.ba-slider`).

## Task 1 — Remove the "Window Sill & Wall Repair" card

Remove this before/after card entirely from the gallery:

- Title: **Window Sill & Wall Repair**
- Copy: "Surface damage, chipped paint, and marked walls repaired and refinished for a clean, polished look."
- This was the two-mirror-wall photo pair (previously the `ba-card-repair` card).

Steps:

1. Delete the full `<article class="ba-card">…</article>` block for this card from inside `.ba-grid`.
2. Remove its two image files from `/assets/` if they are not used anywhere else on the site (check before deleting).
3. Confirm the gallery still renders as a clean, symmetrical grid with the card removed. Card count will drop to **7**. Re-check the responsive centering logic (`applyCentering()` in the `<script>` block) for all three breakpoints, since 7 is not evenly divisible by 2 or 3:
   - Desktop (3 columns, 1280px+): 7 % 3 = 1 → last card should get `ba-center-1` (already supported).
   - Tablet (2 columns, 768–1279px): 7 % 2 = 1 → last card should get `ba-center-1` (confirm the 768px media query still defines `.ba-card.ba-center-1 { grid-column: 2 / span 2 }`).
   - Mobile (1 column): no centering needed.
4. Verify with real screenshots at desktop, tablet, and mobile widths — not just code review — before calling this done. (Last round's grid bug was only caught this way.)

## Task 2 — Make the logo watermark background genuinely transparent

The `.ba-logo-badge` element (bottom-right corner of every slider card) is the small squarish logo watermark. Its CSS background is already set to `transparent`:

```css
.ba-logo-badge {
  background: transparent;
  ...
}
```

But it still visually shows as a solid white/cream box in the browser. That's because **the logo image file itself (`assets/rf-logo.png`) has a non-transparent white/cream background baked into the PNG** — the container is transparent, the image isn't. Toggling CSS alone will not fix this.

Steps:

1. Produce a version of the logo with a true transparent background (remove the white/cream matte via alpha masking — e.g. Pillow/PIL `remove background` or a proper transparent export from the original source file, not just the current PNG).
2. Save as a new asset (e.g. `assets/rf-logo-transparent.png`) rather than overwriting the original, in case the opaque version is used elsewhere on the site (check the header/nav logo usage first).
3. Update the `.ba-logo-badge img` source (injected via JS in the `<script>` block — search for `rf-logo.png`) to point to the new transparent asset.
4. Verify visually on a real card, ideally against both a light-colored and dark-colored "after" photo, to confirm no white box/halo remains around the logo mark.

## Acceptance Criteria

- Window Sill & Wall Repair card no longer appears anywhere on the live site.
- Gallery grid still looks intentional (no orphaned cards, no gaps) at desktop, tablet, and mobile widths — confirmed via screenshots.
- Logo watermark on every card shows no visible box/background — just the logo mark floating over the photo.
- No other unrelated business claims, pricing, hours, or testimonials are touched.

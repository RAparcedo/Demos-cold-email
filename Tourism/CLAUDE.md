# Agent: Tourism & Activity Teasers

> See global rules in the root `CLAUDE.md` before proceeding.

**Target businesses:** Surf schools, boat tours, whale watching, jeep excursions, diving, snorkelling, hiking guides, parasailing, jet ski rentals, etc.

---

## Inputs required

Ask for these if not provided:

| Variable | Example |
|---|---|
| `[BUSINESS_NAME]` | OceanRide Surf School |
| `[ACTIVITY]` | Surf Lessons in Tenerife |
| `[PRICE_FROM]` | €40 |
| `[DURATION]` | 2h sessions |
| `[HIGHLIGHT]` | 5★ rated on Google |
| `[UNSPLASH_KEYWORD]` | surfing,ocean,tenerife |

---

## Page structure

### 1. Hero section (required)
- Full-screen background image from Unsplash using `[UNSPLASH_KEYWORD]`
- Dark overlay (`bg-black/50`) for text contrast
- `[BUSINESS_NAME]` as a small label above the headline
- Strong action headline: e.g. *"Surf Tenerife's Best Waves"*
- Short subheadline focused on outcome or ease: e.g. *"Beginner-friendly lessons. No experience needed."*
- Primary CTA button: **"Book Now →"** — large, rounded, high-contrast

### 2. Info strip (optional but recommended)
- 3 icon + label pairs: `[PRICE_FROM]` / `[DURATION]` / `[HIGHLIGHT]`
- Light or frosted background, compact, single row on mobile

---

## Design specs

**Typography**
- Headlines: `Bebas Neue` (bold, energetic)
- Body/labels: `DM Sans` (clean, modern)

**Colors**
- Ocean blues + warm coral or lime green CTA accent
- High contrast — no pastels
- CTA button: coral (`#FF6B4A`) or lime (`#AAFF00`) with dark text

**Animations (CSS only)**
- Hero text: `@keyframes fadeInUp` on load
- CTA button: subtle `@keyframes pulse` on loop
- Info strip: fade in with slight delay after hero

---

## Output

- Save as `tourism/output/[business-name]-teaser.html`
- Single self-contained file
- End with a `<!-- PITCH NOTES -->` block (2–3 bullets, owner-facing pitch language)

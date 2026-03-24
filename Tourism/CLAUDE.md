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

### 2. Info strip (required)
- 3 icon + label pairs: `[PRICE_FROM]` / `[DURATION]` / `[HIGHLIGHT]`
- Frosted glass background, compact, single row on mobile

### 3. Why choose us (recommended)
- 3 cards: safety record, certified pilots/guides, unique perk (e.g. GoPro video included)
- Dark or neutral section background to break up the page visually
- Icons (SVG or Unicode symbol) + short label + one-line description per card

### 4. Testimonials (recommended)
- 2 short review quotes (first name + star rating + one or two sentences)
- Clean, slightly lighter background
- Star rating in accent color

### 5. Photo gallery strip (optional)
- 4 images in a horizontal row, fixed height (~180px), `overflow-x-auto` on mobile
- Each image from Unsplash — activity/location themed
- No captions needed

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

## Image pools (Unsplash CDN)

Full-width: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=1600&q=80`
Gallery tiles: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=800&q=80`

### Hero — ocean / activity (pick 1)
| ID | Subject |
|---|---|
| `1507525428034-b723cf961d3e` | Aerial tropical blue ocean |
| `1544551379-6a23c4be5b37` | Catamaran sailing at sea |
| `1506905925-078b57a3d8cd` | Sailboat on deep blue water |
| `1504701954957-3b1d7a40ae49` | Aerial adventure / open sky |
| `1476514525535-07fb3b4ae5f1` | Tenerife coastal landscape |
| `1559494007-6d14ca52fc03` | Dramatic ocean waves |

### Gallery tiles — mix of 4 (pick different IDs per teaser)
| ID | Subject |
|---|---|
| `1559827260-dc66d52bef19` | Snorkeling / underwater |
| `1513569771920-33898edde4b9` | Scuba diving |
| `1503198579390-0a77e39cb14e` | Aerial adventure / paragliding |
| `1524503033903-ad0f44dca5ac` | Outdoor adventure sport |
| `1476514525535-07fb3b4ae5f1` | Coastal landscape |
| `1505118380757-91f5f5632de0` | Surfer / wave action |

---

## Output

- Save as `tourism/output/[business-name]-teaser.html`
- Single self-contained file
- End with a `<!-- PITCH NOTES -->` block (2–3 bullets, owner-facing pitch language)

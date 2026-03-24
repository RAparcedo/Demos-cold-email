# Agent: Real Estate Teasers

> See global rules in the root `CLAUDE.md` before proceeding.

**Target businesses:** Property agencies, luxury villa sales, rental management companies, investment property firms, holiday letting agencies, etc.

---

## Inputs required

Ask for these if not provided:

| Variable | Example |
|---|---|
| `[AGENCY_NAME]` | Tenerife Estates Group |
| `[TAGLINE]` | Your dream property in the Canary Islands |
| `[SUBHEADLINE]` | Sun-filled homes. Smart investments. |
| `[CTA_TEXT]` | Browse Properties *(or)* Request Details |
| `[PROP_1]` | 3-bed Villa · Costa Adeje · €420,000 |
| `[PROP_2]` | 2-bed Apartment · Los Cristianos · €195,000 |
| `[PROP_3]` | Luxury Penthouse · Puerto Colón · €890,000 |
| `[UNSPLASH_KEYWORD]` | luxury villa,tenerife,pool,architecture |

---

## Page structure

### 1. Hero section (required)
- Full-screen luxury property or Tenerife landscape image from Unsplash using `[UNSPLASH_KEYWORD]`
- Clean dark or light overlay — go for premium feel, not dramatic
- `[AGENCY_NAME]` bold but refined
- `[TAGLINE]` as main headline
- `[SUBHEADLINE]` smaller, lifestyle or investment angle
- CTA button: `[CTA_TEXT]` — premium accent color (gold, slate, or deep navy)

### 2. Property listings (required)
- 3 property cards each with a real Unsplash property image (direct photo ID URL)
- Price tag + property label (bedrooms, location) overlaid on or below the image
- Clean grid, spacious, easy to scan on mobile; subtle shadow, no loud colors

### 3. Trust stats row (recommended)
- 3–4 figures: properties sold, years in market, client satisfaction %, avg. days to sale
- Clean neutral background, large number + small label layout

### 4. Client pull-quote (optional)
- One testimonial: first name, short quote (1–2 sentences), star rating
- Understated styling — italic text, no loud design treatment

---

## Design specs

**Typography**
- Headlines: `Cormorant Garamond` (luxury, timeless, trustworthy)
- Body/labels: `Nunito Sans` (clean, professional)

**Colors**
- Premium neutrals only — choose one direction:
  - Coastal luxury: ivory + deep navy + gold accent
  - Modern premium: warm white + slate grey + bronze
  - Mediterranean: warm stone + terracotta + aged gold
- CTA button: gold (`#B8952A`), slate (`#4A5568`), or deep navy (`#1A2744`)
- No bright colors, no gradients that look cheap

**Animations (CSS only)**
- Hero content: smooth `@keyframes fadeInUp` on load
- Property cards: staggered `@keyframes slideUp` with 150ms delay between each

---

## Image pools (Unsplash CDN)

Full-width: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=1600&q=80`
Cards: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=800&q=80`

### Hero — luxury villa / property exterior (pick 1)
| ID | Subject |
|---|---|
| `1613977257363-707ba9348227` | Luxury villa with infinity pool |
| `1600596542815-ffad4c1539a9` | Modern villa exterior, sunny |
| `1600585154340-be6161a56a0c` | Pool and villa, warm light |
| `1512917774080-9991f1c4c750` | Upscale house exterior |
| `1560448204-e02f11c3d0e2` | Terrace / balcony sea view |

### Property cards — interiors & exteriors (pick 3 different IDs)
| ID | Subject |
|---|---|
| `1600607687939-ce8a6c25118c` | Luxury interior / living room |
| `1613545325278-f18b3a2a5898` | Master bedroom, natural light |
| `1600566753376-12c8621c13a8` | Modern kitchen, marble |
| `1600047509807-ba8f99d2cdde` | Open-plan living room |
| `1560185007-c5ca9d2c014d` | Apartment exterior / facade |
| `1560448204-e02f11c3d0e2` | Balcony with sea view |
| `1613977257363-707ba9348227` | Infinity pool close-up |

---

## Output

- Save as `real-estate/output/[agency-name]-teaser.html`
- Single self-contained file
- End with a `<!-- PITCH NOTES -->` block (2–3 bullets, owner-facing pitch language)

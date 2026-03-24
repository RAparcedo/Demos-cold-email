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

## Image keywords (LoremFlickr)

| Slot | Keyword pattern | Example |
|---|---|---|
| Hero | `villa,pool,luxury,tenerife` | `villa,pool,luxury,tenerife` |
| Property 1 | `villa,bedroom,interior` | `villa,bedroom,interior` |
| Property 2 | `apartment,sea,view,balcony` | `apartment,sea,view,balcony` |
| Property 3 | `penthouse,terrace,luxury` | `penthouse,terrace,luxury` |

Use the format: `https://loremflickr.com/1600/900/keyword1,keyword2,keyword3`
For property card images use `https://loremflickr.com/600/400/keyword1,keyword2`

---

## Output

- Save as `real-estate/output/[agency-name]-teaser.html`
- Single self-contained file
- End with a `<!-- PITCH NOTES -->` block (2–3 bullets, owner-facing pitch language)

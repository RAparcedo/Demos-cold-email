# Agent: Restaurant & Café Teasers

> See global rules in the root `CLAUDE.md` before proceeding.

**Target businesses:** Restaurants, seafood spots, rooftop bars, brunch cafés, tapas bars, sushi, Italian, Canarian cuisine, wine bars, etc.

---

## Inputs required

Ask for these if not provided:

| Variable | Example |
|---|---|
| `[RESTAURANT_NAME]` | La Brasa del Puerto |
| `[CUISINE_TYPE]` | Fresh Seafood & Canarian cuisine |
| `[TAGLINE]` | Ocean-to-table dining with views to match |
| `[CTA_TEXT]` | View Menu *(or)* Reserve a Table |
| `[DISH_1]` | Grilled octopus · Tender, charred, served with mojo verde |
| `[DISH_2]` | Papas arrugadas · Traditional Canarian wrinkled potatoes |
| `[DISH_3]` | Tarta de queso · Creamy local cheese tart, honey & fig |
| `[UNSPLASH_KEYWORD]` | seafood,restaurant,canary islands |

---

## Page structure

### 1. Hero section (required)
- Full-screen food or ambiance background image from Unsplash using `[UNSPLASH_KEYWORD]`
- Semi-transparent dark overlay
- `[CUISINE_TYPE]` as a small styled label above the name
- `[RESTAURANT_NAME]` large and elegant
- `[TAGLINE]` below — short, appetizing, evocative
- CTA button: `[CTA_TEXT]` — warm food-appropriate color (gold, terracotta, or deep red)

### 2. Signature dishes (required)
- 3 dish cards, each with a real Unsplash food image (use direct photo ID URLs)
- Dish name + one-line description below the image
- Warm card backgrounds, subtle shadow, rounded corners

### 3. Atmosphere / pull-quote block (recommended)
- Full-width section with a muted restaurant/ambiance background image
- Overlaid italic pull-quote about the dining experience (invented but believable)
- Author credit: "— [First name], Google Review" or similar

### 4. Social proof bar (recommended)
- Google rating (e.g. 4.8 ★ · 320 reviews), TripAdvisor mention, or a local award
- Compact, single row, subtle dividers
- Neutral background (slightly different shade from surrounding sections)

---

## Design specs

**Typography**
- Headlines: `Playfair Display` (editorial, refined, appetite-inducing)
- Body/labels: `Lato` (neutral, readable)

**Colors**
- Warm and inviting palette — choose based on cuisine:
  - Seafood/Canarian: deep ocean teal + warm sand + coral accent
  - Italian: deep red + cream + forest green
  - Café/brunch: warm cream + terracotta + sage
- CTA button: gold (`#D4A647`), terracotta (`#C1440E`), or deep red (`#8B1A1A`)

**Animations (CSS only)**
- Hero content: `@keyframes fadeIn` on load
- Dish cards: staggered `@keyframes slideUp` with 100ms delay between each

---

## Image pools (Pexels CDN)

Full-width: `https://images.pexels.com/photos/{ID}/pexels-photo-{ID}.jpeg?auto=compress&cs=tinysrgb&w=1600`
Cards: `https://images.pexels.com/photos/{ID}/pexels-photo-{ID}.jpeg?auto=compress&cs=tinysrgb&w=800`

### Hero — restaurant interior / ambiance (pick 1)
| ID | Subject |
|---|---|
| `3534750` | Sophisticated fine dining, chandeliers, wine glasses |
| `29309717` | Elegant interior, warm tones, geometric wall patterns |
| `3465604` | Warm rustic-industrial café, hanging lights |
| `19689233` | Bar in a luxury restaurant, velvet seating |
| `34686219` | Cosy modern restaurant, ambient lighting |

### Dish cards — food close-ups (pick 3 different IDs)
| ID | Subject |
|---|---|
| `14885388` | Gourmet octopus dish, orange sauce |
| `1510714` | Fried fish with colourful vegetables |
| `1998920` | Shrimp dish with chili, lemon, dipping sauce |
| `3649208` | Seafood pasta with shrimp and seashells |
| `11653557` | Grilled fish with roasted vegetables |
| `1031780` | Grilled shrimps on plates |

### Atmosphere — full-width (pick 1, different from hero)
| ID | Subject |
|---|---|
| `3465604` | Rustic café interior, hanging lights |
| `3534750` | Fine dining room, chandeliers |

---

## Bilingual language toggle

Follow the global toggle pattern in the root `CLAUDE.md` exactly. Below are the Restaurant–specific vocabulary pairs to use:

| Element | ES | EN |
|---|---|---|
| Hero cuisine label | `Cocina Canaria & Mariscos` *(adapt per cuisine)* | `Canarian & Seafood Cuisine` |
| Section heading | `Nuestros Platos` | `Our Dishes` |
| Dish description | Spanish one-liner | English one-liner (class `en`) |
| Social proof label | `Reseñas` | `Reviews` |
| Social proof strip label | `en Google` | `on Google` |
| Primary CTA | `Ver Carta` | `View Menu` |
| Secondary CTA | `Reservar Mesa` | `Reserve a Table` |
| Pull-quote intro | `Lo que dicen nuestros clientes` | `What our guests say` |
| Pull-quote body | Translate the quote into both languages; use `.es` / `.en` on the `<p>` tags |

## Output

- Save as `Restaurants/Outputs/[restaurant-name]-teaser.html`
- Single self-contained file
- End with a `<!-- PITCH NOTES -->` block (2–3 bullets, owner-facing pitch language)

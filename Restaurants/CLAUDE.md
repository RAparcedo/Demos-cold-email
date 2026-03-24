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

## Image pools (Unsplash CDN)

Full-width: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=1600&q=80`
Cards: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=800&q=80`

### Hero — restaurant interior / ambiance (pick 1)
| ID | Subject |
|---|---|
| `1517248135467-4c7edcad34c4` | Warm restaurant interior, bokeh lights |
| `1592417817098-8fd3d2eb9673` | Candlelit dining table |
| `1559339352-11d035aa65de` | Elegant restaurant evening |
| `1414235077428-338989a2e8c0` | Restaurant / upscale dining |
| `1551218808-d5a8b2df83ee` | Intimate dining room |

### Dish cards — food close-ups (pick 3 different IDs)
| ID | Subject |
|---|---|
| `1565299624946-b28f40a0ae38` | Pasta / gourmet plate |
| `1414235077428-338989a2e8c0` | Colourful food bowl |
| `1565958011703-44f9829ba187` | Grilled meat / seafood plate |
| `1482049016688-2d3e1b311543` | Breakfast / brunch close-up |
| `1540420773420-3366772f4999` | Seafood dish |
| `1546069901-ba9599a7a5ae` | Fresh salad / greens |
| `1546554137-f86b372c6dd5` | Elegant plated dessert |

### Atmosphere — full-width (pick 1, different from hero)
| ID | Subject |
|---|---|
| `1551218808-d5a8b2df83ee` | Cosy dining room |
| `1559339352-11d035aa65de` | Evening restaurant interior |
| `1517248135467-4c7edcad34c4` | Bokeh / warm light ambiance |

---

## Output

- Save as `restaurant/output/[restaurant-name]-teaser.html`
- Single self-contained file
- End with a `<!-- PITCH NOTES -->` block (2–3 bullets, owner-facing pitch language)

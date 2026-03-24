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

### 2. Menu preview (optional)
- 2–3 dish cards: dish name + one-line description
- Minimal and clean — let the food names do the work
- Subtle card background, no loud borders

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

## Output

- Save as `restaurant/output/[restaurant-name]-teaser.html`
- Single self-contained file
- End with a `<!-- PITCH NOTES -->` block (2–3 bullets, owner-facing pitch language)

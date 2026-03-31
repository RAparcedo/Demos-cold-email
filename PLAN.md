# Session Plan — Demos Cold Email

> **Desktop resume guide:** Clone the repo, check out `claude/init-project-setup-iMYbZ`, open in Claude Code desktop, and say: *"Resume from PLAN.md"*.

---

## Where we stopped

Template generation paused mid-batch. Issues were found — resume on desktop where files can be previewed in a browser immediately after writing.

**Known issues to fix first:**
1. `Tourism/Outputs/quad-excursions-teaser.html` — wrong Pexels images (motorcycle/mini-car, not quads). Fix the image IDs.
2. EN toggle goes blank on some templates — inconsistent markup from parallel agents. Fix: always use `<span class="es">` / `<span class="en">` for inline, paired `<p class="es">` / `<p class="en">` for block. Never leave an `.es` without a matching `.en`.
3. Hiking, Stargazing, Yoga Retreat templates hit rate limit — never written. Build from scratch.

**Templates done (need browser review):**
- `Tourism/Outputs/surf-school-teaser.html` ✓
- `Tourism/Outputs/quad-excursions-teaser.html` ⚠️ wrong images + EN toggle bug
- `Tourism/Outputs/diving-teaser.html` ✓ needs review
- `Tourism/Outputs/water-sports-teaser.html` ✓ needs review

**Workflow going forward (one at a time on desktop):**
1. Fix quad template images + EN toggle
2. Open in browser → verify ES and EN both work, images on-topic
3. Commit
4. Write next template directly (no subagents)
5. Open in browser → verify
6. Commit → repeat

---

## Two-phase approach

1. **Phase 1 (now):** Generate all templates, save to `Sector/Outputs/`. Review in browser. Polish.
2. **Phase 2 (after review):** Convert to URL-param-injected pages in `docs/` hosted on GitHub Pages. URL params hidden from prospect via `history.replaceState`.

---

## Full template list

### Tourism
| File | Covers | Design direction | Status |
|---|---|---|---|
| `Tourism/Outputs/surf-school-teaser.html` | Surf school | Bebas Neue, ocean blue + coral | ✓ Review |
| `Tourism/Outputs/boat-tours-teaser.html` | Boat tours, catamaran, whale watching, fishing | — | Use `azul-cruises` as base, add toggle |
| `Tourism/Outputs/quad-excursions-teaser.html` | Quad/buggy/jeep, off-road | Terracotta, volcanic, rugged | ⚠️ Fix images |
| `Tourism/Outputs/diving-teaser.html` | Diving, scuba, snorkelling | Deep teal + turquoise | ✓ Review |
| `Tourism/Outputs/paragliding-teaser.html` | Paragliding, parasailing | — | Use `no-parachute` as base, add toggle |
| `Tourism/Outputs/water-sports-teaser.html` | Kayak, jet ski, SUP | Bright aqua + navy | ✓ Review |
| `Tourism/Outputs/hiking-teaser.html` | Hiking, mountain biking, horse riding, ziplines | Earthy greens, Teide, nature | ❌ Not built |
| `Tourism/Outputs/stargazing-teaser.html` | Stargazing tours | Deep space navy + gold | ❌ Not built |
| `Tourism/Outputs/yoga-retreat-teaser.html` | Yoga retreat, meditation | Soft neutral + sage | ❌ Not built |

### Restaurants
| File | Covers | Design direction | Status |
|---|---|---|---|
| `Restaurants/Outputs/canarian-teaser.html` | Traditional Canarian, guachinche, tasca | Warm stone + terracotta, rustic | ❌ Not built |
| `Restaurants/Outputs/spanish-teaser.html` | Spanish tapas, pintxos, bodega | Deep red + cream + olive, tavern | ❌ Not built |
| `Restaurants/Outputs/seafood-teaser.html` | Seafood, fresh fish | Ocean teal + sand | ❌ Not built |
| `Restaurants/Outputs/burger-teaser.html` | Burger, American, pub | Dark + bold, neon accent | ❌ Not built |
| `Restaurants/Outputs/pizza-teaser.html` | Pizza, Italian | Warm red + cream + green, wood-fired | ❌ Not built |
| `Restaurants/Outputs/asian-teaser.html` | Sushi, ramen, Japanese, poke | Minimal, dark, neon | ❌ Not built |
| `Restaurants/Outputs/indian-teaser.html` | Indian | Deep saffron + red + gold, ornate | ❌ Not built |
| `Restaurants/Outputs/thai-teaser.html` | Thai, pan-Asian fusion | Emerald + gold + dark wood | ❌ Not built |
| `Restaurants/Outputs/mexican-teaser.html` | Mexican | Terracotta + lime + deep red, festive | ❌ Not built |
| `Restaurants/Outputs/brunch-teaser.html` | Brunch, café, bakery | Cream + sage + terracotta, airy | ❌ Not built |
| `Restaurants/Outputs/rooftop-bar-teaser.html` | Rooftop bar, cocktail bar, wine bar | Dusk palette, city view, premium | ❌ Not built |
| `Restaurants/Outputs/beach-bar-teaser.html` | Beach bar, chiringuito | Sand + turquoise + coral, tropical | ❌ Not built |
| `Restaurants/Outputs/steakhouse-teaser.html` | Steakhouse, fine dining, grill | Dark wood + ember red + gold | ❌ Not built |
| `Restaurants/Outputs/vegan-teaser.html` | Vegan, vegetarian, healthy | Fresh green + white + earth | ❌ Not built |

### Real Estate
| File | Covers | Status |
|---|---|---|
| `Real estate/Outputs/casas-del-sur-teaser.html` | Luxury villa sales (ES) | ✓ Done |
| `Real estate/Outputs/solaris-estates-teaser.html` | Luxury villa sales (EN) | ✓ Done |
| `Real estate/Outputs/holiday-rentals-teaser.html` | Holiday homes, Airbnb-style | ❌ Not built |
| `Real estate/Outputs/long-term-rentals-teaser.html` | Long-term rentals, property management | ❌ Not built |

### Beauty & Spa
| File | Covers | Status |
|---|---|---|
| `Beauty/Outputs/pop-pimps-teaser.html` | Pimple/acne extraction | ✓ Done |
| `Beauty/Outputs/spa-teaser.html` | Spa, facial, massage, aesthetic clinic | ❌ Not built |

### Fitness (new sector)
| File | Covers | Status |
|---|---|---|
| `Fitness/Outputs/gym-teaser.html` | Gym, strength, crossfit | ❌ Not built |
| `Fitness/Outputs/yoga-studio-teaser.html` | Yoga studio, pilates | ❌ Not built |
| `Fitness/Outputs/personal-trainer-teaser.html` | Personal trainer, bootcamp | ❌ Not built |

---

## Global rules (all templates)

From `CLAUDE.md` — read it before generating anything:
- Single self-contained HTML — Tailwind CDN + Google Fonts only
- Pexels CDN images with `onerror="this.style.visibility='hidden'"` on every `<img>`
- Bilingual ES/EN toggle (fixed pill, top-right, `z-index:9999`) — Spanish default
- Hero + 2 sections max
- Mobile-first 390px
- `<!-- PITCH NOTES -->` block at end of every file

**Bilingual toggle — critical rules:**
- Every visible string needs BOTH a `.es` and `.en` version — never leave one without the other
- Inline text: `<span class="es">` / `<span class="en">`
- Block text: `<p class="es">` / `<p class="en">`
- Brand names, prices, numbers, star ratings — no wrapping needed

---

## Phase 2 — GitHub Pages (after all templates reviewed)

**URL params:** `?n=` (name) · `?t=` (tagline) · `?b=` (badge, optional) · `?c=` (accent hex, optional)

**URL wiped after load** so prospect sees clean URL:
```js
if (location.search) history.replaceState({}, '', location.pathname);
```

**File structure:** `docs/surf-school/index.html` → `domain.com/surf-school?n=...`

**Setup:** Repo Settings → Pages → Source: `/docs` on main branch. Free, unlimited leads.

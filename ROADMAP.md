# Plan: Build all sector templates → host on GitHub Pages

## ⚠️ Resume from here (next session on desktop)

**Where we stopped:** Template generation paused mid-batch. Issues found that need fixing before continuing. Resume on desktop where files can be previewed in a browser immediately after writing.

**Known issues to fix first:**
1. `Tourism/Outputs/quad-excursions-teaser.html` — wrong Pexels images (motorcycle/mini-car, not quads). Image IDs need replacing with quad/off-road specific ones.
2. EN toggle goes blank on some templates — agents used inconsistent markup. Fix: always use `<span class="es">` / `<span class="en">` for inline text, and paired `<p class="es">` / `<p class="en">` for block text. Never leave an `.es` element without a matching `.en`.
3. Hiking, Stargazing, Yoga Retreat templates hit rate limit mid-generation — never written. Build from scratch next session.

**Templates done so far (need browser review):**
- `Tourism/Outputs/surf-school-teaser.html` ✓
- `Tourism/Outputs/quad-excursions-teaser.html` ⚠️ wrong images
- `Tourism/Outputs/diving-teaser.html` ✓ (needs review)
- `Tourism/Outputs/water-sports-teaser.html` ✓ (needs review)

**Workflow going forward (one at a time, desktop):**
1. Fix quad template images
2. Open in browser → verify both ES and EN toggle work, images on-topic
3. Commit
4. Write next template directly (no subagents)
5. Open in browser → verify
6. Commit → repeat

**Screenshot capability:** No headless browser on this machine. Visual QA = open file in real browser on desktop.

---

## Source of truth
Sectors come from `RAparcedo/Cold-email-agent` lead scraper. Three main sectors,
each with many subcategories. Not every subcategory needs its own design — grouping
by visual language reduces template count while covering all leads.

---

## Two-phase approach
1. **Phase 1 (now):** Generate all templates and save to `Sector/Outputs/`. Review. Polish.
2. **Phase 2 (after review):** Convert each to URL-param-injected pages in `docs/` on GitHub Pages. Params wiped from address bar via `history.replaceState` — prospect sees a clean URL.

---

## Phase 1 — Full template list

### Tourism (12 templates)
Different activities need clearly different visual languages.

| File | Covers | Design direction |
|---|---|---|
| `Tourism/Outputs/surf-school-teaser.html` | Surf school | Bebas Neue, ocean blue + coral, surf culture |
| `Tourism/Outputs/boat-tours-teaser.html` | Boat tours, catamaran, sailing, whale watching, fishing | Already exists (`azul-cruises`) — review & add toggle |
| `Tourism/Outputs/quad-excursions-teaser.html` | Quad/buggy/jeep tours, off-road | Dusty terracotta, volcanic, rugged adventure |
| `Tourism/Outputs/diving-teaser.html` | Diving, scuba, snorkelling | Deep teal + turquoise, underwater photography |
| `Tourism/Outputs/paragliding-teaser.html` | Paragliding, parasailing | Already exists (`no-parachute`) — review & add toggle |
| `Tourism/Outputs/water-sports-teaser.html` | Kayaking, jet ski, SUP, paddleboarding | Bright, fun, ocean energy — badge sets the specific sport |
| `Tourism/Outputs/hiking-teaser.html` | Hiking, mountain biking, horse riding, ziplines | Earthy greens, Teide landscape, nature-first |
| `Tourism/Outputs/stargazing-teaser.html` | Stargazing tours | Dark navy + gold stars, Teide observatory, ethereal |
| `Tourism/Outputs/yoga-retreat-teaser.html` | Yoga retreats, meditation | Soft neutral + sage, serene, mindful |

### Restaurants (11 templates)
Food culture varies wildly — each needs a distinct appetite and mood.

| File | Covers | Design direction |
|---|---|---|
| `Restaurants/Outputs/canarian-teaser.html` | Traditional Canarian, guachinche, tasca | Rustic warm stone + terracotta, local character, authentic |
| `Restaurants/Outputs/spanish-teaser.html` | Spanish tapas, pintxos, bodega, traditional Spanish | Deep red + cream + olive, tavern warmth, communal |
| `Restaurants/Outputs/seafood-teaser.html` | Seafood restaurant, fresh fish | Ocean teal + sand, open kitchen, coastal freshness |
| `Restaurants/Outputs/burger-teaser.html` | Burger, American, sports bar, pub | Dark & bold, neon accent, appetite-forward |
| `Restaurants/Outputs/pizza-teaser.html` | Pizza, Italian | Warm red + cream + basil green, rustic wood-fired |
| `Restaurants/Outputs/asian-teaser.html` | Sushi, ramen, Japanese, poke bowl | Minimal, dark, neon accent — badge sets the cuisine |
| `Restaurants/Outputs/indian-teaser.html` | Indian | Deep saffron + warm red + gold, ornate, spice-rich |
| `Restaurants/Outputs/thai-teaser.html` | Thai, pan-Asian fusion | Emerald green + gold + dark wood, tropical & aromatic |
| `Restaurants/Outputs/mexican-teaser.html` | Mexican, Tex-Mex | Terracotta + lime + deep red, festive, vibrant, bold |
| `Restaurants/Outputs/brunch-teaser.html` | Brunch, café, bakery, breakfast | Cream + sage + terracotta, airy, Instagram feel |
| `Restaurants/Outputs/rooftop-bar-teaser.html` | Rooftop bar, cocktail bar, wine bar | Dusk palette, city/ocean view, premium nightlife |
| `Restaurants/Outputs/beach-bar-teaser.html` | Beach bar, chiringuito | Bright sand + turquoise + coral, relaxed, tropical |
| `Restaurants/Outputs/steakhouse-teaser.html` | Steakhouse, fine dining, grill | Dark wood + ember red + gold, bold and masculine |
| `Restaurants/Outputs/vegan-teaser.html` | Vegan, vegetarian, healthy | Fresh green + white + earth tones, clean, conscious |

### Real Estate (3 templates — 2 already exist)
| File | Covers | Design direction |
|---|---|---|
| `Real estate/Outputs/casas-del-sur-teaser.html` | Luxury villa sales | Done ✓ |
| `Real estate/Outputs/solaris-estates-teaser.html` | Luxury villa sales (EN) | Done ✓ |
| `Real estate/Outputs/holiday-rentals-teaser.html` | Holiday homes, vacation rentals, Airbnb-style | Warm, approachable, lifestyle-first |
| `Real estate/Outputs/long-term-rentals-teaser.html` | Long-term rentals, property management, relocation | Professional, trust-focused, clean |

### Beauty & Spa (2 templates — 1 already exists)
| File | Covers | Design direction |
|---|---|---|
| `Beauty/Outputs/pop-pimps-teaser.html` | Pimple/acne extraction | Done ✓ |
| `Beauty/Outputs/spa-teaser.html` | Spa, facial, massage, aesthetic clinic | Soft ivory + stone + sage, premium wellness |

### Fitness (3 templates — new sector)
| File | Covers | Design direction |
|---|---|---|
| `Fitness/Outputs/gym-teaser.html` | Gym, strength training, crossfit | Dark, high contrast, bold type, power |
| `Fitness/Outputs/yoga-studio-teaser.html` | Yoga studio, pilates, meditation | Warm neutral + sage, flowing, mindful |
| `Fitness/Outputs/personal-trainer-teaser.html` | Personal trainer, bootcamp | Energetic, results-forward, social proof heavy |

---

## Total: ~29 templates (10 already done or in progress, ~19 new to build)

---

## Phase 1 — Generation rules (all templates)
All templates must follow root `CLAUDE.md` global rules:
- Bilingual ES/EN toggle (fixed pill button, top-right)
- Pexels CDN images with `onerror` fallback
- Tailwind CDN + Google Fonts only
- Hero + 2 sections max
- `<!-- PITCH NOTES -->` block at the end
- Mobile-first, polished, not template-feeling

---

## Phase 2 — GitHub Pages hosting (after review)

### URL param injection
| Param | Required | Purpose |
|---|---|---|
| `n` | Yes | Business name → injected into H1, page `<title>` |
| `t` | Yes | Tagline → injected into hero subheadline |
| `b` | No | Badge text override (e.g. specific activity/cuisine) |
| `c` | No | Accent hex without `#` |

JS reads params, injects into `data-inject="name|tagline|badge"` elements, then wipes URL:
```js
if (location.search) history.replaceState({}, '', location.pathname);
```
Prospect's address bar shows only `demos.yourdomain.com/surf-school` — clean.

Accent via CSS custom property: `:root { --accent: #FF6B4A; }` — JS sets it if `?c=` present.

### File structure (clean URLs)
`docs/surf-school/index.html` → `domain.com/surf-school?n=...&t=...`
One folder per template, all under `/docs`.

### Hosting & deployment workflow
- **One-time setup:** enable GitHub Pages in repo settings → done forever
- **Per lead:** zero deployment — just construct a URL with `?n=` and `?t=` and paste it in the email. Nothing is committed, nothing is deployed.
- **Template design update:** commit the updated HTML → push to main → GitHub Pages auto-rebuilds in ~60 seconds. All existing leads instantly see the updated design (same URL, no re-send needed).
- **Adding a new sector template:** commit new file → push → immediately live. One push, available for all future leads in that sector.
- GitHub Pages: Settings → Pages → Source: `/docs` on main branch
- Custom domain later: `/docs/CNAME` file + DNS CNAME at registrar

---

## Verification checklist (run after each template is generated)
After generating each HTML file, run a quick automated check:
- Open the file in a headless browser (or just parse the HTML) to confirm:
  - [ ] ES/EN toggle button is present before `</body>`
  - [ ] `data-inject` attributes exist on name, tagline, and badge elements
  - [ ] At least one `<img>` tag contains `onerror="this.style.visibility='hidden'"`
  - [ ] `<!-- PITCH NOTES -->` block is present at the end
  - [ ] File is self-contained (no local file references, only CDN URLs)
- Since we can't run a browser headlessly here, verification = `grep` checks on the generated file for the above markers
- Email outreach update (replace screenshot with link) — **deferred until all templates reviewed and approved**

## Build order (Phase 1)
Start with highest-volume scraper categories first:

**Batch 1 — Tourism**
1. Surf school
2. Quad / jeep excursions
3. Diving / snorkelling
4. Water sports (kayaking, SUP, jet ski)
5. Hiking / nature
6. Stargazing
7. Yoga retreat

**Batch 2 — Restaurants**
8. Seafood
9. Burger / American
10. Pizza / Italian
11. Asian (sushi/ramen)
12. Exotic (Indian/Thai/Mexican)
13. Brunch / café
14. Rooftop bar
15. Beach bar
16. Steakhouse
17. Vegan

**Batch 3 — Real estate + Beauty + Fitness**
18. Holiday rentals
19. Long-term rentals
20. Spa / wellness
21. Gym
22. Yoga studio
23. Personal trainer

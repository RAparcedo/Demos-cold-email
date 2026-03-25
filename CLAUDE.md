# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Demos Cold Email — Tenerife Teaser Pages

This project generates **single-screen HTML teaser pages** for cold email outreach targeting Tenerife businesses. Each page is a visual proof of concept to show prospects what their online presence could look like.

## Project Structure

```
/
├── CLAUDE.md                      ← you are here (global rules)
├── Tourism/
│   ├── CLAUDE.md                  ← surf schools, boat tours, excursions, etc.
│   └── Outputs/                   ← generated tourism teasers
├── Restaurants/
│   ├── CLAUDE.md                  ← restaurants, cafés, rooftop bars, etc.
│   └── Outputs/                   ← generated restaurant teasers
└── Real estate/
    ├── CLAUDE.md                  ← property agencies, villa sales, rentals, etc.
    └── Outputs/                   ← generated real estate teasers
```

## Which agent to use

| Business type | Folder to work in |
|---|---|
| Surf school, boat tour, diving, hiking, excursions, whale watching | `Tourism/` |
| Restaurant, café, bar, tapas, brunch, rooftop | `Restaurants/` |
| Property agency, villa sales, rentals, investment | `Real estate/` |

When asked to generate a teaser, identify the sector and use the `CLAUDE.md` in the matching folder.

## Global Rules (apply to ALL agents)

- Output is always a **single self-contained HTML file** — no external dependencies except Tailwind CDN and Google Fonts
- **Not a full website** — hero + **2–3 focused sections max** (e.g. social proof, gallery, stats, dish cards, testimonials). Enough to impress, not enough to replace a real site.
- Always **mobile-first** — design for 390px width first, then scale up
- Use **Tailwind CSS** via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- Load fonts from **Google Fonts** — pick a font that fits the sector (see each agent's CLAUDE.md)
- Use **Pexels CDN** for all images — hardcode photo IDs from the curated pools listed in each sector's CLAUDE.md. No API key or runtime dependency; the CDN is fully public.
  - Full-width / hero: `https://images.pexels.com/photos/{ID}/pexels-photo-{ID}.jpeg?auto=compress&cs=tinysrgb&w=1600`
  - Cards / gallery tiles: `https://images.pexels.com/photos/{ID}/pexels-photo-{ID}.jpeg?auto=compress&cs=tinysrgb&w=800`
  - Pick the most thematically fitting ID from the pool for each slot. Rotate across different IDs per teaser for variety.
  - **Always add `onerror="this.style.visibility='hidden'"` to every `<img>` tag** — if a photo ever fails to load, the page hides it cleanly instead of showing a broken icon.
- Every page must feel **polished and real**, not like a template
- Save all output files to the `Outputs/` folder inside the matching sector folder
- After the HTML, always include a `<!-- PITCH NOTES -->` comment block with 2–3 bullet points explaining why this design converts better than a typical outdated site — written as if pitching directly to the business owner

## Bilingual language toggle (Spanish + English)

Every teaser must include a **fixed ES | EN toggle button** that persists through scrolling. Spanish is the default language. Switching replaces all copy instantly with no page reload.

### Toggle button (copy this exactly into every teaser)

Place immediately before the closing `</body>` tag:

```html
<!-- ─── LANGUAGE TOGGLE ──────────────────────────────────────── -->
<div style="position:fixed;top:1rem;right:1rem;z-index:9999;display:flex;align-items:center;background:rgba(0,0,0,0.62);backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);border:1px solid rgba(255,255,255,0.22);border-radius:999px;overflow:hidden;font-family:inherit;font-size:13px;font-weight:700;letter-spacing:.08em;">
  <button id="btn-es" onclick="setLang('es')" style="padding:.5rem 1.15rem;color:#fff;background:rgba(255,255,255,0.18);border:none;cursor:pointer;transition:background .2s;">ES</button>
  <button id="btn-en" onclick="setLang('en')" style="padding:.5rem 1.15rem;color:rgba(255,255,255,0.55);background:transparent;border:none;cursor:pointer;transition:background .2s,color .2s;">EN</button>
</div>
<script>
  function setLang(l) {
    document.body.classList.toggle('lang-en', l === 'en');
    document.getElementById('btn-es').style.background  = l === 'es' ? 'rgba(255,255,255,0.18)' : 'transparent';
    document.getElementById('btn-es').style.color       = l === 'es' ? '#fff' : 'rgba(255,255,255,0.55)';
    document.getElementById('btn-en').style.background  = l === 'en' ? 'rgba(255,255,255,0.18)' : 'transparent';
    document.getElementById('btn-en').style.color       = l === 'en' ? '#fff' : 'rgba(255,255,255,0.55)';
  }
</script>
```

### CSS rules (add inside the `<style>` block of every teaser)

```css
/* Language toggle — default ES, switch to EN */
.en          { display: none !important; }
span.es      { display: inline; }
body.lang-en .es { display: none !important; }
body.lang-en .en { display: block; }
body.lang-en span.en { display: inline; }
```

### How to mark up bilingual content

Wrap every user-visible string in either `<span class="es">` / `<span class="en">` (inline) or add the class directly to block elements. The active language shows, the other hides.

**Headings and subheadings:**
```html
<h2 class="es">Propiedades Destacadas</h2>
<h2 class="en">Featured Properties</h2>
```

**Labels / badges / stat captions:**
```html
<span class="es">años en el mercado</span>
<span class="en">years in market</span>
```

**Body copy paragraphs:**
```html
<p class="es">Piscina climatizada, jardín tropical y vistas al mar.</p>
<p class="en">Heated pool, tropical garden and sea views.</p>
```

**CTA buttons (single `<a>`, two inner spans):**
```html
<a href="#">
  <span class="es">Ver Propiedades</span>
  <span class="en">Browse Properties</span>
</a>
```

**What NOT to translate:** brand names, property/dish/business names, locations, prices, numbers, star ratings. These are universal — no `.es` / `.en` wrapping needed.

## What NOT to do

- Do NOT add navigation menus, footers, about pages, or contact forms
- Do NOT use gray placeholder boxes — always use real images and real colors
- Do NOT use generic fonts like Arial, Roboto, Inter, or Space Grotesk
- Do NOT over-explain the code — just produce the file
- Do NOT exceed 3 sections total (hero counts as one)
- Do NOT ask unnecessary questions — if inputs are provided, generate immediately
- Do NOT omit the language toggle — every teaser must be bilingual (ES + EN)
- Do NOT show both languages at once — use the toggle pattern above, never stack them

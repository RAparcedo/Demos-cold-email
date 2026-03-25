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

## Bilingual content (Spanish + English)

All teasers must be **bilingual — Spanish primary, English secondary**. This reflects the Tenerife context: local business owners read Spanish, but their customers are largely international tourists.

Rules:
- **Spanish is the primary language** — all main headings, labels, CTAs, and body copy are in Spanish
- **English translation follows** immediately below each key element — smaller font size, lighter opacity (e.g. `text-white/50` or `text-gray-400`), and italic
- **CTA buttons:** Spanish text on top, English in parentheses or a second smaller line below — still one button, not two
- **Stat labels:** Spanish above, English below in light italic
- **Property / dish / activity names:** keep as-is (proper nouns don't need translation)
- Do NOT translate brand names, locations, or prices

Example pattern for a heading:
```html
<h2>Propiedades Destacadas</h2>
<p class="italic text-white/50 text-sm">Featured Properties</p>
```

Example pattern for a CTA button:
```html
<a href="#">
  Ver Propiedades
  <span class="block text-xs font-light opacity-70">(Browse Properties)</span>
</a>
```

## What NOT to do

- Do NOT add navigation menus, footers, about pages, or contact forms
- Do NOT use gray placeholder boxes — always use real images and real colors
- Do NOT use generic fonts like Arial, Roboto, Inter, or Space Grotesk
- Do NOT over-explain the code — just produce the file
- Do NOT exceed 3 sections total (hero counts as one)
- Do NOT ask unnecessary questions — if inputs are provided, generate immediately
- Do NOT produce monolingual teasers — every teaser must be bilingual (ES + EN)

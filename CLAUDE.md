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
- Use **Unsplash CDN** for all images — hardcode photo IDs from the curated pools listed in each sector's CLAUDE.md. No API key or runtime dependency; the CDN is fully public.
  - Full-width / hero: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=1600&q=80`
  - Cards / gallery tiles: `https://images.unsplash.com/photo-{ID}?auto=format&fit=crop&w=800&q=80`
  - Pick the most thematically fitting ID from the pool for each slot. Rotate across different IDs per teaser for variety.
- Every page must feel **polished and real**, not like a template
- Save all output files to the `Outputs/` folder inside the matching sector folder
- After the HTML, always include a `<!-- PITCH NOTES -->` comment block with 2–3 bullet points explaining why this design converts better than a typical outdated site — written as if pitching directly to the business owner

## What NOT to do

- Do NOT add navigation menus, footers, about pages, or contact forms
- Do NOT use gray placeholder boxes — always use real images and real colors
- Do NOT use generic fonts like Arial, Roboto, Inter, or Space Grotesk
- Do NOT over-explain the code — just produce the file
- Do NOT exceed 3 sections total (hero counts as one)
- Do NOT ask unnecessary questions — if inputs are provided, generate immediately

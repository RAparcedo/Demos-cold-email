# Demos Cold Email — Tenerife Teaser Pages

This project generates **single-screen HTML teaser pages** for cold email outreach targeting Tenerife businesses. Each page is a visual proof of concept to show prospects what their online presence could look like.

## Project Structure

```
/
├── CLAUDE.md                      ← you are here (global rules)
├── tourism/
│   ├── CLAUDE.md                  ← surf schools, boat tours, excursions, etc.
│   └── output/                    ← generated tourism teasers
├── restaurant/
│   ├── CLAUDE.md                  ← restaurants, cafés, rooftop bars, etc.
│   └── output/                    ← generated restaurant teasers
└── real-estate/
    ├── CLAUDE.md                  ← property agencies, villa sales, rentals, etc.
    └── output/                    ← generated real estate teasers
```

## Which agent to use

| Business type | Folder to work in |
|---|---|
| Surf school, boat tour, diving, hiking, excursions, whale watching | `tourism/` |
| Restaurant, café, bar, tapas, brunch, rooftop | `restaurant/` |
| Property agency, villa sales, rentals, investment | `real-estate/` |

When asked to generate a teaser, identify the sector and use the `CLAUDE.md` in the matching folder.

## Global Rules (apply to ALL agents)

- Output is always a **single self-contained HTML file** — no external dependencies except Tailwind CDN and Google Fonts
- **No full websites** — one screen only: hero + one optional section max
- Always **mobile-first** — design for 390px width first, then scale up
- Use **Tailwind CSS** via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- Load fonts from **Google Fonts** — pick a font that fits the sector (see each agent's CLAUDE.md)
- Use **Unsplash** for background images: `https://source.unsplash.com/1600x900/?[keyword]`
- Every page must feel **polished and real**, not like a template
- Save all output files to the `output/` folder inside the matching sector folder
- After the HTML, always include a `<!-- PITCH NOTES -->` comment block with 2–3 bullet points explaining why this design converts better than a typical outdated site — written as if pitching directly to the business owner

## What NOT to do

- Do NOT add navigation menus, footers, about pages, or contact forms
- Do NOT use gray placeholder boxes — always use real images and real colors
- Do NOT use generic fonts like Arial, Roboto, Inter, or Space Grotesk
- Do NOT over-explain the code — just produce the file
- Do NOT create more than one screen of content
- Do NOT ask unnecessary questions — if inputs are provided, generate immediately

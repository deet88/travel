# Travel Site — CLAUDE.md

## What this project is

A personal luxury travel showcase for Troy & Hannah documenting 25+ years of world travel (since 1999). The site displays journeys, Michelin dining, countries visited, and an interactive world map. It should feel like a premium editorial travel magazine — refined, not flashy.

## Architecture — read this first

**This is a single-file static site.** All HTML, CSS, and JavaScript live in `index.html`. There is no build system, no package manager, no framework, no bundler, and no backend. Do not introduce any of these.

- If a task can be done with vanilla JS and CSS, it must be.
- External dependencies are limited to what is already present: AmCharts 5 (CDN), Google Fonts.
- Do not add npm, webpack, Vite, React, or any other tooling.

## Data model

All content is hardcoded as JavaScript arrays and objects inside `index.html`. There is no database or API.

- **Journeys** — objects with fields like `id`, `title`, `region`, `date`, `photos`, `description`, `itinerary`, etc.
- **Restaurants** — objects grouped into 1-star, 2-star, 3-star Michelin tiers.
- **Countries** — array of objects with name, emoji flag, and activity tags (`scuba`, `dining`, `driven`).

When adding a new journey, restaurant, or country: find the existing array in `index.html`, copy the shape of an existing entry, and append. Do not invent new fields without understanding how the rendering code uses them.

## Visual system — do not deviate

| Element | Value |
|---|---|
| Primary palette | Gold (`#c9a96e`), Cream (`#f5f0e8`), Charcoal (`#1a1a1a`) |
| Heading font | Cormorant Garamond (serif) |
| Body font | Montserrat (sans-serif) |
| Layout | Responsive CSS grid; mobile-first |

Never change the color palette or fonts without explicit instruction. New UI elements must match the existing aesthetic.

## Photo conventions

- Galleries live at `/photos/<trip-slug>/` (e.g., `/photos/japan-2026/`)
- Reference photos by relative path in the journey data object
- Photos should be reasonably optimized before adding (aim for web-ready JPEGs)

## Dev workflow

Start the local server:

```bash
python3 -m http.server 8899
```

Then open `http://localhost:8899` in a browser. There is no hot-reload — refresh manually after edits.

## Key invariants — never violate these

- **Never add a build step.** The site must remain deployable by dropping files on any static host.
- **Never break the world map.** The AmCharts 5 map has a specific initialization pattern; test it after any JS changes near it.
- **Never add a backend.** No Node server, no API routes, no database connections.
- **Never change the typography or color palette** without explicit instruction.
- **Minimal diffs.** Touch only the code required for the task. Leave everything else exactly as found.

## Memory and error logs

Read these at the start of every session:

- `MEMORY.md` — decisions made, alternatives rejected, session summaries
- `ERRORS.md` — approaches that failed and what worked instead

Before suggesting a solution to a problem that has been attempted before, check `ERRORS.md`. After any significant decision, update `MEMORY.md`.

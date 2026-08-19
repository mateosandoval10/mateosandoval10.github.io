# mateosandoval10.github.io

Portfolio hub — quantitative research by Mateo Sandoval.

Static site. No build step, no framework, no external CDN, no fonts fetched from a third party.
GitHub Pages serves this repository directly.

## Pages

| File | Section |
|---|---|
| `index.html` | Landing |
| `research.html` | Research methodology — placebo testing, bootstrap CIs, frozen-config OOS. The centerpiece. |
| `profit-pilot.html` | Profit Pilot — event-driven trading platform |
| `strategies.html` | Systematic strategies overview |
| `cbs.html` `vtte.html` `crs.html` `qv2.html` | Individual strategy research notes |
| `projects.html` | Research tooling in development |
| `about.html` | Background and contact |
| `styles.css` | The whole design system, light + dark |

## Local preview

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## File ownership (2026-08-18)

`profit-pilot.html` is owned by the hub session. Everything else in this repo is Workstream A's.
Do not edit a file you do not own while the other session is active — an earlier concurrent write
silently dropped four features from the Profit Pilot page.

## Conventions

- **Every page carrying numbers carries a limitations section.** This is not optional.
- **No fabricated data and no mock output.** Empty states stay empty until there is something real.
- **No performance claim for Profit Pilot** — no P&L, return, win rate, Sharpe or drawdown figure.
  See `BRIEF.md` §3 in the applications directory.
- Screenshots of the Profit Pilot console render the frontend's demo dataset and **must** be
  captioned as such, in words, next to the image.
- **Dark is the default theme**; light is fully supported and both are WCAG AA. Theme is set by an
  inline script in each page's `<head>` (prevents a flash of the wrong theme) and persisted to
  `localStorage`.
- All pages share `styles.css`. Do not give a page its own `<style>` block — that is how the site
  starts looking like two sites.
- Page shape: `<main>` → `header.hero` → `.statband` → `<section><div class="wrap reveal">`.

## Assets

`assets/pp/*.webp` — Profit Pilot console screenshots, 1600px WebP, derived from the Workstream B
handoff in `assets/profit-pilot/` (gitignored: ~18 MB of PNG originals). Regenerate with Pillow if
the originals change.

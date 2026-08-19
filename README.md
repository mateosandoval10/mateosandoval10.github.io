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
| `strategies.html` | Systematic strategies — a full section, incl. published TradingView scripts |
| `projects.html` | Research tooling in development |
| `about.html` | Background and contact |
| `styles.css` | The whole design system, light + dark |

## Local preview

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Write ownership

**Workstream A holds sole write access to this repository and is the only session that commits or
pushes it.** Other sessions hand off through `assets/` for images and through messages or markdown files
for copy — not by editing, deleting, restoring or committing files here.

Three concurrent-write incidents on 2026-08-18 prompted this: pages restored and then deleted again while
being actively edited, and an uncommitted working tree committed by another session. The repo is public and
live, so a half-finished commit is immediately visible.

If something must be reverted urgently and A is unresponsive, take it — but say so, so it is not re-applied.

**Do not remove the `.js` gate on `.reveal` in `styles.css`.** Without it, pages render blank when
JavaScript is disabled, in print, or in a background viewport. That shipped once already.

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

## Strategy research notes live off-site

The four long-form notes (CBS, VTTE, CRS, QV v2) are **not** duplicated here. They live on the already-public
sub-site at <https://mateosandoval10.github.io/quant-strategies/> and `strategies.html` links out to each one.
One copy of every figure — do not re-import them, or the numbers will drift between two live sites.

## Screenshot provenance — get this right

`assets/pp/*.webp` splits two ways and the captions must match:

- **Live production captures** (command-deck, allocator, conviction-board, charts, orders-history,
  catalyst-calendar, news-feed, sleeve-toggles, settings-ai) — captured from the deployed instance.
  Account balances and position values are redacted; percentages, ratios, weights, concentration, drift
  and counts are intact. The account is a **paper** account. Caption these as live production, never as
  sample data.
- **Demo-mode captures** (risk-spine-console, self-improvement-loop, stress-scenario-lab, sim-replay,
  calibration-lab, loss-day-analyzer, telemetry, liquidity-forecaster, and the unused catalysts-intel,
  compliance, execution-afr) — the frontend's bundled sample dataset. Caption these as demo mode, never
  as live.

Captioning either one as the other is the failure mode. `pp-console.html` separates them into two
sections so it cannot be got backwards by accident.

## Assets

`assets/pp/*.webp` — Profit Pilot console screenshots, 1600px WebP, derived from the Workstream B
handoff in `assets/profit-pilot/` (gitignored: ~18 MB of PNG originals). Regenerate with Pillow if
the originals change.

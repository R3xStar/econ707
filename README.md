# ECON 707/807 — Econometrics II: Time Series and Forecasting

Course site for the eight-week accelerated session. Quarto book published to GitHub Pages
from `docs/`.

**Live:** <https://r3xstar.github.io/econ707/>

---

## What's here

A course hub, not a textbook. The eight week pages carry the topic, reading, and
deliverables; the lecture slides are revealjs decks that open in their own tab.

| Path | What it is |
|---|---|
| `_quarto.yml` | Book structure — parts, chapter order, resources |
| `index.qmd` | Home page: schedule table and start-here links |
| `about.qmd` | Course information — objectives, texts, grading, policies |
| `sitti.qmd` | Instructor page |
| `week-1.qmd` … `week-8.qmd` | One page per module week |
| `slides/` | **Rendered** lecture decks (`.html`), copied into `docs/slides/` on render |
| `lecture-src/` | The `.qmd` sources for those decks |
| `docs/` | The rendered site — this is what GitHub Pages serves |
| `ECON-707-Syllabus.pdf` | The syllabus, also copied into `docs/` |

## Rendering

The eleven book pages contain no R code, so plain Quarto renders the site with no R
packages needed:

```bash
quarto render
```

The lecture decks are a separate matter. They are **not** rendered by `quarto render` —
`lecture-src/` is excluded from the project. To update a deck, render it on its own and
copy the result into `slides/`:

```bash
quarto render lecture-src/var_improved_12.qmd
cp lecture-src/var_improved_12.html slides/
quarto render          # copies slides/ into docs/slides/
```

That requires the time-series packages the decks use (fpp3, forecast, vars, tsibble, and
so on). Keeping the decks out of the main render means the site always builds even if a
package is missing.

## Publishing changes

```
edit → quarto render → commit → push
```

In GitHub Desktop: write a summary, "Commit to main", then "Push origin". Live in about a
minute. Pages is set to deploy from branch `main`, folder `/docs`.

## Known TODOs

- [ ] Deck footers still read **"Spring 2026"** and their subtitles use the sixteen-week
      numbering (ARMA is labelled Week 6, VAR is Week 12, etc.). The site maps them to the
      correct eight-week modules, but the slides themselves say otherwise until you
      re-render them from `lecture-src/`.
- [ ] Add your photo: drop it in `images/` and uncomment the line in `sitti.qmd`.
- [ ] Session dates — the syllabus and week pages say "Week 1", "Week 2" rather than
      calendar dates. Add them once the session calendar is confirmed.
- [ ] Week 8 currently links the Model Selection deck as review material. Move it if you'd
      rather it sat with Week 4.

## Deliberately not in this repo

This is a public repository. The following were left out on purpose:

- **Wooldridge publisher PowerPoints** (`FINAL files- from Hishma-copyedited`) — Cengage
  instructor resources, not redistributable.
- **Exams and homework** — answer keys do not belong on a public site. Keep them in Canvas.
- **`trends_03.qmd`** — authored by Alex Cardazzi. Your own `trend_models_improved_3` is
  used instead.
- **Spatial econometrics** — not part of the eight-week schedule; per the syllabus it goes
  in Canvas as optional enrichment.

## Origin

The site's scaffolding started from the ECON 700 Quarto site by Robert M. McNab
(<https://github.com/robertmmcnab/econ700>). All of that content has since been replaced;
what remains in common is the Quarto book format itself.

Built with [Quarto](https://quarto.org).

# ECON 707 / 807 — Course Site

Quarto book with interactive WebR examples, published to GitHub Pages from `docs/`.

Live URL once published: **https://r3xstar.github.io/econ707/**

---

## What this is

A mirror of the ECON 700 course site by Robert M. McNab (ODU), rebranded for ECON 707.
The module content is still McNab's intro-statistics sequence — swap it out for your
time-series material as you go. See **Attribution** below.

## First-time setup: push to GitHub

1. Create an **empty** repo on GitHub named `econ707` under the `R3xStar` account.
   Do *not* add a README, .gitignore, or license — this folder already has a commit.

2. From this folder:

   ```bash
   git remote add origin https://github.com/R3xStar/econ707.git
   git branch -M main
   git push -u origin main
   ```

3. On GitHub: **Settings → Pages → Build and deployment**
   - Source: *Deploy from a branch*
   - Branch: `main`, folder: `/docs`
   - Save. The site is live in a minute or two.

`docs/.nojekyll` is already present, which stops GitHub from stripping the
`_files/` asset folders Quarto generates.

## Editing and re-rendering

You need Quarto (bundled with recent RStudio) and these R packages:

```r
install.packages(c("tidyverse", "dplyr", "ggplot2", "kableExtra", "janitor",
                   "lubridate", "scales", "moments", "gtools", "tidyquant",
                   "censusapi"))
```

Then, in the project folder:

```bash
quarto render          # writes HTML into docs/
git add -A && git commit -m "Update modules" && git push
```

Open `econ707.Rproj` in RStudio and use the **Build → Render Book** button if you
prefer not to use the terminal.

Note: a few chunks use `censusapi`, which needs a free Census API key. Either set
`CENSUS_KEY` in your `.Renviron` or edit those chunks out.

## File map

| Path | What it is |
|---|---|
| `_quarto.yml` | Book structure — parts, chapter order, WebR settings |
| `index.qmd` | Home page with the module link list |
| `sitti.qmd` | Instructor page — **has TODOs for your phone and office hours** |
| `about.qmd` | Course objectives and textbooks — **still McNab's CLOs, rewrite these** |
| `mod-N-M-*.qmd` | Module pages |
| `docs/` | Rendered site (this is what GitHub Pages serves) |
| `_extensions/coatless/webr` | The WebR filter that makes R chunks runnable in the browser |
| `ECON-707-Syllabus.pdf` | Placeholder — replace with your syllabus, keep the filename, put a copy in `docs/` too |

## Still to do

- [ ] Replace `ECON-707-Syllabus.pdf` (root **and** `docs/`) with your syllabus
- [ ] Fill in the TODOs in `sitti.qmd` (phone, office hours, optional photo in `images/`)
- [ ] Rewrite `about.qmd` — the learning objectives and textbook list are McNab's
- [ ] Replace module content with your time-series material (ARDL, VAR, ECM, cointegration)
- [ ] Update `_quarto.yml` part names as the topics change

## Attribution

Content adapted from <https://robertmmcnab.github.io/econ700/> (source:
<https://github.com/robertmmcnab/econ700>). That repository carries no license file,
so reuse is not formally granted — worth a quick email to Bob McNab before this goes
public, especially since he's in your department.

Built with [Quarto](https://quarto.org) and the
[coatless/quarto-webr](https://github.com/coatless/quarto-webr) extension.

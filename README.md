# marthazillig.github.io

Source for Martha Zillig's lab website — plain HTML/CSS/JS, no build step, deploys
directly on GitHub Pages.

## Structure

```
index.html                    Home page
research.html                 Research areas / project index
research-project-example.html Template for an individual project page — copy per project
publications.html             Publications list
people.html                   Lab members
cv.html                       CV (web version + PDF download)
links.html                    Datasets, tools, other resources

assets/css/style.css          All styling (design tokens at the top)
assets/js/main.js             Mobile nav toggle
assets/img/                   Photos — replace the placeholders
assets/pdfs/                  Publication PDFs + BibTeX export
assets/cv/                    CV PDF
```

## Replace before publishing

1. **Photos** — swap out the placeholder images in `assets/img/`:
   - `about-photo.jpg` (portrait, ~4:5) — used in the hero
   - `about-photo-square.jpg` (1:1) — used in About and People
   - `project-photo.jpg` — used on project detail pages
   - `placeholder-person.jpg` — used per lab member on `people.html`
   - Keep the same filenames, or update the `src=` in the HTML if you rename them.

2. **Bio & stats** — edit the About section and stats bar in `index.html`.

3. **Research projects** — edit the cards in `index.html` and `research.html`.
   For each real project, copy `research-project-example.html` to a new file
   (e.g. `research-shorebird-survival.html`) and link to it from `research.html`.

4. **Publications** — edit `publications.html` and the "Recent Publications" section
   in `index.html`. Drop real PDFs into `assets/pdfs/` and update the `href`s.
   Export a real `.bib` file to replace `assets/pdfs/zillig-publications.bib`.

5. **CV** — edit the entries in `cv.html`, and replace `assets/cv/Zillig-CV.pdf`
   with your actual CV exported as a PDF (same filename, or update the download
   link in `cv.html`).

6. **People** — edit `people.html` with real lab members, or delete the page and
   its nav link if you're solo.

7. **Links** — edit `links.html` with your real datasets, tools, and resources.

8. **Contact links** — the email (`you@example.edu`), GitHub, and Google Scholar
   links in the footer/nav appear on every page — search-and-replace across all
   `.html` files once you have final links.

## Preview locally

No build tools needed — just open `index.html` in a browser, or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy

```bash
git add .
git commit -m "Overhaul site"
git push origin main
```

GitHub Pages rebuilds automatically since this repo is `marthazillig.github.io`
(a user page) — no Pages configuration needed. Changes usually go live within
a minute or two.

## Adding a new project page

1. Copy `research-project-example.html` → `research-<slug>.html`.
2. Update the `<title>`, eyebrow/tag, heading, and body content.
3. Add a card linking to it in `research.html` (and optionally `index.html`
   if it should appear in the homepage's featured research).

## Design notes

- Colors and fonts are defined as CSS custom properties at the top of
  `assets/css/style.css` (`:root { ... }`) — change them once, and they
  update sitewide.
- The dashed horizontal rule (`.divider-feather`) and the specimen-label
  cards (`.tag` + `.accession`) are the site's signature visual motifs —
  reuse them if you add new sections.

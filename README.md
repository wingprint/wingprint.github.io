# WingPrint — project & dataset landing page

A single-file, dependency-free landing page for the WingPrint bat re-identification
project. Built to help with paper submission and, later, with disseminating the
datasets. Just static HTML/CSS/JS — ideal for GitHub Pages.

---

## Deploy on GitHub Pages

1. Put `index.html` (and the `assets/` folder) in the repository that serves your
   site — either `<username>.github.io` (root) or any repo with Pages enabled.
2. In the repo: **Settings → Pages → Build and deployment → Deploy from a branch**,
   pick your branch and `/ (root)`.
3. Done. The Google Fonts load automatically over the network — no build step.

To preview locally, just open `index.html` in a browser, or run:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

---

## Customise (no HTML needed)

### 1. Images — drop-in, auto-detected
Place files in `assets/` with these **exact names**. Each appears automatically as
soon as it exists; until then a clean placeholder is shown. No code editing.

| File | Shows up as | Format | Status |
|------|-------------|--------|--------|
| `assets/intro.mp4` + `.webm` + `intro-poster.jpg` | Hero video, right column | **5:4**, muted autoplay loop | ✅ embedded |
| `assets/approach.mp4` + `.webm` + `approach-poster.jpg` | Behaviour clip (competition at the feeder) | **4:3**, e.g. 720×540 | you'll add |
| `assets/manual-scanner.jpg` | Manual scanner (Plate II) | 16:9 | ✅ embedded |
| `assets/inflight-scanner.jpg` | In-flight rig (Plate III) | 16:9 | ✅ embedded |
| `assets/wing-01.jpg` … `wing-06.jpg` | Gallery, 6 species | landscape ~8:5 | ✅ embedded |
| `assets/og.jpg` | Social-share preview | 1200×630 | optional |

The hero plays a muted, looping video (5:4). Your `intro.gif` was ~100 MB, far too heavy for the web and over GitHub's 100 MB file limit, so it was transcoded to `intro.mp4` (3.5 MB) and `intro.webm` (1.6 MB) with a poster still. Replace those three files to update it.

For the behaviour section, convert your clip to video and drop it at `assets/approach.mp4` / `.webm` with a poster still (4:3, e.g. 720×540 — the native format of the in-flight recordings). Never commit the raw GIF: GitHub rejects files over 100 MB, and `*.gif` is in `.gitignore` for that reason. GIFs get heavy fast — if it exceeds a few MB, send it over and I'll convert it to video like the hero.

> If you prefer `.webp`, either rename the file to `.jpg` or update the matching
> `data-img="assets/…"` path in `index.html`.

### 2. Links — search & replace
Replace these three placeholders throughout `index.html`:

- `#DATASET_DOI` → Zenodo / DOI of the datasets
- `#PAPER_URL` → arXiv / journal / PDF
- `#CODE_URL` → GitHub repository

### 3. Numbers
The **Results** section holds current-draft figures (the manuscript still has a few
TBD tables and a small mismatch, e.g. 91.7 % in the abstract vs. 90.3 % mean in
Table 2). Swap in the final values before submission.

### 4. Logos & author links
Replace the `.logo-ph` placeholders in the Authors section with real logos, and
point each author's `<a href="#">` to their profile if desired.

---

## Gallery species (edit captions in the `#gallery` section if needed)
Saccopteryx · Noctilio · Pteronotus · Carollia · Glossophaga · Molossus · Myotis · Artibeus

## Design notes
- Direction: archival naturalist monograph — the wing as an ink specimen plate.
- Accent: Prussian blue (a nod to cyanotype / scientific-plate imaging).
- Type: Spectral (serif) + IBM Plex Mono (labels), via Google Fonts.
- Accessibility: keyboard focus states, skip link, reduced-motion respected.

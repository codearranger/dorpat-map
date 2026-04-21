# Seattle Now & Then — Interactive Map

An interactive, sepia-toned map of all 303 buildings and sites featured in
Paul Dorpat's three-volume *Seattle Now & Then* (1984, 1986, 1990).

Each pin opens the historical "then" photograph along with the title,
volume/feature/page citation, location note, and an excerpt of Dorpat's
write-up. The sidebar supports full-text search and per-volume filtering.

## Contents

- `index.html` — the entire app (data embedded inline)
- `leaflet.js`, `leaflet.css`, `images/` — Leaflet 1.9.4 (self-hosted)
- `thumbs/` — 303 sepia-toned page thumbnails (~8 MB)

## Publishing to GitHub Pages

From this folder, with the `gh` CLI authenticated:

```bash
git add .
git commit -m "Initial commit: Seattle Now & Then map"
gh repo create dorpat-map --public --source=. --push
gh api -X POST repos/:owner/dorpat-map/pages \
  -f 'source[branch]=main' -f 'source[path]=/'
```

The page URL will be `https://<your-username>.github.io/dorpat-map/`
(usually live within a minute or two — check `gh api repos/:owner/dorpat-map/pages`
for status).

## License / attribution

Historical images and text are excerpts from Paul Dorpat's
*Seattle Now & Then* (vols. 1–3). This repo is for personal/educational use;
please credit Dorpat if sharing.

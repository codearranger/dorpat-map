# Seattle Now & Then — Interactive Map

An interactive, sepia-toned map of all 303 buildings and sites featured in
Paul Dorpat's three-volume *Seattle Now & Then* (1984, 1986, 1990), plus
all 516 City of Seattle designated landmarks.

Each Dorpat pin opens the historical "then" photograph along with the title,
volume/feature/page citation, location note, and an excerpt of Dorpat's
write-up. Each landmark pin opens the official photo, designation date,
address, designation report PDF, and ordinance link. The sidebar supports
full-text search across both layers, per-volume filtering, and per-layer
toggles.

## Contents

- `index.html` — the entire app (Dorpat features embedded inline)
- `landmarks.js` — 516 landmark records (name, address, lat/lon, photo,
  designation report, ordinance), pulled from the Seattle.gov ArcGIS
  FeatureServer at `services.arcgis.com/ZOyb2t4B0UYuYNYH`
- `leaflet.js`, `leaflet.css`, `images/` — Leaflet 1.9.4 (self-hosted)
- `thumbs/` — 303 sepia-toned page thumbnails (~8 MB)

## Publishing to GitHub Pages

From this folder, with the `gh` CLI authenticated:

```bash
git add .
git commit -m "Initial commit: Seattle Now & Then map"
gh repo create dorpat-map --public --source=. --push
gh api -X POST repos/:owner/dorpat-map/pa
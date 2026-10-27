# AETHERIA — The Floating Isles

A single-file WebGL voxel world: 33 drifting isles, a vermilion pagoda, a stone
moon-gate approach, sky rays and jellyfish, waterfalls into an endless cloud sea,
a slow cinematic camera tour, and a procedural score (bells, drone, wind, water,
birdsong) synthesised in the browser.

Everything — geometry, textures, sky, audio and the Three.js r170 build — lives in
`index.html` (≈1.5 MB). No CDN, no fonts, no images, no network requests at view time.

## Controls

- The tour starts on load: 12 stops, one slow orbit, dawn → day → sunset → night → dawn.
- Drag to orbit, scroll to zoom. `Space` pauses the tour, `R` restarts it.
- Sound unlocks on first click (browser autoplay policy); toggle with `SOUND ON/OFF`.

## Publish to GitHub Pages

```bash
cd publish
git init
git add index.html .nojekyll README.md
git commit -m "AETHERIA — the floating isles"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```

Then in the repository: **Settings → Pages → Source: Deploy from a branch → main / (root)**.
The site appears at `https://<you>.github.io/<repo>/`.

Or with the GitHub CLI, from this folder:

```bash
gh repo create <repo> --public --source=. --push
gh api -X POST "repos/<you>/<repo>/pages" -f "source[branch]=main" -f "source[path]=/"
```

## Notes

- GitHub Pages serves it as-is; the file must be named `index.html` at the site root
  (or under `/docs`) to appear at the repository URL. `.nojekyll` keeps the file untouched.
- Size is well inside the Pages limits (1 GB site, 100 GB/month bandwidth).
- Three.js is MIT licensed; its license header is preserved inside `index.html`.

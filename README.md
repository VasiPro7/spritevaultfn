# ◆ SpriteVaultFN

A Fortnite sprite collection tracker. Browse every sprite, mark the ones you **own** and have **mastered**, filter and sort the list, post trade offers, and export your collection as an image or a text file. Everything is saved in your browser — no account, no backend.

**Live site:** https://spritevaultfn.pages.dev

## Features

- Sprite catalog with search, variant, rarity, season and status filters
- Own / Master tracking with progress ring and stats
- Collection page with **Save as image** (PNG) and **Save as text** (.txt) export
- Local trade board (name · offer · want)
- Variants page grouping sprites by variant
- Dark, AMOLED and Light themes, plus three grid densities
- Responsive layout for phones and desktop

Roster current as of October 10, 2026 (Chapter 7 Season 4 · Override, patch v42.30).

## Project structure

```
index.html   The whole site (markup, styles and scripts in one file)
README.md    This file
```

## Run locally


It is a static site with no build step. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy

Any static host works.

- **Cloudflare Pages:** connect the GitHub repo, leave the build command empty, set the output directory to `/` (the repo root).
- **GitHub Pages:** Settings → Pages → deploy from the `main` branch, root folder.

## Updating the roster

Sprites live in the `RAW` array inside the `<script>` in `index.html`. Per-sprite powers are in the `ABILITY` object, and variant bonuses are in `VARIANT_BONUS`. To add a new sprite family, add its `_basic`, `_gold`, `_cheat`, `_hacker`, `_bounty` and `_trick` entries to `RAW`, and an `ABILITY` entry keyed by the family name (the part of the id before the first underscore).

Sprite images load from `https://staticvacant.github.io/fnsprites/sprites/<id>.png`, with the official in-game icons as a backup (see `ALT_STEMS`).

## Disclaimer

Not affiliated with Epic Games. Sprite art © Epic Games, used for identification only.

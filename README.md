# slsc

A collection of small interactive pieces. Each one is a self-contained page — no build step, no install.

| # | Piece | Stack |
|---|-------|-------|
| 01 | [3 A.M. Vending Machine](works/3am-vending-machine/) | three.js, WebGL, Web Audio |

## Layout

```
index.html              gallery page
works/<slug>/
  index.html            the piece (loads its libraries from a CDN)
  thumb.webp            1200×750 gallery thumbnail
shared/                 (create once 2+ pieces reuse code)
```

## Run locally

Pieces use ES modules, so serve the folder rather than opening files directly:

```sh
python3 -m http.server 8000
# → http://localhost:8000
```

## Adding a piece

1. Create `works/<slug>/index.html`.
2. Add a 1200×750 `thumb.webp` screenshot.
3. Copy a `<li class="work">` entry in `index.html` (newest first) and add a row above.

## Debug flags

`3am-vending-machine` accepts URL hashes: `#fps` (frame rate + render size overlay), `#nobloom`, `#noarea`.

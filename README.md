# slsc

**slices** — slices of my mind, everything I might come up with. This repo exists so I can nurture the artist inside me.

Live: https://tyler-void.github.io/slsc/

Each slice is a self-contained page: no build step, no install. The hub shows them as frames on one strip of hand-processed film, newest first.

| # | Slice | Stack |
|---|-------|-------|
| 01 | [3 A.M. Vending Machine](works/3am-vending-machine/) | three.js, WebGL, Web Audio |

## Layout

```
index.html              the hub (a strip of film; one frame per slice)
works/<slug>/
  index.html            the slice (loads its libraries from a CDN)
  thumb.webp            1200×750 still for its frame
PRODUCT.md              what this repo is for
DESIGN.md               the hub's design system (derived from Enhalation.md)
shared/                 (create once 2+ slices reuse code)
```

## Run locally

Slices use ES modules, so serve the folder rather than opening files directly:

```sh
bunx serve .
```

## Adding a slice

1. Create `works/<slug>/index.html`.
2. Add a 1200×750 `thumb.webp` still (optional: a slice without a picture stays clear leader).
3. In `index.html`, copy the `<div class="frame">` block to the top of the reel and bump the frame number; add a row to the table above.

## Debug flags

`3am-vending-machine` accepts URL hashes: `#fps` (frame rate + render size overlay), `#nobloom`, `#noarea`.

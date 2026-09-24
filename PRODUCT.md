# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Static HTML/CSS/JS, no build step, deployed to GitHub Pages. Each piece is a self-contained page that loads its libraries from a CDN. Bun is the runtime for any tooling scripts (e.g. `bunx serve` locally); no package.json or bundler.

## Users

Primarily the author: a personal sketchbook they return to, add to, and use to keep making things. Secondarily anyone who wanders in (friends, strangers from GitHub). Nobody needs to be convinced of anything.

## Product Purpose

slsc = "slices" — slices of the author's mind, everything they might come up with. The repo exists so the author can nurture the artist inside them. Success is the author keeps adding pieces and enjoys opening the hub; a visitor can find a piece and step into it quickly.

## Positioning

Not a portfolio and not a product showcase. An open, growing drawer of experiments where finished and half-finished things sit side by side, made for the joy of making.

## Operating Context

Pieces live in `works/<slug>/index.html` with a `thumb.webp` (1200×750). The hub (`index.html`) lists them by hand, newest first. Opened on desktop (including a 3440×1440 ultrawide on Intel integrated graphics) and phones.

## Capabilities and Constraints

- Expected piece types: 3D/WebGL scenes, small games/toys, generative/visual art, and writing/sound/other non-visual experiments. The hub must not assume every slice has a thumbnail-worthy visual.
- Hub must stay light: it must not run heavy WebGL itself; the pieces are the heavy part.
- Adding a piece should be one folder plus one hand-edited entry.

## Brand Commitments

- Name: **slsc**, read as "slices". Anonymous: the handle (tyler-void) appears only in the footer / GitHub link, not as the headline.
- Voice: warm, lowercase-leaning, personal, a little playful; not corporate, not self-promotional.

## Evidence on Hand

- One piece: `works/3am-vending-machine/` ("A bus stop in the rain. A machine that never closes. One regular, most nights."), three.js + WebGL + Web Audio, 2026, thumbnail on disk.
- No bio, no press, no testimonials, no other pieces yet — do not invent them.

## Product Principles

1. The work leads; the hub gets out of the way.
2. Every slice is equally welcome — finished, rough, visual or not.
3. Adding a slice must stay effortless, or the author will stop adding them.
4. Personal over polished-corporate.

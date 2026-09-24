---
name: slsc
description: Slices of my mind, kept as frames on one strip of hand-processed 16mm film.
colors:
  ground-deep: "#11111b"
  ground-sunken: "#181825"
  ground: "#1e1e2e"
  ink: "#cdd6f4"
  ink-muted: "#a6adc8"
  line: "#45475a"
  line-strong: "#6c7086"
  halo-1: "#fab387"
  halo-2: "#f5c2e7"
  halo-3: "#cba6f7"
  spark: "#94e2d5"
  rosewater: "#f5e0dc"
  on-halo: "#11111b"
  glass-fill: "#232334d6"
typography:
  display:
    fontFamily: "Bricolage Grotesque, Geist, system-ui, sans-serif"
    fontSize: "clamp(56px, 7.6vw, 96px)"
    fontWeight: 720
    lineHeight: 0.9
    letterSpacing: "-0.04em"
    fontVariation: "\"opsz\" 96"
  flourish:
    fontFamily: "Instrument Serif, Georgia, serif"
    fontSize: "1.04em"
    fontWeight: 400
    letterSpacing: "-0.01em"
  title:
    fontFamily: "Bricolage Grotesque, Geist, system-ui, sans-serif"
    fontSize: "clamp(28px, 2.9vw, 40px)"
    fontWeight: 620
    lineHeight: 1
    letterSpacing: "-0.025em"
    fontVariation: "\"opsz\" 48"
  body-lg:
    fontFamily: "Geist, system-ui, -apple-system, Segoe UI, sans-serif"
    fontSize: "18px"
    fontWeight: 400
    lineHeight: "28px"
  body:
    fontFamily: "Geist, system-ui, -apple-system, Segoe UI, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: "24px"
  action:
    fontFamily: "Geist, system-ui, -apple-system, Segoe UI, sans-serif"
    fontSize: "15px"
    fontWeight: 560
    lineHeight: "20px"
  label:
    fontFamily: "Geist Mono, ui-monospace, monospace"
    fontSize: "11px"
    fontWeight: 500
    lineHeight: "16px"
    letterSpacing: "0.14em"
    fontFeature: "\"tnum\" 1"
  pencil:
    fontFamily: "Caveat Brush, cursive"
    fontSize: "28px"
    fontWeight: 400
    lineHeight: 1
    letterSpacing: "0.01em"
rounded:
  xs: "6px"
  sm: "8px"
  film: "12px"
  core: "18px"
  glass: "26px"
  glass-compact: "20px"
  full: "50%"
spacing:
  gutter: "clamp(16px, 3.4vw, 48px)"
  rail: "44px"
  cap: "2240px"
  stage-gap: "clamp(32px, 5vw, 88px)"
  section: "112px"
  section-compact: "72px"
components:
  core-action:
    backgroundColor: "{colors.halo-1}"
    textColor: "{colors.on-halo}"
    typography: "{typography.action}"
    rounded: "{rounded.core}"
    padding: "0 44px"
    height: "54px"
  glass-caption:
    backgroundColor: "{colors.glass-fill}"
    textColor: "{colors.ink}"
    rounded: "{rounded.glass}"
    padding: "20px 24px 22px"
  reel:
    backgroundColor: "{colors.ground-sunken}"
    padding: "28px 56px 150px"
  film-frame:
    rounded: "{rounded.film}"
    padding: "26px 0 30px"
  nav-link:
    textColor: "{colors.ink}"
    typography: "{typography.label}"
  nav-link-hover:
    textColor: "{colors.halo-2}"
  edge-print:
    textColor: "{colors.ink-muted}"
    typography: "{typography.label}"
    width: "{spacing.rail}"
---

# Design System: slsc

Scope: this file covers the hub surface (`index.html`) only. Each piece under `works/<slug>/` is a self-contained artwork with its own look; none of the rules below apply inside a piece, and nothing from a piece flows back into the hub.

Upstream: the hub's tokens derive from **Enhalation** (`Enhalation.md`), the author's own design system on Catppuccin Mocha. Color values, the warm-core gradient, grain, glass, focus ring, the type families, and the easing curves come from Enhalation unchanged. The film materials (strip, perforations, frames, halation, leak, scratches, edge print, grease pencil, burn) are the hub's own. Where the two differ, this file records what the hub actually ships.

## Overview

**Creative North Star: "One Strip of Hand-Processed Film"**

The hub is a single strip of 16mm film on a dark leader. Every slice is one frame, and the strip grows downward, newest first. Frames rest as grayscale emulsion with grain and faint scratches. The frame crossing the middle of the viewport is "in the gate": its own highlights halate in Enhalation's warm core, a light leak floods in from its right edge, and colour starts to develop from that side. Hovering or focusing the frame develops it fully. Entering a slice burns the film in the gate before the page changes.

The page is quiet and dark, with generous air and very few voices. The light is the event. Warm light shows up in exactly two places at once: the frame in the gate and the one core action. Everything else is the materials of a film bench: Mocha leader, sunken film base, punched sprockets, a monospace edge print down the margin, and rosewater grease pencil for the hand-made marks. Glass is used once, for the caption that floats over each frame's lower edge. It is the one element allowed to break the grid.

The system rejects the thumbnail-card grid. Slices are frames on a strip, never tiles in a gallery.

**Key Characteristics:**
- Dark Mocha leader (`ground-deep`) with a sunken film base (`ground-sunken`) for the reel.
- Grayscale frames at rest; warm-core halation, a leak, and colour only for the frame in the gate.
- One warm-core action per view, sprocket-punched like leader.
- Glass caption overlapping each frame's lower edge, with a grease-pencil frame numeral.
- Geist Mono edge print in the margins; Caveat Brush grease pencil for hand marks.
- Grain over the whole page, stronger on everything that glows.
- One authored transition: the burn.

## Colors

All Catppuccin Mocha, via Enhalation's semantic names: a near-black violet leader, cool lavender ink, and a warm peach-to-pink core with a mauve bleed.

### Primary
- **Warm Core Peach** (halo-1): the start of the warm-core gradient on the core action. Also used for the frame number of the frame in the gate, the edge-print start marks, and the serif flourish word in the display line.
- **Warm Core Pink** (halo-2): the middle of the warm-core gradient. Also the hover colour for every text link (nav, caption title, footer).

### Secondary
- **Mauve Bleed** (halo-3): the glow that escapes the core action (`halo-glow`), the outer stop of the leak, the focus ring, and text selection. It shows up as light or as the ring, never as a fill of its own.

### Tertiary
- **Spark Teal** (spark): the live dot beside the slice count. It appears once per view.
- **Grease Pencil Rosewater** (rosewater): anything marked by hand: the caption numeral, the circle around the newest frame's number, "the next slice goes here", the tail note, and scratches on the emulsion. It also tints the glass rim (`glass-edge`).

### Neutral
- **Leader Crust** (ground-deep): the page and the html background; the leader the strip sits on.
- **Film Base Mantle** (ground-sunken): the reel's body. Perforations are punched through it in `ground-deep`.
- **Mocha Base** (ground): the gap ring inside the focus ring, and a stop in the burn.
- **Lavender Ink** (ink): primary text, the wordmark, links at rest.
- **Muted Lavender** (ink-muted): the lead paragraph, caption description, and the default colour of all edge print.
- **Rule Surface** (line): 1px dividers (rail edge, top bar, footer) and the scrollbar thumb. This is decoration, not a boundary anyone needs to find.
- **Strong Rule** (line-strong): the unexposed stripe in the wordmark and favicon. It is kept for any edge that has to be seen.
- **On Halo** (on-halo): text and the icon on the warm-core fill. Never white.
- **Caption Glass** (glass-fill): the caption's frosted fill. `glass-fill-strong` (#232334eb) is declared for denser glass; the hub does not use it yet.

### Named Rules
**The Gate Rule.** Warm light (halation, leak, colour) goes only to the frame in the gate, and the warm-core fill goes only to the one core action. Frames outside the gate stay silver.

**The Grease Pencil Rule.** Rosewater means a hand made this mark. Use it only for pencil type, pencil strokes, scratches, and the glass rim. Never use it for UI text.

**The One Spark Rule.** Teal appears once per view, as the live dot.

## Typography

**Display Font:** Bricolage Grotesque, variable in opsz, wdth, and wght (with Geist, system-ui)
**Flourish Font:** Instrument Serif italic (with Georgia)
**Body Font:** Geist (with system-ui, -apple-system, Segoe UI)
**Label/Mono Font:** Geist Mono (with ui-monospace)
**Hand Font:** Caveat Brush (with cursive)

**Character:** A tight, heavy variable grotesque carries the voice. One serif word inside it adds warmth. Geist is quiet for reading. Geist Mono reads as the stamped edge print of film stock, and Caveat Brush is the grease pencil in the lab.

### Hierarchy
- **Display** (720, clamp(56px, 7.6vw, 96px), 0.9, -0.04em, opsz 96, balanced wrap): the one page title. Use it once per page.
- **Flourish** (Instrument Serif italic 400, 1.04em of its line, halo-1): one English word inside the display line ("mind").
- **Title** (620, clamp(28px, 2.9vw, 40px), 1, -0.025em, opsz 48): the slice name inside the glass caption.
- **Wordmark** (700, 26px, 1, opsz 48, wdth 85, -0.02em): "slsc" in the top bar, and nowhere else.
- **Body large** (400, 18px/28px, max 40ch, ink-muted with `ink` 500 emphasis): the lead under the display line.
- **Body** (400, 15px/24px): base text, including caption descriptions (max 52ch).
- **Action** (560, 15px/20px): the core action's label.
- **Label / edge print** (Geist Mono 500, 11px/16px, 0.14em, uppercase, tabular numerals): nav, caption meta, frame numbers, the vertical rail, and the footer. The vertical rail opens up to 0.34em. Frame numbers on mobile drop to 9px/12px at 0.08em.
- **Pencil** (Caveat Brush 400): 40px for the caption numeral (rotated -4deg, 32px on mobile), 28px for leader notes (rotated -3deg on unexposed frames), 1.22em inline.

### Named Rules
**The Edge Print Rule.** Mono uppercase is film-stock edge print. It lives in the margins and metadata (rail, frame numbers, meta row, nav, footer). It is never a label stacked above a heading.

**The One Flourish Rule.** Only one serif word per display line, at the line's size, and only an English word.

## Layout

The page is a centred container (`cap`, 2240px max) offset by a fixed 44px edge-print rail on the left. On ultrawide screens the rail stays next to the container instead of the viewport edge. Inside it, a top bar (16px vertical padding, 1px `line` rule underneath) sits over a two-column stage: intro `0.95fr`, strip `1.2fr`, with a column gap of clamp(32px, 5vw, 88px) and side padding of `gutter`.

The intro column is sticky and vertically centred in the viewport (72px vertical padding), so the title, lead, and core action stay put while the strip scrolls past. The strip is one continuous reel: 28px top, 56px sides (room for the perforations), and a 150px tail that the clip-path cuts diagonally, like film cut at the splice. Frames stack at 4:3, with 26px above and 30px below, separated by a 1px near-black splice line. The footer sits 112px below the stage.

**Responsive (at 860px and below):** the rail is hidden (`--rail: 0`). The stage becomes a single column, and the intro stops being sticky (48px top padding). The strip gets 40px of top padding. The reel narrows to 20px/42px/120px with its perforations 6px from the edge. Frame numbers and the pencil circle tighten. The glass caption's overlap shrinks (-40px up, -14px left), its padding drops to 16px/18px, and its radius to 20px. The footer gap becomes 72px.

**How to add a slice:** copy the `frame` block to the top of the reel, bump the frame number (caption numeral, edge-print number, heading id), and point its link and three image lines at `works/<slug>/` and its 1200x750 `thumb.webp`. The three lines use the same src: silver, halation, colour. A slice without a picture drops the image lines, and its frame stays clear leader (the unexposed treatment). The slice count in the nav updates from the number of frames. Keep one unexposed frame and the "end of strip, for now." tail after the newest frames.

## Elevation & Depth

Depth is mostly light and material, not shadow. There are only two real elevations. The reel and the glass caption both float on `glass-float`, a long, soft, near-black drop. The core action radiates `halo-glow`, a mauve-and-peach bloom, instead of a cast shadow. Everything else is flat: the page, the rails, the rules. Frames get their depth from the emulsion stack: silver base, screened halation, masked colour, screened leak, screened scratches, all under page grain.

### Shadow Vocabulary
- **Glass float** (`box-shadow: 0 30px 60px -20px #08080de6, 0 12px 24px -12px #08080d99`): the reel, and the glass caption (the caption adds the rim).
- **Glass rim** (`inset 0 1px 0 #f5e0dc29, inset 0 -1px 0 #11111b99`): the glass caption's lit top edge and shaded bottom edge.
- **Halo glow** (`0 10px 34px -8px #cba6f780, 0 6px 22px -8px #fab38766`): the core action at rest and while pressed.
- **Halo glow lift** (`0 18px 48px -8px #cba6f7a6, 0 8px 28px -8px #fab3878c`): the core action on hover.
- **Focus ring** (`0 0 0 2px #1e1e2e, 0 0 0 4px #cba6f7`): every focusable element. It goes first in the shadow stack.

### Named Rules
**The Light Is Not a Shadow Rule.** Anything that glows gets a coloured bloom (halo glow, halation, leak), never a dark drop shadow. Dark drops are only for things that float (the reel, glass).

**The Grain on Glow Rule.** Everything that glows carries grain: the core action at `grain-strength` (.22), the leak at .5, the burn at `grain-strength`. The whole page gets `grain-soft` (.12) as a fixed overlay that boils in 6 steps per second.

## Shapes

Corners are soft and get rounder as elements get closer to the hand. Edges are 6px (focus rings on links), the wordmark takes 8px, film frames 12px, the core action 18px, and the glass caption 26px (20px on mobile). The live dot is a full circle. Perforations are rounded rectangles: 14x18 with 3.5px radius on a 46px pitch along the reel, and 10x12 with 2.5px radius on the core action. The reel is the one angular silhouette. It is a rectangle with a diagonal cut across its tail. Rules are 1px hairlines. There are no borders around frames or panels.

## Components

### Core Action
*A strip of warm leader you can push.*
- **Shape:** an 18px-radius pill of leader (54px tall, 44px side padding). Its left and right ends are punched through with two perforations each, masked 13px in from the edge.
- **Fill:** the warm core `linear-gradient(115deg, halo-1, halo-2, halo-1)` at 220% width, plus a 1px inner top light (`#ffffff59`) and a grain layer at `grain-strength`. The label and a 1.75px-stroke arrow are in `on-halo`.
- **Hover:** the gradient slides to the far end (420ms, ease-out-expo). The glow lifts to halo-glow-lift (180ms), and the arrow nudges 3px right on the spring.
- **Press:** scale .972 in 90ms on ease-press, and the glow settles back to halo-glow.
- **Magnetic lean:** on fine pointers, the button leans up to 3px toward the cursor. It returns on the spring when the pointer leaves.
- **Focus:** the focus ring sits in front of halo-glow.
- **Rule:** one per view. It carries `data-burn`.

### Film Frame
*The slice itself, as emulsion.*
- **Structure:** a 4:3, 12px-radius window over a `#0c0c14` well. It stacks five layers from one 1200x750 thumbnail:
  - **Silver:** grayscale, contrast 1.18, brightness .8.
  - **Halation:** the same image thresholded (grayscale, brightness .62, contrast 9), blurred 26px, brightened 2.6, multiplied by a peach-to-red tint (`#fab387` to `#f38ba8`), then screened back at .6.
  - **Colour:** the full image, masked from the right edge with a 30% soft edge.
  - **Leak:** a radial of warm core from just outside the right edge (hot `#fff0e2` centre, then peach, pink, and mauve falloff), screened at .3 with its own grain.
  - **Scratches:** two rosewater hairlines (at 31.2% and 71%), screened at .45.
- **In the gate** (the frame crosses the middle 44% of the viewport): halation goes to full, the leak goes to full and breathes (4.5s), and colour develops to 14% from the leak side.
- **Hover / focus:** colour develops to 100% (1.1s, ease-out-expo, using a registered `--reveal` percentage).
- **Edge print:** the frame number ("01 · e7") runs vertically in the right sprocket margin. It is in `ink-muted`, and in `halo-1` while the frame is in the gate.
- **Grease pencil circle:** a hand-drawn rosewater loop (2.2px, .8 opacity) circles the newest frame's number. It draws itself in 1.6s after a .35s delay when the frame enters the gate.

### Unexposed Frame
*Clear leader, waiting.* The same 4:3 window, filled with a faint rosewater glow at the lower left over a `#1a1a28` to `#141420` gradient. It is centred on a 28px grease-pencil note at 50% rosewater, rotated -3deg. Its edge-print number is set in `line`: it is decorative and hidden from assistive technology. It has no link, no caption, and no halation.

### Glass Caption
*The one element that breaks the grid.*
- **Placement:** it overlaps the frame's lower edge by 56px and pushes 28px past its left edge (20px short of the right).
- **Surface:** `glass-fill`, `blur(22px) saturate(170%)`, 26px radius, 20px/24px/22px padding, glass float, and the glass rim.
- **Grid:** a two-column baseline grid. The left column is the grease-pencil numeral (40px, rotated -4deg) spanning three rows. The right column holds the title, then the description (ink-muted, max 52ch, 8px above), then an edge-print meta row (year and stack, 6px by 18px gaps, 12px above).
- **Title link:** `ink`, and `halo-2` on hover (180ms).

### Top Bar and Navigation
- A flex row with the wordmark on the left and edge-print nav on the right, 24px apart. The wordmark is a 22x30 film-cell glyph (sprockets, an unexposed stripe, and a warm-core stripe) next to "slsc".
- The nav holds the live slice count (with the spark dot) and a Source link. Links are `ink` at rest and `halo-2` on hover (180ms, ease-out-expo). They are never underlined inside the bar.

### Edge Print Rail
A fixed 44px column on the left, with a 1px `line` rule on its right. Between two small peach triangles (start marks) it runs the stock line "slsc · 16mm · strip 01 · 2026" vertically, bottom-to-top, at 0.34em tracking. It is decorative and hidden from assistive technology. It is removed at 860px and below.

### Burn Transition
*The one authored transition.* When you click a `data-burn` link (plain left click, no modifier keys), a fixed overlay opens as a circle. It starts from the in-gate frame's leak side (92% across, 42% down) when that frame is visible, and from the viewport centre otherwise. It grows to 150vmax in 720ms on ease-exit. The fill is a radial melt: white-hot, then peach, pink, mauve, base, crust. Grain sits on top. Navigation fires at 680ms. The overlay clears on `pageshow`, so going back never shows a burnt page. Reduced motion skips the burn and navigates normally.

### Motion
- **Easing:** ease-out-expo `cubic-bezier(.16,1,.3,1)` for arrivals and hovers. ease-spring `cubic-bezier(.34,1.56,.64,1)` for releases and the arrow. ease-press `cubic-bezier(.3,0,.2,1)` for press. ease-exit `cubic-bezier(.5,0,.75,0)` for the burn.
- **Durations:** press 90ms, hover 180ms, slide 420ms, burn 720ms, halation 0.9s, colour 1-1.1s, leak 1.2s, pencil draw 1.6s, breathe 4.5s, grain boil 1s in 6 steps.
- **Sprocket roll:** the reel's perforations move with the scroll (0.35 of scroll distance, modulo the 46px pitch, once per animation frame), so the strip reads as film running through the gate.
- **Ambient loops** (grain boil and leak breathe) pause while the tab is hidden.
- **Reduced motion:** grain, breathe, sprocket roll, magnetic lean, spring travel, and the burn are all off. Colour fades and glow changes stay.
- Only `transform`, `opacity`, `clip-path`, `box-shadow`, `background-position`, `stroke-dashoffset`, and the registered `--reveal` are animated.

## Do's and Don'ts

### Do:
- **Do** add every new slice as a frame on the one strip, newest at the top, with its number stamped in the sprocket margin and a grease-pencil numeral on its glass caption.
- **Do** keep frames silver at rest. Warm light (halation, leak, colour) belongs to the frame in the gate.
- **Do** keep exactly one warm-core action per view, with its perforations, grain, halo glow, and `on-halo` label.
- **Do** put grain on everything that glows (`grain-strength` .22 on fills and the burn, `grain-soft` .12 over the page).
- **Do** use Geist Mono uppercase (11px, 0.14em) for edge print in margins and metadata, and Caveat Brush in rosewater for hand marks.
- **Do** show a picture-less slice as clear leader: the unexposed frame treatment, no invented image.
- **Do** list the focus ring first in any shadow stack, and keep links `ink` at rest and `halo-2` on hover.
- **Do** take tokens from Enhalation when the hub needs something new (clay controls, status colours, `accent-ink`), and add them here once they ship.

### Don't:
- **Don't** lay slices out as a thumbnail-card grid or a gallery of tiles.
- **Don't** put the warm core, halation, or the leak on more than the gate frame and the one core action.
- **Don't** set white text on the warm core. Use `on-halo`.
- **Don't** stack an uppercase mono label above a heading. Edge print lives in the margins, not as a section opener.
- **Don't** use rosewater or Caveat Brush for UI copy, controls, or anything a visitor must read to navigate.
- **Don't** add a second authored page transition. The burn is the only one.
- **Don't** run WebGL or heavy canvas work on the hub. The film effects are CSS layers over one still per slice.
- **Don't** apply these rules inside `works/<slug>/`. Each piece keeps its own look.

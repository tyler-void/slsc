Enhalation is an expressive interface language built on Catppuccin: **Mocha** (dark, the default) and **Latte** (light). Halation is the glow that bleeds around a bright highlight on film; this system is made of that light, the glass it passes through, and the soft clay it lands on. Every surface is one of three materials, every color pairing is contrast-checked in both flavors, and every interaction, down to a click or a dropdown, is choreographed.

## Principles

1. **Glass floats, clay rests, the halo is the moment.** Controls that live on the page are clay (the ground pushed up or pressed in). Anything that floats over content is glass. The warm-core gradient marks the one thing that matters in a view.
2. **Warm core, violet bleed.** Fills run `halo-1` (peach) to `halo-2` (pink); the glow that escapes them is `halo-3` (mauve), the same hue as the `focus-ring`. `spark` (teal) is the single cool counterpoint.
3. **Grain on everything that glows.** Every halo fill and every Halo carries grain. Flat gradients are unfinished.
4. **Enter slow, leave fast, press faster.** Nothing appears instantly and nothing lingers on the way out.
5. **Legible first.** Expression never costs contrast: the pairs below are measured, not eyeballed.

## Materials

| Material | Where | Surface | Depth | Never |
| --- | --- | --- | --- | --- |
| Clay | On the page: buttons, triggers, fields, switches, segmented controls, resting cards | `ground` with a `clay-hi` to `clay-lo` gradient at 145deg | `clay-raised`, `clay-lift` on hover, `clay-pressed` on press, `clay-well` for hollows | On glass, on a Halo |
| Glass | Floating: menus, popovers, dialogs, cards over a Halo or imagery, nav bars | `glass-fill` (or `glass-fill-strong`), `backdrop-filter: blur(var(--blur-glass)) saturate(170%)` | `glass-float`; a 1px rim from `glass-edge` to `glass-shade` | On plain ground with nothing behind it |
| Halo | Heroes, stages for glass, empty states, the core Button, the on state of Switch and filter Chips | `halo-1` to `halo-2` fills; Halo backdrops add `halo-3` and `spark` | `halo-glow`, `halo-glow-lift` on hover | More than one core action per view |

Depth runs, from lowest: `clay-well` (hollow), `ground` (flat), `clay-raised`, `clay-lift`, `glass-float`. A menu is always above the control that opened it.

## Content fundamentals

- Write short, sensory and direct. Say what happens, then stop: "Menus open from where you clicked and close faster than they came."
- Sentence case everywhere, buttons included: "Start the session", not "Start The Session".
- Buttons start with a verb. Switch labels name the setting, not the action: "Drift the halo".
- Address the reader as "you". No exclamation marks, no emoji, no hype words ("revolutionary", "seamless").
- Errors say what happened and what to do next: "That name is taken. Try enhalation-2."
- Section openers pair an `overline` index with a display line: `01 / MATERIALS` above "Glass floats, clay rests".
- One flourish word per display line, set in `flourish` at the line's size: "Warm light, *bled* through glass".
- Numbers use numerals ("3 items", "2 min ago").

## Color

Two themes, `mocha` first. Use semantic tokens; the `ctp-*` palette underneath is for syntax colors, charts and illustration.

- **Grounds:** `ground` (page and clay body), `ground-sunken` (sidebars, code), `ground-deep` (footers, under a Halo).
- **Text:** `ink` for primary text, `ink-muted` for secondary text and placeholders, `accent-ink` for links and active labels. All three hold 4.5:1 on every ground and on both glass fills, even with a full-strength halo blob behind the glass.
- **The warm core:** `halo-1` to `halo-2`. Text on it is always `on-halo` (Mocha crust, in both flavors): at least 10.6:1 in Mocha and 6.3:1 in Latte. White on Latte peach is 3:1, so never white.
- **The bleed and the ring:** `accent` (mauve) for focus rings, checks, active marks and icons; `on-accent` for text on an accent fill.
- **Spark:** `spark` (teal) for live dots, one data highlight, the fourth Halo blob. One per view; never text in Latte.
- **Edges:** `line` for decorative dividers; `line-strong` wherever an edge must be seen (the field baseline, structural rules): at least 3.2:1 on ground.
- **Status:** `success`, `warning`, `danger`, `info` for glyphs, dots and error text; `*-soft` tints behind chips and banners. Set status words in `ink` and always pair the color with a glyph or word.

Latte keeps Catppuccin's hues but deepens five of them where the originals are tuned for syntax, not UI text: `accent-ink` (#8230e7), `success` (#22720d), `warning` (#935300), `danger` (#c80031), `info` (#0d57e5). Each clears 4.5:1 on base, mantle and crust.

## Gradients and grain

The warm core, for fills (buttons, switch on, selected chips):

```css
background: linear-gradient(115deg, var(--halo-1) 0%, var(--halo-2) 50%, var(--halo-1) 100%);
background-size: 220% 100%;               /* hover slides background-position to 100% */
box-shadow: var(--halo-glow);             /* halo-glow-lift on hover */
color: var(--on-halo);
```

A Halo backdrop is five radial blobs (`halo-1`, `halo-2`, a `halo-1`/`halo-2` bridge, `halo-3`, and a small `spark`) blurred 20px with `saturate(135%)`, on `ground-deep`, drifting over `dur-ambient`. Use the Halo component rather than rebuilding it; `assets/Textures` has static SVG versions for decks and social images.

Grain is an SVG `feTurbulence` tile (fractal noise, base frequency .85, 3 octaves) laid over the surface with `mix-blend-mode: overlay` at `grain-strength` (Mocha fills and Halos) or `grain-strength-soft` (glass, and everything in Latte). The tile ships as `--enh-grain` in `bundle.css` and as `assets/Textures/grain.svg`.

## Typography

- **Display:** Bricolage Grotesque (variable: opsz, wdth, wght). `display-xl` once per page, `display` for section openers, `headline` for big panel heads, `title` for cards and dialogs. Set tight (negative tracking is in the styles) and always at opsz 96 for display sizes. Scale with `clamp()`: `display-xl` clamp(56px, 9vw, 112px), `display` clamp(44px, 6vw, 72px), `headline` clamp(32px, 4vw, 44px).
- **Flourish:** Instrument Serif italic, one or two words inside a display line at the same size. It has no Vietnamese glyphs; keep flourishes to English words.
- **Text:** Geist. `body-lg` for leads (max 60ch), `body` for reading (max 68ch), `label` for controls, `caption` for hints and metadata.
- **Mono:** Geist Mono. `overline` for section indices (uppercase in CSS), `code` on `ground-sunken`.
- Never set display type on a warm-core fill, and never set body copy straight on a Halo: put it on Glass.

## Layout and spacing

- 4px base (`space-1`) with a steep top: `space-9` (112px) between desktop sections, `space-8` (72px) on mobile. Do not compress the air; it is what makes the type loud.
- Asymmetric 12-column layouts. Let display lines run wide and let one element break the grid per section (a glass card overlapping a Halo edge, a line of type bleeding into the next block).
- Padding: `space-5` inside cards, `space-6` inside glass panels, `space-4` horizontal inside controls.
- Radii are generous: `radius-md` for controls, `radius-lg` for cards and menus, `radius-xl` for hero panels and Halos, `radius-full` for pills and switches. A nested radius is the outer radius minus the padding between them.

## Motion

| Moment | Duration | Easing |
| --- | --- | --- |
| Press down | `dur-press` (90ms) | `ease-press` |
| Release after press | `dur-slide` (420ms) | `ease-spring` |
| Hover lift, glow, label roll | `dur-hover` (180ms), roll `dur-slide` | `ease-out-expo` |
| Menu, popover, focus bloom in | `dur-enter` (280ms) | `ease-out-expo` |
| Menu, popover out | `dur-exit` (150ms) | `ease-exit` |
| Menu items cascade | `dur-stagger` (24ms) per item, max 8 | `ease-out-expo` |
| Thumbs, hover pill, chevrons | `dur-slide` (420ms) | `ease-spring` |
| Halo drift | `dur-ambient` (18s), alternate | ease-in-out |

- The signature details: labels roll up on hover, the sheen follows the pointer, the core button leans 3px toward the cursor, the dropdown trigger stays pressed while its menu is out, one hover pill glides between menu items, checks draw themselves, errors shake once.
- Animate only `transform`, `opacity`, `clip-path`, `box-shadow` and `background-position`. Clay shadows share one five-layer shape so rest, lift, press and well interpolate instead of snapping.
- Under `prefers-reduced-motion: reduce`, keep short fades and drop all travel, drift, rolls, springs and shakes. The components do this already.

## Interaction states

| State | Clay | Glass | Core |
| --- | --- | --- | --- |
| Rest | `clay-raised` | `glass-float` + rim | `halo-glow` + inner top light |
| Hover | `clay-lift`, up 1px, sheen | `glass-fill-strong`, sheen | `halo-glow-lift`, gradient slides, magnetic lean |
| Press | `clay-pressed`, scale .972 | inner `glass-shade` | inner shade, glow settles |
| Focus | `focus-ring` in front of the rest shadow | same | same |
| Disabled | `opacity-disabled`, `clay-well` | `opacity-disabled` | `opacity-disabled`, no glow |

## Iconography

- Line icons on a 24px grid, 1.75px stroke, round caps and joins, drawn in `currentColor`; 18px inside controls, 20px standalone, 13–14px in chips and messages.
- The bundle ships the glyphs the components need as `Enhalation.Icon` (Chevron, Check, Arrow, Close, Alert, Info, Spark, Plus). For anything else, use Lucide at `strokeWidth={1.75}`: it shares the grid and geometry. This is a recommendation, not a copied asset set.
- Icons take `ink-muted` at rest and `ink` or `accent` when active. No emoji as icons, no filled icon sets, no two-tone icons.

## Accessibility

- Every text pairing above is measured in both flavors, including glass over a full halo blob; the numbers are in each token's usage note.
- Neumorphic edges alone fail WCAG 1.4.11, so every clay control that needs to be found has a mark at 3:1 or more: the field's `line-strong` baseline, the switch `thumb`, the segmented thumb's `accent` underline, button labels.
- Focus is always visible: `focus-ring` (2px ground gap, 2px solid `accent`: 8.1:1 Mocha, 4.8:1 Latte) listed first in the box-shadow.
- Status never relies on hue: every status chip has a glyph and a word.
- Dropdown is a listbox with full keyboard support; Segmented is a radiogroup with a roving tab stop; Switch is `role="switch"`.

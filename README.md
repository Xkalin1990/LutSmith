# LUTsmith

A visual colour-grading tool that turns a photo into a `.cube` 3D LUT you can load anywhere — in-camera real-time LUTs, Resolve, Premiere, Final Cut, Photoshop.

Free for personal and non-commercial use ([CC BY-NC 4.0](LICENSE)) — see the Licence section below.

Grade an image with familiar controls, watch the result live, then export the grade as a standard LUT file. Free and entirely offline: it's a single HTML file with no build step, no server, no account, and no network calls.

## Quick start

Download `lutsmith.html` and open it in your browser. That's it.

```
git clone https://github.com/Xkalin1990/LutSmith.git
cd LutSmith
# open lutsmith.html in any modern browser
```

Or use the hosted version at `https://xkalin1990.github.io/LutSmith/index.html`

Because everything runs locally in the browser, your photos are never uploaded anywhere.

## What it does

**Load a photo → grade it → export a LUT.** The preview shows exactly what the LUT will do, because the preview and the export run through the same grading engine.

### Grading controls

- **Tone** — exposure, contrast, highlights, shadows, blacks, gamma, fade blacks
- **Colour** — temperature, tint, saturation, vibrance, skin-tone protection
- **Curves** — master plus per-channel red, green and blue, with click-to-add, drag-to-shape, double-click-to-remove control points
- **Hue vs hue** — rotate specific hues, eight-handle strip
- **Hue vs saturation** — saturate or desaturate specific hues
- **Luma vs saturation** — control saturation by brightness
- **Secondary colour** — isolate a hue range (with eyedropper) and shift its hue, saturation and luminance
- **Colour balance** — three-way shadows / midtones / highlights wheels
- **Split toning** — separate shadow and highlight tints with adjustable amounts
- **Look strength** — blend the whole grade back toward the original

### Workflow

- **Starting looks** — 12 film-inspired presets (Portra 400, Ektar 100, Gold 200, Kodachrome 64, Velvia 50, Provia 100F, Pro 400H, Superia 400, CineStill 800T, Tri-X 400, HP5 Plus, and Neutral) as editable starting points
- **Extract look from photo** — analyses a reference image with per-channel histogram matching and sets up an approximate grade for you to refine
- **My looks** — save grades to a personal library, or import `.cube` files into it; stored locally in your browser
- **Base LUT** — import an existing `.cube` and grade on top of it
- **Log footage** — V-Log source conversion for log-encoded material
- **A/B slots** — hold two versions of a grade and switch between them
- **Undo / redo** — 60 steps
- **Projects** — save and reload your whole session as a `.lutsmith.json` file
- **Look pack export** — write your entire library out as `.cube` files at once

### Viewing tools

- Live histogram and scopes
- Clipping warnings for blown highlights and crushed shadows
- Split-compare wipe, plus hold-to-compare against the original
- Multiple images at once with a thumbnail strip, so you can check a grade across several photos
- Built-in test chart (colour checker, grey ramp, hue ramp, skin patches)
- Transfer ramp and cube analysis panels for inspecting what the LUT actually does
- White-balance eyedropper

### Export

- `.cube` 3D LUT at 17, 33 or 65 points
- Graded photo as a JPEG
- Standard format, so it works with in-camera LUT slots and every major NLE and grading application

## Browser support

Any current version of Chrome, Edge, Firefox or Safari. The library uses IndexedDB, so private/incognito windows may limit how much you can store.

## Contributing

Issues and pull requests are welcome. The whole app is one self-contained `lutsmith.html` — HTML, CSS and JavaScript in a single file with no dependencies and no build tooling, so you can edit it directly and refresh the browser to see changes.

If you're changing the grading maths, note that the preview and the `.cube` export both call the same `grade()` function, and the order of operations in that pipeline is deliberate — changing it changes everyone's saved looks.

## A note on the film presets

The film-stock presets are *tasteful approximations* of each stock's well-documented colour and contrast character. They are not calibrated emulations: real film emulation is built from lab-measured spectral dye data, which this project doesn't use. Treat them as creative starting points rather than accurate reproductions of the stocks they're named after.

Film-stock names are trademarks of their respective owners and are used here only to describe the character of a look.

## Licence

CC BY-NC 4.0 — free to use, modify and share, but **not for commercial use** (no selling the app, selling copies or modified versions, or bundling it into a paid product) without permission. See [LICENSE](LICENSE) or the [full legal text](https://creativecommons.org/licenses/by-nc/4.0/legalcode).

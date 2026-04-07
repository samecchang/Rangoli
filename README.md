# Rangoli Drawing Tool

A single-file, browser-based radial symmetry drawing tool for creating [Rangoli](https://en.wikipedia.org/wiki/Rangoli)-style patterns. No install, no dependencies — just open `Rangoli.html` in any modern browser.

---

## Features

- **Radial Symmetry** — Choose 2–36 divisions; draw in one segment and all others replicate in real time.
- **Centered Active Segment** — The drawable area is always at the top, symmetrically straddling 12 o'clock, regardless of division count.
- **Brush Controls** — Color picker and adjustable brush size (1–30 px).
- **Undo / Clear** — Step back stroke by stroke, or clear the entire canvas.
- **Clean Export** — Save as PNG without guide lines or dashed overlays.
- **HiDPI Support** — Renders at native `devicePixelRatio` for crisp output on Retina / high-DPI displays.
- **Touch & Mouse** — Works on desktop and mobile; touch-action is handled to prevent scroll interference.
- **Zero Dependencies** — Single self-contained HTML file with embedded CSS and JavaScript using Canvas 2D API.

## Getting Started

1. Download or clone this repository.
2. Open `Rangoli.html` in a browser (Chrome, Edge, Firefox, Safari).

Or serve it locally:

```bash
python -m http.server 8080
# then visit http://localhost:8080/Rangoli.html
```

## Usage

1. **Select divisions** from the dropdown (default: 8).
2. **Pick a color** and **brush size** from the bottom toolbar.
3. **Draw** inside the highlighted segment at the top of the circle.
4. All other segments mirror your strokes automatically.
5. Use **Undo** to remove the last stroke, or **Clear** to start over.
6. Click **Save** to download a clean PNG (no guide lines).

## Controls

| Control | Action |
|---------|--------|
| Divisions dropdown | Split the circle into N equal parts |
| Color picker | Set brush color |
| Brush slider | Set stroke width (1–30 px) |
| ↩ Undo | Remove last stroke |
| 🗑 Clear | Erase all strokes |
| 💾 Save | Export as `rangoli.png` |

## Technical Details

- **Rendering**: HTML5 Canvas 2D with rotational transform replication.
- **Resolution**: Canvas internal size = CSS size × `devicePixelRatio`.
- **Segment detection**: Point-in-sector test using `atan2` relative to the centered segment boundaries.
- **Export**: Redraws without overlays before `toDataURL()`, then restores guides.

## License

MIT

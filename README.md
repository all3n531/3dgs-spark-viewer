# 3DGS Spark Viewer

A browser-based 3D Gaussian Splatting viewer built with [SparkJS](https://sparkjs.dev) and Three.js. No server required — runs as a static file.

## Features

- Load any local `.ply` file (3DGS format) directly in the browser
- Orbit / pan / zoom the scene with mouse
- Optional animated character (blocky humans + animals) with WASD walking
- Rapier3D physics — gravity and ground collision
- Auto-centers the loaded scene on load

## Usage

Because `explore.html` uses ES modules, you need a local HTTP server (can't open directly as `file://`).

```bash
cd /path/to/3dgs-spark-viewer
python3 -m http.server 8888
```

Then open `http://localhost:8888/explore.html` in your browser.

## Controls

| Input | Action |
|-------|--------|
| Left drag | Orbit camera |
| Right drag / two-finger drag | Pan |
| Scroll | Zoom |
| WASD | Move character |
| Q / E | Rotate character |
| Space | Run |

**Camera modes**
- **Follow Camera** (default) — camera tracks the character
- **Free Camera** — standard orbit controls, click "Switch to Free Camera" in the panel

## Loading a Scene

Click **📂 Load PLY File** in the top-left panel and select a `.ply` file. The scene will be auto-centered on load.

Supported input: 3DGS `.ply` files with `f_dc_0 / f_dc_1 / f_dc_2` spherical harmonic coefficients.

## Character

The character is hidden by default. To enable:
1. Check **Show Character** in the Avatar section
2. Select a model from the dropdown (18 human characters + 13 animals)
3. Adjust Scale, Speed, and Height as needed
4. Use **📌 Set Ground Here** to pin the ground plane to the current height

## File Structure

```
explore.html        — main viewer
characters/         — 31 GLB character models (Kenney assets)
Textures/           — texture atlases for characters
```

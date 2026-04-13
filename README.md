# Particle Text v3

15000 particles floating on screen gather to form the text you type. Supports multi-line input.

**Live Demo**: [prayer168.github.io/particle-type3](https://prayer168.github.io/particle-type3/)

## Features

- **15000 particles** — High density for crisp, detailed text rendering
- **Multi-line support** — Press Enter to create new lines, up to 60 characters
- **Chinese & English** — Full support for both languages
- **Smooth transitions** — Grid-sorted O(n log n) spatial matching keeps particles near their region when text changes
- **Mouse interaction** — Cursor pushes nearby particles away within a 130px radius
- **Optimized rendering** — Flat typed arrays + 3-layer alpha batching (only 3 draw calls per frame)
- **Dreamy physics** — Soft spring convergence (~3 seconds) with slow wandering drift

## Performance

Compared to v2, v3 is optimized for 7.5x more particles:

| Optimization | Detail |
|---|---|
| Flat `Float32Array` | No object overhead per particle |
| `ctx.rect()` batching | 3 draw calls instead of 15000 `arc()` calls |
| Grid-sorted assignment | O(n log n) instead of O(n²) nearest-neighbor |
| `Uint16Array` sort indices | Memory-efficient spatial sorting |

## Tech Stack

Single HTML file — HTML5 Canvas + vanilla JavaScript. No dependencies.

## Run Locally

Open `index.html` in any modern browser. No build step needed.

# SCGraph2

SCGraph2 is a single-file HTML application for single-case graphing and analysis.

## Run
Open `index.html` or `SCGraph2.html` in a browser. For GitHub Pages, publish `index.html` from the repository root.

## Saving and exporting

Open SCGraph2 directly as a top-level page (for example, the GitHub Pages URL) when using Save Location, Save State, Export SVG, or Export PNG. Browsers block writable-folder pickers in cross-origin embedded previews, and sandboxed previews may also block ordinary downloads. In supported top-level Chrome/Edge pages, Save Location can remember a writable folder.

## Data syntax
- `|` creates phase boundaries.
- `(value)` ghosts an observation while retaining its session position.
- `+` creates vertically stacked multiple-baseline tiers on a shared session timeline.
- `-` creates an independent graph panel. Up to three graph panels are supported.

Each independent graph can have its own graph label, Y-axis label, vertical scale, tick interval, autoscale method, and number of phases.

# SCGraph2 2.2.13

Standalone single-file HTML application for single-case graphing and analysis.

## Revision 2.2.13

Adds Trend/IQR Trend projection beyond observed data with three modes:

- **Observed data only** — stop at the last active observed point.
- **To end of X-axis** — project the fitted trend and IQR band across the current displayed session range.
- **To goal** — project the source-phase Theil–Sen trend forward until it intersects a selected applicable goal line, extend the X-axis when necessary, and mark the projected intersection.

The projection changes display only. The trend and IQR band continue to be calculated from observed source-phase data. Goal-dependent projections are invalidated automatically if their goal is edited or removed.

Help, Start Up guidance, tooltips, saved-state persistence, and result text were updated for the new projection modes.

## Files

- `index.html` — GitHub Pages entry point
- `SCGraph2.html` — standalone application

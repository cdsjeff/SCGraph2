# SCGraph2

Standalone single-file HTML application for teaching and conducting single-case graphing and analysis.

## Version 2.2.2

### Calendar-time workflow

Proportional calendar time now uses a recurring clinical schedule rather than requiring a date for every observation.

1. Choose **Proportional calendar time** under **Graph Controls → X-Axis / Session Timeline**.
2. Enter the **First session date**. This date is used exactly for Session 1.
3. Check the recurring **Session days** (Monday through Sunday).
4. SCGraph2 assigns each subsequent observation to the next checked weekday and spaces observations by actual elapsed calendar days.

The first session date is independent of the recurring weekday selection. SCGraph2 does not silently add a weekday to the schedule.

Calendar-time display changes only graph geometry. Statistical analyses remain based on session order. Phase boundaries are positioned midway in elapsed time between the adjacent sessions. Timeline settings are persisted in SCGraph2 JSON state files.

### Other 2.2 features retained

- Per-series connecting-line visibility
- Per-series line color and dash style
- Level, IQR Level, Trend, and IQR Trend display extension into adjacent phases without recomputation
- Decimal/fractional numerical input
- Configurable minimum sequential-session span
- Graph Controls/Analysis viewport-aware right panel
- JSON save/load, SVG/PNG export, report workspace, and existing analysis methods

## Run

Open `SCGraph2.html` or `index.html` directly in a modern browser. No server is required for core graphing functionality.

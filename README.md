# SCGraph2 2.2.1

Standalone single-file application for teaching and conducting single-case graphing and analysis.

## Run locally
Open `SCGraph2.html` directly in a modern browser.

## GitHub Pages
`index.html` is an identical copy of `SCGraph2.html`, included so the repository can be published directly with GitHub Pages.

## 2.2.1 changes
- Per-series **Show connecting line** control with JSON persistence.
- Correct startup state for the sticky right panel: Graph Controls open, Analysis collapsed.
- Visual-analysis span controls: calculate Level/IQR Level/Trend/IQR Trend from one phase and display through later adjacent phases without recomputation.
- Verified decimal/fractional numerical handling through data parsing, axis/goal inputs, calculations, overlays, and state persistence.
- X-axis/session timeline controls for configurable minimum sequential-session span and proportional calendar-time display with explicit dates and validation.
- Calendar/session label modes and JSON persistence.

## Browser note
Persistent folder selection uses the File System Access API and therefore depends on browser/security context. Normal browser downloads remain the fallback.

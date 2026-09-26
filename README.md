# SCGraph2 2.2.8

Standalone single-file application for single-case graphing and analysis.

## 2.2.8 change

The former **Notes / context** feature has been removed so the **Report — Student Report Workspace** is the single narrative/documentation workspace.

Removed from the application:

- Notes / context field in Data Input
- Add Table to Notes action
- Insert Notes action in both in-page and pop-out Report toolbars
- Notes persistence in newly saved SCGraph2 JSON state files
- Help/Start Up references to the removed Notes workflow

The selective graph data table remains available and can be inserted directly into the Report workspace. Existing SCGraph2 state files remain loadable; any legacy `data.notes` field is ignored.

## Files

- `SCGraph2.html` — standalone application
- `index.html` — identical GitHub Pages entry point

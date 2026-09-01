# SCGraph2

## Phase-label parsing and automatic graph separation

State version: 28.

### New parsing behavior
- `label(Name)` inside a phase is parsed as that phase's label and then removed from the numerical data stream.
- Legacy `G(...)` directives are removed from the data stream; goal lines should be created with SCGraph2's Goal Lines controls.
- Parenthesized numerical values such as `(29.3)` remain ghosted observations.
- If one plain series has `|` phase boundaries and a companion series has none, SCGraph2 infers the companion boundaries from the explicit series without inventing observations.
- Plain series are overlaid only when **every resulting phase has the same length**.
- When phase lengths differ, SCGraph2 automatically separates the series into independent graph panels, up to the existing three-graph limit.
- Inline phase labels supplied on one series are inherited by companion automatically separated graphs when those graphs do not supply their own labels.

Example:

```text
Total Strategy: 7.5,18.6,17.7,12.0,13.8 label(Baseline) | (29.3),20.8,19.1,23.3,23.9,23.8,23.8 G(4,5,23) label(Parental Coaching) | 25.0,25.2,22.8,25 G(4,5,23)
Target Strategy: 0.9,1.4,2.1,2.0,1.3,6.8,5.2,6.6,7.8,7.5,13.1,13.1,9.0,8.0,8.0
```

The two series are displayed as separate graphs when their inferred phase lengths differ.

## Selected-phase analysis
- The Analysis pane now has a multi-select Phase(s) control.
- Level, IQR Level, Trend, and IQR Trend may be drawn for one or several selected phases simultaneously.
- Visual overlays are confined to the selected phase boundaries.
- PND, Mann–Whitney, Trend + 0.3 IQR, and Tau-U compare exactly two selected phases, including nonadjacent pairs such as Phase 1 vs Phase 3.
- Compact commands such as `Level, 1, 3` and `T-U, 1, 3` are supported.

# SCGraph2 v60

Open `index.html` or `SCGraph2.html` in a modern browser. This standalone app works offline with no build or external dependencies. For GitHub Pages, extract the ZIP into the repository root and use that branch/root in Pages settings.

## Tau-U controls and uncorrected cloud

This release is a separate copy. Earlier HTML, ZIP and backup versions are preserved.

- Tau-U has no IQR multiplier in either settings dropdown. CDC-NonPar retains its existing multiplier and saved values. Changing that value no longer moves Tau-U rings or cloud boundaries, and an invalid CDC multiplier does not block Tau-U.
- **Tau-U uncorrected** now shows its cloud. The previous renderer required a nonzero applied correction, suppressing all uncorrected clouds. The raw mode now shades using running uncorrected Tau, without a baseline-correction fade. Its descriptive reference is the active A-phase median, extended through later sessions.
- **Tau-U baseline corrected** uses the A-phase Theil–Sen projection as its descriptive reference. Running corrected Tau-U and the existing baseline-influence fade set the shade. A zero correction no longer suppresses this cloud; its running distinction bands remain available.
- Neither mode adds an IQR margin to the reference. Spread softens the cloud edge only. Rings flag B observations strictly beyond the selected reference in the improvement direction; they are visual flags, not individual-point significance tests.
- Both modes retain ten smooth, one-sided layers; the four running distinction categories; the Lighter–Darker control (internal range 0–500); Classroom/Technical views; On/Cloud only/Off; and the shared legend. A running Tau of .90 or above is unshaded by design. Off retains the available reference guide. All cloud/guide/ring/legend explanations, results descriptions and help match the selected correction mode.

The cloud is a custom descriptive display, not a pointwise overlap probability, p-value or confidence region. The statistical calculations, phase correction, one-/two-sided inference, session identities and missing/ghost exclusions are unchanged. Uncorrected cloud geometry is level-based; corrected geometry is trend-based. The earlier IQR-based Tau visual criterion is intentionally retired, including for loaded older projects. Their result/overlay snapshots and their CDC multiplier values remain preserved.

For `Sniffing: 2,4,5,2|6,7,4,5`, raw Tau remains 0.75. Always-corrected Tau-U remains 0.6875 with one-sided corrected pEst approximately 0.067765898. Corrected rings remain at sessions 5 and 6. Uncorrected rings use the A median, rather than a trend/IQR threshold.

452 checks passed using JSDOM interaction/state tests and independent Sharp SVG/PNG rasterization. Checks covered unchanged statistical functions and numerical/model/simple results against v59 across tied, short, constant, missing/ghost and mirrored-decrease datasets, one-/two-sided alternatives and both correction modes; visible raw and zero-correction clouds; four category boundaries; one-sided vertical fades; monotonic ink at 0/50/100/300/500; CDC multiplier independence and invalid-input isolation; visualization modes, rings, guides and keys; current/legacy state and ink clamping; date overrides and displayed phase numbering; shared controls and existing toggles; unrelated tests; multiple graphs/tiers; six full/compact/all/selected SVG/PNG export combinations; report snapshots/results; palette, exclusive Plot Control categories and reset. The browser PNG exporter is unchanged and consumes the same complete SVG. No full-browser binary was available, so these are DOM/raster checks, not a full-browser layout test. Representative raw, corrected, decrease, calendar and multi-tier figures were visually inspected.

On the reproduction data, at session 7.5 / score 1, the uncorrected cloud's sampled luminance was 255.00/243.49/234.33/202.44/178.81 at internal ink 0/50/100/300/500 (lower is darker). The former v59 uncorrected display contained no cloud. Corrected luminance was 255.00/230.73/209.58/151.99/123.34 at the same settings. ZIP integrity and byte-identical root HTML/standalone files were verified.

The existing conceptual Level/Trend categories, simple-line header toggles, exclusive carets, menus, report Insert dropdown, descriptive Phase 1 IQR extensions and Phase 2 visibility controls, eight-color palette, timeline/date/numbering controls, grids, and full/compact/all/selected exports remain in the SCGraph2 framework. Visible and saved-state build identifiers are 60.

## Earlier release notes

The notes below document earlier versions; v60's Tau-U reference/cloud behavior above supersedes their descriptions of IQR-based Tau rings and correction-only clouds.

# SCGraph2 v59

Open `index.html` or `SCGraph2.html` in a modern browser. The standalone app works offline and requires no build or external dependencies. For GitHub Pages, extract these files into the repository root and select that branch/root in Pages settings.

## v59 separate copy: unfolding categories and simple-line header toggles

This version is saved as new `SCGraph2_v59.html` and `SCGraph2_v59_GitHub.zip` files. The earlier v58 and v57 files/backups are preserved.

**Level** and **Trend** each have a label button and an adjacent caret. Both option lists start folded:

- Click the **Level label** to toggle simple median lines for the selected phases and unfold its list.
- Click the **Trend label** to toggle simple Theil–Sen trend lines and unfold its list.
- Click a **caret** to expand/collapse the list without changing the graph. Opening one list folds the other and rolls up its settings. Folding an option list does not remove enabled analyses.

Each unfolded list shows its Descriptive and Statistical variants:

| Level | Trend |
| --- | --- |
| IQR | IQR |
| PND | CDC-NonPar |
| CDC-NonPar | Tau-U baseline corrected |
| Mann–Whitney | |
| Tau-U uncorrected | |

PND and Mann–Whitney remain under Level only, with their existing level-based calculations. The IQR entries retain the descriptive center lines, Phase 1 forward projection and Phase 2 IQR visibility settings. CDC-NonPar uses the category's Level or Trend reference, as in v58.

The two Tau-U entries choose the existing correction modes explicitly: **uncorrected** applies no baseline correction; **baseline corrected** always applies it. Clicking the other Tau-U entry switches the same test between these modes; clicking its active entry turns it off. Only the matching entry is highlighted. Existing saved Auto-mode results load without recalculation and highlight the category matching their actual stored correction state. Settings, legend choices and the current explanation synchronize across the two entry points. The uncorrected graph retains its existing A-trend guide/criterion-ring display; no cloud is drawn without an applied nonzero baseline correction.

Graph, Series and Phases to analyze stay once at the top. Other controls remain in the associated dropdowns, with general labels. Shared settings stay synchronized and enabled analyses refresh automatically. The open category is saved with the project; older projects default to both lists folded. Reset folds both lists. Existing analyses, results, data/session identities, menus, reports, accordion behavior, palette, grids and exports retain their prior calculations/behavior.

148 checks passed: unchanged parser/statistical/fit/cloud/executor functions; exact option lists and parent header behaviors; caret-only operations leaving graph state unchanged; nested settings rolling up; original simple Level/Trend result and overlay equality; exact raw and corrected Tau-U result/overlay equality against v58; raw Tau 0.75 and corrected Tau-U 0.6875 for the reproduction data; unchanged rings at sessions 5 and 6; correction-mode switching/off behavior; shared legend/explanation/parameters; unchanged PND/Mann–Whitney/CDC behavior; independent simultaneous tests; current/legacy Auto-mode state; open-category roundtrip; Phase 2 IQR display; nonadjacent phases, calendars, multiple graphs/tiers and SVG/PNG export combinations; report snapshots/results; live data updates and ghost positions; reset, unique IDs and preserved palette/cloud/Plot Control controls. Validation used JSDOM interaction/state checks and independent Sharp SVG/PNG rasterization. No full-browser binary was available, so this is not a full-browser layout test. ZIP integrity and byte equality of root HTML files and the standalone file were verified.

## v58 separate copy: conceptual Level / Trend analysis panel

This edition is saved separately as `SCGraph2_v58.html` and `SCGraph2_v58_GitHub.zip`. The existing v57 HTML/ZIP and its backups are preserved.

The right Analysis panel is organized by concept, with visual analyses and statistical comparisons listed within each category:

| Level | Trend |
| --- | --- |
| Level | Trend |
| IQR Level | IQR Trend |
| PND | CDC-NonPar (Trend reference) |
| Mann–Whitney | Tau-U |
| CDC-NonPar (Level reference) | |

Each analysis has an adjacent settings caret; opening a dropdown does not enable that analysis. **Graph to analyze**, **Series to analyze**, and **Phases to analyze** appear once at the top and apply to all analyses. They are not repeated inside the individual dropdowns. Other relevant shared controls remain synchronized across dropdowns, using general labels such as Alpha, IQR multiplier, Display, Baseline correction, Statistical alternative, Visualization and Cloud darkness. Descriptive IQR dropdowns retain Show Phase 2 IQR. The optional command input is collapsed under its own Analysis command caret. Detailed-result format is available in the analysis dropdowns.

Both CDC buttons are labelled simply **CDC-NonPar**. The category chooses the reference: median/raw IQR in Level, or Theil–Sen/residual IQR in Trend. Clicking the other category's CDC button switches the existing comparison to that reference; clicking the active CDC button turns it off. The two entries share one comparison and its settings. Only the entry matching the active reference is highlighted. This changes organization and access to the reference choice, not the underlying method.

Independent toggles, automatic statistical refresh, shared parameter synchronization, current/legacy state, data/missing/ghost identities, Phase 1 IQR projection, Phase 2 visibility choices, cloud ink/legend and ordinary Classroom points, menus/help carets/report Insert, the outer accordion, exclusive Plot Control categories, grids and full/compact/all/selected exports retain the v57 behavior.

168 checks passed: correct category membership and nine entry points; an associated dropdown for every analysis; unique DOM IDs; global targets present once with no dropdown copies; generic labels; dropdown behavior; per-test numeric result and overlay equality against v57; both CDC reference calculations and switching/off behavior; independent simultaneous visual/statistical analyses; synchronized settings and immediate updates; current/legacy save-load; Phase 2 display preferences; nonadjacent phases, calendars and multiple graphs/tiers; full/compact/all/selected SVG and PNG rasterization; report snapshots/results; live data edits and ghost exclusions; reset; and retained palette/cloud/accordion controls. Validation used JSDOM interaction/state checks and independent Sharp SVG/PNG rasterization. No full-browser binary was available; this is not a full-browser layout test. ZIP integrity and byte equality of root `index.html`, root `SCGraph2.html`, and the standalone file were verified.

## v57 statistical toggles, per-test settings and live updates

The Analysis panel separates **Visual analyses** (Level, Trend, IQR Level and IQR Trend) from **Statistical comparisons** (PND, Mann–Whitney, CDC-NonPar and Tau-U). Every main test button toggles independently. Several statistical tests can remain enabled together, alongside enabled visual analyses. Clicking an enabled test removes only its results and graph layers. Each refresh clears and rebuilds the enabled statistical layers from current data/settings, preventing stale or duplicated displays.

Each statistical button has an adjacent **settings caret**. Opening a dropdown does not enable its test, and opening another dropdown closes the previous one. Relevant controls are placed inside each dropdown:

- All four tests: graph, series, phases, improvement direction, and detailed-result format.
- Mann–Whitney, CDC-NonPar and Tau-U: alpha.
- CDC-NonPar and Tau-U: IQR multiplier and Classroom/Technical display.
- CDC-NonPar: Level/Trend reference.
- Tau-U: baseline correction, one-/two-sided alternative, visualization, cloud darkness, and its explanation/legend controls.

Shared controls are synchronized with every copy, including the original graph/series/phase selectors and Data Input's improvement direction. Changes apply to every enabled comparison at the shared target. Changes in selections and checkboxes update immediately; numeric/data typing uses a short debounce. Tau-U display/ink/legend changes redraw without changing its calculated results. Editing data refits enabled visual analyses and recomputes the enabled tests. The command field remains available: Run enables or refreshes that comparison, while the main buttons toggle it off/on.

The CDC button now reads simply **CDC-NonPar**. Level/Trend and IQR details appear in its dropdown and result text; no Trend ± IQR suffix is appended to the button.

The carets beside **IQR Level** and **IQR Trend** also offer **Show Phase 2 IQR**. Each independently hides or shows Phase 2's IQR band and boundary lines while retaining its center line, the descriptive comparison results, and Phase 1's forward IQR projection. These display choices are saved with the project, default to visible for older projects, and apply immediately to SVG/PNG exports and report snapshots. They do not change calculated fits, IQR values or statistics.

Enabled tests are saved in project JSON and restored with the settings/results. Older saved tests are recognized from their stored results/overlays, so their buttons can toggle them off cleanly. Stored result snapshots remain intact until a setting/data change requests a refresh. Incomplete phase selection or invalid settings clear the affected statistical output and show an explanation; enabled tests with valid settings remain available. Clear analysis overlays and Reset cancel any pending refresh.

Two validation findings were also fixed: project saving now preserves nonadjacent phase selections and explicit reference/comparison order; Ghost/Restore commands count blank comma-delimited session positions, and requesting a blank session cannot affect another point. Missing and ghosted observations retain their underlying identities and exclusions.

172 checks passed: JavaScript syntax and unchanged statistical/fit/cloud functions; per-test v56 numerical result and overlay equality; all four toggles independently and concurrently; visual/statistical coexistence; dropdown open/close without activation; unique IDs and accessible cloned control references; shared settings/targets; live counts, p-value interpretation, direction, correction and alternative changes; display/ink/legend updates; invalid/incomplete settings; pending data/numeric edits; current/legacy state, explicit reversed references and nonadjacent phases; ghost/blank positioning; cancelled queued refreshes; Phase 2 IQR visibility in both descriptive comparisons, unchanged results/center lines, state roundtrips and exports; report results/snapshots; calendar and multi-graph/tier all/selected full/compact SVG/PNG rasterization; and retained category, palette and cloud-range controls. Validation used JSDOM event/state checks and independent Sharp SVG/PNG rasterization. No full-browser binary was available, so these checks do not constitute a full-browser layout test. ZIP integrity and byte-identical root HTML files were verified.

## v56 Tau-U symbol legend and CDC-NonPar reference selection

**Tau-U legend:** a compact symbol key now appears below the live graph and in SVG/PNG exports and report graph snapshots. It explains the projected A trend, the cloud, the extra criterion ring, and the four descriptive cloud distinction categories: below 50% No difference, 50–<70% Negligible, 70–<90% Noticeable, and 90%+ Distinct. Swatches follow the Lighter–Darker ink setting. The legend stays outside the observation area, wraps in compact figures, identifies the series/phases, and follows Classroom/Technical and On/Cloud only modes. Off keeps the data/trend guide and hides this key. Hidden clouds and unapplied corrections are explained without displaying cloud swatches. The existing checkbox inside **Tau-U explanation** is now **Show Tau-U legend on graph and exports**; its saved value is retained. The longer explanation remains available under its caret.

**CDC-NonPar** (Conservative Dual Criteria Test, nonparametric version) is the new name for SCGraph2's existing Trend ± IQR/binomial comparison. The new **CDC-NonPar reference** selector chooses:

- **Trend** (default): the A-phase Theil–Sen projection, with the selected multiplier of A residual IQR.
- **Level**: the A-phase median, with the selected multiplier of A raw IQR. The criterion stays horizontal and does not depend on A's ordering or trend.

Choose a reference and run CDC-NonPar. Both modes retain the one-sided comparison: B observations strictly above the upper criterion for improvement by increase, or strictly below the lower criterion for improvement by decrease. Ties do not qualify. The existing binomial tail calculation uses B observations only and p0 = .50. Shading extends from A through B on the non-improvement side, and Classroom View retains criterion rings and a mode-specific key. The name identifies this configured IQR/binomial comparison; calculations and criteria are stated explicitly in the results/help.

The IQR multiplier remains editable and retains its existing default of 0.30 and saved values. Reference mode is saved in project JSON. Older projects default to Trend when no mode is stored; existing saved result/overlay snapshots are retained. Rerun an older comparison for the new CDC-NonPar result heading. Compact commands `CDC-NonPar, 1, 2`, `CDC, 1, 2`, and `CDCNonPar, 1, 2` are supported. Legacy `TrendBinomial`, `trend-binomial` and `binomial` commands remain aliases and use the currently selected reference. A Trend reference needs at least two active A observations; Level can use one with the existing small-phase caution.

PND results and shading are unchanged. The CDC Level/Trend choice does not change Tau-U's trend-based rings, cloud or statistics. Missing and ghosted positions, calendar mapping, phase-specific displayed numbering, Phase 1 IQR projections, descriptive Level/Trend comparisons, palette, menus, carets and accordion behavior are preserved.

150 checks passed using JSDOM interactions and independent Sharp SVG/PNG rasterization. On `Reference: 1,2,3,4|3,4,5,6,7`, Trend mode matches the previous comparison (0/5 crossing, p = 1), while Level gives median 2.5, IQR 1.5, margin 0.45 and 5/5 crossing (one-sided p = 0.03125). Level results are invariant to reordering A. Tests also covered aliases/natural requests/buttons, decrease direction in both modes, boundary ties, missing/ghost sessions, one-point/invalid trend handling, quantitative replotting, current/legacy save-load/reset, result/report mode labels, unchanged PND and Tau-U output, legend visibility/placement/ink/modes, multi-graph/tier and calendar full/compact/all/selected SVG/PNG rendering and report snapshots. The reproduction Tau-U remains 0.6875 with identical corrected pEst and rings at sessions 5 and 6. Representative legend and CDC figures were visually inspected. No full-browser binary was available; these are DOM/raster checks, not a full-browser layout test. ZIP integrity and byte-identical root HTML files were verified.

## v55 Level/Trend comparisons and Phase 1 IQR projections

Select two or more phases and run Level or Trend to obtain a single comparison result for those phases. The IQR and whisker variants provide the same comparison summaries.

- **Level:** each selected phase's active-observation median and the signed median difference (later phase minus earlier phase), in score units.
- **Trend:** each selected phase's Theil–Sen change per session; the signed slope difference (later slope minus earlier slope); and the fitted score difference at the later phase's first observed session (later fitted score minus the earlier trend projected to that same session). This second difference makes a level shift visible even for equal slopes.
- More than two phases are compared in chronological order between consecutive selected phases. Unselected phases are not analyzed. A single selected phase reports its own estimate and explains how to request a comparison.
- These are descriptive differences, with no added p-values or claims of significance. Trends with fewer than two active observations are reported as unavailable rather than as an estimated flat trend. A single-observation reference line remains visible. Existing cautions identify every selected phase with fewer than five active observations.

For **IQR Level**, Phase 1's median line and Q1/Q3 band now extend through all subsequent phases. For **IQR Trend**, only Phase 1's fitted trend and residual Q1/Q3 band project through subsequent phases. Center lines and IQR bands fitted to later phases stay within their own phase. Only selected phases are fitted. Projections include missing/ghost session positions, remain clipped to the plot, and stop at the last phase rather than the optional unused right margin.

Each new IQR overlay saves its reference-phase identity and projection scope. Repeated redraws, calendar mode, state save/load, reports and exports retain the Phase 1-only extension. Earlier saved IQR overlays and results retain their saved snapshots; rerun IQR Level/Trend after loading an older project to apply the new projection rule and comparison results.

Missing and ghosted observations stay excluded from fits and medians; their positions still count in session spacing. Calendar dates and displayed phase numbering do not change the estimates or differences. Small nonzero rates remain readable; differences within floating-point roundoff of zero are displayed as zero.

189 checks passed. Known-data fixtures verified medians 2.5 and 11 (difference +8.5), slopes +1 and +2 (difference +1), and a fitted gap +3 at the later phase's first observed session. Checks covered all visual-analysis variants; ascending, descending, constant, decimal and very small values; unequal/missing/ghost positions; one-point and no-active-data phases; nonadjacent and three-phase comparisons; commands and toggle buttons; per-graph/tier selection; unchanged quantitative results and overlays; concise/detailed report text; current/legacy state; calendar/renumbering invariance; Phase 1-only rendered IQR extents; repeated redraws; all/selected full/compact SVG and PNG rasterization; and retained palette, cloud and accordion controls. Level and Trend fitted values and quantiles match v54; all statistical and cloud-rendering functions remain unchanged.

Validation used JSDOM interactions and independent Sharp SVG/PNG rasterization, with visual inspection of the IQR Level and Trend figures. No full-browser binary was available, so this is not a full-browser layout test. ZIP integrity and byte-identical root HTML files were checked.

## v54 directional cloud and discrete series colors

The Tau-U cloud now stays darkest on the non-improvement side: toward lower scores for an increase, and higher scores for a decrease. Ten nested layers share that plot edge and fade toward the projected A trend plus/minus the selected residual-IQR margin, matching the existing extra-ring criterion. The fading edge updates with the IQR multiplier. This corrects the previous layering artifact that concentrated darkness near the trend while making lower, non-improving scores appear clear. The across-session running Tau-U categories, baseline-influence fade, Lighter–Darker range (internally 0–500), calculated statistics and criterion rings remain unchanged. The cloud is a custom directional visual reference, not a pointwise overlap probability or significance region.

Graph Controls → Graph → Plot Appearance → Series line style now offers eight named swatches for **Line and symbol color**: Black, Blue, Red, Orange, Green, Purple, Teal and Gray. Choosing a swatch updates the selected series line and symbol outlines together. Each series/tier retains its own color. Buttons support keyboard operation, visible focus, accessible names and a selected checkmark. Existing saved custom colors remain intact until a swatch is explicitly selected; changing the dash does not replace them.

226 checks passed using JSDOM and independent Sharp SVG/PNG rasterization. The exact reproduction data `Sniffing: 2,4,5,2|6,7,4,5` retained corrected Tau-U 0.6875, corrected one-sided pEst approximately 0.067765898, and criterion rings at sessions 5 and 6. At session 7.4 with maximum ink, sampled luminance progressed from 120.77 at lower non-improving scores to 255.00 above the criterion (higher means lighter), with no reversal across the sampled score range. The mirrored decrease display was also monotonic. At internal ink values 0/50/100/300/500, the low-score luminance was 255.00/230.73/208.17/151.04/120.77. Both directions were visually inspected.

Validation also covered all eight colors in actual line/marker SVG output, per-series and graph switching, current/legacy save-load including custom colors, unchanged inference results and overlay numbers, IQR updates, missing/ghost sessions, calendar mapping, independent Y ranges, multiple graphs/tiers, all/selected full/compact SVG and PNG rasterization, report snapshots, visualization modes, and exclusive category controls. No full-browser binary was available; these are DOM/raster checks, not a full-browser layout test. The browser PNG exporter itself is unchanged and uses the same complete SVG.

## v53 cloud contrast correction

The darkness slider now reads **Lighter–Darker**, with no numeric percentage readout. Its internal range extends to 500, preserving existing saved values and the default value of 100. Accessible value descriptions use Hidden, Light, Default, Darker and Darkest. The cloud now uses deeper blue ink (#1f4e79), addressing the washed-out appearance caused by pale ink combined with gradient and layer opacity. Ten layers, category thresholds, smooth fade, criterion rings and statistics are unchanged.

85 checks passed. On the reproduction data `Sniffing: 2,4,5,2|6,7,4,5`, average luminance in a fixed cloud-only region below the projection was 231.68 for v52 at its maximum, 211.26 for v53 at the former maximum position, and 190.31 at the new maximum. Lower luminance means darker ink. Pixel measurements across internal values 0,25,50,100,300,500 were strictly monotonic. The maximum cloud was visually inspected. Tau-U remained 0.6875 and the one-sided corrected pEst remained approximately 0.067765898; sessions 5 and 6 retained their criterion rings.

Checks covered old/new saved values, clamping/defaults, accessible qualitative readout, unchanged inference functions/results, decrease data, missing and ghost sessions, calendar and multiple graph/tier full/compact SVG/PNG rasterization, report snapshots and exclusive categories. Validation used JSDOM and Sharp; no full-browser run was available. The browser PNG exporter is unchanged and consumes the same complete SVG.

## v52 Tau-U changes

- **Cloud darkness:** running corrected Tau-U now sets the descriptive cloud category: below .50 dark; .50–.69 medium-dark; .70–.89 light; .90+ unshaded. The baseline correction still supplies a fade across B, and the Lighter–Darker ink slider still applies. A small nonzero correction no longer makes a negligible-difference cloud nearly invisible. Smooth interpolation and ten layers remain. These are user-defined distinction categories, separate from statistical significance.
- **Corrected pEst:** the corrected contrast now reports an estimated p-value, one-sided by default. The Tau-U effect size and the existing uncorrected p-value are unchanged. For `Sniffing: 2,4,5,2|6,7,4,5`, Always correct gives Tau-U = 0.6875 and one-sided pEst ≈ 0.067766.
- **Criterion rings:** B observations beyond the improvement-side A trend ± selected residual-IQR multiplier receive an extra ring. At the default 0.3 multiplier, sessions 5 and 6 in that example qualify. Changing the multiplier updates rings immediately without changing Tau-U or pEst. On and Cloud only show criterion rings; Off hides them. Ordinary classroom observations remain plain. A ring is a visual criterion flag, not an individual-point significance test.

The corrected pEst uses S_AB − S_A, with reversed A occasion ranks followed by a tied B block, tie-adjusted Kendall-S variance and a normal approximation without continuity correction. The signed upper tail tests the chosen improvement direction; the existing two-sided option uses both tails. This construction follows the A-vs-B-minus-A-trend calculation in [scan::tau_u](https://rdrr.io/cran/scan/src/R/tau_u.R) and its [Kendall-S variance](https://rdrr.io/cran/scan/src/R/private_kendall.R). It assumes independent/exchangeable observations and does not adjust for serial dependence or selection of the correction in Auto mode. The p-value is nominal and approximate; caution remains for phases with fewer than five active points. Software conventions differ; [SingleCaseES](https://jepusto.github.io/SingleCaseES/articles/Effect-size-definitions.html) omits corrected inference. No exact test or confidence interval is asserted here.

204 checks passed, including 24 one-/two-sided comparisons against independent SciPy asymptotic Kendall references across ties, unequal phase lengths and both directions; unchanged effect sizes/raw p-values; cloud category boundaries and slider behavior; ring thresholds and missing/ghost sessions; calendar and compact rendering; project save/load, older cloud compatibility, report snapshots and the exclusive category accordion. Representative SVGs were independently rasterized and visually inspected. No full-browser binary was available. Older saved results remain snapshots: rerun Tau-U to refresh pEst.

## Plot Control categories

Graph Controls now has four major collapsible categories: **Global**, **Graph**, **X-Axis**, and **Y-Axis**. All four start rolled up. Click a category caret to expand or collapse its entire contents; opening a category automatically closes the other three. Selecting the open category closes it.

- Global contains the overall figure title and direct-editing explanation.
- Graph contains graph selection, title, phase labels, plot appearance, series/phase-boundary styles, grid and visibility choices, goal lines and graph commands.
- X-Axis contains the axis label, session timeline, dates and displayed phase numbering.
- Y-Axis contains the axis label, limits, tick interval and scaling choices.

Existing explanations retain their smaller carets inside the categories. Shared Apply controls and Clear analysis overlays buttons remain below the categories.

The v51 change passed syntax and DOM interaction checks: initial collapsed state, exclusive category selection, closing the active category, rapid switching, programmatic opening, nested help, outer accordion, complete preservation of control attributes, redraw and save/load. All calculation, rendering and save/load code is unchanged from v50; only category interaction wiring and the build number changed. Default/calendar/Tau-U graph rendering and results, plus compact SVG exports, matched v50. These were DOM checks rather than a full-browser layout run.

## Restored X-Axis / Session Timeline

Open **Graph Controls → X-Axis / Session Timeline**. The controls remain visible; explanations start collapsed behind small carets.

- **Sequential sessions:** equally spaced positions, with Auto, 10, 15, 20, 25, 30, or a custom positive whole-number minimum. The app always includes all actual sessions. Existing saved projects without timeline settings retain the 15-session default.
- **Proportional calendar time:** enter the first session date and select recurring weekdays. Session 1 uses the exact date entered; subsequent positions use the next selected weekday. Session numbers appear above dates, which rotate when needed.
- **Edited dates:** click a plotted date, or focus it and press Enter. Each edited date must remain chronologically between its neighbors. Escape cancels. Returning a date to its generated value removes its override. Changing the first date or recurring weekdays regenerates the schedule and clears overrides.
- **Displayed session numbering by phase:** enter an optional starting number for each phase of the selected graph. Blank continues the preceding numbering. Shared graphs follow the first series/tier for their common labels.

Dates and displayed numbers affect presentation only. Missing comma-delimited positions still consume sessions, ghosted observations remain excluded from analyses, and underlying observation/session identities do not change. Trend fits and all statistical calculations continue to use the original session positions.

Timeline choices are shared across graphs and tiers. Each graph retains its independent Y scale and phase numbering. Project state and editable graph JSON preserve these settings, including date overrides. Compatible older schedules and explicit date lists are restored. Invalid custom spans or date schedules produce feedback and cannot be exported or silently saved as a different timeline.

## Exports and preserved features

Graph → Export Graph retains full/compact layout, all/selected graphs, SVG/PNG and compact margin choices. Compact export trims unused right-side session padding. Calendar trend lines, IQR bands, reference shading, phase connectors and grids use the same session-to-date mapping as the data. PNG export decodes the complete standalone SVG to retain paths, cloud gradients and clipping, with a primitive-rendering fallback. Report graph insertion captures a static snapshot with the current timeline.

The v48 restoration ported the earlier SCGraph2 2.2.29 timeline functionality into the v47 framework. This release continues that v48 framework. It preserves the current Project/Report/Graph/Help menus, independent report toggle, exclusive full-height right accordion, help carets, five-item report Insert dropdown and caret fix, report autosave, analyses/results, Tau-U darkness slider/classroom view, both grid directions, and Phase 1 IQR projections. Visible and saved-state build numbers are 59.

## Validation

The v48 restoration passed 265 checks: JavaScript syntax; unchanged v47 parser/statistical/result functions and numerical results; missing/ghost session identities; sequential presets/custom validation; weekday/weekend calendars, date overrides and editing; displayed numbering; current/v47/older save-load and graph JSON; unequal overlaid lengths, three graphs and staggered tiers; independent Y scales and grids; every full/compact/all/selected SVG/PNG export combination; report snapshots and caret insertion; and preserved UI controls.

DOM interactions were checked in JSDOM. PNG encoding used a native Canvas SVG decoder. Representative SVGs were independently rasterized and visually inspected, including increase/decrease Tau-U clouds, nonzero residual-IQR projection, trend shading, dense date labels and compact layouts. ZIP integrity and byte equality of `index.html` and `SCGraph2.html` were checked. No full-browser binary was available, so these checks are not a full-browser layout test.

# AI-Oriented Interpretation Guide — Figure 6.2-c

## Figure Identity
- Figure: 6.2-c
- Title: VOLTAGE WAVEFORMS — SETUP AND HOLD TIMES
- Image: `6.2-c.png`
- Context source: `Tables_related.md`
- Source status: user-verified

## Purpose
This figure defines setup and hold timing relationships between the data input and the active clock/reference transition.

## Primary Parameters
- `tsu`: setup time; interval during which input data must be stable before the active reference edge.
- `th`: hold time; interval during which input data must remain stable after the active reference edge.

## Waveform geometry (curves and intersections)
- **Timing Input (CLK):** drawn with dashed segments away from its single transition — dashed means "not specified / don't care" (a standard convention), not an additional real transition. The one solid rising crossing through `V_M` is the reference edge for both `tsu` and `th`.
- **Data Input:** two crossings of `V_M` — falls before the CLK reference edge (marks the start of `tsu`) and rises after it (marks the end of `th`).
- `tsu` = time from the Data falling crossing to the CLK reference-edge crossing.
- `th` = time from the CLK reference-edge crossing to the Data rising crossing.

As drawn, Data is held low across the CLK edge, illustrating a "Data low" capture case; a mirrored drawing would illustrate "Data high". Unlike `images_6.1`, `Tables_related.md` for `images_6.2` does not provide separate Data-high/Data-low `tsu` rows or any numeric `tsu`/`th` limits — do not fabricate them.

## Visual Interpretation
Use the PNG to identify the data transition, active clock/reference edge, threshold/reference levels, and the intervals labelled or implied by the waveform.

## AI Rules
1. Identify the active reference edge before interpreting `tsu` or `th`.
2. `tsu` is measured before the active reference edge.
3. `th` is measured after the active reference edge.
4. Do not confuse setup/hold timing with propagation delay `tpd`.
5. Use `Tables_related.md` and the YAML for electrical test context.
6. Do not infer unspecified numerical limits from the image alone; `tsu`/`th` currently have no numeric limits in the available source for `images_6.2`.

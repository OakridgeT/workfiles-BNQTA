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

## Visual Interpretation
Use the PNG to identify the data transition, active clock/reference edge, threshold/reference levels, and the intervals labelled or implied by the waveform.

## AI Rules
1. Identify the active reference edge before interpreting `tsu` or `th`.
2. `tsu` is measured before the active reference edge.
3. `th` is measured after the active reference edge.
4. Do not confuse setup/hold timing with propagation delay `tpd`.
5. Use `Tables_related.md` and the YAML for electrical test context.
6. Do not infer unspecified numerical limits from the image alone.

# AI-Oriented Interpretation Guide — Figure 6.2-d

## Figure Identity
- Figure: 6.2-d
- Title: VOLTAGE WAVEFORMS — ENABLE AND DISABLE TIMES, LOW- AND HIGH-LEVEL ENABLING
- Image: `6.2-d.png`
- Context source: `Tables_related.md`
- Source status: user-verified

## Purpose
This figure illustrates timing associated with enabling and disabling an output, including low- and high-level enabling conditions.

## Primary Parameters
- Enable: `tPZL`, `tPZH`, equivalent to `ten`.
- Disable: `tPLZ`, `tPHZ`, equivalent to `tdis`.

## Waveform Semantics
- Waveform 1: output is internally low except when disabled by the output control.
- Waveform 2: output is internally high except when disabled by the output control.

## Visual Interpretation
Use the PNG to identify the output-control transition, the resulting output transition, the high-impedance interval, and the reference thresholds. The image provides timing relationships; numerical limits must come from the associated source tables.

## AI Rules
1. Determine whether the measurement is an enable or disable transition.
2. For enable, map the transition to `tPZL` or `tPZH`.
3. For disable, map the transition to `tPLZ` or `tPHZ`.
4. Apply the source equivalences `ten` and `tdis`.
5. Use waveform 1 for the internally-low case and waveform 2 for the internally-high case.
6. Do not assume all parameters apply to every device.

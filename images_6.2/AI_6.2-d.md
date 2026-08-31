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

## Switch context
Per Figure 6.2's test-selection table: `tPZL`/`tPLZ` both apply with `S1 = VLOAD` (Output Waveform 1); `tPZH`/`tPHZ` both apply with `S1 = GND` (Output Waveform 2).

## Waveform geometry (curves and intersections)
- **Output Control:** two crossings of `V_M` — falling (crossing 1, the *enable* edge) then rising (crossing 2, the *disable* edge).
- **Output Waveform 1** (S1 = VLOAD): falls through `V_M` in step with the enable edge — this is `tPZL` — then rises asymptotically toward `V_LOAD/2`, measured against the reference line `V_OL + V_D` (not `V_M`, since the curve approaches the high-impedance level asymptotically rather than crossing it) in step with the disable edge — this is `tPLZ`.
- **Output Waveform 2** (S1 = GND): rises through `V_M` in step with the enable edge — this is `tPZH` — then falls asymptotically toward ≈0 V, measured against the reference line `V_OH - V_D` in step with the disable edge — this is `tPHZ`.

**tPZL and tPLZ are both measured on Waveform 1 (S1 = VLOAD); tPZH and tPHZ are both measured on Waveform 2 (S1 = GND).** Do not pair tPZL with tPZH or tPLZ with tPHZ. `V_D` is the test-condition value defined per VCC in Figure 6.2's table (0.15 V or 0.3 V depending on VCC).

## Visual Interpretation
Use the PNG to identify the output-control transition, the resulting output transition, the high-impedance interval, and the reference thresholds. The image provides timing relationships; numerical limits must come from the associated source tables.

## AI Rules
1. Determine whether the measurement is an enable or disable transition.
2. For enable, map the transition to `tPZL` or `tPZH`.
3. For disable, map the transition to `tPLZ` or `tPHZ`.
4. Apply the source equivalences `ten` and `tdis`.
5. Use waveform 1 (S1 = VLOAD) for the internally-low case and waveform 2 (S1 = GND) for the internally-high case.
6. Do not assume all parameters apply to every device.

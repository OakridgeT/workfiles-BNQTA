# AI-Oriented Interpretation — Figure 6.1-d

## Figure identity
- Figure: 6.1-d
- Title: VOLTAGE WAVEFORMS — ENABLE AND DISABLE TIMES, LOW- AND HIGH-LEVEL ENABLING
- Image: `6.1-d.png`
- Parameters: `tPZL`, `tPZH`, `tPLZ`, `tPHZ`

## Purpose
This waveform defines output enable and disable timing for low- and high-level enabling conditions.

## AI visual-grounding instructions
Use the PNG to identify output-control transitions, Q transitions, high-impedance intervals, polarity, and timing markers. Use `AI_6.1-d.yaml` for structured relationships. Do not infer numerical limits from graphical scale.

## Parameter mapping
- `tPZL` and `tPZH` are equivalent to `ten`.
- `tPLZ` and `tPHZ` are equivalent to `tdis`.
- Figure 6.0 associates `tPLZ/tPZL` with S1 = VLOAD and `tPHZ/tPZH` with S1 = GND.

## Waveform geometry (curves and intersections)
- **Output Control:** two crossings of `V_M` — falling (crossing 1, the *enable* edge) then rising (crossing 2, the *disable* edge).
- **Output Waveform 1** (S1 = VLOAD): falls through `V_M` in step with the enable edge — this is `tPZL` — then rises asymptotically toward `V_LOAD/2`, measured against the reference line `V_OL + V_D` (not `V_M`, since the curve approaches the high-impedance level asymptotically rather than crossing it) in step with the disable edge — this is `tPLZ`.
- **Output Waveform 2** (S1 = GND): rises through `V_M` in step with the enable edge — this is `tPZH` — then falls asymptotically toward ≈0 V, measured against the reference line `V_OH - V_D` in step with the disable edge — this is `tPHZ`.

**tPZL and tPLZ are both measured on Waveform 1 (S1 = VLOAD); tPZH and tPHZ are both measured on Waveform 2 (S1 = GND).** Do not pair tPZL with tPZH or tPLZ with tPHZ — an earlier revision of `AI_6.1-d.yaml` made exactly that mistake; it has been corrected to match this figure and Figure 6.0's test-selection table.

## Waveform semantics
- **Waveform 1:** output is internally low except when disabled by the output control.
- **Waveform 2:** output is internally high except when disabled by the output control.

## Test context
- `CL = 15 pF` for the switching-characteristics condition.
- `RL = 1 MΩ` in the Figure 6.0 load circuit.
- Timing requirements cover TA = -40°C to +85°C and TA = -40°C to +125°C.

## Interpretation rules
1. Identify the output-control transition and the resulting Q transition or high-impedance state.
2. Determine whether the measurement is an enable (`ten`) or disable (`tdis`) event.
3. Use the PNG for visual timing geometry and the YAML/tables for structured context.
4. Do not confuse enable/disable timing with propagation delay (`tpd`).
5. Outputs are measured one at a time, with one transition per measurement.
6. Not every parameter or waveform is applicable to all devices.

## Source status
Based on the user-verified current `Tables_related.md`.

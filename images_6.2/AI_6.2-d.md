# AI Interpretation Guide — Figure 6.2-d

## Figure Identity

- **Figure:** 6.2-d
- **Image:** `6.2-d.png`
- **Title:** VOLTAGE WAVEFORMS — ENABLE AND DISABLE TIMES, LOW- AND HIGH-LEVEL ENABLING
- **Parameters:** `tPLZ`, `tPZL`, `tPHZ`, `tPZH`
- **Equivalent parameters:** `tdis`, `ten`
- **Parent test circuit:** `6.2.png`
- **Structured companion:** `AI_6.2-d.yaml`

## Purpose

Figure 6.2-d illustrates timing associated with **enabling and disabling a tri-state output**, including the transition between a valid LOW or HIGH output and the **high-impedance (HIGH-Z)** state.

## Waveform Semantics

The source notes define two waveform cases:

- **Waveform 1:** output is internally LOW except when disabled by the output control.
- **Waveform 2:** output is internally HIGH except when disabled by the output control.

The AI must recognize `HIGH-Z` as a third output state rather than treating it as an ordinary HIGH or LOW voltage level.

## Parameter Interpretation

| Parameter | Operation | Meaning | Equivalent |
|---|---|---|---|
| `tPLZ` | Disable | LOW output → HIGH-Z | `tdis` |
| `tPHZ` | Disable | HIGH output → HIGH-Z | `tdis` |
| `tPZL` | Enable | HIGH-Z → LOW output | `ten` |
| `tPZH` | Enable | HIGH-Z → HIGH output | `ten` |

## Visual Grounding

When inspecting `6.2-d.png`, identify:

1. Output-control waveform.
2. Output waveform.
3. Initial output state.
4. Final output state.
5. High-impedance interval, when present.
6. Voltage reference level and timing thresholds.
7. Timing arrows associated with enable or disable operation.

## Switch Relationship

The parent load circuit defines:

- `S1 = VLOAD` → `tPLZ / tPZL`
- `S1 = GND` → `tPHZ / tPZH`

## AI Interpretation Rules

- Determine whether the output is normally LOW or normally HIGH before selecting the parameter.
- Recognize HIGH-Z as an electrical output state with the driver disabled.
- For disable timing, identify the control transition and subsequent entry into HIGH-Z.
- For enable timing, identify the exit from HIGH-Z and the resulting valid output state.
- Do not confuse `tPLZ`/`tPHZ` with propagation delay.
- Use the PNG for state transitions and timing-arrow geometry; use the tables for numerical limits.

## Measurement Conditions

The associated load circuit provides VCC-dependent values for `VM`, `VLOAD`, `CL`, `RL`, and `VD`. `CL` includes probe and jig capacitance.

Input generators are specified as:

- `PRR ≤ 10 MHz`
- `Z = 50 Ω`

Outputs are measured one at a time, with one transition per measurement.

## Data Quality Note

The source Markdown contains OCR artifacts (`£` for `≤` and `W` for `Ω`). This AI-oriented file normalizes those symbols when their intended meaning is unambiguous.

## Related Figures

- `6.2` → load circuit
- `6.2-a` → pulse duration
- `6.2-b` → propagation delay
- `6.2-c` → setup and hold times

# AI Interpretation Guide — Figure 6.2-a

## Figure Identity

- **Figure:** 6.2-a
- **Image:** `6.2-a.png`
- **Title:** VOLTAGE WAVEFORMS — PULSE DURATION
- **Primary parameter:** `tW`
- **Parent test circuit:** `6.2.png`
- **Structured companion:** `AI_6.2-a.yaml`

## Purpose

Figure 6.2-a shows the voltage waveform relationship used to define **pulse duration (`tW`)**.

The AI should interpret the graphical timing interval from the waveform and its voltage reference levels. Numerical guaranteed limits must come from the appropriate switching-characteristics table, not from the apparent scale of the PNG.

## Visual Interpretation

When examining `6.2-a.png`, identify:

1. The active pulse.
2. The beginning of the pulse interval.
3. The end of the pulse interval.
4. The voltage reference/threshold used by the drawing.
5. The timing arrow or bracket representing `tW`.
6. The waveform polarity and whether the pulse is active-high or active-low.

## Timing Parameter

### `tW` — Pulse Duration

`tW` is the duration of the specified pulse, measured between the relevant waveform reference points shown in the figure.

- Parameter: `tW`
- Unit: `ns`
- Measurement type: temporal interval

## Associated Test Conditions

The parent Figure 6.2 load circuit specifies `CL` values of 30 pF or 50 pF depending on VCC, with the applicable temperature range determined by the associated timing table.

## AI Visual Grounding Rules

- Use the PNG to identify waveform polarity, transition points, threshold markers, and timing arrows.
- Use `AI_6.2-a.yaml` for structured parameter semantics.
- Use `Tables_related.md` and the relevant datasheet table for numerical limits.
- Do not calculate `tW` from image pixels unless the time-axis scale is explicitly available and calibrated.
- Do not confuse pulse duration with propagation delay, setup time, or hold time.

## Related Figures

- `6.2` → load circuit
- `6.2-b` → propagation delay
- `6.2-c` → setup and hold times
- `6.2-d` → enable and disable times

## Common Measurement Notes

- `CL` includes probe and jig capacitance.
- Input pulses are supplied by generators with `PRR ≤ 10 MHz` and `Z = 50 Ω`.
- Outputs are measured one at a time, with one transition per measurement.
- Not all parameters and waveforms apply to all devices.

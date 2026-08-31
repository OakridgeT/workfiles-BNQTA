# AI-Oriented Interpretation — Figure 6.1-a

## Figure identity
- Figure: 6.1-a
- Title: VOLTAGE WAVEFORMS — PULSE DURATION
- Image: `6.1-a.png`
- Associated parameter: `tw`

## Purpose
This waveform defines the pulse-duration measurement for CLK when CLK is high or low.

## AI visual-grounding instructions
Use the PNG to identify CLK, its high/low interval, voltage reference crossings, and measurement markers. Use `AI_6.1-a.yaml` for numeric limits. Do not infer numerical limits from pixel distances.

## Waveform geometry (curves and intersections)
The figure has a single "Input" curve referenced against two rails, `V_I` (high) and `0 V` (low), and crosses the threshold `V_M` exactly twice:
1. **First crossing (falling):** the curve transitions from `V_I` down through `V_M` to `0 V`.
2. **Second crossing (rising):** the curve transitions from `0 V` back up through `V_M` to `V_I`.

`tw` is the horizontal distance between these two `V_M` crossings. As drawn, the interval spans the **low** portion of the pulse (`tw` for CLK low). The same measurement method — the time between two consecutive `V_M` crossings — applies symmetrically to the **high** portion of the pulse (`tw` for CLK high: a rising crossing followed by a falling crossing), which this figure does not draw separately; both cases share one definition and one minimum limit.

## Parameter
`tw` = pulse duration, CLK high or low.

Minimum `tw` from Tables 5.6 and 5.7: 2.5 ns for each listed VCC condition.

Maximum clock frequency: 160 MHz for the listed VCC conditions.

## Context
Timing requirements apply over TA = -40°C to +85°C and TA = -40°C to +125°C. Switching characteristics are specified at TA = -40°C to +85°C with CL = 15 pF.

## Interpretation rules
1. Identify whether the measured CLK pulse is high or low.
2. Measure the pulse duration using the voltage-reference convention shown in the PNG.
3. Use the YAML/table values for specification limits.
4. Do not confuse `tw` with propagation delay (`tpd`) or setup/hold (`tsu`, `th`).
5. Not every parameter or waveform is applicable to all devices.

## Source status
Based on the user-verified current `Tables_related.md`.

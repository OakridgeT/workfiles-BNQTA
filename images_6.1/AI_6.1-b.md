# AI-Oriented Interpretation — Figure 6.1-b

## Figure identity
- Figure: 6.1-b
- Title: VOLTAGE WAVEFORMS — PROPAGATION DELAY TIMES INVERTING AND NONINVERTING OUTPUTS
- Image: `6.1-b.png`
- Parameters: `tPLH`, `tPHL`, equivalent to `tpd`

## Purpose
This waveform defines propagation delay from the relevant CLK input transition to the corresponding Q output transition for inverting and noninverting outputs.

## AI visual-grounding instructions
Use the PNG to identify CLK, Q, transition polarity, reference voltage crossings, and timing markers. Use `AI_6.1-b.yaml` for numerical specifications. Do not derive timing limits from image scale.

## Parameter mapping
- `tPLH` / `tPHL` = `tpd`.
- `tPLH` represents a low-to-high output transition.
- `tPHL` represents a high-to-low output transition.
- Figure 6.0 uses S1 = Open for the propagation-delay test group.

## Switching characteristics — TA = -40°C to +85°C, CL = 15 pF
| VCC | tpd MIN | tpd MAX |
|---|---:|---:|
| 1.8 V ± 0.15 V | 3 ns | 9.1 ns |
| 2.5 V ± 0.2 V | 1.5 ns | 6 ns |
| 3.3 V ± 0.3 V | 1.3 ns | 4.2 ns |
| 5 V ± 0.5 V | 1.1 ns | 3.8 ns |

## Interpretation rules
1. Identify the input transition and the corresponding Q transition.
2. Determine whether the output transition is low-to-high or high-to-low.
3. Apply the reference-crossing convention shown in the PNG.
4. Use the YAML/table values for specification limits.
5. Do not confuse `tpd` with `tsu`, `th`, `ten`, or `tdis`.
6. Measurements are made one transition at a time.
7. Not every parameter or waveform is applicable to all devices.

## Source status
Based on the user-verified current `Tables_related.md`.

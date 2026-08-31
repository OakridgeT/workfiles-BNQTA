# AI-Oriented Interpretation Guide — Figure 6.2-b

## Figure Identity
- Figure: 6.2-b
- Title: VOLTAGE WAVEFORMS — PROPAGATION DELAY TIMES INVERTING AND NONINVERTING OUTPUTS
- Image: `6.2-b.png`
- Context source: `Tables_related.md`
- Source status: user-verified

## Purpose
This figure illustrates propagation delay timing for inverting and noninverting outputs.

## Primary Parameters
- `tPLH`: propagation delay associated with the low-to-high output transition.
- `tPHL`: propagation delay associated with the high-to-low output transition.
- Both are identified in the source notes as equivalent to `tpd`.

## Waveform geometry (curves and intersections)
The figure has three rows, all crossing `V_M`:
- **Input:** two crossings — falls (V_I → 0 V) at crossing 1, rises (0 V → V_I) at crossing 2.
- **Output, upper row (inverting output):** rises (V_OL → V_OH) at the point aligned with Input crossing 1 — this rising output edge is `tPLH` — then falls (V_OH → V_OL) at the point aligned with Input crossing 2 — this falling output edge is `tPHL`.
- **Output, lower row (noninverting output):** falls (V_OH → V_OL) aligned with Input crossing 1 — this is `tPHL` — then rises (V_OL → V_OH) aligned with Input crossing 2 — this is `tPLH`.

Both output rows react to the **same** two Input transitions but move in **opposite** directions from each other. The label to use is decided by the direction of the specific output edge being measured (rising → `tPLH`, falling → `tPHL`), not by which row it is or by the Input's own direction.

## Visual Interpretation
Use the PNG to identify input/output polarity, the relevant input transition, output transition, reference thresholds, and the measured time interval. Do not infer exact nanosecond values from image dimensions.

## Electrical Context
Tables 5.9 and 5.10 provide `tpd` minimum/maximum values versus VCC and temperature range. Figure 6.2 supplies the associated load/test configuration.

### Table 5.9 — TA = -40°C to +85°C, CL = 30 pF or 50 pF
| VCC | tpd MIN | tpd MAX |
|---|---:|---:|
| 1.8 V ± 0.15 V | 4.4 ns | 9.9 ns |
| 2.5 V ± 0.2 V | 2.3 ns | 7 ns |
| 3.3 V ± 0.3 V | 2 ns | 5.2 ns |
| 5 V ± 0.5 V | 1.3 ns | 4.5 ns |

### Table 5.10 — TA = -40°C to +125°C, CL = 30 pF or 50 pF
| VCC | tpd MIN | tpd MAX |
|---|---:|---:|
| 1.8 V ± 0.15 V | 4.4 ns | 12.5 ns |
| 2.5 V ± 0.2 V | 2.3 ns | 8.5 ns |
| 3.3 V ± 0.3 V | 2 ns | 6 ns |
| 5 V ± 0.5 V | 1.3 ns | 5.5 ns |

## AI Rules
1. Determine whether the output transition is low-to-high or high-to-low.
2. Map the transition to `tPLH` or `tPHL` accordingly.
3. Treat both as `tpd` according to the source notes.
4. Use tabulated values for numerical limits.
5. Do not transfer a value from one VCC or temperature condition to another.

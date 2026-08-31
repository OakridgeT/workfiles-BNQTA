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

## Visual Interpretation
Use the PNG to identify input/output polarity, the relevant input transition, output transition, reference thresholds, and the measured time interval. Do not infer exact nanosecond values from image dimensions.

## Electrical Context
Tables 5.9 and 5.10 provide `tpd` minimum/maximum values versus VCC and temperature range. Figure 6.2 supplies the associated load/test configuration.

## AI Rules
1. Determine whether the output transition is low-to-high or high-to-low.
2. Map the transition to `tPLH` or `tPHL` accordingly.
3. Treat both as `tpd` according to the source notes.
4. Use tabulated values for numerical limits.
5. Do not transfer a value from one VCC or temperature condition to another.

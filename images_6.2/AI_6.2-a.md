# AI-Oriented Interpretation Guide — Figure 6.2-a

## Figure Identity
- Figure: 6.2-a
- Title: VOLTAGE WAVEFORMS — PULSE DURATION
- Image: `6.2-a.png`
- Context source: `Tables_related.md`
- Source status: user-verified

## Purpose
This figure represents the voltage waveform used to define pulse duration.

## Primary Parameter
- `tW`: pulse duration.

## Visual Interpretation
Use the PNG to identify the active portion of the pulse and the timing reference levels/markers shown by the manufacturer. The numerical specification must come from the associated switching-characteristics tables, not from pixel measurements.

## Associated Conditions
Tables 5.9 and 5.10 apply to the switching-characteristics context. The load configuration can use `CL = 30 pF` or `50 pF` depending on VCC as defined in `Tables_related.md`.

## AI Rules
1. Identify the pulse and its active interval from the image.
2. Interpret `tW` as pulse duration, not propagation delay.
3. Use the YAML and `Tables_related.md` for electrical test conditions.
4. Do not invent a numerical `tW` value if it is not explicitly provided by the source table.
5. Preserve the distinction between visual evidence and tabulated specification.

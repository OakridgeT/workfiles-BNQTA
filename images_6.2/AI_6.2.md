# AI-Oriented Interpretation Guide — Figure 6.2

## Figure Identity
- Figure: 6.2
- Title: LOAD CIRCUIT
- Image: `6.2.png`
- Context source: `Tables_related.md`
- Source status: user-verified

## Purpose
Figure 6.2 defines the electrical load and switching configuration used to measure timing characteristics represented by Figures 6.2-a through 6.2-d.

## Test Selection
| Timing parameters | S1 condition |
|---|---|
| `tPLH / tPHL` | Open |
| `tPLZ / tPZL` | VLOAD |
| `tPHZ / tPZH` | GND |

## Electrical Conditions
The load configuration varies with VCC. The authoritative values are maintained in `Tables_related.md` and represented structurally in `AI_6.2.yaml`.

## AI Visual Grounding
Use the image to determine circuit topology and S1/load routing. Do not derive precise component values from image geometry; use the YAML/table context.

## Relationship to Timing Figures
- `6.2-a`: pulse duration (`tW`)
- `6.2-b`: propagation delay (`tPLH`, `tPHL`, equivalent to `tpd`)
- `6.2-c`: setup and hold (`tsu`, `th`)
- `6.2-d`: enable/disable (`tPZL`, `tPZH`, `tPLZ`, `tPHZ`)

## Source Notes
- `CL` includes probe and jig capacitance.
- Waveform 1 represents an output internally low except when disabled.
- Waveform 2 represents an output internally high except when disabled.
- Input pulses are supplied by generators with the characteristics stated in `Tables_related.md`.
- Outputs are measured one at a time, with one transition per measurement.
- `tPLZ` and `tPHZ` are the same as `tdis`.
- `tPZL` and `tPZH` are the same as `ten`.
- `tPLH` and `tPHL` are the same as `tpd`.
- Not all parameters and waveforms apply to all devices.

## AI Interpretation Rule
Treat `Tables_related.md` as the verified source for numerical values. Treat the PNG as visual evidence and this document as semantic guidance; do not invent unspecified timing values.

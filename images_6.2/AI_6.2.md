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

## Circuit topology
The "From Output Under Test" node feeds a shared junction with two parallel branches to ground: `CL` (load capacitance, see Note A) and a shunt `RL` (load resistance to ground). From that same junction, the signal continues in series through a **second, separate** resistor — also labeled `RL` — to switch `S1`, which selects one of three terminations: `V_LOAD`, `Open`, or `GND`.

The schematic reuses the label `R_L` for two different resistors: one shunt (output node to ground) and one in series (junction to S1). The `RL` column in the electrical-conditions table (1 kΩ or 500 Ω depending on VCC) gives a single value; both resistors are physically distinct components in the same signal path — do not collapse them into a single resistor when describing the circuit.

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

# AI-Oriented Interpretation — Figure 6.0

## Figure identity
- Figure: 6.0
- Title: LOAD CIRCUIT
- Image: `6.0.png`
- Primary source: `Tables_related.md`
- Role: Defines the electrical load and switch configuration used for timing measurements associated with Figures 6.1-a through 6.1-d.

## AI visual-grounding instructions
Use `6.0.png` for circuit topology, load components, VLOAD, and S1 position/function. Use the YAML for structured numerical conditions. Do not infer unspecified values from visual geometry.

## Circuit topology
The "From Output Under Test" node feeds a shared junction with two parallel branches to ground: `CL` (load capacitance, see Note A) and a shunt `RL` (load resistance to ground). From that same junction, the signal continues in series through a **second, separate** resistor — also labeled `RL` — to switch `S1`, which selects one of three terminations: `V_LOAD`, `Open`, or `GND`.

The schematic reuses the label `R_L` for two different resistors: one shunt (output node to ground) and one in series (junction to S1). Both are 1 MΩ per the electrical-conditions table (only one `RL` value is given), but they are physically distinct components in the same signal path — do not collapse them into a single resistor when describing the circuit.

## Test selection
| Timing group | S1 condition |
|---|---|
| `tPLH`, `tPHL` | Open |
| `tPLZ`, `tPZL` | VLOAD |
| `tPHZ`, `tPZH` | GND |

## Electrical conditions
| VCC | VI inputs | Input tr/tf | VM | VLOAD | CL | RL | VD |
|---|---|---|---|---|---|---|---|
| 1.8 V ± 0.15 V | VCC | ≤2 ns | VCC/2 | 2 × VCC | 15 pF | 1 MΩ | 0.15 V |
| 2.5 V ± 0.2 V | VCC | ≤2 ns | VCC/2 | 2 × VCC | 15 pF | 1 MΩ | 0.15 V |
| 3.3 V ± 0.3 V | 3 V | ≤2.5 ns | 1.5 V | 6 V | 15 pF | 1 MΩ | 0.3 V |
| 5 V ± 0.5 V | VCC | ≤2.5 ns | VCC/2 | 2 × VCC | 15 pF | 1 MΩ | 0.3 V |

## Parameter equivalence
- `tPLH` and `tPHL` correspond to `tpd`.
- `tPLZ` and `tPHZ` correspond to `tdis`.
- `tPZL` and `tPZH` correspond to `ten`.

## Measurement rules
1. `CL` includes probe and jig capacitance.
2. Outputs are measured one at a time.
3. One transition is used per measurement.
4. Detailed waveform interpretation belongs to Figures 6.1-a through 6.1-d.
5. Not every parameter or waveform is applicable to every device.

## Source status
`Tables_related.md` was verified and corrected by the user. Its current values are treated as the authoritative repository context; no independent OCR corrections are applied.

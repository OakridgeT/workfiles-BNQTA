# AI-Oriented Interpretation — Figure 6.0

## Figure identity
- Figure: 6.0
- Title: LOAD CIRCUIT
- Image: `6.0.png`
- Primary source: `Tables_related.md`
- Role: Defines the electrical load and switch configuration used for timing measurements associated with Figures 6.1-a through 6.1-d.

## AI visual-grounding instructions
Use `6.0.png` for circuit topology, load components, VLOAD, and S1 position/function. Use the YAML for structured numerical conditions. Do not infer unspecified values from visual geometry.

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

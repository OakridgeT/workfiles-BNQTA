# AI-Oriented Interpretation — Figure 3

## Figure identity
- Figure: 3
- Title: Waveform
- Image: `fig3.png`
- Related parameters: `tr`, `tf`, `TH`, `TL`, `Period`, Duty Cycle

## Purpose
This waveform defines how rise time, fall time, high/low pulse widths, period, and duty cycle are measured on the LVCMOS output.

## AI visual-grounding instructions
Use the PNG to identify the 20% Vdd, 50%, and 80% Vdd reference lines, the tr/tf intervals at the rising and falling edges, and the TH (High Pulse), TL (Low Pulse), and Period intervals. Use `AI_fig3.yaml` for numeric limits. Do not infer numerical values from pixel distances.

## Definitions
- `tr`, `tf`: rise and fall time, measured from 20% Vdd to 80% Vdd.
- `TH`: high pulse width, measured at the 50% crossing.
- `TL`: low pulse width, measured at the 50% crossing.
- `Period`: TH + TL.
- `Duty Cycle` = TH / Period (note [8]).

## Parameter limits (Table 1, LVCMOS Output Characteristics)
| Parameter | Condition | Typ. | Max. | Unit |
|---|---|---|---|---|
| Duty Cycle (DC) | All Vdd levels | – | 45–55 | % |
| Rise/Fall Time (Tr, Tf) | Vdd = 2.25 V – 3.63 V, 20%–80% | 1.5 | 3 | ns |
| Rise/Fall Time (Tr, Tf) | Vdd = 1.8 V, 20%–80% | 1.3 | 2.5 | ns |

## Context
This waveform is measured at Vout under the Figure 2 test circuit, with a 15 pF output load.

## Interpretation rules
1. Use the 20%/50%/80% Vdd lines in the PNG to identify measurement thresholds.
2. Compute or read Duty Cycle as TH / Period.
3. Use Table 1 limits for Tr, Tf, and Duty Cycle; do not estimate them from the drawing scale.
4. Relate this figure to Figure 2 for the load condition (15 pF) under which the waveform is specified.

## Source status
Based on `Context.md` from this repository (SiT8924 datasheet excerpt).

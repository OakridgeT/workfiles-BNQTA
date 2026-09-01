# AI-Oriented Interpretation — Figure 2

## Figure identity
- Figure: 2
- Title: Test Circuit
- Image: `fig2.png`
- Device: SiT8924

## Purpose
This circuit defines how the oscillator output (Vout) is measured at the Test Point, including power-supply decoupling and output load capacitance.

## AI visual-grounding instructions
Use the PNG to identify the four device pins (1: OE/ST/NC, 2: GND, 3: OUT, 4: Vdd), the 0.1 µF decoupling capacitor between Vdd and GND, the 1 kΩ pull-up on pin 1, and the 15 pF load capacitor at the Test Point. Use `AI_fig2.yaml` for the structured component list and referenced requirements. Do not infer component values from pixel geometry.

## Circuit elements
| Element | Description |
|---|---|
| Power Supply | Supplies Vdd to the device and to the decoupling capacitor. |
| 0.1 µF capacitor | Decoupling capacitor between Vdd and GND (Table 2, note [4]). |
| Pin 1 (OE/ST/NC) | Pulled up to Vdd through 1 kΩ in this test circuit (Table 2, note [3] recommends ≤10 kΩ if not externally driven). |
| Pin 2 (GND) | Electrical ground. |
| Pin 3 (OUT) | Oscillator output, connected to Vout and the Test Point. |
| Pin 4 (Vdd) | Power supply input. |
| 15 pF capacitor | Output load at the Test Point, including probe and fixture capacitance. |

## Context
- All electrical specifications in Table 1 are specified with a 15 pF output load unless otherwise stated.
- This is the reference load circuit for the waveform defined in Figure 3.

## Interpretation rules
1. Identify pin numbers and functions using the PNG labels (1, 2, 3, 4) and Table 2 (Pin Description).
2. Treat the 15 pF capacitor as the standard output load referenced throughout the electrical characteristics table.
3. Treat the 0.1 µF capacitor and 1 kΩ pull-up as example/recommended values, not absolute device limits.
4. Use this figure together with Figure 3 to interpret how TH, TL, and duty cycle are measured at Vout.

## Source status
Based on `Context.md` from this repository (SiT8924 datasheet excerpt).

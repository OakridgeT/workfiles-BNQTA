# AI-Oriented Interpretation — Figure 4

## Figure identity
- Figure: 4
- Title: Startup Timing (OE/ ST Mode)
- Image: `fig4.png`
- Parameter: `T_start`

## Purpose
This diagram defines the startup time from power-off: the time from Vdd reaching its rated minimum value until the CLK output becomes active.

## AI visual-grounding instructions
Use the PNG to identify Pin 4 Voltage ramping to Vdd, the 90% Vdd reference (dashed line), the T_start interval, and the CLK Output transition from the hatched "HZ" (high-impedance) region to active clock pulses. The "No Glitch during startup" callout indicates the output is clean once it starts. Use `AI_fig4.yaml` for the numeric limit. Do not infer the numeric value from pixel geometry.

## Parameter
`T_start` = Startup Time = time to start from power-off.

Maximum `T_start` (Table 1, Startup and Resume Timing): **5.5 ms**, measured from the time Vdd reaches its rated minimum value.

## Context
Applies to devices using the OE or ST configuration on pin 1. SiT8924 produces "no runt" pulses and "no glitch" output during startup or resume (note [9]).

## Interpretation rules
1. Identify the Vdd ramp and its 90% crossing as the timing reference.
2. Identify the CLK Output transition from HZ to active clock pulses.
3. Use the Table 1 value for the numeric limit, not the drawing scale.
4. Do not confuse `T_start` (power-up) with `T_resume` (Figure 5) or `T_oe` (Figures 6 and 7).

## Source status
Based on `Context.md` from this repository (SiT8924 datasheet excerpt).

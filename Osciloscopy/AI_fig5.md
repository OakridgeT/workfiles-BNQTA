# AI-Oriented Interpretation — Figure 5

## Figure identity
- Figure: 5
- Title: Standby Resume Timing ( ST Mode Only)
- Image: `fig5.png`
- Parameter: `T_resume`

## Purpose
This diagram defines the time to resume clock output after the ST (Standby) pin is driven high, exiting Standby mode.

## AI visual-grounding instructions
Use the PNG to identify the ST Voltage ramp, the 50% Vdd reference (dashed line), the T_resume interval, and the CLK Output transition from the hatched "HZ" (high-impedance) region to active clock pulses. Use `AI_fig5.yaml` for the numeric limit. Do not infer the numeric value from pixel geometry.

## Parameter
`T_resume` = Resume Time = time to resume from Standby (ST).

Maximum `T_resume` (Table 1, Startup and Resume Timing): **5 ms**, measured from the time the ST pin crosses the 50% threshold.

## Applicability
This timing applies only to devices configured in ST (Standby) mode on pin 1. It does not apply when pin 1 is configured as OE or NC.

## Interpretation rules
1. Identify the ST Voltage ramp and its 50% crossing as the timing reference.
2. Identify the CLK Output transition from HZ to active clock pulses.
3. Use the Table 1 value for the numeric limit, not the drawing scale.
4. Do not confuse `T_resume` (Standby exit) with `T_start` (Figure 4, power-up) or `T_oe` (Figures 6 and 7, OE enable/disable).

## Source status
Based on `Context.md` from this repository (SiT8924 datasheet excerpt).

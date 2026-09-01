# AI-Oriented Interpretation — Figure 7

## Figure identity
- Figure: 7
- Title: OE Disable Timing (OE Mode Only)
- Image: `fig7.png`
- Parameter: `T_oe` (disable direction)

## Purpose
This diagram defines the time to put the output into high-impedance (High Z) mode after the OE (Output Enable) pin is driven low.

## AI visual-grounding instructions
Use the PNG to identify the active CLK pulses before the transition, the OE Voltage falling edge, the 50% Vdd reference (dashed line), the T_oe interval, and the CLK Output transition into the hatched "HZ" (high-impedance) region. Use `AI_fig7.yaml` for the numeric limit. Do not infer the numeric value from pixel geometry.

## Parameter
`T_oe` = Enable/Disable Time = time to put the output in High Z mode (disable direction).

Maximum `T_oe` (Table 1, Startup and Resume Timing): **130 ns** at f = 110 MHz. For other frequencies, `T_oe = 100 ns + 3 × cycles` of the operating frequency.

## Applicability
This timing applies only to devices configured in OE (Output Enable) mode on pin 1. It does not apply when pin 1 is configured as ST or NC.

## Interpretation rules
1. Identify the OE Voltage falling edge and its 50% crossing as the timing reference.
2. Identify the CLK Output transition from active pulses to the HZ (high-impedance) state.
3. Use the Table 1 formula/value for the numeric limit, not the drawing scale.
4. Pair this figure with Figure 6 (OE Enable Timing) to fully characterize OE-mode enable/disable behavior.
5. Do not confuse this `T_oe` (disable direction) with `T_start` (Figure 4) or `T_resume` (Figure 5).

## Source status
Based on `Context.md` from this repository (SiT8924 datasheet excerpt).

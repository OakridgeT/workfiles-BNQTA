# AI-Oriented Interpretation — Figure 6.1-c

## Figure identity
- Figure: 6.1-c
- Title: VOLTAGE WAVEFORMS — SETUP AND HOLD TIMES
- Image: `6.1-c.png`
- Parameters: `tsu`, `th`

## Purpose
This waveform defines the data-validity intervals surrounding the active CLK rising edge.

## AI visual-grounding instructions
Use the PNG to identify the CLK rising edge, data waveform, transition direction, and setup/hold measurement markers. Use `AI_6.1-c.yaml` for numerical limits. Do not infer limits from graphical scale.

## Parameter definitions
- `tsu`: setup time before CLK rising edge.
- `th`: hold time for data after CLK rising edge.

## Requirements — TA = -40°C to +85°C
The same limits are given for TA = -40°C to +125°C.

### Setup time, data high
| VCC | MIN |
|---|---:|
| 1.8 V ± 0.15 V | 2.3 ns |
| 2.5 V ± 0.2 V | 1.5 ns |
| 3.3 V ± 0.3 V | 1.3 ns |
| 5.5 V ± 0.5 V | 1.1 ns |

### Setup time, data low
| VCC | MIN |
|---|---:|
| 1.8 V ± 0.15 V | 2.5 ns |
| 2.5 V ± 0.2 V | 1.5 ns |
| 3.3 V ± 0.3 V | 1.3 ns |
| 5.5 V ± 0.5 V | 1.1 ns |

### Hold time
| VCC | MIN |
|---|---:|
| 1.8 V ± 0.15 V | 0 ns |
| 2.5 V ± 0.2 V | 0.2 ns |
| 3.3 V ± 0.3 V | 0.9 ns |
| 5.5 V ± 0.5 V | 0.4 ns |

## Interpretation rules
1. Identify the CLK rising edge as the reference event.
2. `tsu` is measured before that edge; `th` is measured after it.
3. Select the data-high or data-low `tsu` row according to the waveform state.
4. Use the YAML/table values for numerical limits.
5. Do not confuse setup/hold timing with propagation delay.
6. Not every parameter or waveform is applicable to all devices.

## Source status
Based on the user-verified current `Tables_related.md`.

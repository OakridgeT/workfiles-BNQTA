# AI Interpretation Guide — Figure 6.2-c

## Figure Identity

- **Figure:** 6.2-c
- **Image:** `6.2-c.png`
- **Title:** VOLTAGE WAVEFORMS — SETUP AND HOLD TIMES
- **Parameters:** `tsu`, `th`
- **Parent test circuit:** `6.2.png`
- **Structured companion:** `AI_6.2-c.yaml`

## Purpose

Figure 6.2-c illustrates the temporal relationship between an input data transition and the relevant clock/reference edge. It defines **setup time (`tsu`)** and **hold time (`th`)**.

## Parameter Interpretation

### `tsu` — Setup Time

The minimum interval during which the input data must remain stable **before** the specified active clock/reference edge.

### `th` — Hold Time

The minimum interval during which the input data must remain stable **after** the specified active clock/reference edge.

## Visual Interpretation

When inspecting `6.2-c.png`, the AI should identify:

1. Data/input waveform.
2. Clock waveform.
3. Active clock/reference edge.
4. Data transition relative to that edge.
5. Timing arrow representing `tsu`.
6. Timing arrow representing `th`.
7. Relevant voltage reference levels.

## Temporal Relationship

Conceptually:

```text
DATA:     ────────┐                 ┌────────
                  │<--- tsu --->    │
CLOCK:            │        ↑        │
                  │   active edge   │
                  │<------ th ------>│
```

The exact graphical arrangement, polarity, and reference markers must be taken from the PNG rather than inferred from this simplified representation.

## AI Interpretation Rules

- Identify the active clock edge first.
- For `tsu`, measure backward from the active clock edge to the relevant data transition.
- For `th`, measure forward from the active clock edge to the relevant data transition.
- Do not interpret `tsu` or `th` as propagation delay.
- Do not infer guaranteed numerical limits from image dimensions.
- Use the associated datasheet table for numerical timing specifications.

## Test Conditions

The parent Figure 6.2 load circuit uses `CL = 30 pF` or `50 pF` depending on VCC. The relevant temperature range is determined by the applicable timing table.

## Measurement Notes

- `CL` includes probe and jig capacitance.
- Input pulses are supplied by generators with `PRR ≤ 10 MHz` and `Z = 50 Ω`.
- Outputs are measured one at a time, with one transition per measurement.
- Not all parameters and waveforms apply to all devices.

## Related Figures

- `6.2` → load circuit
- `6.2-a` → pulse duration
- `6.2-b` → propagation delay
- `6.2-d` → enable and disable timing

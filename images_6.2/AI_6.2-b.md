# AI Interpretation Guide — Figure 6.2-b

## Figure Identity

- **Figure:** 6.2-b
- **Image:** `6.2-b.png`
- **Title:** VOLTAGE WAVEFORMS — PROPAGATION DELAY TIMES INVERTING AND NONINVERTING OUTPUTS
- **Parameters:** `tPLH`, `tPHL`
- **Equivalent parameter:** `tpd`
- **Parent test circuit:** `6.2.png`
- **Structured companion:** `AI_6.2-b.yaml`

## Purpose

Figure 6.2-b illustrates how **propagation delay** is measured between an input transition and the corresponding output transition for inverting and noninverting output behavior.

## Parameter Interpretation

### `tPLH`

Propagation delay associated with the output transition from LOW to HIGH.

### `tPHL`

Propagation delay associated with the output transition from HIGH to LOW.

Both are represented by the generic propagation-delay parameter `tpd` in the switching-characteristics tables.

## Visual Interpretation

The AI should inspect the PNG and identify:

1. Input waveform and transition direction.
2. Output waveform and transition direction.
3. Whether the illustrated device behavior is inverting or noninverting.
4. The voltage midpoint/reference level `VM`.
5. The start and end points of each timing interval.
6. The timing arrow associated with `tPLH` or `tPHL`.

## Measurement Concept

Propagation delay is the temporal separation between the specified input reference crossing and the corresponding output reference crossing.

The exact reference levels are defined by the test conditions associated with Figure 6.2. For example, `VM` is `VCC/2` for the 1.8 V, 2.5 V, and 5 V conditions and 1.5 V for the 3.3 V condition in the supplied context table.

## Switching Characteristics Context

### `TA = -40°C to +85°C`

| VCC | tpd MIN | tpd MAX |
|---|---:|---:|
| 1.8 V ± 0.15 V | 4.4 ns | 9.9 ns |
| 2.5 V ± 0.2 V | 2.3 ns | 7 ns |
| 3.3 V ± 0.3 V | 2 ns | 5.2 ns |
| 5 V ± 0.5 V | 1.3 ns | 4.5 ns |

### `TA = -40°C to +125°C`

| VCC | tpd MIN | tpd MAX |
|---|---:|---:|
| 1.8 V ± 0.15 V | 4.4 ns | 12.5 ns |
| 2.5 V ± 0.2 V | 2.3 ns | 8.5 ns |
| 3.3 V ± 0.3 V | 2 ns | 6 ns |
| 5 V ± 0.5 V | 1.3 ns | 5.5 ns |

## AI Interpretation Rules

- Determine the input transition before identifying the output transition.
- Determine waveform polarity from the PNG; do not assume all devices are noninverting.
- Use `tPLH` for LOW-to-HIGH output propagation and `tPHL` for HIGH-to-LOW output propagation.
- Do not confuse propagation delay with setup/hold time.
- Do not derive guaranteed MIN/MAX values from the drawing scale.
- Use the tables for numerical specifications and the PNG for visual timing relationships.

## Measurement Notes

- `CL` includes probe and jig capacitance.
- Outputs are measured one at a time.
- One transition is used per measurement.
- Not all parameters and waveforms apply to all devices.

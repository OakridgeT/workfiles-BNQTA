# AI-Oriented Interpretation Guide — Figure 6.1-b

## 1. Figure Identity

- **Figure:** 6.1-b
- **Image:** `6.1-b.png`
- **Section:** 5.6 — Timing Requirements, `TA = -40°C to +85°C`
- **Waveform function:** Setup and hold timing measurement.
- **Associated parameters:** `tsu` and `th`.

## 2. Purpose

Figure 6.1-b defines the temporal relationship between the data input and the rising edge of CLK.

The critical reference event is the **rising edge of CLK**.

## 3. Visual Interpretation

The AI should identify:

1. The CLK waveform.
2. The data input waveform.
3. The voltage reference `VM`.
4. The rising CLK edge used as the reference event.
5. The `tsu` interval before the CLK rising edge.
6. The `th` interval after the CLK rising edge.

The diagram represents both data-high and data-low timing conditions.

## 4. Timing Semantics

### Setup time — `tsu`

`tsu` is the minimum time by which the data transition must precede the rising edge of CLK.

### Hold time — `th`

`th` is the minimum time for which the data must remain valid after the rising edge of CLK.

Therefore:

`data transition → tsu → CLK rising edge → th → data may change`

## 5. Numerical Conditions

For `TA = -40°C to +85°C`, the supplied table gives:

### Setup time, data high

| VCC | Minimum `tsu` |
|---|---:|
| 1.8 V ± 0.15 V | 2.3 ns |
| 2.5 V ± 0.2 V | 1.5 ns |
| 3.3 V ± 0.3 V | 1.3 ns |
| 5.5 V ± 0.5 V | 1.1 ns |

### Setup time, data low

| VCC | Minimum `tsu` |
|---|---:|
| 1.8 V ± 0.15 V | 2.5 ns |
| 2.5 V ± 0.2 V | 1.5 ns |
| 3.3 V ± 0.3 V | 1.3 ns |
| 5.5 V ± 0.5 V | 1.1 ns |

### Hold time

| VCC | Minimum `th` |
|---|---:|
| 1.8 V ± 0.15 V | 0 ns |
| 2.5 V ± 0.2 V | 0.2 ns |
| 3.3 V ± 0.3 V | 0.9 ns |
| 5.5 V ± 0.5 V | 0.4 ns |

## 6. AI Rules

- Always use the rising CLK edge as the reference event for `tsu` and `th`.
- `tsu` occurs **before** the reference edge.
- `th` occurs **after** the reference edge.
- Do not interpret either parameter as propagation delay.
- Do not infer setup/hold values from graphical scale.
- Use the YAML for structured values and the PNG for marker placement.

## 7. Visual Grounding

If the question asks which waveform transition is being measured, inspect `6.1-b.png`. If the question asks for a numerical limit, use `AI_6.1-b.yaml` and the associated timing table.

## 8. Source Integrity

The supplied Markdown contains OCR/transcription inconsistencies in VCC notation. Values should be reconciled against the original manufacturer datasheet before being treated as authoritative.

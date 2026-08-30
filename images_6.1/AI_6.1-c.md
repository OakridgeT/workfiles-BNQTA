# AI-Oriented Interpretation Guide — Figure 6.1-c

## 1. Figure Identity

- **Figure:** 6.1-c
- **Image:** `6.1-c.png`
- **Section:** 5.8 — Switching Characteristics, `TA = -40°C to +85°C`, `CL = 15 pF`
- **Waveform function:** Propagation-delay measurement.
- **Associated parameters:** `tPLH` and `tPHL`, equivalent to `tpd`.

## 2. Purpose

Figure 6.1-c shows how propagation delay is measured between an input/reference transition and the corresponding output transition.

The figure covers both non-inverting and inverting output relationships.

## 3. Timing Semantics

- `tPLH`: propagation delay for an output LOW-to-HIGH transition.
- `tPHL`: propagation delay for an output HIGH-to-LOW transition.
- Both are aliases of `tpd` according to the associated notes.

The timing interval is measured between the defined input and output reference thresholds, represented by `VM` in the waveform diagram.

## 4. Visual Interpretation

The AI should identify:

1. Input waveform.
2. Output waveform.
3. `VM` threshold/reference level.
4. Input transition.
5. Corresponding output transition.
6. `tPLH` and/or `tPHL` marker.
7. Whether the waveform represents an inverting or non-inverting relationship.

The graphical horizontal distance represents a timing interval, not an electrical voltage difference.

## 5. Numerical Conditions

For `TA = -40°C to +85°C` and `CL = 15 pF`, the supplied table gives:

| VCC | `tpd` minimum | `tpd` maximum |
|---|---:|---:|
| 1.8 V ± 0.15 V | 3.0 ns | 9.1 ns |
| 2.5 V ± 0.2 V | 1.5 ns | 6.0 ns |
| 3.3 V ± 0.3 V | 1.3 ns | 4.2 ns |
| 5 V ± 0.5 V | 1.1 ns | 3.8 ns |

The table also specifies `fmax = 160 MHz` for the listed supply conditions.

## 6. Relationship to Figure 6.0

The load configuration used for propagation-delay measurement is established by Figure 6.0 with `S1 = Open`.

Therefore:

`Figure 6.0 → test/load configuration`

`Figure 6.1-c → waveform/timing interpretation`

An AI should use these figures as complementary information rather than independent specifications.

## 7. AI Rules

- `tPLH` and `tPHL` are propagation-delay measurements.
- Treat both as `tpd` aliases.
- Do not confuse `tPLH/tPHL` with `tsu/th`.
- Use the PNG to determine which transition is illustrated.
- Use the YAML/table for numerical limits.
- Do not estimate nanoseconds from the visual horizontal scale.

## 8. Visual Grounding

The exact waveform polarity, marker placement, and input/output relationship must be obtained from `6.1-c.png`.

If the question asks whether the output transition is LOW-to-HIGH or HIGH-to-LOW, inspect the waveform rather than inferring polarity from the parameter name alone.

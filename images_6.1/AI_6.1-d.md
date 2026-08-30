# AI-Oriented Interpretation Guide — Figure 6.1-d

## 1. Figure Identity

- **Figure:** 6.1-d
- **Image:** `6.1-d.png`
- **Section:** 5.8 — Switching Characteristics / enable and disable timing.
- **Waveform function:** Output enable and disable timing measurement.
- **Associated parameters:** `tPZL`, `tPZH`, `tPLZ`, `tPHZ`.

## 2. Purpose

Figure 6.1-d describes timing associated with an output transitioning between an active logic state and high impedance (`Hi-Z`).

The figure uses two waveform cases:

- **Waveform 1:** output internally LOW except when disabled.
- **Waveform 2:** output internally HIGH except when disabled.

## 3. Parameter Semantics

### Enable time

- `tPZL`: high impedance → LOW.
- `tPZH`: high impedance → HIGH.
- Both are equivalent to `ten`.

### Disable time

- `tPLZ`: LOW → high impedance.
- `tPHZ`: HIGH → high impedance.
- Both are equivalent to `tdis`.

## 4. Visual Interpretation

The AI should identify:

1. Output control waveform.
2. Output waveform.
3. The active logic state before/after the transition.
4. The high-impedance region.
5. `VM` reference threshold.
6. `VLOAD/2` or `VOL + VD` / `VOH - VD` references where applicable.
7. The timing marker associated with enable or disable.

A high-impedance state must **not** be interpreted as an ordinary logic HIGH or LOW state.

## 5. Switch Relationship

The corresponding test configuration is defined in Figure 6.0:

- `S1 = VLOAD` for `tPLZ/tPZL`.
- `S1 = GND` for `tPHZ/tPZH`.

Therefore Figure 6.1-d should be interpreted together with `AI_6.0.md` and `AI_6.0.yaml` when the measurement topology is relevant.

## 6. Measurement Concepts

### Disable

The output changes from an actively driven logic state to high impedance. The measured interval is `tdis`:

- LOW → Hi-Z: `tPLZ`
- HIGH → Hi-Z: `tPHZ`

### Enable

The output changes from high impedance to an actively driven logic state. The measured interval is `ten`:

- Hi-Z → LOW: `tPZL`
- Hi-Z → HIGH: `tPZH`

## 7. Associated Conditions

The Figure 6.0 load configuration specifies, depending on VCC:

- `CL = 15 pF`
- `RL = 1 MΩ`
- `VD = 0.15 V` for 1.8 V and 2.5 V conditions.
- `VD = 0.3 V` for 3.3 V and 5 V conditions.

The switching-characteristics table is associated with `TA = -40°C to +85°C` and `CL = 15 pF`.

## 8. AI Rules

- Distinguish **Hi-Z** from logic HIGH and logic LOW.
- `tPLZ` and `tPHZ` are disable times (`tdis`).
- `tPZL` and `tPZH` are enable times (`ten`).
- Do not treat enable/disable timing as propagation delay.
- Use the PNG to identify the waveform polarity and exact timing-marker placement.
- Use the YAML and tables for numerical specifications.

## 9. Visual Grounding

The PNG is authoritative for the visual relationship between `Output Control`, `Output`, `Waveform 1`, and `Waveform 2`. Numerical values must be taken from the associated tables, not estimated from the drawing.

## 10. Source Integrity

The supplied Markdown contains OCR/transcription artifacts. In particular, VCC notation varies between `5 V ± 0.5 V` and `5.5 V ± 0.5 V` in different sections. Preserve this discrepancy as a source-quality issue and verify against the original manufacturer datasheet before treating it as an authoritative specification.

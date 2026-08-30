# AI-Oriented Interpretation Guide — Figure 6.0

## 1. Figure Identity

- **Figure:** 6.0
- **Image:** `6.0.png`
- **Role:** Load circuit / parameter-measurement configuration.
- **Associated source:** `Tables_related.md`
- **Primary purpose:** Defines how the output under test is loaded and how switch `S1` is configured for propagation-delay, enable-time, and disable-time measurements.

## 2. AI Interpretation Strategy

This figure must be interpreted together with `AI_6.0.yaml` and `Tables_related.md`.

- Use the **PNG** to identify the physical topology, signal paths, switch position, output node, and load connections.
- Use the **YAML** for structured parameter relationships and test-condition semantics.
- Use `Tables_related.md` as the source-context record for the associated numerical test conditions.
- Do not derive a numerical timing specification from the drawing geometry unless the datasheet explicitly provides a scale or threshold definition.

## 3. Test Circuit Semantics

The figure contains an output-under-test node connected to a selectable load through switch `S1`.

The relevant measurement groups are:

| Measurement | S1 condition | Meaning |
|---|---|---|
| `tPLH`, `tPHL` | Open | Propagation delay between input/reference transition and output transition |
| `tPLZ`, `tPZL` | VLOAD | Disable/enable timing associated with the low-state waveform |
| `tPHZ`, `tPZH` | GND | Disable/enable timing associated with the high-state waveform |

## 4. Parameter Equivalences

The figure uses waveform-specific timing names. The datasheet notes establish these equivalences:

- `tPLH = tpd`
- `tPHL = tpd`
- `tPLZ = tdis`
- `tPHZ = tdis`
- `tPZL = ten`
- `tPZH = ten`

An AI should treat these as aliases for the same underlying timing concept, not as six unrelated physical parameters.

## 5. Load Conditions

The associated table defines `CL = 15 pF` and `RL = 1 MΩ` for the Figure 6.0 context.

The VCC-dependent conditions are:

| VCC | Input level | Input tr/tf | VM | VLOAD | CL | RL | VD |
|---|---|---|---|---|---|---|---|
| 1.8 V ± 0.15 V | VCC | ≤2 ns | VCC/2 | 2×VCC | 15 pF | 1 MΩ | 0.15 V |
| 2.5 V ± 0.2 V | VCC | ≤2 ns | VCC/2 | 2×VCC | 15 pF | 1 MΩ | 0.15 V |
| 3.3 V ± 0.3 V | 3 V | ≤2.5 ns | 1.5 V | 6 V | 15 pF | 1 MΩ | 0.3 V |
| 5 V ± 0.5 V | VCC | ≤2.5 ns | VCC/2 | 2×VCC | 15 pF | 1 MΩ | 0.3 V |

## 6. Visual Grounding Rules

When inspecting `6.0.png`, identify:

1. The output under test.
2. The `S1` switch.
3. The `VLOAD` connection.
4. The GND connection.
5. `RL` and `CL`.
6. The measurement node.
7. Which test label is associated with each switch position.

Do not assume that a switch label represents a signal value unless the diagram explicitly connects it to that node.

## 7. Measurement Logic

### Propagation delay

For `tPLH` and `tPHL`, `S1` is open. The measurement compares the input/reference transition with the corresponding output transition.

### Disable time

For `tPLZ` and `tPHZ`, the output transitions from an active logic state toward high impedance. The associated timing quantity is `tdis`.

### Enable time

For `tPZL` and `tPZH`, the output transitions from high impedance toward an active logic state. The associated timing quantity is `ten`.

## 8. Important Notes

- `CL` includes probe and jig capacitance.
- Outputs are measured one at a time, with one transition per measurement.
- Waveform 1 corresponds to an internally low output except when disabled by the output control.
- Waveform 2 corresponds to an internally high output except when disabled by the output control.
- Not every timing parameter or waveform necessarily applies to every device.

## 9. Data-Quality Warning

`Tables_related.md` contains OCR/transcription artifacts such as `£2 ns`, `1MW`, and `50 W`. This guide normalizes obvious notation where the engineering context is unambiguous, but the original datasheet should remain the authority when an ambiguity affects a specification.

## 10. AI Decision Rule

If the question concerns **where or how a timing parameter is measured**, use this document plus `AI_6.0.yaml` and inspect `6.0.png` when topology is required.

If the question concerns the **actual timing limits**, use the numerical tables associated with Sections 5.6–5.8 rather than estimating values from the image.

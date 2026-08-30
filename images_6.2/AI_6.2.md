# AI Interpretation Guide — Figure 6.2

## Figure Identity

- **Figure:** 6.2
- **Image:** `6.2.png`
- **Title:** LOAD CIRCUIT
- **Source context:** `Tables_related.md`
- **Role:** Defines the electrical test/load configuration used by the timing waveforms in Figures 6.2-a through 6.2-d.
- **Structured companion:** `AI_6.2.yaml`

## Purpose

Figure 6.2 is a **test circuit**, not a waveform. It provides the electrical conditions under which propagation delay, enable/disable timing, and related switching characteristics are measured.

An AI should therefore interpret this image together with the associated tables. The PNG provides the visual circuit topology and switch arrangement; the YAML and Markdown provide the semantic and numerical context.

## Switch S1 Interpretation

| Timing measurement | S1 position | Meaning |
|---|---|---|
| `tPLH / tPHL` | Open | Propagation delay measurement |
| `tPLZ / tPZL` | VLOAD | Disable/enable measurement for the corresponding low-state path |
| `tPHZ / tPZH` | GND | Disable/enable measurement for the corresponding high-state path |

## Load Conditions

The associated load-condition table defines the following test configurations:

| VCC | VI INPUTS | tr/tf INPUTS | VM | VLOAD | CL | RL | VD |
|---|---|---|---|---|---|---|---|
| 1.8 V ± 0.15 V | VCC | ≤2 ns | VCC/2 | 2 × VCC | 30 pF | 1 kΩ | 0.15 V |
| 2.5 V ± 0.2 V | VCC | ≤2 ns | VCC/2 | 2 × VCC | 30 pF | 500 Ω | 0.15 V |
| 3.3 V ± 0.3 V | 3 V | ≤2.5 ns | 1.5 V | 6 V | 50 pF | 500 Ω | 0.3 V |
| 5 V ± 0.5 V | VCC | ≤2.5 ns | VCC/2 | 2 × VCC | 50 pF | 500 Ω | 0.3 V |

## AI Visual Grounding

When inspecting `6.2.png`, the AI should identify:

1. The DUT/output node.
2. The input signal path.
3. The load capacitance `CL`.
4. The load resistance `RL`.
5. The `VLOAD` source.
6. Switch `S1` and its selectable positions.
7. Ground/reference connections.
8. Any voltage or measurement labels shown directly in the drawing.

Do not reconstruct component values solely from graphical dimensions. Use the table for numerical values.

## Relationship to Figures 6.2-a through 6.2-d

Figure 6.2 provides the physical measurement configuration. The companion waveform figures illustrate how timing quantities are measured using this configuration:

- `6.2-a` → pulse duration (`tW`)
- `6.2-b` → propagation delay (`tPLH`, `tPHL`, equivalent to `tpd`)
- `6.2-c` → setup and hold time (`tsu`, `th`)
- `6.2-d` → enable/disable timing (`tPZL`, `tPZH`, `tPLZ`, `tPHZ`)

## Measurement Rules

- `CL` includes probe and jig capacitance.
- Input pulses are supplied by generators with `PRR ≤ 10 MHz` and `Z = 50 Ω`.
- Outputs are measured one at a time.
- One transition is used per measurement.
- Not every timing parameter or waveform applies to every device.

## Parameter Equivalences

- `tPLH` and `tPHL` → `tpd`
- `tPLZ` and `tPHZ` → `tdis`
- `tPZL` and `tPZH` → `ten`

## AI Interpretation Constraints

- Do not treat Figure 6.2 as a timing waveform.
- Do not infer MIN/MAX timing specifications from the circuit drawing.
- Do not confuse `VLOAD` with `VCC`; they are distinct test nodes/conditions.
- Do not assume that all four waveform families apply to every device.
- Use the PNG to resolve topology and the YAML/tables to resolve numerical conditions.

## Data Quality Note

`Tables_related.md` contains OCR artifacts, including `£` where `≤` is intended and `W` where `Ω` is intended. This AI-oriented representation normalizes those symbols when the context is unambiguous.

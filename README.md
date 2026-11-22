# A Low-Power Hybrid Flip-Flop using Sleepy Stack Inverter Pairs: A Replication and Extension Study

> **Course Project (Complex Engineering Problem)** for *Linear Integrated Circuit Design*  
> Department of ECE, Air University, Islamabad — 2023  
> **Team:** Waseem Akram, Ali Abdullah, Abdul Mohsin  
> **Repository maintained by:** Ali Abdullah (led Part 2 — SSI Design & Integration)  
> **All authors approve this public release.**

[![Cadence Virtuoso](https://img.shields.io/badge/Tool-Cadence%20Virtuoso-red)]()
[![Node](https://img.shields.io/badge/Node-90nm%20CMOS-blue)]()
[![Vdd](https://img.shields.io/badge/Vdd-1.8V-green)]()
[![Clock](https://img.shields.io/badge/Clock-1%20GHz-orange)]()

---

## What this project is (and is not)

This is a **course project**, not a peer-reviewed publication. The objective was to:

1. **Replicate** a published low-power flip-flop design — the Dual Dynamic Node Pulsed Hybrid Flip-Flop (DDFF), Absel et al., IEEE TVLSI 2013.
2. **Extend** it by replacing the static CMOS inverters with **Sleepy Stack Inverters** (Park & Mooney, IEEE TVLSI 2006).
3. **Learn** the full Cadence Virtuoso flow: schematic entry, DC operating point, transient simulation, power/leakage measurement, and technical report writing in LaTeX.

The report is presented as a **technical report** — a record of methodology and results obtained during the course. It is not claimed as novel research.

---

## Key Results

### D Flip-Flop: Conventional DDFF vs. Proposed (SSI-DDFF)

| Metric | Conventional DDFF | Proposed (SSI) | Change |
|--------|-------------------|----------------|--------|
| Leakage Power | 52.596 nW | 5.7438 nW | **↓ 89%** |
| Total Power | 63.25 μW | 50.44 μW | **↓ 20%** |
| Delay | 4.6205 ns | 4.6175 ns | ≈ unchanged |
| PDP | 292.25 fJ | 232.91 fJ | **↓ 20%** |

### T Flip-Flop: Conventional vs. Proposed

| Metric | Conventional | Proposed (SSI) | Change |
|--------|--------------|----------------|--------|
| Leakage Power | 55.404 nW | 8.0514 nW | **↓ 85%** |
| Total Power | 93.55 μW | 78.9 μW | **↓ 16%** |
| Delay | 2.61 ns | 2.6065 ns | ≈ unchanged |
| PDP | 244.17 fJ | 205.65 fJ | **↓ 16%** |

### Sleepy Stack Inverter vs. Static CMOS Inverter

| Inverter | Leakage Power | Total Power |
|----------|---------------|-------------|
| Static CMOS | 4041.1 pW | 414 nW |
| Sleepy Stack | 3.2508 pW | 356.8 nW |

> Full data tables are available in the [`data/`](data/) folder. High-resolution simulation waveforms and schematics are in the [`images/`](images/) folder.

---

## Honest Discussion & Limitations

These are documented openly because they are part of the real engineering work:

1. **50% Data-Activity Anomaly (Table III):** At 50% switching activity, the proposed D-FF reports **82.68 μW** vs. conventional **73.2 μW**. This is a real trade-off: the Sleepy Stack Inverter adds transistors (area overhead), which increases dynamic power at mid-activity. The proposed design still wins at **0% and 25% activity**, where leakage dominates. 
2. **Placeholder References Removed:** The original course submission contained two unverifiable placeholder references ([5] and [6]). These have been removed in the corrected version. The verifiable foundational references are Park & Mooney (2006) and Absel et al. (2013).
3. **SR/JK Claims Removed:** The original report briefly mentioned SR and JK flip-flops but never provided simulation results for them. The corrected version explicitly limits its scope to the D and T variants.
4. **PDK NDA:** The 90nm PDK is not uploaded (NDA / licensing). Netlists and model files are excluded. Reproduction requires a licensed Cadence Virtuoso + 90nm PDK.
5. **Shared Simulation Environment:** Cadence Virtuoso with the 90nm PDK is a heavy installation. The team used a single shared machine (Waseem Akram's laptop) for all simulation runs. This is why Cadence screenshots display his username; it is a session identity, not an authorship stamp.

---

## Design Architecture

1. **Baseline:** Conventional DDFF (Absel et al., 2013) — dynamic input stage + static output stage.
2. **Replacement:** Static CMOS inverters in the output latch replaced with **Sleepy Stack Inverter (SSI) pairs** (Park & Mooney, 2006).
3. **Modes:** SSI operates in Active (S=0) and Sleep (S=1) modes — high-Vth sleep transistors + stack effect suppress leakage.
4. **Extension:** T-FF derived from the proposed D-FF using XOR (PTL) feedback.
5. **Simulation:** Cadence Virtuoso / Spectre, 90nm, 1.8V, 1 GHz, 27 °C, DC + transient.

**Timing:** Tov = 61 ps, Tho = 24 ps, Tht = 35 ps.

---

## Repository Contents

| Folder | Contents |
|--------|----------|
| `docs/report/` | **Corrected** Course Report (PDF) and LaTeX source (`tex/`) |
| `docs/report/original_as_submitted/` | Original, unedited course submission (PDF) |
| `images/` | High-resolution figures extracted from the Cadence project |
| `data/` | CSV versions of Tables I–V from the report |

---

## References (Replicated Works)

- J. C. Park and V. J. Mooney III, "Sleepy Stack Leakage Reduction," *IEEE TVLSI*, vol. 14, no. 11, pp. 1250–1263, 2006.
- K. Absel, L. Manuel, and R. K. Kavitha, "Low-Power Dual Dynamic Node Pulsed Hybrid Flip-Flop Featuring Efficient Embedded Logic," *IEEE TVLSI*, vol. 21, no. 9, pp. 1693–1704, 2013.

---

## License

CC BY 4.0 — share and adapt with attribution. See [`LICENSE`](LICENSE).

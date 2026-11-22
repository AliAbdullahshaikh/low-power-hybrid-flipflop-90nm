# Credits & Division of Work

This was a 3-person team project for the **Complex Engineering Problem (CEP)** in *Linear Integrated Circuit Design*, Department of ECE, Air University, Islamabad (2023).

**All authors approve this public release.**

## Team

| Name | Role |
|------|------|
| Waseem Akram | Co-author |
| Ali Abdullah | Co-author — **maintainer of this repository** |
| Abdul Mohsin | Co-author |

## Division of Work

The project was divided into three coherent parts, following the natural workflow of theory → design → measurement.

### Part 1 — Literature Review, Baseline DDFF & Flip-Flop Theory
- Studied the two source papers: Park & Mooney (2006, Sleepy Stack) and Absel et al. (2013, DDFF).
- Documented conventional DDFF operation: Evaluation phase (CLK=1) and Pre-charge phase (CLK=0) — nodes X1, X2, Q, Q̄.
- Covered flip-flop theory: T-FF characteristic equation, XOR via Pass Transistor Logic (PTL).
- Produced the T-FF block diagram.
- Drafted Sections I–III + References of the report.

### Part 2 — Proposed Architecture: SSI Design & Integration  ← **Ali Abdullah (maintainer)**
- Designed the **Sleepy Stack Inverter** schematic: high-Vth sleep transistors P2/N2, low-Vth P3/N3, stacked pairs P1/P3 and N1/N3.
- Documented **Active mode (S=0)** vs. **Sleep mode (S=1)** and the stack-effect leakage blocking.
- Integrated SSI pairs into the DDFF static stage → proposed D-FF schematic.
- Designed timing: Tov = 61 ps, Tho = 24 ps, Tht = 35 ps; race-around mitigation via CLK/CLKB 1-1 overlap.
- Drafted Section IV (Architecture).

### Part 3 — Simulation, Results & Documentation
- Set up Cadence Virtuoso 90nm: DC operating point + transient, 1.8V, 1 GHz, 27 °C.
- Measured power, leakage, delay, and PDP for the inverter and all flip-flops → Tables I, II, IV, V.
- Ran the data-activity sweep (0/25/50/100%) → Table III.
- Captured waveforms → Figs. 7–9.
- Wrote Section V (Results), formatted figures/tables, and compiled the LaTeX report.

## Note on the Simulation Environment

Cadence Virtuoso with the 90nm PDK is a heavy installation that did not fit on all team laptops. The team therefore used **one shared machine (Waseem Akram's laptop)** for all simulation runs. This is why the Cadence session screenshots in the report display the username "Waseem Akram" — it is the **shared session identity**, not an authorship stamp. Part 3 was a collaborative effort across the team.

## Author Contributions (Summary)

| Author | Parts |
|--------|-------|
| Waseem Akram | Part 1 / Part 3 (collaborative) |
| Ali Abdullah | **Part 2 — SSI Design & Integration** (repository maintainer) |
| Abdul Mohsin | Part 1 / Part 3 (collaborative) |

> Parts 1 and 3 were collaborative. The per-author split between Waseem and Abdul Mohsin for those parts is left general here because it was a shared effort. Ali Abdullah led Part 2, which is the focus of this repository's documentation.
# Changelog — Corrections to the Original Course Report

This repository contains both the **original course submission** and a **corrected version** with fixes applied. This file documents every change made between the two to maintain academic transparency.

## Original Submission
- **File:** `docs/report/original_as_submitted/CEP_LowPower_Hybrid_FF_ORIGINAL.pdf`
- **Status:** Preserved exactly as submitted for the CEP course, 2023.
- **Purpose:** Historical record.

## Corrected Version
- **File:** `docs/report/CEP_LowPower_Hybrid_FF_CORRECTED.pdf`
- **Source:** `docs/report/tex/main.tex`
- **Purpose:** Portfolio-quality version with issues fixed for transparency.

## Changes Applied

1. **Removed placeholder references [5] and [6]**
   The original report included two references ("Smith & Johnson 2023" and "Brown & Garcia 2022") that could not be verified as real publications. These have been removed. The remaining references [1]–[4] are verifiable foundational works.

2. **Removed unsupported SR/JK flip-flop claims**
   The original introduction and Section III mentioned SR and JK flip-flop derivations, but no simulation results for these variants were ever produced. The corrected version limits its scope to the D and T variants, which are fully simulated.

3. **Reconciled Table II and Table V**
   The original report had two sets of values for the proposed D-FF (Table II: 50.44 μW / 232.91 fJ; Table V: 50.02 μW / 230.97 fJ), stemming from separate simulation runs. The corrected version uses the Table II values consistently, as they form the direct head-to-head comparison with the conventional DDFF baseline.

4. **Updated title**
   The title was adjusted from "A Novel Low Power Hybrid Flip Flop..." to "A Low-Power Hybrid Flip-Flop using Sleepy Stack Inverter Pairs: A Replication and Extension Study" to more accurately reflect the project's scope.

5. **Fixed table structures and formatting**
   Tables II, IV, and V had malformed column alignments in the original LaTeX source. These were restructured into clean 5-column tables. The duplicated table caption and empty figure captions were also fixed.

## Changes NOT Applied (Deliberately Preserved)

- **50% activity anomaly (Table III):** At 50% switching activity, the proposed D-FF reports higher power (82.68 μW) than the conventional design (73.2 μW). This is a real result, likely due to the SSI's increased transistor count adding dynamic power at mid-activity. It is preserved unchanged because it reflects the actual simulation output.
- **Low power savings at 100% activity:** At 100% activity, both designs consume nearly the same power. This is a real result and is preserved unchanged.

---
*All authors have approved these corrections.*
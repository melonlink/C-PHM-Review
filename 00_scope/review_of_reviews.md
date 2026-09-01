# Review of Reviews — Capacitor Condition Monitoring & PHM

**Created:** 2026-08-30 · **Revised:** 2026-08-31 — all 8 reviews now at `FULLTEXT` strength
**Companion data:** [review_gap_matrix.csv](review_gap_matrix.csv) (8 × 30)

Evidence discipline: every entry is Crossref-verified, every PDF identity-checked against its expected DOI, and every claim below rests on complete extracted text. No entry is carried at abstract strength.

---

## 1. The corpus

| ID | Review | Year | Venue | Citations | Words |
|---|---|---|---|---:|---:|
| R01 | Wang & Blaabjerg — *Reliability of Capacitors for DC-Link Applications: An Overview* | 2014 | IEEE TIA 50(5) 3569–3578 | 1317 | 7 355 |
| R02 | Soliman, Wang & Blaabjerg — *A Review of the Condition Monitoring of Capacitors in PECs* | 2016 | IEEE TIA 52(6) 4976–4989 | 262 | 10 359 |
| R03 | Dang & Kwak — *Review of Health Monitoring Techniques for Capacitors* | 2020 | Sensors 20(13) 3740 | 32 | 10 627 |
| R04 | Nathan et al. — *Review of condition monitoring methods for capacitors* | 2023 | Microelectron. Reliab. 145 115003 | 21 | 9 073 |
| R05 | Muhammed Ramees & Ahmad — *Advances in Capacitor Health Monitoring Techniques* | 2023 | IEEE Access 11 133540–133576 | 35 | 26 582 |
| R06 | Torki, Joubert & Sari — *Electrolytic capacitor: Properties and operation* | 2023 | J. Energy Storage 58 106330 | 82 | 16 625 |
| **R07** | Fassi et al. — *Toward Physics-Informed ML-Based Predictive Maintenance for Power Converters* | 2024 | **IEEE TPEL 39(2) 2692–2720** | **138** | 24 495 |
| **R08** | Yu et al. — *Review of Health Monitoring Techniques for Capacitors in MMCs* | 2025 | **IEEE TPEL 40(9) 13363–13382** | 7 | 15 611 |

R01 was added beyond the task book's list as the field's citation anchor (1317 cites). R07 was added because systematic search identified it as the strongest competitor — the task book did not anticipate it.

---

## 2. How each review organises the field

The organising axis determines what a review can and cannot say.

| ID | Primary taxonomy | Axis type |
|---|---|---|
| R01 | Capacitor type × (reliability-oriented design \| condition monitoring) | Component + design |
| R02 | CM method family (capacitor-model / circuit-model / data-driven signal) | Method principle |
| R03 | Estimated parameter (ESR \| C) × measurement principle | Parameter |
| R04 | CM method family + ANN-based predictive maintenance | Method principle |
| R05 | Converter topology × output-filter type (C \| LC \| both) × offline/online | **Topology** |
| R06 | Component physics: construction → properties → ageing laws → predictive maintenance | Physics |
| R07 | Paradigm: analytical \| data-driven \| physics-informed ML | **Paradigm** |
| R08 | MMC CM method category (direct \| indirect) × implementation | Topology (single) |

**Observation.** Eight reviews, and none uses *health-state capability* as an organising axis. Every review answers "how is it measured?" or "where is it measured?" — none answers **"what health state can this method actually resolve?"** Confirmed lexically: `capability level`, `maturity level`, `PHM level`, `readiness level`, `functional level` return **zero hits in all eight**.

---

## 3. Coverage measured across the full corpus

| Concept | R01 | R02 | R03 | R04 | R05 | R06 | **R07** | **R08** |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| `SOH` / state-of-health | **0** | **0** | **0** | **0** | **0** | 1 | 1 | **0** |
| `RUL` / remaining useful life | 0 | 2 | 0 | 2 | 3 | 6 | 48 | **0** |
| `prognostic*` | 2 | 1 | 1 | 2 | **0** | 9 | 22 | **0** |
| physics-informed / PINN | 0 | 0 | 0 | 2 | 0 | 0 | **136** | 0 |
| `digital twin` | 0 | 0 | 0 | 0 | 0 | 0 | 2 | 4 |
| `uncertaint*` | 1 | 0 | 0 | 0 | 1 | 0 | 21 | 1 |
| transfer learning / domain adapt. | 0 | 0 | 0 | 0 | 0 | 0 | 2 | 0 |
| Wiener / Gamma / particle filter | 0 | 0 | 0 | 0 | 0 | 0 | 7 | 0 |
| **capability / maturity level** | **0** | **0** | **0** | **0** | **0** | **0** | **0** | **0** |
| additional / extra sensor | — | 1 | — | 4 | **40** | 0 | **0** | 2 |
| computational burden/cost/complexity | — | 0 | — | 0 | 13 | 0 | 2 | 4 |
| sampling rate / frequency | — | 0 | — | 0 | 20 | 0 | 0 | 3 |
| **execution time / latency** | 0 | **0** | 0 | **0** | **0** | 0 | 2 | **0** |
| **memory footprint** | 0 | **0** | 0 | **0** | **0** | 0 | **0** | **0** |

### False-positive audit

R05's six apparent `hybrid model` hits were inspected individually. All six mean **hybrid switched-circuit models of boost converters** (its refs [34], [55], [56]) — not physics-informed machine learning. **Corrected count: 0.** Without this audit an automated sweep would have reported "physics-informed coverage exists" and the analysis would have erred in the opposite direction.

### Correction to the 2026-08-30 draft

The earlier claim that *"deployability has zero lexical presence"* was **wrong**, and is retracted. Broad-synonym recheck shows R05 carries 53 deployability-relevant hits. Inspection of R05's comparison tables (lines 315–360 of extracted text) shows a per-method **"limitations/requirements" column** recording *"Additional sensor" / "No additional sensor is required"*, alongside tabulated sampling rate and processor (DSP/MCU) entries.

R05 therefore holds the **best per-method deployability data of any existing review**. The revised argument is in §5 and does not depend on the retracted claim.

---

## 4. Per-review gap statement

**R01 Wang & Blaabjerg 2014** — Still the best treatment of failure mechanisms and lifetime models across Al-Cap / MPPF / MLCC. Lifetime models serve *design-stage reliability prediction*, not online RUL. Condition monitoring is one sub-section. Pre-dates the data-driven era.

**R02 Soliman 2016** — Established the method-family taxonomy that R03–R05 inherit. `SOH` = 0, `RUL` = 2. Stops at parameter estimation; no prognostics layer.

**R03 Dang & Kwak 2020** — Clean parameter-centred survey with some ML content. `SOH` = 0, `RUL` = 0. Narrow (Al-Cap / DC-link dominant).

**R04 Nathan 2023** — The only capacitor review to foreground ANN-based predictive maintenance, but treats ML as a method list. `SOH` = 0. No capability discrimination, no uncertainty.

**R05 Ramees & Ahmad 2023** — Most comprehensive by page count (26 582 words), most topology-bound by structure:

```
I. Introduction → II. Classification of CM → III. Offline
→ IV. Online (LC-filter / C-filter / both; then MMC) → V. Conclusions
```

`SOH` = 0, `prognostic*` = 0, no prognostics section. But — per the §3 correction — it holds the richest deployability data of the corpus. Its own conclusion names "measurement accuracy, adaptability to different system architectures, and cost-effectiveness" as open challenges, i.e. it *identifies* the deployability problem without building an axis to analyse it. Quotable support for Contribution C.

**R06 Torki 2023** — Excellent component physics and ageing laws; the natural backbone for our Section 2. Component-centric, not converter-centric: no online estimation inside a running converter, no algorithmic taxonomy.

**R07 Fassi 2024 — the strongest competitor.** Actual structure:

```
II. Degradation Mechanisms (A. Power Semiconductors · B. Capacitors)
III. Analytical Modeling
IV. Data-Driven Models (A. Condition Monitoring · B. Fault Detection & Diagnosis · C. RUL Prediction)
V. Physics-Informed Machine Learning
```

It genuinely owns the physics-informed framing — 136 occurrences, dedicated section, 48 RUL, 21 uncertainty. **Closed to us.**

**Correction to the 08-30 draft:** §IV's CM → FDD → RUL split is a functional grouping, closer to a capability axis than the abstract suggested. Three things still separate it from a capability ladder: it applies only within the data-driven paradigm; it is a section-level topical split written as narrative enumeration, not a rubric applied per method; and it carries no distribution audit.

**What it does not do:** additional-sensor = 0, memory = 0, execution time = 2, SOH = 1, component-agnostic, RUL section IGBT-dominated. **No deployability analysis in the strongest competitor.**

**R08 Yu 2025 — the recency problem, and a surprise.** Purely condition monitoring: SOH, RUL and `prognostic*` **all zero**. A 2025 TPEL review of capacitor *health monitoring* with no prognostic content whatsoever — the single most quotable data point in this analysis.

**New information not visible from the abstract:** §VII.B carries an **original benchmark** — five CM methods (RLS, second-order impedance extraction, trigonometric transformation, capacitor-storage-energy closed-loop, SM switching function) simulated on a three-phase MMC in PSCAD/EMTDC, assessed for noise immunity (vs SNR) and load dependence; all five below 2.5 % estimation error. It is accuracy-only: no timing, no memory, no processor. It measures *how well*, never *at what cost*.

---

## 5. What is genuinely unoccupied

Ranked by evidence strength:

1. **Health-state capability as an organising axis.** 0/8 reviews. Closest precedent is R07 §IV's 3-way split within one paradigm. Enables a quantitative, falsifiable headline claim.
2. **SOH definition and EOL reconciliation.** Absent from 7/8, including a 2025 TPEL health-monitoring review. The field has never defined the state it monitors.
3. **Deployability as an *integrated* axis** *(re-based after the §3 correction)* — three legs: (a) attributes appear as isolated table annotations, never a consistent rubric; (b) execution time = 2 across 8 reviews, memory = **0/8**, so embeddability claims are unverifiable; (c) **nobody cross-tabulates deployability against capability** — the question "does higher PHM capability cost deployability?" is unanswerable from any existing review. Leg (c) is strongest and depends on item 1.
4. **Capacitor-specific degradation-physics → observable-indicator causal mapping.** R01/R06 have the physics, R02–R05/R08 have the indicators; nobody connects them causally per chemistry inside a converter.
5. **Uncertainty quantification in capacitor prognostics.** ≤1 mention in every capacitor review; R07's 21 mentions are converter-wide and semiconductor-weighted.

## 6. What is NOT available to claim

- **Physics-informed / hybrid PHM for power converters** — R07 owns it (136 occurrences, dedicated section). Cite prominently as complementary. Claiming novelty here would be the exact error task book §24.5 forbids.
- **"First review of capacitor condition monitoring"** — R02 (2016) holds priority.
- **MMC capacitor monitoring** — R08 (TPEL 2025) is current, thorough, and benchmark-bearing.
- **"No review discusses sensor requirements or computational cost"** — **retracted.** R05 tabulates both.

---

## 7. Status

All eight reviews at `FULLTEXT`. The two acquisitions that could have overturned the Stage 0 verdict — R07 and R08 — have been read in full and do not; they sharpen it. Three corrections were made against the author's own earlier draft and are recorded in [decisions.md](../99_logs/decisions.md) D-005.

This document is complete for Stage 0. It will be revisited only if Stage 1 surfaces a review not in this corpus.

# Review of Reviews — Capacitor Condition Monitoring & PHM

**Date:** 2026-08-30 · **Stage:** 0 · **Companion data:** [review_gap_matrix.csv](review_gap_matrix.csv)

Evidence discipline: every entry is Crossref-verified. Each is tagged with the evidence level actually available — `FULLTEXT` (PDF obtained, text extracted, keyword-counted), `ABSTRACT+CITED` (abstract plus how it is characterised in citing full texts we hold), `ABSTRACT` (publisher abstract only). Claims are never stated more strongly than the tag permits.

---

## 1. The corpus

| ID | Review | Year | Venue | Citations | Evidence |
|---|---|---|---|---:|---|
| R01 | Wang & Blaabjerg — *Reliability of Capacitors for DC-Link Applications: An Overview* | 2014 | IEEE TIA 50(5) 3569–3578 | 1317 | FULLTEXT |
| R02 | Soliman, Wang & Blaabjerg — *A Review of the Condition Monitoring of Capacitors in PECs* | 2016 | IEEE TIA 52(6) 4976–4989 | 262 | ABSTRACT+CITED |
| R03 | Dang & Kwak — *Review of Health Monitoring Techniques for Capacitors* | 2020 | Sensors 20(13) 3740 | 32 | FULLTEXT |
| R04 | Nathan et al. — *Review of condition monitoring methods for capacitors* | 2023 | Microelectron. Reliab. 145 115003 | 21 | ABSTRACT |
| R05 | Muhammed Ramees & Ahmad — *Advances in Capacitor Health Monitoring Techniques* | 2023 | IEEE Access 11 133540–133576 | 35 | FULLTEXT |
| R06 | Torki, Joubert & Sari — *Electrolytic capacitor: Properties and operation* | 2023 | J. Energy Storage 58 106330 | 82 | ABSTRACT |
| R07 | Fassi et al. — *Toward Physics-Informed ML-Based Predictive Maintenance for Power Converters* | 2024 | **IEEE TPEL 39(2) 2692–2720** | **138** | ABSTRACT |
| R08 | Yu et al. — *Review of Health Monitoring Techniques for Capacitors in MMCs* | 2025 | **IEEE TPEL 40(9) 13363–13382** | 7 | ABSTRACT |

R01 was added beyond the task book's list because it is the field's citation anchor (1317 citations) and every later review builds on its failure-mechanism framing. R07 was added because systematic search identified it as the **strongest competitor**, and the task book did not anticipate it.

---

## 2. How each review organises the field

The organising axis matters more than the content, because it determines what the review can and cannot say.

| ID | Primary taxonomy | Axis type |
|---|---|---|
| R01 | Capacitor type × (reliability-oriented design \| condition monitoring) | Component + design |
| R02 | CM method family (circuit-model / signal-based / capacitor-model) | Method principle |
| R03 | Estimated parameter (ESR \| C) × measurement principle | Parameter |
| R04 | CM method family + ANN-based predictive maintenance | Method principle |
| R05 | Converter topology × output-filter type (C \| LC \| both) × offline/online | **Topology** |
| R06 | Component physics: construction → properties → ageing laws → predictive maintenance | Physics |
| R07 | Paradigm: model-based \| data-driven \| physics-informed ML | **Paradigm** |
| R08 | MMC monitoring method category × implementation | Topology (single) |

**Observation.** Eight reviews, and not one uses *health-state capability* as an organising axis. Every review answers "how is it measured?" or "where is it measured?" — none answers **"what health state can this method actually resolve?"** That vacancy is this project's primary opportunity.

---

## 3. Coverage measured, not assumed

Keyword occurrence over complete extracted text, for the three reviews held in full:

| Concept | R01 (2014) | R03 (2020) | R05 (2023) |
|---|---:|---:|---:|
| `state-of-health` / `SOH` | **0** | **0** | **0** |
| `remaining useful life` / `RUL` | 0 | 0 | 3 |
| `prognostic*` | 2 | 1 | **0** |
| `physics-informed` / `grey-box` | 0 | 0 | **0** |
| `digital twin` | 0 | 0 | 0 |
| `uncertaint*` | 1 | 0 | 1 |
| `deployab*` / `industrial adoption` | **0** | **0** | **0** |
| `transfer learning` / `domain adaptation` | 0 | 0 | 0 |
| Wiener / Gamma / particle filter | 0 | 0 | 0 |
| `MCU` / `DSP` / `FPGA` | 1 | 2 | 14 |

### False-positive audit

R05's six apparent `hybrid model` hits were inspected individually. All six refer to **hybrid switched-circuit models of boost converters** (its refs [34], [55], [56]) — a converter-modelling technique, unrelated to physics-informed machine learning. **Corrected count: 0.**

This audit matters. Without it, an automated keyword sweep would have reported "physics-informed coverage exists" and the novelty analysis would have been wrong in the opposite direction.

### R05 structural check

```
I. Introduction
II. Classification of Condition Monitoring
III. Offline Technique
IV. Online Techniques
    1) LC-type output filter   2) C-type output filter
    3) Both filter types       D) Monitoring in MMC
V. Conclusions
```

37 pages, 26 582 words, no prognostics section, no SOH section, no deployment section. The three RUL mentions are in the abstract and two passing sentences.

---

## 4. Per-review gap statement

**R01 Wang & Blaabjerg 2014** — Still the best treatment of failure mechanisms and lifetime models across Al-Cap / MPPF / MLCC. But lifetime models are used for *design-stage reliability prediction*, not online RUL. Condition monitoring is one sub-section. Pre-dates the data-driven era entirely.

**R02 Soliman 2016** — Established the method-family taxonomy that R03–R05 inherit. Stops at parameter estimation; the terms SOH and RUL do not organise it. *Full text needed to confirm at FULLTEXT strength — currently ABSTRACT+CITED.*

**R03 Dang & Kwak 2020** — Clean parameter-centred survey; some ML content (5 deep-learning hits). Zero SOH, zero RUL, zero deployability. Narrow (Al-Cap / DC-link dominant).

**R04 Nathan 2023** — The only capacitor review to foreground ANN-based predictive maintenance, but treats ML as a method list. No capability discrimination, no uncertainty, no deployment analysis. *ABSTRACT only — must be upgraded.*

**R05 Ramees & Ahmad 2023** — The most comprehensive by page count and the most topology-bound by structure. Its own conclusion names "measurement accuracy, adaptability to different system architectures, and cost-effectiveness" as open challenges — **naming the deployability gap without analysing it.** That sentence is quotable support for Contribution C.

**R06 Torki 2023** — Excellent component physics and ageing laws; the natural backbone for our Section 2. Component-centric, not converter-centric: no online estimation inside a running converter, no algorithmic taxonomy.

**R07 Fassi 2024 — the competitor.** In the target journal, 138 citations in ~2 years, and its model-based → data-driven → physics-informed structure *is* the task book's Generations 3→4→5. **Its limits define our space:** component-agnostic (capacitors share the paper with semiconductors, solder, PCB), paradigm-organised rather than capability-organised, and carrying no per-method deployability assessment. *ABSTRACT only — this is the single highest-priority acquisition.*

**R08 Yu 2025 — the recency problem.** Capacitor health monitoring, in TPEL, published September 2025. Topologically narrow (MMC submodule capacitors only) and without a prognostics layer, so it does not occupy our ground — but its existence is the strongest argument against a *generic* capacitor monitoring review in TPEL. *ABSTRACT only — second-highest priority.*

---

## 5. What is genuinely unoccupied

Ranked by strength of evidence:

1. **Health-state capability as an organising axis (Level 0–7).** No review uses it. Enables a quantitative, falsifiable headline claim.
2. **SOH definition and EOL criteria reconciliation.** Zero SOH occurrences across three full texts. The field has never defined the state it monitors.
3. **Engineering deployability as a first-class evaluation axis.** Zero lexical presence; R05 names it as an open challenge without analysing it.
4. **Capacitor-specific degradation-physics → observable-indicator causal mapping.** R01 and R06 have the physics, R02–R05 have the indicators; nobody connects them causally per chemistry.
5. **Uncertainty quantification in capacitor prognostics.** Near-zero (≤1 mention per review).

## 6. What is NOT available to claim

- **Physics-informed / hybrid PHM for power converters** — R07 (TPEL 2024) owns it. Cite prominently as complementary; claiming novelty here would be the exact error the task book's §24.5 forbids.
- **"First review of capacitor condition monitoring"** — R02 (2016) holds priority.
- **MMC capacitor monitoring** — R08 (TPEL 2025) is current and thorough.

---

## 7. Outstanding work before this document reaches full strength

Five full texts are needed to lift R02, R04, R06, R07, R08 from ABSTRACT to FULLTEXT: see [papers_to_obtain.csv](../02_literature/papers_to_obtain.csv). **R07 (Fassi 2024) and R08 (Yu 2025) are the two that could still change the verdict.** The remaining three would refine the gap matrix but are unlikely to overturn it, since the zero-coverage findings for SOH and deployability are already established on full text in three independent reviews spanning 2014–2023.

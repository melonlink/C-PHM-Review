# STAGE 0 REPORT — Scope Lock & Novelty Assessment

**Project:** Capacitor PHM Review (C-PHM-Review)
**Created:** 2026-08-30 · **Revised:** 2026-08-31 (all 8 reviews now analysed at full-text strength)
**Status:** Stage 0 — **PASS**. Stage 1 authorised.

---

## 0. Executive verdict

| Item | Result |
|---|---|
| Novelty verdict | **MODIFY** — confirmed on full text, with three corrections to the 08-30 draft |
| Is a new capacitor PHM review scientifically justified? | **Yes.** Strengthened, not weakened, by the competitor full texts. |
| Venue | **Path 2** — IEEE JESTPE first choice ([D-002](99_logs/decisions.md)) |
| Evidence strength | All 8 reviews now `FULLTEXT`. No claim rests on an abstract. |

**One-sentence answer:** the gap is a **capability and health-state-definition gap**, not a physics-informed gap; and it is now confirmed against the two competitors that could have overturned it.

### What changed on 2026-08-31

Three corrections, all made against the author's own earlier draft:

1. **"Deployability has zero coverage" was too strong.** Ramees 2023 tabulates additional-sensor need (40×), sampling rate (20×), and processor (14×) per method. Contribution C is re-based accordingly (§4C).
2. **Fassi 2024 is closer to a capability axis than its abstract suggested.** Its §IV splits data-driven work into CM → Fault Detection/Diagnosis → RUL Prediction. Contribution A is narrowed accordingly (§4A).
3. **Yu 2025 carries its own 5-method PSCAD benchmark** — new information, not visible from the abstract. Reinforces D-002 (§5).

**The core finding survived all three.** `SOH` is absent from 7 of 8 reviews; no review uses a capability ladder; execution time and memory footprint are absent from all 8.

---

## 1. Evidence base

All 8 reviews obtained in full text, text-extracted, and machine-analysed. Every DOI Crossref-verified; every PDF identity-checked against its expected DOI in-text (8/9 automatic; D08 confirmed by volume/issue/page/title/author match, being a Letters paper that does not print its DOI in the body).

Two DOIs I attempted to reconstruct from memory returned HTTP 404 at Crossref and were **discarded rather than guessed**.

---

## 2. Coverage measured across all eight reviews

Keyword occurrence over complete extracted text:

| | R01 '14 | R02 '16 | R03 '20 | R04 '23 | R05 '23 | R06 '23 | **R07 '24** | **R08 '25** |
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
| **execution time / latency** | 0 | **0** | 0 | **0** | **0** | 0 | 2 | **0** |
| **memory footprint** | 0 | **0** | 0 | **0** | **0** | 0 | **0** | **0** |

R07 = Fassi 2024 (TPEL), R08 = Yu 2025 (TPEL) — the two competitors.

### Three findings that survive scrutiny

**1. The field's reviews have never defined the state they monitor.** `SOH` is absent from 7 of 8 reviews; the two occurrences (Torki, Fassi) are single passing mentions, not definitions. Most striking: **Yu et al. 2025 — a capacitor health-monitoring review in TPEL, published September 2025 — contains zero occurrences of SOH, RUL, and `prognostic*` combined.** A 2025 review of "health monitoring" with no prognostic content is the clearest possible evidence that the field's reviews stop at parameter estimation.

**2. No review uses a capability or maturity grading.** Zero hits across all eight for `capability level`, `maturity level`, `PHM level`, `readiness level`, `functional level`. The organising axis is always *how* or *where* measured — never *what health state can be resolved*.

**3. Nobody reports what determines embeddability.** Execution time appears twice in one review (Fassi) and nowhere else; memory footprint appears **zero times in all eight**. These are precisely the quantities that decide whether an algorithm fits an MCU.

### False-positive audit

R05's six apparent `hybrid model` hits were inspected individually: all six mean **hybrid switched-circuit models of boost converters** (refs [34], [55], [56]), not physics-informed ML. Corrected count: **0**. Without this audit an automated sweep would have reported the opposite conclusion.

Full matrix: [review_gap_matrix.csv](00_scope/review_gap_matrix.csv) — 8 reviews × 30 fields, all `FULLTEXT`.

---

## 3. The competitors, read in full

### R07 · Fassi et al. 2024, IEEE TPEL 39(2):2692–2720 — 138 citations

Actual structure:

```
II. Degradation Mechanisms  (A. Power Semiconductors · B. Capacitors)
III. Analytical Modeling
IV. Data-Driven Models  (A. Condition Monitoring · B. Fault Detection & Diagnosis · C. RUL Prediction)
V. Physics-Informed Machine Learning
```

It genuinely owns the physics-informed framing: 136 occurrences, a dedicated section, 48 RUL and 21 uncertainty mentions. **Any claim of novelty there is closed to us.**

**Correction to the 08-30 draft:** §IV's CM → FDD → RUL split *is* a functional grouping, closer to a capability axis than the abstract suggested. But three things separate it from Contribution A: it applies only *within* the data-driven paradigm (not to analytical or physics-informed methods); it is a section-level topical split written as narrative enumeration ("Ismail et al. presented…", "Another study compared…"), not a rubric applied to each method; and it carries **no distribution audit** — it never asks how the corpus divides across the three.

**What it does not do, confirmed on full text:** additional-sensor requirement = **0**, memory = **0**, execution time = 2, SOH = 1. It is component-agnostic, and its RUL section is IGBT-dominated. **There is no deployability analysis in the strongest competitor.**

### R08 · Yu et al. 2025, IEEE TPEL 40(9):13363–13382

Purely condition monitoring: SOH, RUL and prognostics all zero. Structure is direct vs indirect monitoring methods for MMC submodule capacitors, plus temperature effects.

**New information not visible from the abstract:** §VII.B carries an **original benchmark** — five typical CM methods (RLS, second-order impedance extraction, trigonometric transformation, capacitor-storage-energy closed-loop, SM switching function) simulated on a three-phase MMC in PSCAD/EMTDC, evaluated for noise immunity (vs SNR) and load dependence. All five held estimation error below 2.5 %.

Two consequences. It confirms **TPEL expects reviews to carry original quantitative content** — reinforcing D-002. And it is accuracy-only: no execution time, no memory, no processor. The benchmark measures *how well*, never *at what cost*.

---

## 4. Novelty — the defensible line, after correction

### Contribution A — capability ladder plus distribution audit *(primary)*

Grade every method on Level 0–7 (Measurement → HI extraction → Parameter estimation → Detection → Severity → SOH → RUL → Maintenance decision), then **report the distribution**.

**Narrowed claim, post-correction.** Fassi 2024 §IV is the closest precedent and must be cited as such. What remains novel: (i) a *graded* axis, finer than a 3-way split; (ii) applied across **all** paradigms, not only data-driven; (iii) applied to **capacitors specifically**; and (iv) — the real contribution — the **distribution audit**. The headline *"N % of papers presenting themselves as capacitor PHM do not exceed Level 2"* is quantitative, falsifiable, reproducible, and no existing review can state it.

Supporting evidence: zero of eight reviews use any capability grading (§2, finding 2).

### Contribution B — SOH / EOL definitional disambiguation *(primary)*

`SOH` absent from 7 of 8 reviews. The field uses ESR×2 and ΔC = −20 % (Al-Cap) against ΔC = −2…−5 % (film) as EOL thresholds without reconciling them into a state definition. Deliver a **normalised SOH/EOL taxonomy per chemistry**, establishing which reported accuracies are actually comparable.

This is prerequisite to Contribution A: capability cannot be graded without defining the state. Yu 2025 — zero SOH in a 2025 TPEL health-monitoring review — is the quotable anchor.

### Contribution C — deployability as an integrated axis *(re-based)*

**Correction.** The 08-30 claim of "zero lexical presence" was wrong. Ramees 2023 tabulates additional-sensor need (40×), sampling rate (20×) and processor (14×) per method; Yu 2025 notes computational complexity and additional sensors; Fassi 2024 mentions computational cost twice.

The accurate and still-defensible claim has three legs:

1. **Nobody integrates these attributes into an evaluation axis.** They appear as isolated table annotations under "limitations", with no consistent rubric across methods.
2. **Nobody reports what actually determines embeddability.** Execution time: 2 occurrences across 8 reviews. Memory footprint: **0 across all 8**. Without these, no claim about MCU/DSP feasibility in the literature is verifiable.
3. **Nobody cross-tabulates deployability against capability.** The question *"does higher PHM capability cost deployability?"* cannot be answered from any existing review — and it is the question a practising engineer actually has.

Leg 3 is the strongest form, and it depends on Contribution A. That coupling makes A and C a single argument rather than two lists.

**Constraint (task book §11):** report axes separately or as a 2-D map. Do **not** synthesise a weighted "Deployability Score" unless the collected data independently justifies one.

### Contribution D — degradation-physics → observable-indicator mapping *(supporting)*

Per chemistry (Al-Cap / MPPF / MLCC), map mechanism → parameter drift → measurable signature. Fassi 2024 cannot do this, being component-agnostic; Torki 2023 has the physics but no converter context. Combining them is genuine added value.

### Contribution E — physics-informed / digital-twin outlook *(supporting only)*

**Demoted, definitively.** 136 physics-informed occurrences in Fassi 2024 settle it. Cite prominently, position as complementary, claim nothing. The task book's §24.5 prohibition on manufactured gaps applies to us first.

**Recommended title:**

> **"Capacitor Prognostics and Health Management in Power Electronic Converters: A Capability- and Deployability-Centred Review"**

---

## 5. Venue — decision and its confirmation

**Decision taken: Path 2** (author, 2026-08-30 — [D-002](99_logs/decisions.md)). Target ranking: **IEEE JESTPE** → IEEE TIE → IEEE OJPEL → IEEE Trans. Reliability.

The full texts **reinforce** this decision. TPEL published two adjacent reviews within 24 months, and Yu 2025 shows TPEL's current bar for a review in this exact topic includes an original simulation benchmark. A pure literature review would enter TPEL against that precedent. Path 2 avoids the comparison.

**Downstream consequence — the part that is easy to get wrong.** Under Path 2 the reproducibility fields (`Sampling_Rate`, `Processor`, `Real_Time`, `Computation_Cost`, `Code_Available`, `Data_Available`) are best-effort, recorded `NR` when unreported. **`NR` is not missing data — it is the evidence.** With no benchmark of our own, Contribution C leg 2 rests entirely on what the literature fails to report. `NR` counts must be tallied per axis and reported. The §2 finding that memory footprint is absent from all eight reviews is exactly this measurement, performed at review level; Stage 4 repeats it at paper level.

---

## 6. Stage 0 gate — task book §28

| # | Criterion | Status |
|---|---|---|
| 1 | Major existing reviews verified | **Pass** — 8/8 at full text |
| 2 | 2024–2026 dedicated search completed | **Pass** — Fassi 2024 + Yu 2025 identified and read |
| 3 | Review gap matrix completed | **Pass** — 8 × 30, all `FULLTEXT` |
| 4 | Clear difference vs 2016/2020/2023/2025 reviews | **Pass** — capability ladder 0/8; SOH 0/8 as a defined state; timing+memory 0/8 |
| 5 | ≥1 evidence-supported independent taxonomy | **Pass** — Level 0–7 capability ladder |
| 6 | Deployability adds incremental value | **Pass, re-based** — not "unmentioned" but "never integrated, never quantified, never cross-tabulated against capability" |
| 7 | PHM/SOH/RUL literature sufficient for standalone chapters | **Open** — deferred to Stage 1; main residual risk (§7) |
| 8 | Physics-informed maturity objectively assessed | **Pass** — low for capacitors (0/6 capacitor reviews); demoted to supporting |
| 9 | Not a re-titled duplicate | **Pass** — with the §4 repositioning |

**Gate decision: PASS.** Criterion 7 is a Stage 1 measurement, not a Stage 0 blocker. **Stage 1 is authorised.**

---

## 7. Principal risk carried into Stage 1

**There may not be enough genuine capacitor RUL/prognostics literature to fill Sections 5–6.**

The evidence is now stronger than on 08-30: `prognostic*` = 0 in both Ramees 2023 and Yu 2025, and Fassi's 48 RUL mentions sit in an **IGBT-dominated** section. Capacitor-specific prognostics may be an order of magnitude smaller than capacitor condition monitoring.

If Stage 1 confirms this, it is **not fatal — it is the finding.** The paper becomes *"the field has built extensive monitoring capability and almost no prognostic capability; here is the measured evidence and the reason why"* — which is precisely what Contribution A is designed to demonstrate. Yu 2025 already provides the anchor: a 2025 TPEL review of capacitor health monitoring with zero prognostic content.

**Stage 1 stop condition:** if fewer than ~25 papers reach Level 5 (SOH) or above, merge Sections 5–6 into a single "prognostic capability deficit" chapter rather than padding two thin ones.

---

## 8. Final answer to the mandated Stage 0 question

> *Based on the existing review literature, is a new capacitor PHM review scientifically justified, and what is the strongest defensible novelty of the proposed review?*

**Justified: yes**, and more firmly than the 08-30 draft could claim, because the two reviews that could have overturned the verdict have now been read in full and do not.

Eight reviews spanning 2014–2025 contain: no capability or maturity grading (0/8); no defined state-of-health (SOH absent from 7/8, and absent entirely from a 2025 TPEL health-monitoring review); no memory-footprint reporting (0/8); and no cross-tabulation of deployability against capability (0/8).

**Strongest defensible novelty:** *the first capacitor review that grades methods by **what health state they can actually resolve** (Level 0–7), reports the resulting capability distribution, and cross-tabulates that distribution against an integrated deployability assessment — quantifying the gap between what the field calls PHM and what it demonstrably delivers, and showing what that capability costs to deploy.*

**Not defensible, removed from the framing:** any novelty claim in physics-informed or hybrid PHM for power converters. Fassi et al. 2024 holds that ground with 136 in-text occurrences and a dedicated section.

---

## 9. Next actions

1. ~~Decide venue path.~~ **Done — Path 2, JESTPE first** ([D-002](99_logs/decisions.md)).
2. ~~Obtain P0 full texts.~~ **Done — all 9 received, verified, and analysed.**
3. ~~Re-run gap matrix at full-text strength.~~ **Done — verdict confirmed with three corrections.**
4. **Open Stage 1:** search strategy, query execution, screening log, master literature. Priority measurement: the Level 5+ paper count that resolves the §7 risk.

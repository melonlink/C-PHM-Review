# Research Questions

**Status:** Stage 0 draft, revised against the review-of-reviews evidence. Supersedes the task book §20 list where marked.

The task book's RQ1–RQ8 are retained, but re-ordered and re-weighted so that the questions carrying the paper's novelty come first, and the questions already answered by [Fassi 2024](https://doi.org/10.1109/TPEL.2023.3328438) are demoted to supporting status.

---

## Primary questions — these carry the contribution

### RQ-A — Capability *(new; was implicit in task book RQ2/RQ3)*
**What health state can each published method actually resolve, and how is the literature distributed across the Level 0–7 capability ladder?**

- Answerable quantitatively; falsifiable; reproducible from `method_evaluation_matrix.csv`.
- No existing review can answer it — none uses a capability axis (see [review_of_reviews.md](review_of_reviews.md) §2).
- Expected headline: the share of self-described "PHM"/"prognostics" papers that do not exceed Level 2 (parameter estimation).
- **Evidence required:** every core paper graded L0–L7 by two independent passes, with disagreements logged.

### RQ-B — Definition *(new; not in task book)*
**How is capacitor SOH defined across the literature, and are reported accuracies mutually comparable?**

- Motivated by a measured fact: `SOH` occurs **zero** times across three capacitor reviews held in full text (2014, 2020, 2023).
- Sub-questions: which EOL thresholds are used per chemistry (Al-Cap ESR×2 / ΔC = −20 %; film ΔC = −2…−5 %)? Is SOH a normalised parameter drift, a remaining-life fraction, or a classifier output? Under which definition pairs is a cross-paper accuracy comparison legitimate?
- Prerequisite for RQ-A: capability cannot be graded without a definition of the state.

### RQ-C — Deployability *(task book RQ7, promoted)*
**How far are published algorithms from embedded, online, industrial deployment — measured on separable axes rather than a composite score?**

- Axes: sensor requirement · intrusiveness (passive / semi-invasive / active / offline) · computational cost · real-time feasibility (sample rate, window, execution time, memory, processor) · operating-point robustness · cross-device generalisation.
- Zero lexical presence in prior reviews; Ramees 2023 names cost-effectiveness as an open challenge without analysing it.
- **Constraint (task book §11):** report axes separately. Do not synthesise a weighted "Deployability Score" unless the collected data independently justifies one.

---

## Supporting questions

### RQ-D — Physics-to-indicator mapping *(task book RQ1)*
**What is the causal relationship between capacitor failure physics and observable health indicators, per chemistry?**
Feeds Fig. 2 (Physics-to-PHM chain) and Section 3. Distinguishes this paper from the component-agnostic Fassi 2024.

### RQ-E — Prognostic capability *(task book RQ4)*
**Which methods perform genuinely reliable RUL prediction, and under what validation conditions?**
Sub-questions: accelerated-ageing versus field data; constant versus varying operating conditions; is prediction uncertainty calibrated or merely reported?
**Risk flag:** the answer may be "very few." If Stage 1 finds < ~25 papers at Level 5+, this question and RQ-F merge into a single "prognostic capability deficit" chapter rather than two thin ones (see STAGE0_REPORT §7).

### RQ-F — Value added by data-driven methods *(task book RQ5)*
**What capability do data-driven methods add over physical models — beyond accuracy on a single laboratory dataset?**
Must be answered in terms of capability gained (e.g. multi-parameter fusion, operating-point decoupling), not benchmark accuracy. Accuracy-only comparison is explicitly forbidden by task book §24.2.

### RQ-G — Physics-informed maturity *(task book RQ6, demoted)*
**Is physics-informed / hybrid PHM forming a distinct research direction for capacitors specifically?**
**Demoted deliberately.** Fassi 2024 (TPEL) already answers this at converter level. Our contribution is limited to the capacitor-specific instantiation and its current maturity — assessed at Stage 0 as **low** (zero coverage in capacitor reviews). Report as an emerging opportunity; do not overstate.

### RQ-H — Future breakthroughs *(task book RQ8)*
**What are the key breakthrough points for capacitor PHM?**
Answered last, and only from what RQ-A through RQ-G actually establish. Must separate *evidence-supported gaps* from *author-proposed opportunities* (task book Stage 5).

---

## Mapping to task book RQs

| Task book | Here | Change |
|---|---|---|
| RQ1 | RQ-D | Retained, supporting |
| RQ2, RQ3 | **RQ-A** | Merged and promoted to primary; made quantitative |
| RQ4 | RQ-E | Retained; risk-flagged |
| RQ5 | RQ-F | Retained; reframed from accuracy to capability |
| RQ6 | RQ-G | **Demoted** — pre-empted by Fassi 2024 |
| RQ7 | **RQ-C** | **Promoted to primary** |
| RQ8 | RQ-H | Retained, answered last |
| — | **RQ-B** | **New** — arises from the measured zero-coverage of SOH |

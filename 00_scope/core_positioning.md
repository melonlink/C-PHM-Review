# Core Positioning — LOCKED 2026-09-01

**This document defines the paper's identity.** Every later decision — outline, figures, which papers to read in full, what goes in the abstract — resolves against it. Changing it requires a logged decision in [decisions.md](../99_logs/decisions.md).

---

## 1. Title

> ## The Missing State-of-Health Layer in Capacitor Prognostics and Health Management: A Capability-Graded Review for Power Electronic Converters

Chosen 2026-09-01 by the author, over two more conservative alternatives, so that the **finding** rather than the method is what a reviewer reads first.

**Target venue:** IEEE JESTPE (first choice) → IEEE TIE → IEEE OJPEL → IEEE Trans. Reliability. Not TPEL ([D-002](../99_logs/decisions.md)).

---

## 2. Thesis — one sentence

> **The capability ladder of capacitor health management has a missing rung: between parameter estimation and life prediction there is no state of health.**

This is not "the field is immature." It is a structural defect with a precise location, measured rather than asserted.

---

## 3. The evidence chain

Two measurements, made independently at different stages, that lock together.

### Stage 0 — measured on the reviews

Nine reviews (2014–2025), all analysed at full text:

| | result |
|---|---|
| `SOH` | **zero occurrences in 7 of 9**; at most one passing mention in the other two |
| capability / maturity grading | **0 / 9** |
| memory footprint | **0 / 9** |
| execution time | 2 occurrences across all nine |

### Stage 1 — measured on the literature itself

151 capacitor-relevant papers, graded on the L0–L7 ladder, every L5+ claim adversarially audited by two independent lenses:

| Level | n | share |
|---|---:|---:|
| L7 maintenance decision | 2 | 1.3 % |
| L6 RUL prediction | 15 | 9.9 % |
| **L5 SOH estimation** | **0** | **0.0 %** |
| L4 severity | 3 | 2.0 % |
| L3 detection / diagnosis | 18 | 11.9 % |
| L2 parameter estimation | 95 | 62.9 % |
| L1 / L0 / unclassifiable | 18 | 11.9 % |

**74.8 % of the literature does not exceed parameter estimation.**

### The join

Stage 1 **explains** Stage 0. The reviews do not define SOH because **the literature does not produce it**. What began as a bibliometric absence is a structural one.

---

## 4. What "the L5 rung is empty" precisely claims

The wording must survive review. It does **not** claim nobody works on capacitor SOH. It claims:

> **SOH is never a terminal capability in this corpus.**

Under audit every candidate resolved one of two ways:

- **Downward** — the "health state" is an ESR estimate with a threshold attached. *Life-Cycle Monitoring and Voltage-Managing Unit for DC-Link Electrolytic Capacitors* (TPEL 2011) delivers online ESR identification; no accumulated life consumption, no normalised index, no state variable. → **L2**
- **Upward** — the state exists only as an intermediate toward a predicted life. *Prognostics of Multilayer Ceramic Capacitors Via the Parameter Residuals* (TDMR 2012) propagates residuals in a Bayesian state-space model to a failure threshold, yielding per-device RUL with uncertainty bounds. → **L6**

The field goes from parameter estimation **straight to** life prediction. Nothing shared, defined, and reusable sits in between — and that is exactly what a maintenance planner consumes. A planner does not act on an ESR value.

---

## 5. Contributions, ranked by evidential strength

| # | Contribution | Status |
|---|---|---|
| **1** | **The missing L5 layer.** The field jumps parameter estimation → life prediction with no health-state definition. | **Measured.** 0 / 151. The paper's thesis. |
| **2** | **Capability grading + inflation audit.** Grade methods by what they *output*, not what the title claims; report the distribution. | **Demonstrated.** 23 high-level claims audited, 7 corrected (30 %), 6 down 1 up. |
| **3** | **Deployability as an integrated axis**, cross-tabulated against capability. | Argued; needs Stage 4 full-text extraction. |
| **4** | **Degradation-physics → observable-indicator mapping** per chemistry. | Supporting. Fassi 2024 cannot do this — it is component-agnostic. |
| **5** | Physics-informed / digital-twin outlook. | **Demoted.** Fassi 2024 owns it (136 in-text occurrences). Cite as complementary; claim nothing. |

Contributions 1 and 2 are symbiotic: without the capability grading the missing rung is invisible; without the missing rung the grading is just another taxonomy.

Contribution 3 gains its sharpest form from Contribution 1 — the reason nobody reports execution time or memory is that there is no health state to compute in the first place. The deployability gap and the capability gap are two faces of one defect.

---

## 6. What is NOT claimed

- **Physics-informed / hybrid PHM for power converters** — Fassi et al. 2024 (TPEL) owns it.
- **First review of capacitor condition monitoring** — Soliman 2016 holds priority.
- **MMC capacitor monitoring** — Yu 2025 (TPEL) is current and benchmark-bearing.
- **"No review discusses sensor requirements or computational cost"** — retracted; Ramees 2023 tabulates both ([D-005](../99_logs/decisions.md)).

---

## 7. The one thing that can still overturn this

**Corpus provenance.** The 151 papers come from review reference lists, which are IEEE-heavy (86 % of co-cited papers) and demonstrably neglect prognostics. So L5+ is **under-counted**, and the measured deficit is an **upper bound on severity**.

If the supplementary sweep of the PHM community's own venues surfaces a body of genuine SOH-terminal work, the claim weakens from *"the rung is empty"* to *"the rung is thin"* — still publishable, far less sharp.

**Status: the supplementary sweep is running now, before the outline is written** (author decision, 2026-09-01). Exhaustive Crossref `prefix` / `issn` sweeps — deterministic filters, not relevance ranking — over PHM Society (all outlets incl. IJPHM), Microelectronics Reliability, IEEE Trans. Reliability, Reliability Engineering & System Safety, IEEE TDMR, IEEE JESTPE.

**No percentage from §3 may appear in the manuscript until that sweep is classified and this section is updated.**

---

## 8. Structural consequence already taken

**Sections 5 (SOH) and 6 (RUL) merge** into a single chapter on the prognostic capability deficit ([D-007](../99_logs/decisions.md)). The Stage 0 stop condition — fewer than ~25 papers at L5+ — is triggered at 17. The empty rung is that chapter's organising claim, not an apology for thin coverage.

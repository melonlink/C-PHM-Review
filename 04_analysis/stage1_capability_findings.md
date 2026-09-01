# Stage 1 — Capability Distribution of the Capacitor PHM Literature

**Date:** 2026-09-01 · **Evidence table:** [stage1_capability_matrix.csv](stage1_capability_matrix.csv)
**Status:** first measurement of Contribution A. Provisional — Stage 4 re-grades from full text.

---

## 1. Headline result

151 capacitor-relevant papers, drawn from the reference lists of the field's own 10 reviews, graded on the PHM capability ladder and adversarially audited:

| Level | What the method delivers | n | share |
|---|---|---:|---:|
| **L7** | Maintenance decision | 2 | 1.3 % |
| **L6** | RUL prediction | 15 | 9.9 % |
| **L5** | **SOH estimation** | **0** | **0.0 %** |
| L4 | Severity / identification | 3 | 2.0 % |
| L3 | Detection / diagnosis | 18 | 11.9 % |
| **L2** | **Parameter estimation (ESR / C / Z)** | **95** | **62.9 %** |
| L1 | Health-indicator extraction | 1 | 0.7 % |
| L0 | Measurement only | 4 | 2.6 % |
| — | Not classifiable from metadata | 13 | 8.6 % |

**Two numbers carry the paper:**

- **74.8 % of the literature does not exceed Level 2.** Nearly three quarters of capacitor "health" research terminates at estimating a parameter.
- **Level 5 is empty.** Not scarce — *empty*.

---

## 2. What the empty L5 rung actually means

This needs stating precisely, because the obvious reading is wrong.

It does **not** mean "nobody works on capacitor SOH." It means **SOH is never a terminal capability**. Every candidate resolved into one of two other things under audit:

1. **Downward** — what the paper calls a health state is an ESR or capacitance estimate with a threshold attached. Example: *"Life-Cycle Monitoring and Voltage-Managing Unit for DC-Link Electrolytic Capacitors"* (TPEL 2011) was graded L5 on its title; the audit found the delivered output is "online identification of the capacitor's ESR" with no accumulated life consumption, no normalised index, no state variable. Corrected to **L2**.

2. **Upward** — the paper defines a degradation state only as an intermediate quantity on the way to a predicted life, so its terminal output is RUL. Example: *"Prognostics of Multilayer Ceramic Capacitors Via the Parameter Residuals"* (TDMR 2012) was graded L5 and **upgraded to L6** — the residuals are propagated in a Bayesian state-space model to a failure threshold, yielding per-device RUL with uncertainty bounds.

So the field jumps **from parameter estimation straight to life prediction**, with no shared, defined notion of health state in between. That is the structural fact behind the Stage 0 observation that `SOH` occurs zero times across 8 of 9 reviews: the reviews do not define it because **the literature does not produce it**.

This converts Contribution B from a bibliometric curiosity into a substantive claim: the missing SOH layer is not a labelling oversight, it is a missing rung in the field's capability ladder — and it is exactly the rung that a deployable PHM system needs, because a maintenance planner consumes a health state, not an ESR value.

---

## 3. The audit worked — 30 % of high-level claims were misgraded

Every L5+ assignment was re-examined by two independent adversarial agents, each with a distinct lens (*does the output reach this level?* / *is the high-level claim about a capacitor at all?*), both instructed to default to refutation. Agents retrieved abstracts from external indexes where Crossref carried none.

**23 high-level claims audited → 7 corrected (30 %): 6 downgrades, 1 upgrade.**

Representative corrections:

| DOI | Title signal | Audited output | Change |
|---|---|---|---|
| `10.1109/imccc.2012.199` | "Fault diagnosis and **life prediction**" | RLS estimate of ESR and C while the motor is stopped; no lifetime model, no time-to-failure | L6 → **L2** |
| `10.1016/j.microrel.2017.11.002` | "**Prognostics** of electrolytic capacitors" | back-propagation ANN estimating ESR against a pristine baseline | L6 → **L2** |
| `10.1109/tim.2020.3001368` | health-state framing | forecasts C and ESR in an accelerated-ageing rig; no normalised state | L5 → **L2** |
| `10.36001/phme.2012.v1i1.1423` | Kulkarni et al., PHME 2012 | quadratic electrolyte-volume model fitted to C(t); Bayesian state estimation named as *future work* | L5 → **L2** |
| `10.1109/aero.2007.352885` | "prognostic" framing | precursor detection with discrete degradation states; RUL framed prospectively | L6 → **L3** |
| `10.1109/tdmr.2011.2162517` | "Prognostics via parameter residuals" | Bayesian propagation to failure threshold → per-device RUL with uncertainty | L5 → **L6** ⬆ |

**This is Contribution A demonstrated, not asserted.** A 30 % misgrading rate among self-described high-capability papers is precisely the "PHM level inflation" the review sets out to quantify — and the one upgrade shows the audit is not merely a deflation engine.

---

## 4. Where the surviving prognostic work sits

All 17 L5+ papers (15 × L6, 2 × L7):

- **Chemistry:** 13 aluminium electrolytic, 1 metallised film, 1 ceramic (MLCC), 2 unspecified. Film and ceramic prognostics are each represented by a **single paper**.
- **Method:** 8 model-based/filtering (Kalman, particle filter, state-space), 6 physics-of-failure/physics-informed, 2 data-driven, 1 experimental.
- **Era:** spans 1996 → 2020. This is not an emerging front; it is a thin, long-running strand.
- **Venue:** 9 IEEE, 2 Elsevier, 1 IET, 4 conference/other — a substantial share sits in conference proceedings (PHM Society, APEC, IAS, Infotech@Aerospace), which is why journal-only retrieval under-counts it.

**Consequence for the manuscript.** 17 papers cannot support two full chapters. The Stage 0 stop condition (< ~25 papers at L5+ → merge Sections 5 and 6) **is triggered**. Sections 5 and 6 should become a single chapter arguing the prognostic capability deficit, with the L5 vacancy as its organising claim rather than an apology for thin coverage.

---

## 5. Limitations — stated before the numbers are used

1. **Corpus provenance is not neutral.** These papers come from review reference lists, so the corpus is the canon *as reviews define it*, not the field. Since these reviews demonstrably neglect prognostics, **L5+ is under-counted here**. The measured deficit is therefore a *lower bound* on capability and an *upper bound* on the deficit's severity — read directionally, not as a population estimate. A supplementary pass over the PHM Society / NASA PCoE lineage is required before any percentage is published.

2. **Grading was mostly title-based.** Crossref deposits abstracts for only 52 of 619 records. The L5+ tier is well-grounded (auditors fetched abstracts externally — 326 tool calls across 30 agents), but **L2/L3 assignments rest on titles** and are softer. The 13 unclassifiable records are honest abstentions, not zeros.

3. **The proxy is biased upward by construction** (first match in descending order), so the true ≤L2 share is likely *higher* than 74.8 %, not lower. The bias runs against the paper's thesis, which makes the finding conservative.

4. **L5 = 0 is definition-dependent.** It follows from grading each paper at its *highest terminal* capability. A paper that estimates SOH *and* predicts RUL scores L6. The defensible claim is therefore "SOH is never a terminal capability in this corpus," not "no one computes a health index." That distinction must survive into the manuscript wording.

5. **Provisional.** Stage 4 re-grades every core paper from full text with two independent passes and logged disagreements. These numbers are the screening estimate that sizes the corpus and settles the Section 5–6 structure.

---

## 6. What this changes

| Contribution | Before Stage 1 | After Stage 1 |
|---|---|---|
| **A** — capability ladder + audit | Proposed as measurable | **Measured.** 74.8 % ≤ L2; 30 % of high-level claims misgraded |
| **B** — SOH definitional gap | Reviews never define SOH | **Stronger.** The literature never *delivers* SOH — the rung is structurally empty |
| **C** — deployability axis | Re-based on 3 legs | Unchanged; needs Stage 4 full-text extraction |
| **D** — physics→indicator mapping | Supporting | Unchanged |
| **E** — physics-informed outlook | Demoted | Confirmed: only 6 of 151 papers are PoF/physics-informed, all inside the L6 tier |

**Sections 5 and 6 merge** into one chapter on the prognostic capability deficit, per the Stage 0 stop condition.

# Stage 1 — Revised Findings after the Refutation Hunt

**Date:** 2026-09-01 · **Supersedes:** [stage1_capability_findings.md](stage1_capability_findings.md)
**Matrices:** [stage1_capability_matrix.csv](stage1_capability_matrix.csv) (151) · [stage1_supplementary_matrix.csv](stage1_supplementary_matrix.csv) (65)

---

## 0. The validation did its job — the earlier claim was wrong in one respect

Five agents were tasked with **refuting** the claim that Level 5 is empty, each from a different search angle, rewarded for breaking it. They ran 927 tool calls across 3.1 M tokens.

**Verdicts: 1 × claim_holds, 4 × claim_weakened, 0 × claim_refuted.** 22 candidates surfaced, **0 rated strong**, 9 moderate.

But the supplementary sweep changed a different number badly, and that is the honest headline of this document:

> **L6 (RUL) went from 15 papers to 54.**

The earlier corpus — built from review reference lists — under-counted prognostics by roughly **3.5×**, exactly the bias flagged in `stage1_capability_findings.md` §5. **The Section 5–6 merge decision was therefore made on bad numbers and is reversed** ([D-008](../99_logs/decisions.md)).

---

## 1. Combined distribution — 216 capacitor-relevant papers

| Level | | n | share |
|---|---|---:|---:|
| L7 | Maintenance decision | 2 | 0.9 % |
| **L6** | **RUL / lifetime prediction** | **52** | **24.1 %** |
| **L5** | **SOH estimation** | **1** | **0.5 %** |
| L4 | Severity / identification | 5 | 2.3 % |
| L3 | Detection / diagnosis | 22 | 10.2 % |
| **L2** | **Parameter estimation** | **107** | **49.5 %** |
| L1 / L0 / unclassifiable | | 27 | 12.5 % |

The shape is **bimodal with a hole**. Two large, well-populated peaks — parameter estimation at 49.5 % and life prediction at 24.1 % — separated by a rung containing **one paper**.

This is a better finding than the original one, and it forces a sharper thesis: it is no longer true that "the field stops at parameter estimation." The field is *also* substantial at prediction. What is missing is anything **between** them.

---

## 2. The real structure — three layers that do not compose

Splitting the 54 L6/L7 papers by what they *consume* and what they *emit* (measurable on the 30 records carrying an explicit `terminal_output`) reveals that "L6" was hiding two unrelated communities:

| | n | consumes | emits | typical venue |
|---|---:|---|---|---|
| **Design-stage lifetime prediction** | 17 | mission profile, ambient/hot-spot temperature, ripple current | *Bx life*, unreliability curve, time-to-failure under stated stress | JESTPE, Microelectronics Reliability, RESS |
| **Online prognostics** | 13 | *measured* degradation trajectory (ESR/C) | per-unit RUL with credible intervals | **PHM Society / IJPHM**, IEEE TR, TDMR |
| unclassified (field absent) | 24 | — | — | — |

The separation is nearly clean **by venue**, which is the tell: these are two research communities that publish in different places and cite each other sparingly.

Adding the condition-monitoring layer gives the actual architecture of the field:

```
  L2  Condition monitoring          107 papers   measures ESR / C in a live converter
        │                                        ... and stops
        ✗  no shared health state  (L5: 1 paper)
        │
  L6a Design-stage reliability       17 papers   consumes mission profile, never measures
  L6b Online prognostics             13 papers   consumes measured degradation directly
```

**Why the L5 rung is vacant: none of the three layers needs it.** Condition monitoring outputs a parameter and terminates. Design-stage lifetime prediction never touches a measurement. Online prognostics goes from measurement to life in one step, treating any internal degradation state as private scaffolding rather than as a published, reusable quantity.

**A defined state of health is precisely the interface that would let layer 1 feed layer 3** — and it is the quantity a maintenance planner actually consumes. Its absence explains, in one mechanism, both the SOH vacancy measured in Stage 0 (absent from 8 of 9 reviews) and the deployability vacancy (execution time reported twice across nine reviews, memory footprint never): **the layers do not compose, so nobody has had to cost the composition.**

---

## 3. What the hunters found, and why it does not break the claim

22 candidates, **0 strong**. The four moderate ones worth naming:

| DOI | Terminal output | Why it does not settle the matter |
|---|---|---|
| `10.1109/PEAS58692.2023.10395879` | composite failure probability on [0,1] explicitly declared to describe capacitor health state | Conference paper, 2023. The strongest single candidate. Full text not obtained. |
| `10.1109/ICEPET61938.2024.10626628` | scalar health score from a matrix condition number | Conference paper, 2024. Score is over *internal element breakdowns*, closer to severity (L4). |
| `10.1007/s43236-023-00744-7` | "health status" from a stacked MLP/RF/XGBoost + SVM ensemble | SVM meta-learner implies discrete health *classes* → L4, not a normalised state. Paywalled. |
| `10.1109/TPWRD.2022.3144267` | health condition of a distribution shunt-capacitor unit | Defined over count of broken internal elements → severity, and a distribution capacitor, not a converter capacitor. |

**Honest reading:** L5 is **not empty — it holds roughly 1 to 4 papers out of 216 (0.5–1.9 %)**, all recent (2022–2024), all conference or paywalled, none with a verified normalised health-state definition. The claim must be restated from *"the rung is empty"* to *"the rung is vacant relative to both its neighbours, and what little occupies it is recent, unverified, and does not share a definition."*

That the hunters' best effort produced **zero strong candidates** across five independent search angles is itself the evidence for the restated claim.

---

## 4. Consequences

| | Before | After |
|---|---|---|
| L6 count | 15 | **52** |
| L5 count | 0 | **1** (+3 unverified) |
| Sections 5 & 6 | merged ([D-007](../99_logs/decisions.md)) | **un-merged** ([D-008](../99_logs/decisions.md)) — 54 papers support a full chapter |
| Thesis | "the field stops at parameter estimation" | **"three layers that do not compose"** — sharper, and survives the larger L6 count |
| Title | unchanged | **unchanged** — "The Missing State-of-Health Layer" describes the revised finding better than the original one |
| New sub-finding | — | design-stage lifetime prediction vs online prognostics is a **community split**, cleanly separated by venue, and belongs in the prognostics chapter as its organising axis |

---

## 5. Standing limitations

1. **24 of 54 L6/L7 records lack a `terminal_output` field** (the first classification pass did not collect it). The design-life / online-RUL split is therefore measured on 30 papers, not 54. Stage 4 must re-extract this field for all of them before the split is quantified in the manuscript.
2. **The 0.5 % L5 figure is not yet publishable.** The four moderate candidates need full text to settle whether any defines a normalised health state. Two are conference papers likely obtainable; one is paywalled Springer.
3. Grading remains largely title- and abstract-based. Stage 4 re-grades core papers from full text.
4. Big general power-electronics journals (TPEL, TIE, TIA, Access) were not swept exhaustively — see `search_strategy.md` §9 coverage note. The review reference lists cover them densely, but a fully independent sweep would be stronger.

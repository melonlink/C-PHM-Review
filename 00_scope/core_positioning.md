# Core Positioning — LOCKED 2026-09-01 · REVISED after the refutation hunt

**This document defines the paper's identity.** Every later decision — outline, figures, which papers to read in full, what goes in the abstract — resolves against it. Changing it requires a logged decision in [decisions.md](../99_logs/decisions.md).

---

## 1. Title

> ## The Missing State-of-Health Layer in Capacitor Prognostics and Health Management: A Capability-Graded Review for Power Electronic Converters

Chosen 2026-09-01 by the author, over two more conservative alternatives, so that the **finding** rather than the method is what a reviewer reads first.

**Target venue:** IEEE JESTPE (first choice) → IEEE TIE → IEEE OJPEL → IEEE Trans. Reliability. Not TPEL ([D-002](../99_logs/decisions.md)).

---

## 2. Thesis — one sentence

> **Capacitor health management has three well-populated layers that do not compose, because the interface between them — a defined state of health — does not exist.**

Condition monitoring (107 papers) measures ESR and stops. Design-stage lifetime prediction (17) consumes mission profiles and never measures. Online prognostics (13) goes from measurement to remaining life in one step. Between the monitoring layer and the prognostic layer sits **one paper out of 216**.

This is not "the field is immature." It is a structural defect with a precise location, measured rather than asserted — and it survived a dedicated attempt to refute it.

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

216 capacitor-relevant papers (151 from the co-citation census + 65 from an exhaustive sweep of PHM-community venues), graded on the L0-L7 ladder, every L5+ claim adversarially audited:

| Level | n | share |
|---|---:|---:|
| L7 maintenance decision | 2 | 0.9 % |
| **L6 RUL / lifetime prediction** | **52** | **24.1 %** |
| **L5 SOH estimation** | **1** | **0.5 %** |
| L4 severity | 5 | 2.3 % |
| L3 detection / diagnosis | 22 | 10.2 % |
| **L2 parameter estimation** | **107** | **49.5 %** |
| L1 / L0 / unclassifiable | 27 | 12.5 % |

**Bimodal with a hole.** Two large peaks separated by a rung holding one paper.

### The join

Stage 1 **explains** Stage 0. The reviews do not define SOH because no layer of the field produces one — and none needs one, because the layers never hand work to each other.

---

## 4. What the claim precisely says

The wording must survive review. It does **not** say nobody works on capacitor SOH.

> **L5 is vacant relative to both its neighbours.** L2 holds 107 papers, L6 holds 52, and between them sits 1 confirmed paper plus 3 unverified candidates — all from 2022-2024, all conference or paywalled, none with a verified normalised health-state definition.

Five agents were tasked with **refuting** this from five independent search angles, rewarded for breaking it: 927 tool calls, 22 candidates, **zero rated strong**. Verdicts: 1 holds, 4 weakened, **0 refuted**.

### Why the rung is vacant — the mechanism

Splitting L6 by what each paper consumes and emits showed it was hiding two unrelated communities, separated cleanly by venue:

| | n | consumes | emits | venue |
|---|---:|---|---|---|
| Design-stage lifetime prediction | 17 | mission profile, temperature, ripple | Bx life, unreliability curve | JESTPE, Microelectron. Reliab., RESS |
| Online prognostics | 13 | *measured* degradation trajectory | per-unit RUL with credible intervals | PHM Society / IJPHM, IEEE TR, TDMR |

```
  L2  Condition monitoring        107   measures ESR / C in a live converter, then stops
        x  no shared health state  (L5: 1)
  L6a Design-stage reliability     17   consumes mission profile, never measures
  L6b Online prognostics           13   measurement to life in one step
```

**None of the three needs an SOH, so none produces one.** A defined health state is exactly the interface that would let layer 1 feed layer 3, and it is what a maintenance planner consumes. Its absence explains in one mechanism both the Stage 0 SOH vacancy and the deployability vacancy — the layers do not compose, so nobody has had to cost the composition.

---

## 5. Contributions, ranked by evidential strength

| # | Contribution | Status |
|---|---|---|
| **1** | **The vacant SOH layer.** L2 = 107, L5 = 1, L6 = 52. The two adjacent layers are large; the interface between them is not. | **Measured** on 216 papers, and it survived a dedicated refutation attempt (0 of 22 candidates rated strong). The paper's thesis. |
| **2** | **The three-layer disconnection.** Condition monitoring, design-stage lifetime prediction and online prognostics are three populated communities that do not hand work to each other — the split is clean by venue. | **New, found during the refutation hunt.** Explains *why* the SOH rung is vacant, rather than only reporting that it is. |
| **3** | **Capability grading + inflation audit.** Grade methods by what they *output*, not what the title claims; report the distribution. | **Demonstrated.** 23 high-level claims audited, 7 corrected (30 %), 6 down 1 up. |
| **4** | **Deployability as an integrated axis**, cross-tabulated against capability. | Argued; needs Stage 4 full-text extraction. |
| **5** | **Degradation-physics → observable-indicator mapping** per chemistry. | Supporting. Fassi 2024 cannot do this — it is component-agnostic. |
| — | Physics-informed / digital-twin outlook. | **Demoted out of the contribution list.** Fassi 2024 owns it (136 in-text occurrences). Cite as complementary; claim nothing. |

Contributions 1, 2 and 3 are one argument, not three. Without the capability grading (3) the vacant rung (1) is invisible; without the rung the grading is just another taxonomy; and without the community split (2) the vacancy is a curiosity rather than an explained defect.

Contribution 4 follows from 1 and 2 directly: **nobody reports execution time or memory because nobody is computing a health state on a controller in the first place.** The monitoring layer stops before it, and the prognostic layers never arrive at it. The deployability gap is not a separate shortcoming — it is what a disconnected architecture looks like from the engineering side.

---

## 6. What is NOT claimed

- **Physics-informed / hybrid PHM for power converters** — Fassi et al. 2024 (TPEL) owns it.
- **First review of capacitor condition monitoring** — Soliman 2016 holds priority.
- **MMC capacitor monitoring** — Yu 2025 (TPEL) is current and benchmark-bearing.
- **"No review discusses sensor requirements or computational cost"** — retracted; Ramees 2023 tabulates both ([D-005](../99_logs/decisions.md)).

---

## 7. Status of the validation — done, and it changed things

The supplementary sweep ran **before** the outline, as intended. 27,916 records swept exhaustively across six PHM-community venues via deterministic Crossref `prefix`/`issn` filters, yielding 186 capacitor+health records, 168 new.

**It broke one number and strengthened the thesis.** L6 rose from 15 to 52 — the review-reference corpus had under-counted prognostics ~3.5x. The Section 5-6 merge was made on that bad number and is reversed ([D-008](../99_logs/decisions.md)). The L5 vacancy survived.

Two counts from the sweep are findings in their own right, and they are complete over the venues rather than samples:

- **The PHM Society's entire publication record since 2007 — 2,754 papers — contains 13 on capacitors.**
- **Reliability Engineering & System Safety contains exactly one.**

These separate "genuinely thin literature" from "literature that capacitor reviews under-cite," which was the corpus-artefact objection the claim had to survive.

### What is still open

1. The 0.5 % L5 figure needs the four moderate candidates settled from full text.
2. 24 of 54 L6/L7 records lack the `terminal_output` field required to quantify the design-life / online-RUL split.
3. TPEL / TIE / TIA / Access were not swept exhaustively (`search_strategy.md` §9 coverage note).

**No percentage from §3 appears in the manuscript until 1 and 2 close at Stage 4.**

---

## 8. Structural consequence

**Sections 5 (SOH) and 6 (RUL) stay separate** — D-007 reversed by [D-008](../99_logs/decisions.md). 54 L6/L7 papers support a full prognostics chapter.

That chapter's organising axis is the newly found **community split**: design-stage lifetime prediction versus online prognostics, and the fact that they barely read each other. The short Section 5 becomes the argument for why the SOH rung is vacant, and why that vacancy is what keeps the two communities apart.

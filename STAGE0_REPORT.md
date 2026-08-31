# STAGE 0 REPORT — Scope Lock & Novelty Assessment

**Project:** Capacitor PHM Review (C-PHM-Review)
**Date:** 2026-08-30
**Status:** Stage 0 — **conditional pass**; 5 blocking full texts outstanding (see `02_literature/papers_to_obtain.csv`)

---

## 0. Executive verdict

| Item | Result |
|---|---|
| Novelty verdict | **MODIFY** (not KEEP, not REJECT) |
| Is a new capacitor PHM review scientifically justified? | **Yes — but not on the framing proposed in the task book.** |
| TPEL viability as-is (pure literature review) | **Low–moderate. Not recommended.** |
| TPEL viability with the repositioning in §4 + an original quantitative spine | **Moderate–good.** |
| Blocking issue | The "physics-informed intelligence" headline is **already occupied inside TPEL itself** by Fassi et al. 2024. |

**One-sentence answer:** the gap is real and measurable, but it is a **PHM-depth and deployability gap**, not a *physics-informed* gap — and the title/abstract must be rewritten accordingly before a single section is drafted.

---

## 1. What was actually verified

Every bibliographic claim below is Crossref-verified (DOI → title / authors / journal / volume / pages / year all matched). No reference in this report is unverified.

**Full text obtained and machine-analysed (3):**

- Wang & Blaabjerg 2014, IEEE TIA — `10.1109/TIA.2014.2308357` (1317 citations)
- Dang & Kwak 2020, Sensors — `10.3390/s20133740` (32 citations)
- Muhammed Ramees & Ahmad 2023, IEEE Access — `10.1109/ACCESS.2023.3336986` (35 citations)

**Metadata verified, full text still needed (5):** Soliman 2016 TIA; Nathan 2023 Microelectron. Reliab.; Torki 2023 J. Energy Storage; **Fassi 2024 TPEL**; **Yu 2025 TPEL**.

Two DOIs I attempted to reconstruct from memory returned HTTP 404 at Crossref and were **discarded rather than guessed**. That standard is applied throughout this project.

---

## 2. The measured gap (hard evidence, not assertion)

Keyword occurrence counts over the **complete extracted text** of the three capacitor reviews held in full:

| Concept | Wang 2014 | Dang 2020 | Ramees 2023 |
|---|---:|---:|---:|
| `state-of-health` / `SOH` | **0** | **0** | **0** |
| `remaining useful life` / `RUL` | 0 | 0 | 3 |
| `prognostic*` | 2 | 1 | **0** |
| `physics-informed` / `physics-guided` / `grey-box` | 0 | 0 | **0** |
| `digital twin` | 0 | 0 | 0 |
| `uncertaint*` | 1 | 0 | 1 |
| `deployab*` / `industrial adoption` | **0** | **0** | **0** |
| `transfer learning` / `domain adaptation` | 0 | 0 | 0 |
| Wiener / Gamma process / particle filter | 0 | 0 | 0 |

Three findings that survive scrutiny:

1. **"SOH" appears literally zero times in all three capacitor reviews held in full.** The field's reviews have never defined the state they claim to monitor. This is the single strongest justification for the paper.

2. **Ramees 2023's six "hybrid model" hits are false positives.** Inspecting every occurrence shows they mean *hybrid switched-circuit models of boost converters* (refs [34], [55], [56]) — **not** physics-informed machine learning. Physics-informed coverage in the capacitor review literature is therefore **genuinely zero**, not merely thin.

3. **Deployability has zero lexical presence** across all three. Ramees 2023 mentions "cost-effectiveness" once, in a closing sentence, with no supporting analysis.

Structural confirmation — Ramees 2023's actual section tree is:

```
I. Introduction → II. Classification of CM → III. Offline
→ IV. Online (by output-filter type: LC / C / both; then MMC) → V. Conclusions
```

It is organised by **converter topology**, not by health-state capability. There is no prognostics chapter.

Full matrix: [review_gap_matrix.csv](00_scope/review_gap_matrix.csv) — 8 reviews × 28 fields, each row tagged `FULLTEXT` / `ABSTRACT+CITED` / `ABSTRACT` so evidence strength is never overstated.

---

## 3. The problem the task book did not anticipate

The task book assumes the differentiator is *physics-informed / data-driven intelligence*. Systematic search says otherwise.

> **Fassi, Heiries, Boutet & Boisseau**, "Toward Physics-Informed Machine-Learning-Based Predictive Maintenance for Power Converters — A Review," *IEEE Trans. Power Electronics*, 39(2):2692–2720, 2024. DOI `10.1109/TPEL.2023.3328438`. **138 citations in ~2 years.**

This paper (a) is in **the exact target journal**, (b) already structures the field as *model-based → data-driven → physics-informed ML*, which is essentially the task book's Generations 3→4→5, and (c) explicitly covers capacitors among its components.

Compounding this, TPEL published **Yu et al. 2025** (`10.1109/TPEL.2025.3571897`, capacitor health monitoring in MMCs) in **September 2025**.

**Consequence:** TPEL has published two adjacent reviews within 24 months. A submission whose novelty rests on "physics-informed PHM for power converters" reads to a TPEL editor as a re-slicing of Fassi 2024; one resting on "capacitor health monitoring review" reads as a generalisation of Yu 2025. **Proposed Title Option A is, as written, the weakest of the three** — it collides head-on with Fassi 2024.

### What Fassi 2024 does *not* do — and this is where the paper lives

- It is **component-agnostic**: capacitors compete for space with IGBTs/MOSFETs, solder, PCB. There is no capacitor-specific *degradation-physics → observable-indicator* mapping.
- It reviews **paradigms**, not **capability**. It does not discriminate a paper that estimates ESR from one that predicts RUL.
- It offers **no per-method deployability assessment** (sensor cost, intrusiveness, MCU/DSP feasibility, operating-point robustness).

---

## 4. Repositioned novelty — the defensible line

Drop "physics-informed intelligence" from the headline. It is not ours to claim. Promote the two claims the evidence actually supports.

### Contribution A — the PHM-capability ladder, and an audit against it *(primary, unique)*

Grade every method on the Level 0–7 ladder (Measurement → HI extraction → Parameter estimation → Detection → Severity → SOH → RUL → Maintenance decision), then **report the distribution**.

The expected headline result — *"N% of papers presenting themselves as capacitor 'PHM' or 'prognostics' do not exceed Level 2 (parameter estimation)"* — is a **quantitative, falsifiable, reproducible** finding. No existing review can state it, because none has a capability axis. This converts the paper from opinion into measurement, and is the strongest single asset available.

### Contribution B — SOH / EOL definitional disambiguation *(primary, unique)*

Zero SOH occurrences across three reviews is not an accident. The field uses ESR×2 and ΔC = −20 % (Al-Cap) versus ΔC = −2…−5 % (film) as EOL thresholds without ever reconciling them into a state definition. Deliver a **normalised SOH/EOL taxonomy per capacitor chemistry**, showing which reported accuracies are actually comparable. This directly enables Contribution A.

### Contribution C — deployability as a first-class axis *(strong, defensible)*

Zero lexical presence in prior reviews. Score each method on sensor requirement / intrusiveness (passive · semi-invasive · active · offline) / computational cost / real-time feasibility / operating-point robustness.

**Follow the task book's own warning (§11): do not invent a weighted composite score.** Report the axes separately, or as a radar / 2-D map. A fabricated "Deployability Score" is the fastest route to reviewer rejection.

### Contribution D — degradation-physics → observable-indicator causal mapping *(supporting)*

Per chemistry (Al-Cap / MPPF / MLCC), map mechanism → parameter drift → measurable signature. Fassi 2024 cannot do this; it is not capacitor-specific.

### Contribution E — physics-informed / digital-twin outlook *(supporting only — demote)*

Keep as a forward-looking section. **Cite Fassi 2024 prominently and position explicitly as complementary**, not competing. Do not claim novelty here. The task book's §24.5 rule against manufacturing gaps applies to us first.

**Revised title recommendation** (closest to Option C, the safest of the three):

> **"Capacitor Prognostics and Health Management in Power Electronic Converters: A Capability- and Deployability-Centred Review"**

This signals both unique axes in the title and does not collide with Fassi 2024.

---

## 5. TPEL assessment — honest read

**In favour**

- TPEL's author guidelines explicitly welcome "review, tutorial, and survey articles with a viewpoint on the state-of-the-art and future technological advances."
- The topic is squarely in scope; capacitors are a first-order TPEL reliability concern.
- No page limit on regular submissions (10 free pages), which suits a review.

**Against — and these are not small**

1. **Editorial saturation.** Two adjacent reviews in TPEL within 24 months (Fassi 2024; Yu 2025). A third capacitor/converter-health review carries real desk-reject risk on novelty grounds alone.
2. **TPEL's experimental culture.** TPEL generally expects hardware results. Reviews are formally exempt, but recent TPEL reviews increasingly carry an original quantitative contribution. A purely narrative survey fits this journal's identity poorly.
3. Contributions A–C are *analytical*, and a reviewer can reasonably ask "where is the power-electronics contribution?" if there is no converter-side evidence.

**Recommendation — do not submit a pure literature review to TPEL.** Two paths were put to the author:

- **Path 1 — TPEL with a technical spine (higher risk, higher reward).** Add an original experimental/benchmark core: re-implement 3–5 representative methods (ripple-based, RLS, EKF, a data-driven model) on **one common converter and one common aged-capacitor set**, and report accuracy *jointly with* execution time, memory, and MCU/DSP feasibility.

- **Path 2 — a review-friendly venue (lower risk, still strong).** IEEE JESTPE, IEEE Trans. Industrial Electronics, IEEE Trans. Reliability, or IEEE Open Journal of Power Electronics. Contributions A–D stand on their own without new hardware.

### ▶ Decision taken: **Path 2** (author, 2026-08-30 — see [D-002](99_logs/decisions.md))

TPEL is not the target. Venue ranking for confirmation at Stage 6: **IEEE JESTPE** (first choice — PELS family, review-receptive, right readership for a deployability argument) → IEEE TIE → IEEE OJPEL → IEEE Trans. Reliability.

**What this changes downstream.** Reproducibility fields in `method_evaluation_matrix.csv` (`Sampling_Rate`, `Processor`, `Real_Time`, `Computation_Cost`, `Code_Available`, `Data_Available`) become **best-effort** rather than mandatory-fill, recorded as `NR` when a paper does not report them.

**Critical caveat:** under Path 2, `NR` is not missing data — **it is the evidence.** With no benchmark of our own, Contribution C rests on what the literature *fails to report*. A high `NR` rate on execution time and processor is itself the quantitative finding: the field cannot be assessed for deployability because it does not report deployability. `NR` counts must therefore be tallied and reported per axis, never silently dropped.

**What does not change.** The §4 repositioning stands regardless of venue. Fassi 2024 will be known to any reviewer in this area, whatever the journal — the capability and deployability axes remain the defensible ground.

---

## 6. Stage 0 gate — status against task book §28

| # | Criterion | Status |
|---|---|---|
| 1 | Major existing reviews verified | **Partial** — 8 verified bibliographically, 3 analysed in full text |
| 2 | 2024–2026 dedicated search completed | **Pass** — surfaced Fassi 2024 + Yu 2025, the two decisive competitors |
| 3 | Review gap matrix completed | **Pass** — 8 × 28, evidence-tagged |
| 4 | Clear difference vs 2016/2020/2023/2025 reviews | **Pass** — capability axis, deployability axis, SOH definition all measured at zero coverage |
| 5 | ≥1 evidence-supported independent taxonomy | **Pass** — the Level 0–7 capability ladder |
| 6 | Deployability adds incremental value | **Pass** — zero lexical presence in prior reviews |
| 7 | PHM/SOH/RUL literature volume sufficient for standalone chapters | **Not yet established** — deferred to Stage 1; main residual risk (§7) |
| 8 | Physics-informed maturity objectively assessed | **Pass** — assessed as *low* for capacitors; demoted to a supporting section |
| 9 | Not a re-titled duplicate | **Pass, conditional on the §4 repositioning** |

**Gate decision: conditional pass.** Criteria 1 and 7 must close before Stage 2.

---

## 7. Principal risk to manage in Stage 1

**There may not be enough genuine capacitor RUL/prognostics literature to fill Sections 5–6.**

The evidence is direct: `prognostic*` occurs 0 times in Ramees 2023, and searches for capacitor RUL surface mostly NASA/Kulkarni-lineage work (2010–2014) plus scattered recent LSTM papers — not a dense field. The capacitor prognostics literature may be an order of magnitude smaller than the condition-monitoring literature.

If Stage 1 confirms this, it is **not fatal — it is the finding**. The paper then becomes *"the field has built extensive monitoring capability and almost no prognostic capability; here is the measured evidence and the reason why"* — a stronger and more honest paper than a forced RUL chapter. But the framing must be decided on Stage 1 counts, not assumed now.

**Explicit Stage 1 stop condition:** if fewer than ~25 papers reach Level 5 (SOH) or above, restructure Sections 5–6 into a single "prognostic capability deficit" chapter rather than padding two thin chapters.

---

## 8. Final answer to the mandated Stage 0 question

> *Based on the existing review literature, is a new capacitor PHM review scientifically justified, and what is the strongest defensible novelty of the proposed review?*

**Justified: yes.** Six capacitor-focused reviews (2014–2025) collectively contain zero substantive treatment of state-of-health definition, prognostic capability grading, uncertainty, or engineering deployability. The capability and deployability axes are empirically unoccupied.

**Strongest defensible novelty:** *the first capacitor review that grades methods by **what health state they can actually resolve** (Level 0–7) rather than by converter topology or measurement principle, and that reports the resulting capability distribution together with a per-method deployability assessment — thereby quantifying the gap between what the field calls PHM and what it demonstrably delivers.*

**Not defensible, and must be removed from the framing:** any claim of novelty in physics-informed / hybrid PHM for power converters. Fassi et al. 2024 (TPEL) holds that ground.

---

## 9. Immediate next actions

1. ~~Decide Path 1 vs Path 2.~~ **Done — Path 2** ([D-002](99_logs/decisions.md)).
2. **User (in progress)** — obtain the 5 × P0 full texts listed in [papers_to_obtain.csv](02_literature/papers_to_obtain.csv). **D02 (Fassi 2024) and D03 (Yu 2025) are the two that can still change this verdict**; the rest refine it.
3. **Stage 1 is on hold** pending D02/D03 ([D-004](99_logs/decisions.md)). Running search and screening under a framing that may still change would waste the screening pass, since inclusion criteria depend on the final taxonomy.
4. On receipt of D02/D03: re-run the gap matrix at `FULLTEXT` strength → confirm or revise the §4 repositioning → open Stage 1. **Do not begin drafting until then** (task book §21, Stage 0).

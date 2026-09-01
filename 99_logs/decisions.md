# Decision Log

---

## D-001 · 2026-08-30 · Novelty repositioning: drop the physics-informed headline

**Decision:** Stage 0 verdict is **MODIFY**. Novelty moves onto the *capability* (Level 0–7) and *deployability* axes. Physics-informed / hybrid PHM is demoted to a supporting outlook section.

**Rationale:** [Fassi et al. 2024, IEEE TPEL 39(2):2692–2720](https://doi.org/10.1109/TPEL.2023.3328438) (138 citations) already structures the field as model-based → data-driven → physics-informed ML — essentially the task book's Generations 3→4→5. Claiming novelty there would be the exact error task book §24.5 forbids.

Meanwhile the capability and deployability axes are measurably unoccupied: `SOH` and `deployab*` each occur **zero** times across three capacitor reviews held in full text (2014 / 2020 / 2023).

**Supersedes:** task book §2.1 Title Option A, §25 Contribution 2 and Contribution 5 as primary claims.

**Reversible if:** full text of Fassi 2024 (D02) shows it does grade methods by health-state capability, or carries per-method deployability analysis. Pending acquisition.

---

## D-002 · 2026-08-30 · Venue: Path 2 — review-friendly journal, not TPEL

**Decision (user):** **Path 2.** Target a review-receptive venue rather than TPEL-with-benchmark.

**Rationale:** TPEL carries two compounding obstacles — editorial saturation (Fassi 2024 and Yu 2025 both published there within 24 months) and an experimental culture that disfavours pure surveys. Path 1 would have required original hardware work to clear both. Contributions A–D stand on their own without new hardware, so Path 2 delivers the same scientific content at materially lower risk and shorter cycle time.

**Venue ranking (my recommendation, for confirmation at Stage 6):**

1. **IEEE JESTPE** — *Journal of Emerging and Selected Topics in Power Electronics*. Best fit: PELS family, explicitly review-receptive, right readership for a deployability argument.
2. **IEEE Trans. Industrial Electronics** — publishes surveys, high impact, more competitive.
3. **IEEE Open Journal of Power Electronics** — OA, faster, lower barrier; good fallback.
4. **IEEE Trans. Reliability** — fits the PHM/capability framing, but a weaker power-electronics readership for Contribution C.

**Consequences for Stage 1:**

- Reproducibility fields in `method_evaluation_matrix.csv` (`Sampling_Rate`, `Processor`, `Real_Time`, `Computation_Cost`, `Code_Available`, `Data_Available`) revert from **mandatory-fill** to **best-effort**, recorded as `NR` (not reported) when absent.
- **`NR` is itself a finding.** Under Path 2 the deployability argument rests on *what the literature fails to report*, so `NR` counts must be tallied and reported, not silently dropped. A high `NR` rate on execution time and processor is direct evidence for Contribution C.
- No hardware or benchmark work is scheduled. Contribution C is argued from reported characteristics plus reporting gaps.

**Reversible if:** Stage 4 reveals enough reproducible methods (with code/data available) that a low-cost desk benchmark becomes feasible. Re-evaluate at Stage 5, not before.

---

## D-003 · 2026-08-30 · PDFs excluded from version control

**Decision:** `*.pdf` is gitignored. The `ReferencePaper/` tree structure and README are tracked; the PDFs are not.

**Rationale:** `melonlink/C-PHM-Review` is a **public** repository. Redistributing publisher PDFs — including accepted manuscripts under green OA, whose redistribution terms are restrictive — would be copyright infringement. The library is reproducible from verified DOIs via `PAPERS_TO_DOWNLOAD.md`.

---

## D-004 · 2026-08-30 · Sequencing: pause Stage 1 pending D02/D03

**Decision (user):** Stage 1 is on hold. User is obtaining the P0 full texts now.

**Rationale:** D02 (Fassi 2024) and D03 (Yu 2025) are the only two acquisitions that can still overturn D-001. Running Stage 1's search and screening under a framing that may change would waste the screening pass, since inclusion criteria depend on the final taxonomy.

**Resumes when:** D02 and D03 are in `ReferencePaper/`. Then: re-run the gap matrix at `FULLTEXT` strength → confirm or revise D-001 → open Stage 1.

---

## D-005 · 2026-08-31 · Stage 0 gate PASS; three corrections to the 08-30 draft

**Trigger:** all 9 requested full texts received, verified and analysed. The eight reviews now sit at `FULLTEXT` strength; nothing rests on an abstract.

**Verdict: unchanged — MODIFY.** The two acquisitions that could have overturned it (R07 Fassi 2024, R08 Yu 2025) were read in full and sharpen the case rather than weakening it. **Stage 0 gate: PASS. Stage 1 authorised.**

### Correction 1 — "deployability has zero lexical presence" is RETRACTED

The 08-30 draft claimed no review discusses deployability. **Wrong.** Broad-synonym recheck gives R05 (Ramees 2023) 53 relevant hits; its comparison tables carry a per-method limitations column recording *"Additional sensor" / "No additional sensor is required"* (40 occurrences), plus tabulated sampling rate (20) and processor DSP/MCU (14). R05 holds the best per-method deployability data in the corpus.

**Consequence:** Contribution C is re-based on three legs — (a) attributes appear as isolated annotations, never an integrated rubric; (b) execution time = 2 across all 8 reviews and memory footprint = **0/8**, so embeddability claims are unverifiable; (c) nobody cross-tabulates deployability against capability. Leg (c) is strongest and couples C to A.

**Why this was caught:** the original sweep used a narrow keyword set (`deployab|industrial adoption`). Running a broad-synonym recheck before publishing a zero-coverage claim is now standard practice for this project.

### Correction 2 — Fassi 2024 is closer to a capability axis than its abstract implied

Its §IV splits data-driven work into Condition Monitoring / Fault Detection & Diagnosis / RUL Prediction — a functional grouping.

**Consequence:** Contribution A narrows. It remains novel on four grounds: a *graded* axis finer than a 3-way split; applied across all paradigms rather than only data-driven; capacitor-specific; and carrying a **distribution audit**, which is the actual contribution. Fassi §IV must be cited as the closest precedent.

### Correction 3 — Yu 2025 carries its own benchmark (new information)

§VII.B simulates five CM methods on a three-phase MMC in PSCAD/EMTDC, assessed for noise immunity and load dependence. Not visible from the abstract.

**Consequence:** reinforces [D-002](#d-002--2026-08-30--venue-path-2--review-friendly-journal-not-tpel). TPEL's current bar for a review in this exact topic includes original quantitative content; a pure literature review would enter against that precedent. Also confirms the benchmark is accuracy-only (no timing/memory/processor) — it measures how well, never at what cost.

### What survived unchanged

- `SOH` absent from 7/8 reviews — including **Yu 2025, a 2025 TPEL health-monitoring review with SOH, RUL and prognostics all at zero**. The strongest single data point in the analysis.
- Capability/maturity grading: **0/8**.
- Memory footprint: **0/8**. Execution time: 2 occurrences across all 8.
- R05's six `hybrid model` hits remain confirmed false positives (switched-circuit models, not PIML).

**Residual open item:** task book §28 criterion 7 (is there enough capacitor RUL literature for standalone chapters?) is a Stage 1 measurement, not a Stage 0 blocker. Stop condition recorded in STAGE0_REPORT §7.

---

## D-006 · 2026-09-01 · Stage 0 corpus corrected to 9 reviews; Crossref rejected for retrieval

### A missed review, found by Stage 1 retrieval

Stage 1's first OpenAlex probe surfaced a capacitor review absent from the Stage 0 corpus:

> **Zhao, Davari, Lu, Wang & Blaabjerg — "An Overview of Condition Monitoring Techniques for Capacitors in DC-Link Applications," IEEE TPEL 36(4):3692-3716, 2021.** DOI `10.1109/TPEL.2020.3023469`. **252 citations.**

Obtained (hybrid OA), verified, and analysed at full-text strength as **R09**. Its coverage matches the established pattern exactly: SOH=0, RUL=3, prognostics=3, physics-informed=0, execution time=0, memory=0, computational cost=0, capability grading=0. It is organised by **application domain** (ASD / PV inverter / PFC / DC-DC) x CM derivation principle — a fourth non-capability axis.

**Effect on the verdict: strengthens it.** The zero-coverage findings now hold across **9** reviews spanning 2010-2025, and SOH is absent from **8 of 9**.

**Effect on the venue decision: strengthens D-002.** TPEL has now published **three** adjacent reviews — Zhao 2021, Fassi 2024, Yu 2025. Not two.

**Why it was missed at Stage 0.** Stage 0 searched via WebSearch, which surfaces by popularity rather than by index coverage. A dedicated title-level database sweep is what found it. Recorded as a limitation of WebSearch-based scoping.

### Crossref rejected as a retrieval database

Two Crossref retrieval attempts were run and both rejected. Full method and evidence in `01_search/search_strategy.md` §3.

- **Attempt 1** (deep-paged to 1000/query): 10 874 records, 41 containing "capacitor", 1 included. Crossref `query.title` is relevance-ranked fuzzy OR; paging past the relevant head returns the index tail.
- **Attempt 2** (relevance top-200/query): 5 001 records, 270 included, top-20 precision 19/20 — but recall against 12 known-relevant papers was **6/12**. Decisive test: `query.title=capacitor condition monitoring converter` does not return Soliman 2016 in the top 200 despite a near-exact title match, while querying its full title returns it at rank 2. Crossref relevance is not monotone in title overlap.

**Decision:** OpenAlex is the retrieval database (deterministic boolean, returns the complete matching set). Crossref is retained for **metadata verification by DOI**, which it does reliably.

**No statistic was computed from the Crossref corpus.** A capability distribution over a 50 %-recall sample is not a measurement, and reporting one would have been the same class of error as the retracted deployability claim in D-005.

**Two rules adopted for the rest of the project:**

1. Never deep-page a relevance-ranked endpoint.
2. Validate every retrieval strategy against a held-out set of known-relevant records **before** computing any statistic from the corpus.


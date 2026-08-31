# C-PHM-Review

Systematic review project: **Prognostics and Health Management of Capacitors in Power Electronic Converters**.

**Current stage:** Stage 0 (Scope Lock) — conditional pass. Drafting is **not** yet authorised.

---

## Start here

| Document | What it answers |
|---|---|
| **[STAGE0_REPORT.md](STAGE0_REPORT.md)** | Is this review worth writing? What is the defensible novelty? Can it go to TPEL? |
| **[PAPERS_TO_DOWNLOAD.md](PAPERS_TO_DOWNLOAD.md)** | 论文下载清单（含已核验 DOI） |
| [00_scope/review_of_reviews.md](00_scope/review_of_reviews.md) | What the 8 existing reviews cover, and what they measurably do not |
| [00_scope/review_gap_matrix.csv](00_scope/review_gap_matrix.csv) | 8 reviews × 28 coverage fields, evidence-tagged |
| [00_scope/research_questions.md](00_scope/research_questions.md) | The questions, re-weighted against the competitive landscape |

## Stage 0 headline

- **Verdict: MODIFY.** A new review is justified — but on a *capability and deployability* axis, **not** on physics-informed intelligence.
- **Why:** `SOH` occurs **zero times** across three capacitor reviews held in full text (2014, 2020, 2023). So does `deployability`. Meanwhile [Fassi et al. 2024 (TPEL)](https://doi.org/10.1109/TPEL.2023.3328438) already owns the physics-informed framing *in the target journal*.
- **TPEL:** viable only with an original quantitative spine (a benchmark), not as a pure literature review. TPEL has published two adjacent reviews within 24 months.

## Evidence discipline

Applied throughout, per task book §16:

1. Every DOI is Crossref-verified before use. Two DOIs reconstructed from memory returned 404 and were **discarded, not guessed**.
2. Every gap-matrix row carries an evidence tag: `FULLTEXT` / `ABSTRACT+CITED` / `ABSTRACT`. Claims never exceed the tag.
3. Keyword sweeps are audited for false positives before being reported. (This mattered: Ramees 2023's six `hybrid model` hits proved to be switched-circuit models, not physics-informed ML.)
4. No fabricated references. No unverifiable claims of "first" or "no study has."

## Layout

```
00_scope/       Research questions, review-of-reviews, gap matrix
01_search/      Search strategy, logs, screening       [Stage 1]
02_literature/  Master literature, core papers, BibTeX
03_taxonomy/    PHM / degradation / algorithm / deployability taxonomies  [Stage 3]
04_analysis/    Method evaluation matrix, trends, gaps  [Stage 4-5]
05_figures/     Six core figures                        [Stage 7]
06_paper/       Outline and manuscript                  [Stage 6-8]
99_logs/        Decisions, changelog
ReferencePaper/ PDF library, categorised (see its README)
Tasks/          Original task specification
```

## Next actions

1. Obtain the 5 × P0 full texts in [PAPERS_TO_DOWNLOAD.md](PAPERS_TO_DOWNLOAD.md). **D02 (Fassi 2024) and D03 (Yu 2025) can still change the verdict.**
2. Decide **Path 1** (TPEL + original benchmark) vs **Path 2** (review-friendly venue: JESTPE / TIE / T-Rel / OJPEL). This gates the Stage 1 data schema.
3. Re-run the gap matrix on the new full texts, finalise the verdict, then open Stage 1.

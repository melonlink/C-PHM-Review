# C-PHM-Review

Systematic review project: **Prognostics and Health Management of Capacitors in Power Electronic Converters**.

**Current stage:** Stage 0 (Scope Lock) — conditional pass. Drafting is **not** yet authorised.

---

## Start here

| Document | What it answers |
|---|---|
| **[STAGE0_REPORT.md](STAGE0_REPORT.md)** | Is this review worth writing? What is the defensible novelty? Which venue? |
| **[PAPERS_TO_DOWNLOAD.md](PAPERS_TO_DOWNLOAD.md)** | 论文下载清单（含已核验 DOI） |
| [00_scope/review_of_reviews.md](00_scope/review_of_reviews.md) | What the 8 existing reviews cover, and what they measurably do not |
| [00_scope/review_gap_matrix.csv](00_scope/review_gap_matrix.csv) | 8 reviews × 30 coverage fields, all at full-text strength |
| [00_scope/research_questions.md](00_scope/research_questions.md) | The questions, re-weighted against the competitive landscape |

## Stage 0 headline

- **Verdict: MODIFY — confirmed on full text.** All 8 reviews analysed completely; nothing rests on an abstract. A new review is justified on a *capability and deployability* axis, **not** on physics-informed intelligence.
- **Why:** `SOH` is absent from **7 of 8** reviews. No review uses a capability grading (**0/8**). Memory footprint is reported by **none** (0/8). Most telling: [Yu et al. 2025 (TPEL)](https://doi.org/10.1109/TPEL.2025.3571897) — a 2025 capacitor *health monitoring* review — contains zero occurrences of SOH, RUL and prognostics combined.
- **Not claimable:** physics-informed PHM. [Fassi et al. 2024 (TPEL)](https://doi.org/10.1109/TPEL.2023.3328438) owns it — 136 in-text occurrences, dedicated section.
- **Venue: Path 2 — not TPEL** ([D-002](99_logs/decisions.md)). Target ranking: **IEEE JESTPE** → TIE → OJPEL → T-Rel.
- **Stage 0 gate: PASS. Stage 1 authorised.**

## Evidence discipline

Applied throughout, per task book §16:

1. Every DOI is Crossref-verified before use. Two DOIs reconstructed from memory returned 404 and were **discarded, not guessed**.
2. Every gap-matrix row carries an evidence tag. All 8 rows now read `FULLTEXT`; no claim rests on an abstract.
3. Keyword sweeps are audited for false positives, and any zero-coverage claim is rechecked with a broad synonym set before publication. Both checks caught real errors: Ramees 2023's six `hybrid model` hits proved to be switched-circuit models rather than physics-informed ML, and a narrow first sweep produced a false "zero deployability coverage" claim that was retracted ([D-005](99_logs/decisions.md)).
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

1. ~~Decide venue path.~~ **Done — Path 2, targeting JESTPE first.**
2. ~~Obtain full texts.~~ **Done — all 9 received, identity-verified, analysed.**
3. ~~Re-run gap matrix at full-text strength.~~ **Done — verdict confirmed, three corrections logged in [D-005](99_logs/decisions.md).**
4. **Open Stage 1** — search strategy, query execution, screening, master literature. Priority measurement: the Level 5+ paper count that resolves the standing risk in [STAGE0_REPORT §7](STAGE0_REPORT.md).

Decisions are logged in [99_logs/decisions.md](99_logs/decisions.md).

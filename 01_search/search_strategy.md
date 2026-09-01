# Search Strategy

**Stage:** 1 · **Status:** retrieval complete via co-citation census + exhaustive venue sweeps
**Companion files:** [supplementary_sweep_log.csv](supplementary_sweep_log.csv) · [inclusion_exclusion.md](inclusion_exclusion.md) · [../02_literature/supplementary_pool.csv](../02_literature/supplementary_pool.csv)

---

## 1. Requirement

A systematic review needs **deterministic retrieval**: a query must return *every* indexed record matching the stated boolean expression, so that the recall of the corpus is a property of the query rather than of an opaque ranking function. Anything less makes the capability distribution — the paper's headline result — unquantifiable, because the shape of what was missed is unknown.

This requirement drove the choice of database, and it eliminated two candidates before it was met.

---

## 2. Databases evaluated

| Database | Boolean AND | Returns all matches | Abstracts | Verdict |
|---|---|---|---|---|
| OpenAlex | Yes | Yes (cursor over full result set) | Yes (inverted index) | Correct tool, but **unusable** — persistent IP-level HTTP 429 (§4) |
| Crossref `query.*` | No — relevance-ranked fuzzy OR | No | Partial (~50 %) | **Rejected** for retrieval (§3) |
| **Crossref `filter=prefix/issn`** | n/a — exact filter | **Yes, deterministic** | Partial | **Adopted** for exhaustive venue sweeps (§9) |
| **Crossref reference lists** | n/a | Complete per record | n/a | **Adopted** for the co-citation census (§8) |
| Semantic Scholar | Yes | Yes | Yes | Unusable — unauthenticated pool returns HTTP 429 |
| IEEE Xplore / Scopus / WoS | Yes | Yes | Yes | No programmatic access from this environment |

---

## 3. Two rejected attempts, and why they were rejected

Recorded because a systematic review's method section must state what was tried, and because both failures produce reusable rules.

### Attempt 1 — Crossref `query.title`, deep-paged to 1000 per query

21 queries, cursor-paged. Yielded **10 874 unique DOIs**, of which **41 titles contained the word "capacitor"**. The pool was dominated by unrelated medicine and materials science (*mitral regurgitation*, *retinitis pigmentosa*). Screening returned **1 included record**.

**Diagnosis.** Crossref `query.title` is a relevance-ranked fuzzy match, not a boolean filter. Cursor-paging past the relevant head returns the entire long tail of the index.

**Rule adopted.** Never deep-page a relevance-ranked endpoint. Relevance ranking bounds useful depth; paging beyond it adds noise, not recall.

### Attempt 2 — Crossref `query.title`, relevance top-200 per query

36 queries × top-200, no paging. Yielded **5 001 unique DOIs → 270 included**. Top-20 precision measured at **19/20** — the noise problem was solved.

But a recall check against 12 known-relevant papers (the eight Stage 0 reviews plus four verified method papers, all confirmed present in Crossref) returned **6/12**.

Missing: Soliman 2016, Wang & Blaabjerg 2014, Fassi 2024, Yu 2025, Nathan 2023, Yang 2010.

**The decisive test.** Querying `query.title=capacitor condition monitoring converter` does not return Soliman et al. 2016 — *"A Review of the Condition Monitoring of Capacitors in Power Electronic Converters"* — anywhere in the top 200, despite a near-exact title match. Querying the full title directly returns it at rank 2. Crossref's relevance function is therefore not monotone in title overlap and cannot be relied upon for retrieval.

**Rule adopted.** Every retrieval strategy is validated against a held-out set of known-relevant records **before** any statistic is computed from the corpus. 50 % recall was caught by this check; without it, the capability distribution would have been reported from a corpus missing half its anchors.

**This is why the headline statistic was not computed from the Crossref corpus.** A capability distribution over a 50 %-recall sample is not a measurement.

---

## 4. OpenAlex — correct method, blocked in practice

```
GET https://api.openalex.org/works
  filter = title_and_abstract.search:<BOOLEAN EXPRESSION>,
           from_publication_date:2009-01-01,
           to_publication_date:2026-12-31,
           type:article
  per-page = 200, cursor-paged to exhaustion
```

`title_and_abstract.search` supports `AND`, `OR` and parentheses, and the filter returns the complete matching set rather than a ranked prefix. Cursor paging is therefore exhaustive rather than noise-accumulating — the opposite of Attempt 1.

**Outcome: not usable from this environment.** An initial unthrottled run triggered an IP-level HTTP 429 that did not clear across 45 minutes of polite retries, nor on later attempts hours apart. Both `curl` and `urllib` were blocked, with and without the polite-pool `mailto`. Semantic Scholar returned 429 as well.

This is the correct method and should be used by anyone reproducing the review from an unthrottled IP — the query set in §5 is retained for that purpose. It did not run here, so **nothing in this review's corpus came from OpenAlex**. Retrieval fell back to §8 and §9, both of which are deterministic and, for the venues they cover, exhaustive.

**Date window.** 2009-01-01 to 2026-12-31. The task book (§12.2) specifies 2010–2026; one extra year is retained as a margin so boundary-year records are screened rather than silently dropped. Foundational pre-2009 work enters through the supplementary pass (§6), not through the systematic queries.

---

## 5. Query set (specified, not executed)

These are the boolean queries the OpenAlex method would run. They were never executed here (§4); they are recorded so the intended systematic search is reproducible from an unthrottled IP. Implements task book §13 Queries A–H, plus two supplementary strands (I). `CAP` denotes `(capacitor OR capacitors OR capacitance)`.

| ID | Strand | Boolean expression |
|---|---|---|
| A1 | Condition monitoring | `CAP AND ("condition monitoring" OR "health monitoring")` |
| A2 | DC-link | `"dc-link capacitor" OR "dc link capacitor" OR "DC-link capacitors"` |
| B1 | SOH | `CAP AND ("state of health" OR "state-of-health")` |
| B2 | Health indicators | `CAP AND ("health indicator" OR "health assessment" OR "health estimation")` |
| C1 | Prognostics / RUL | `CAP AND ("remaining useful life" OR prognostics OR prognosis)` |
| C2 | Lifetime / EOL | `CAP AND ("lifetime prediction" OR "life prediction" OR "end of life")` |
| D1 | Degradation in converters | `CAP AND (degradation OR aging OR ageing) AND (converter OR inverter OR "power electronic")` |
| D2 | Film capacitors | `("film capacitor" OR "metallized film" OR "metallised film") AND (degradation OR lifetime OR aging OR reliability)` |
| D3 | Electrolytic capacitors | `"electrolytic capacitor" AND (degradation OR aging OR ageing OR failure OR wear-out)` |
| D4 | Accelerated ageing | `CAP AND ("accelerated aging" OR "accelerated ageing" OR "accelerated life test")` |
| E1 | Data-driven | `CAP AND ("machine learning" OR "deep learning" OR "neural network") AND (health OR degradation OR fault OR life)` |
| F1 | Physics-informed | `CAP AND ("physics-informed" OR "physics informed" OR "grey-box" OR "gray-box")` |
| G1 | Digital twin | `CAP AND "digital twin"` |
| H1 | Parameter estimation | `CAP AND ("parameter estimation" OR "online estimation" OR "parameter identification")` |
| H2 | ESR | `("equivalent series resistance" OR ESR) AND (estimation OR monitoring OR identification OR measurement)` |
| I1 | Fault diagnosis | `CAP AND (converter OR inverter) AND (fault OR failure) AND (diagnosis OR detection)` |
| I2 | Reliability | `CAP AND (converter OR inverter OR "power electronic") AND reliability` |

Saturation evidence (task book §23) comes instead from the co-citation census in §8: 619 unique cited DOIs across 10 independent reviews, with the co-citation frequency distribution reported.

---

## 6. Supplementary pass — logged, never silent

Records known to be relevant but not returned by the systematic queries are added in a **separate, flagged** pass, so that database recall stays measurable instead of being quietly patched.

Sources: (a) the nine Stage 0 reference papers; (b) backward citation chasing from the reviews; (c) the NASA PCoE / PHM Society capacitor prognostics lineage, which is component-level and often lacks converter vocabulary; (d) foundational pre-2009 work.

Every supplementary record carries `source = SUPPLEMENTARY` with its reason. The systematic-versus-supplementary split is reported, because the proportion of Level 5+ papers that only a supplementary pass could find is itself a finding about how this literature is indexed.

---

## 7. Verification chain

Retrieval and verification are deliberately separated across two independent databases:

1. **Retrieve** by co-citation census (§8) and exhaustive venue sweep (§9) — both deterministic.
2. **Verify** every core paper's metadata against **Crossref** by DOI — title, authors, journal, volume, pages, year.
3. Any DOI failing Crossref resolution is marked `UNVERIFIED` and excluded from the evidence tables (task book §16.7). Two DOIs reconstructed from memory during Stage 0 returned HTTP 404 and were discarded rather than guessed; the same rule applies here.
4. Open-access status is checked via **Unpaywall** before any download attempt; nothing is fetched from a source not declared OA.

---

## 8. Adopted method A — co-citation census

With both search APIs unusable, the primary corpus was built without any search ranking at all.

All 10 reviews held in full text deposit their reference lists with Crossref. Those lists were pulled and unioned, giving **619 unique cited DOIs**, each resolved against Crossref. Records were then ranked by **how many INDEPENDENT reviews cite them** — a core-ness signal produced by domain experts rather than by a ranking function, and exactly reproducible from the 10 review DOIs.

| cited by | papers |
|---:|---:|
| 6 reviews | 5 |
| 5 | 7 |
| 4 | 33 |
| 3 | 25 |
| 2 | 57 |
| 1 | 492 |

**Its bias must be stated wherever its numbers are used.** A corpus of review references is the canon *as reviews define it*. These reviews neglect prognostics (SOH absent from 8 of 9), so Level-5+ work is systematically under-counted here. That bias is what §9 exists to correct.

---

## 9. Adopted method B — exhaustive venue sweep

*(2026-09-01 — the validation of the core claim)*

The core claim rests on a corpus built from review reference lists, which are IEEE-heavy (86 % of co-cited papers) and demonstrably neglect prognostics. The venues most likely to hold missed Level-5 work are therefore the PHM community's **own** outlets, which those reviews barely cite.

**Key realisation.** Crossref's `filter=prefix:` and `filter=issn:` are **deterministic** — unlike `query.*`, which is relevance-ranked and was measured at 50 % recall (§3). A venue can therefore be swept *completely* by cursor and title-filtered locally, with no ranking function anywhere in the path.

**27 916 records swept exhaustively across six venues:**

| Venue | Filter | Swept | capacitor + health |
|---|---|---:|---:|
| PHM Society — all outlets (PHM Conf, PHME, IJPHM, PHMAP) | `prefix:10.36001` | 2 754 | **13** |
| Microelectronics Reliability | `issn:0026-2714` | 6 619 | 108 |
| IEEE Trans. Device and Materials Reliability | `issn:1530-4388` | 2 106 | 34 |
| IEEE JESTPE | `issn:2168-6777` | 5 253 | 25 |
| IEEE Trans. Reliability | `issn:0018-9529` | 2 614 | 5 |
| Reliability Engineering & System Safety | `issn:0951-8320` | 8 570 | **1** |
| **Total** | | **27 916** | **186** |

168 of the 186 were new to the corpus.

### The sweep is itself a finding

Two numbers deserve to appear in the manuscript regardless of how the classification lands:

- **The PHM Society's entire publication record since 2007 — 2 754 papers across its conference series and IJPHM — contains 13 papers on capacitors.**
- **Reliability Engineering & System Safety, the flagship reliability-and-prognostics journal, contains exactly one.**

These are complete counts over the venues, not samples. They establish that capacitor prognostics is *genuinely* a thin literature, and not merely a literature that capacitor reviews happen to under-cite. That distinction is what separates a corpus artefact from a finding, and it is why the sweep was run before the outline rather than after.

### Coverage note

Big general power-electronics journals (TPEL, TIE, TIA, IEEE Access) were **not** swept exhaustively — they are large, and the nine reviews' reference lists already cover them densely (86 % of co-cited papers are IEEE). The supplementary sweep deliberately targets the complement of that coverage.

---

## 10. Known limitations, stated up front

1. **No Scopus / Web of Science / IEEE Xplore API access**, and OpenAlex blocked. Retrieval therefore rests on Crossref-deposited data: reference lists (§8) and deterministic venue filters (§9). A paper cited by none of the 10 reviews and published outside the six swept venues is absent from this corpus. §9's coverage note states which venues that leaves uncovered.
2. **Abstract coverage is uneven.** Many IEEE records carry no abstract in open metadata. Records without abstracts are screened on title alone and skew toward lower assigned capability. The `has_abstract` flag is retained throughout so this can be quantified rather than assumed — and the level distribution is reported separately for abstract-bearing records.
3. **Conference papers are not systematically retrieved.** `type:article` excludes most proceedings. Task book §14 admits conference papers with independent method contributions; these enter through the supplementary pass. This matters disproportionately for prognostics, where the PHM Society conference series carries much of the capacitor RUL lineage.
4. **English-language bias.** Not corrected.
5. **The level proxy is a screening estimate, not the finding.** Assignment from title and abstract is biased upward by design (see `inclusion_exclusion.md` §4). Stage 4 re-assigns every core paper from full text.

---

# Search Strategy

**Stage:** 1 · **Status:** retrieval in progress (OpenAlex harvest running)
**Companion files:** [search_log.csv](search_log.csv) · [screening_log.csv](screening_log.csv) · [inclusion_exclusion.md](inclusion_exclusion.md)

---

## 1. Requirement

A systematic review needs **deterministic retrieval**: a query must return *every* indexed record matching the stated boolean expression, so that the recall of the corpus is a property of the query rather than of an opaque ranking function. Anything less makes the capability distribution — the paper's headline result — unquantifiable, because the shape of what was missed is unknown.

This requirement drove the choice of database, and it eliminated two candidates before it was met.

---

## 2. Databases evaluated

| Database | Boolean AND | Returns all matches | Abstracts | Verdict |
|---|---|---|---|---|
| **OpenAlex** | Yes | Yes (cursor over full result set) | Yes (inverted index) | **Adopted for retrieval** |
| Crossref | No — relevance-ranked fuzzy OR | No | Partial (~50 %) | Rejected for retrieval; retained for **metadata verification** |
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

## 4. Adopted method — OpenAlex boolean retrieval

```
GET https://api.openalex.org/works
  filter = title_and_abstract.search:<BOOLEAN EXPRESSION>,
           from_publication_date:2009-01-01,
           to_publication_date:2026-12-31,
           type:article
  per-page = 200, cursor-paged to exhaustion
```

`title_and_abstract.search` supports `AND`, `OR` and parentheses, and the filter returns the complete matching set rather than a ranked prefix. Cursor paging is therefore exhaustive rather than noise-accumulating — the opposite of Attempt 1.

**Rate limiting.** An initial unthrottled run triggered an IP-level HTTP 429. Retrieval now runs at **1 request / 1.2 s** with a polite-pool `mailto`, and the harvester waits for the limit to clear before starting. Recorded because it materially affects reproduction time.

**Date window.** 2009-01-01 to 2026-12-31. The task book (§12.2) specifies 2010–2026; one extra year is retained as a margin so boundary-year records are screened rather than silently dropped. Foundational pre-2009 work enters through the supplementary pass (§6), not through the systematic queries.

---

## 5. Query set

Implements task book §13 Queries A–H, plus two supplementary strands (I). `CAP` denotes `(capacitor OR capacitors OR capacitance)`.

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

Per-query yield, new-unique contribution and cumulative pool size are logged in `search_log.csv` — this is the saturation evidence required by task book §23.

---

## 6. Supplementary pass — logged, never silent

Records known to be relevant but not returned by the systematic queries are added in a **separate, flagged** pass, so that database recall stays measurable instead of being quietly patched.

Sources: (a) the nine Stage 0 reference papers; (b) backward citation chasing from the reviews; (c) the NASA PCoE / PHM Society capacitor prognostics lineage, which is component-level and often lacks converter vocabulary; (d) foundational pre-2009 work.

Every supplementary record carries `source = SUPPLEMENTARY` with its reason. The systematic-versus-supplementary split is reported, because the proportion of Level 5+ papers that only a supplementary pass could find is itself a finding about how this literature is indexed.

---

## 7. Verification chain

Retrieval and verification are deliberately separated across two independent databases:

1. **Retrieve** with OpenAlex (deterministic boolean).
2. **Verify** every core paper's metadata against **Crossref** by DOI — title, authors, journal, volume, pages, year.
3. Any DOI failing Crossref resolution is marked `UNVERIFIED` and excluded from the evidence tables (task book §16.7). Two DOIs reconstructed from memory during Stage 0 returned HTTP 404 and were discarded rather than guessed; the same rule applies here.
4. Open-access status is checked via **Unpaywall** before any download attempt; nothing is fetched from a source not declared OA.

---

## 8. Known limitations, stated up front

1. **Single retrieval database.** No Scopus or Web of Science access from this environment. OpenAlex indexes Crossref plus additional sources, but a record absent from OpenAlex is absent from this review unless the supplementary pass catches it.
2. **Abstract coverage is uneven.** Many IEEE records carry no abstract in open metadata. Records without abstracts are screened on title alone and skew toward lower assigned capability. The `has_abstract` flag is retained throughout so this can be quantified rather than assumed — and the level distribution is reported separately for abstract-bearing records.
3. **Conference papers are not systematically retrieved.** `type:article` excludes most proceedings. Task book §14 admits conference papers with independent method contributions; these enter through the supplementary pass. This matters disproportionately for prognostics, where the PHM Society conference series carries much of the capacitor RUL lineage.
4. **English-language bias.** Not corrected.
5. **The level proxy is a screening estimate, not the finding.** Assignment from title and abstract is biased upward by design (see `inclusion_exclusion.md` §4). Stage 4 re-assigns every core paper from full text.

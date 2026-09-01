# Inclusion & Exclusion Criteria

**Stage:** 1 · **Applied:** deterministically, by regex, over title + abstract (Crossref metadata)
**Implementation:** `screen.py` — every decision is reproducible from `search_log.csv` + the recorded rules below. No paper is included or excluded by unrecorded judgement at this stage.

---

## 1. Screening philosophy

Stage 1 screening is **deliberately permissive on the health axis and strict on the subject axis**. A false exclusion is unrecoverable (the paper never reaches Stage 4); a false inclusion costs one line in a CSV and is removed at Stage 2 core-paper selection, where abstracts and full texts are read.

Consequently the rules below are applied as a *sieve*, not a verdict.

---

## 2. Inclusion rule (all three must hold)

A record is `INCLUDE` iff it matches **CAPACITOR** *and* **HEALTH** *and* (**POWER-ELECTRONICS** *or* **STRONG-PHM**), and is not caught by an exclusion rule.

### CAPACITOR — the subject must be a capacitor
```
capacitor | capacitance | ESR | electrolytic | metallized/metallised film
| MLCC | DC-link | dielectric
```

### HEALTH — the paper must be about health, not design
```
condition monitoring | health monitoring | state-of-health | SOH | degradation
| aging/ageing | deterioration | fault | failure | diagnosis | prognosis
| remaining useful life | RUL | lifetime | end-of-life | reliability | wear-out
| anomaly | predictive maintenance | health assessment/estimation/indicator
```

### POWER-ELECTRONICS — converter context
```
converter | inverter | rectifier | drive | power electronic | MMC | modular multilevel
| PWM | photovoltaic | PV | wind turbine | motor drive | VSI | DC-link | power supply
| SMPS | grid-connected | traction | electric vehicle | EV | boost | buck | flyback
| H-bridge | SVG | UPS
```

### STRONG-PHM — admits component-level prognostics work without converter context
```
prognostics | remaining useful life | RUL | state-of-health | SOH
| predictive maintenance | health management | accelerated aging | condition monitoring
```

**Why STRONG-PHM exists.** The NASA/Kulkarni-lineage capacitor prognostics work is component-level and often carries no converter term. Excluding it would remove precisely the Level 6–7 papers whose scarcity is the review's central question, and would bias the capability distribution toward the monitoring end. This disjunction is the single most consequential screening choice in Stage 1 and is flagged here for that reason.

---

## 3. Exclusion rules

| Rule | Rationale |
|---|---|
| Supercapacitor / ultracapacitor / EDLC / electric double-layer | Task book §15 — different device physics and health semantics |
| Lithium-ion / battery / fuel cell / pseudocapacitive | Task book §15 — not the review subject |
| Electrode materials, nanocomposites, MXene, graphene electrodes, device synthesis | Materials science with no PHM pathway |
| No title in Crossref metadata | Unverifiable |
| Published before 2009 | Outside the systematic window (task book §12.2 sets 2010–2026; 2009 is kept as a one-year margin so that boundary-year records are screened rather than silently dropped) |
| Exclusion term appears **in the title** | Subject-level exclusion overrides an abstract-level mention |

**Asymmetry, stated explicitly.** An exclusion term in the *abstract* does not exclude if the *title* is capacitor-focused. This preserves papers that legitimately cite battery SOH methodology as transferable prior art — task book §15 permits exactly this use in the methodology-transfer discussion.

---

## 4. PHM capability level proxy (L0–L7)

Each included record receives a **provisional** level from title + abstract, assigned by first match in descending order:

| Level | Trigger |
|---|---|
| **L7** Maintenance decision | maintenance decision/scheduling/policy/planning, replacement decision |
| **L6** RUL prediction | remaining useful life, RUL, prognosis, life prediction, end-of-life prediction, residual life |
| **L5** SOH estimation | state-of-health, SOH, health state/status/assessment/evaluation/index, degradation state/level estimation |
| **L4** Severity / identification | severity, fault identification/isolation/location/classification, degree of degradation |
| **L3** Detection / diagnosis | fault detection, fault diagnosis, anomaly, incipient fault, open-circuit fault |
| **L2** Parameter estimation | estimation, identification, extraction, observer, monitoring |
| **L1** Health indicator | health indicator, feature extraction, signature |
| **L0** Measurement | none of the above |

### Known limitations — stated before the numbers are used

1. **Descending-order first-match inflates upward.** A paper titled *"ESR estimation for RUL prediction"* scores L6 even if it only estimates ESR and cites RUL as motivation. The proxy therefore yields an **upper bound** on capability.
2. **That bias is the right direction.** The review's hypothesis is that the field claims more capability than it delivers. An upward-biased proxy makes the hypothesis *harder* to support, so any observed capability deficit is conservative.
3. **Abstract coverage is incomplete.** Crossref abstracts are absent for many IEEE records; those are scored on title alone and skew low. The `has_abstract` flag is retained so this can be quantified rather than assumed.
4. **This is a screening estimate, not the finding.** Stage 4 re-assigns every core paper's level from full text, with two independent passes and logged disagreements. The Stage 1 distribution is used only to size the corpus and decide the Section 5–6 structure.

---

## 5. What Stage 1 deliberately does not do

- **No quality judgement.** Venue prestige, citation count and methodological rigour play no role in inclusion. They inform Stage 2 core-paper selection.
- **No full-text reading.** Screening is metadata-only by design, so it is reproducible by anyone with the same Crossref queries.
- **No manual additions at screening time.** Papers known to be relevant but missed by the queries (e.g. the NASA capacitor prognostics set) are added in a separate, **logged** supplementary pass so that database recall can be measured honestly rather than quietly patched.

---

## 6. Relation to the task book

| Task book §14 / §15 | Implementation here |
|---|---|
| Peer-reviewed journals | Crossref filter `type:journal-article` |
| Conference papers with independent method contribution | **Not harvested at Stage 1.** Added selectively at Stage 2 where a conference paper is the primary record of a method. Journal extensions are linked per §16.6. |
| Directly related to capacitor health | CAPACITOR ∧ HEALTH |
| Clear model / algorithm / experimental validation | Deferred to Stage 2 — not assessable from metadata |
| Power-electronics relevance | POWER-ELECTRONICS ∨ STRONG-PHM |
| Supercapacitor & battery excluded from the main corpus | Exclusion rules; methodology-transfer citations preserved via the title/abstract asymmetry |

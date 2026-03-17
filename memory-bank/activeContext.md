# Active Context

_Last updated: 2026-03-17_

## Current Phase

**Phase 2e: Submission Day — March 17, 2026 (DEADLINE TODAY)**

PA-AKG (abstract_v2) is confirmed as submission #1 — citation issues fixed, authors added, provenance definition sentence added. AKG-E (v4e) is the selected primary AKG-E submission — professor-guided structure with full VVUQ framing, RQ1/RQ2 with evaluation criteria, and extensible domain design. SVF (v5) remains available as a third option but is not the current focus. All changes have been merged to main; no open PRs.

## Current Workflow

**~~Polish All 3~~ → ~~Run Reviewer Process~~ → ~~Incorporate Feedback~~ → ~~Finalize Citations~~ → ~~Select AKG-E Variant~~ → Submit by Mar 17**

| Rank | Proposal | CFP Topics | Status |
|---|---|---|---|
| **#1** | **PA-AKG** (v2) | Knowledge Grounding + Agentic AI | SUBMISSION-READY — citation issues fixed (Yan2024CRAG, Yu2024COSMO), provenance definition sentence added, authors added (Jason Cusati, Chris Brown); all changes on main |
| **#2** | **AKG-E** (v4e) | AI for Science & Engineering + Agentic AI | SUBMISSION-READY — professor structure, VVUQ backbone, RQ1/RQ2 with evaluation criteria, extensible 3-domain design (construction primary + transportation + energy), Bedrock hook; site fully updated; on main |
| **#3** | **SVF** (v5) | Agentic Evaluation + Responsible AI | SUBMISSION-READY — reserved for other venues if AKG-E submitted |

## Current Focus

- [x] Apply advisor edits to PA-AKG (v2) — completed Mar 16 (PR #12)
- [x] Fix citation issues in abstract_v2 (Yan2024CRAG, Yu2024COSMO) — completed Mar 17
- [x] Add provenance definition sentence to abstract_v2 — completed Mar 17
- [x] Add authors to abstract_v2 (Jason Cusati, Chris Brown) — completed Mar 17
- [x] Add authors to all AKG-E variants (v3/v4/v4b/v4c/v4d/v4e: Jason Cusati + Kereshmeh Afsari) — completed Mar 17
- [x] Create AKG-E v4d — domain-agnostic synthesis with VVUQ + engineering-agent citations — completed Mar 17
- [x] Create AKG-E v4e — full professor structure, application challenge, RQ1/RQ2 with evaluation criteria, extensible domain design — completed Mar 17
- [x] Update citation matrix — v4d and v4e columns; 7 new citation keys registered — completed Mar 17
- [x] Update docs/proposal-akge.html — full v4e professor structure posted — completed Mar 17
- [x] Update docs/downloads.html — v4e PDF entry added at top — completed Mar 17
- [x] Merge all changes to main — no open PRs — completed Mar 17
- [ ] **[CRITICAL — TODAY]** Portal submission by March 17, 2026

## Strategy Pivot (Mar 14)

The devil's advocate analysis revealed key insights that shifted our strategy:

1. **PA-AKG is our strongest proposal** — highest reviewer alignment, feasibility, and Amazon relevance
2. **SVF has honest weaknesses** — "meta" nature (evaluates systems but doesn't build one), overclaimed novelty
3. **Topic overlap concern was overstated** — different primary topics go to different reviewer pools; PA-AKG and AKG-E are genuinely different proposals
4. **PA-AKG is most feasible in 1 year** — clearly scoped system with natural ablation points

As a result, PA-AKG is ranked #1, AKG-E is #2, and SVF is #3 (reserved for other venues if not submitted).

See `memory-bank/strategy-pivot.md` for full analysis and AKG-E reframing notes.

## Polish Summary (Completed Mar 14)

All abstracts have been polished to submission quality with the following changes:

- **PA-AKG (v2)**: Sharpened novelty framing (unified substrate vs isolated components), added Self-RAG citation, added concrete evaluation tasks
- **SVF (v3)**: Toned down overclaims (removed "first framework" language), developed coordination reliability dimension, narrowed scope to feasible 1-year plan
- **AKG-E (v4)**: Added concrete simulation tools (OpenSeesPy, SUMO), tightened prose throughout, narrowed focus to 2+1 domains
- **AKG-E (v4b)**: New file created as reframed variant with 2 focused application domains + VVUQ as unifying validation backbone

## Research Directions

### PA-AKG — Provenance-Aware Agentic Knowledge Graph Systems (Rank #1)
- Primary Topic: Knowledge Grounding
- Secondary Topic: Agentic AI
- Key framing: Hybrid retrieval (sparse+dense) is now mainstream. Novelty is in provenance-aware KG grounding + validation loops — addressing gaps in multi-hop structured reasoning and fine-grained verifiable evidence chains.

### AKG-E — Agentic Knowledge Graphs for Engineering (Rank #2)
- Primary Topic: AI Accelerated Science & Engineering
- Secondary Topic: Agentic AI
- Key framing: Reframed around extensible application domains (construction primary, transportation, energy) with VVUQ as unifying validation backbone. Aligns with advisor's construction.ai initiative.
- **v4e variant (PRIMARY)**: Full professor structure — application challenge (VVUQ gap), RQ1/RQ2 with evaluation criteria (benchmark suite for RQ1; constraint violation rate + task success rate for RQ2), intellectual merit, contributions, practice impact, expandability. Hypothesis reframed as evaluation design target (>50% constraint violation reduction), not a prediction. Authors: Jason Cusati + Kereshmeh Afsari.
- **v4d variant**: Domain-agnostic synthesis with VVUQ + engineering-agent citations (Park2026MCPSIM, LLMAgentsFEM2025, Soman2025ConstructionDT). Superseded by v4e.
- **v4c variant**: Construction-only. Superseded by v4e.
- **v4b variant**: 2 focused domains (construction + transportation). Superseded by v4e.

### SVF — Structured Validation Framework (Rank #3)
- Primary Topic: Foundation Model/Agentic Evaluation
- Secondary Topic: Responsible Generative AI
- Status: May be reserved for other venues.

## What's Working

- Project infrastructure complete (memory-bank, construction, agents)
- CFP requirements fully captured
- Abstracts v1-v4e (+ v4b, v4c, v4d) complete across 3 proposals (7 total variants)
- All abstracts polished to submission quality with authors
- Deep research reports published on dashboard (SVF + AKG-E)
- Devil's advocate analysis completed
- Submission strategy analysis completed
- Website restructured with ranked proposal cards, dedicated pages, v4e posted
- Citation matrix covers v2–v4e with 7 new citation keys registered Mar 17
- All changes merged to main; no open PRs
- GitHub repo, Pages site, and CI pipeline live

## What's Next

- [x] Polish all 3 abstracts to submission quality (completed Mar 14)
- [x] Create AKG-E v4b variant (completed Mar 14)
- [x] Create AKG-E v4c variant (construction-only) (completed Mar 15/16)
- [x] Apply advisor edits to PA-AKG v2 (completed Mar 16)
- [x] Create SVF v5 from deep research synthesis (completed Mar 16)
- [x] Deploy deep research HTML pages for SVF and AKG-E (completed Mar 16)
- [x] Add citation tooltips and keywords to proposal pages (completed Mar 16)
- [x] Fix abstract_v2 citation issues + add provenance sentence + add authors (completed Mar 17)
- [x] Create AKG-E v4d (domain-agnostic + VVUQ + engineering-agent citations) (completed Mar 17)
- [x] Create AKG-E v4e (full professor structure, RQ1/RQ2 with eval criteria) (completed Mar 17)
- [x] Update citation matrix with v4d/v4e columns and 7 new keys (completed Mar 17)
- [x] Update proposal-akge.html and downloads.html with v4e (completed Mar 17)
- [x] Merge all changes to main (completed Mar 17)
- [ ] Portal submission (CRITICAL — TODAY March 17, 2026)

## Active Decisions

- **Decided**: PA-AKG (v2) is submission #1 — citation issues fixed, authors added, ready to submit
- **Decided**: AKG-E (v4e) is the primary AKG-E submission — professor structure, full evaluation framing, extensible domains
- **Decided**: PA-AKG ranked #1, AKG-E #2, SVF #3
- **Decided**: v4e supersedes v4b, v4c, v4d — all prior AKG-E variants are archived
- **Decided**: SVF (v5) reserved for other venues; not the current submission focus

## Blockers

- Portal submission must be completed today (March 17, 2026 — deadline)

---

**Note:** Update every session with current status.

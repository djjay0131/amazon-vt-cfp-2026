# Active Context

_Last updated: 2026-03-15_

## Current Phase

**Phase 2d: Reviewer Process & Final Selection**

All abstracts (v2, v3, v4, v4b, and new v4c) have been polished to submission quality. Next step is running the reviewer process on all polished abstracts, incorporating feedback, selecting which 2 to submit, and submitting by March 17.

## Current Workflow

**~~Polish All 3~~ → Run Reviewer Process → Incorporate Feedback → Select 2 → Submit**

| Rank | Proposal | CFP Topics | Status |
|---|---|---|---|
| **#1** | **PA-AKG** (v2) | Knowledge Grounding + Agentic AI | POLISHED — sharpened novelty (unified substrate vs isolated), added Self-RAG citation, concrete eval tasks |
| **#2** | **AKG-E** (v4) | AI for Science & Engineering + Agentic AI | POLISHED — concrete simulation tools, tightened prose, narrowed to 2+1 domains |
| **#2b** | **AKG-E** (v4b) | AI for Science & Engineering + Agentic AI | POLISHED — 2 focused domains (construction + transportation) + VVUQ backbone |
| **#2c** | **AKG-E** (v4c) | AI for Science & Engineering + Agentic AI | CREATED (Mar 15) — construction-only variant, drops transportation domain, VVUQ backbone |
| **#3** | **SVF** (v3) | Agentic Evaluation + Responsible AI | POLISHED — toned down overclaims, developed coordination reliability, narrowed scope |

## Current Focus

- [x] Create AKG-E v4c (construction-only variant) — completed Mar 15
- Run reviewer process on all polished abstracts (Mar 15)
- Incorporate reviewer feedback (Mar 16)
- Final selection of which 2 to submit (Mar 16) — now choosing from: v2 (PA-AKG), v3 (SVF), v4 (AKG-E 4-domain), v4b (AKG-E 2-domain), v4c (AKG-E construction-only)
- Portal registration and submission by March 17, 2026

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
- Key framing: Reframed around 2 concrete applications (construction material takeoff with CV, transportation digital twin) with VVUQ as unifying validation backbone. Aligns with advisor's construction.ai initiative.
- **v4b variant**: Further reframed with 2 focused domains (construction + transportation) and VVUQ as the backbone rather than a component.
- **v4c variant**: Construction-only version of AKG-E — drops transportation domain entirely, tightens focus to construction material takeoff with VVUQ backbone. Based on v4b.

### SVF — Structured Validation Framework (Rank #3)
- Primary Topic: Foundation Model/Agentic Evaluation
- Secondary Topic: Responsible Generative AI
- Status: May be reserved for other venues.

## What's Working

- Project infrastructure complete (memory-bank, construction, agents)
- CFP requirements fully captured
- Abstracts v1-v4 (+ v4b, v4c) complete across 3 proposals (5 submission-ready variants)
- All abstracts polished to submission quality
- Deep research report published on dashboard
- Devil's advocate analysis completed
- Submission strategy analysis completed
- Website restructured with ranked proposal cards and dedicated pages
- GitHub repo, Pages site, and CI pipeline live

## What's Next

- [x] Polish all 3 abstracts to submission quality (completed Mar 14)
- [x] Create AKG-E v4b variant (completed Mar 14)
- [x] Create AKG-E v4c variant (construction-only) (completed Mar 15)
- [ ] Run reviewer process on all polished abstracts (Mar 15)
- [ ] Incorporate feedback, select final 2 for submission (Mar 16)
- [ ] Portal registration and submission (by March 17)

## Active Decisions

- **Decided**: PA-AKG ranked #1, AKG-E #2, SVF #3
- **Decided**: Polish all 3 → review → select → submit workflow
- **Decided**: AKG-E reframing: 2 applications (construction CV + transportation digital twin) + VVUQ
- **Decided**: Created AKG-E v4b as alternative submission option alongside v4
- **Decided**: Created AKG-E v4c (construction-only) as third AKG-E variant (Mar 15)
- **Pending**: Which 2 proposals to submit (decision after reviewer process, Mar 16)
- **Pending**: Which AKG-E variant to submit — v4 (4-domain), v4b (2-domain), or v4c (construction-only)

## Blockers

- None — 3 days until abstract deadline (March 17, 2026)

---

**Note:** Update every session with current status.

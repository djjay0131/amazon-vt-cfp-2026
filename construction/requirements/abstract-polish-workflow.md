# Abstract Polish Workflow

_Created: 2026-03-14_

## Workflow Overview

```
Polish All 3 Abstracts → Run Reviewer Process → Incorporate Feedback → Select 2 → Submit
```

### Timeline

| Date | Task |
|------|------|
| Mar 15 | Polish all 3 abstracts to submission quality |
| Mar 16 | Run reviewer process on each; incorporate feedback; decide which 2 to submit |
| Mar 17 | Portal registration and submission (deadline) |

### Selection Criteria

After the reviewer process, the final 2 will be selected based on:

1. Reviewer feedback quality and concerns raised
2. Strength of novelty claims after polish
3. Amazon/CFP topic alignment
4. Feasibility within 1-year scope
5. Advisor enthusiasm and fit

---

## Proposal 1: PA-AKG — Provenance-Aware Agentic Knowledge Graph Systems

**Rank**: #1 (highest priority)

| Field | Value |
|-------|-------|
| Primary Topic | Knowledge Grounding |
| Secondary Topic | Agentic AI |
| Abstract Version | v2 (abstract_v2.pdf) |
| Current Status | **POLISHED** — novelty sharpened, Self-RAG citation added, concrete eval tasks |

### Known Strengths

- Strongest topic fit for CFP (Knowledge Grounding is a core Amazon interest)
- Highest feasibility — clearly scoped system with natural ablation points
- Best abstract writing quality (v2 is SOA-grounded with 2024-2026 citations)
- Strong Amazon relevance (Bedrock, RAG, knowledge management)
- Addresses real gaps: provenance-aware KG grounding + validation loops beyond GraphRAG/CRAG
- Dr. Brown as co-PI/collaborator — strong fit

### Known Weaknesses

- Knowledge Grounding is a competitive topic area — many submissions expected
- "Provenance-aware" framing needs to be clearly differentiated from standard attribution/citation work
- Architecture diagram may be too complex for 1-page abstract

### Remaining Work

- [x] Sharpen novelty claims: unified substrate vs isolated capabilities (GraphRAG/CRAG/Self-RAG)
- [x] Tighten Amazon/Bedrock relevance language
- [x] Verify 1-page fit with references excluded
- [x] Final language polish

---

## Proposal 2: AKG-E — Agentic Knowledge Graphs for Engineering

**Rank**: #2

| Field | Value |
|-------|-------|
| Primary Topic | AI Accelerated Science & Engineering |
| Secondary Topic | Agentic AI |
| Abstract Version | v4 (abstract_v4.pdf) |
| Current Status | **POLISHED** — concrete sim tools, tightened scope; v4b reframed variant created |

### Known Strengths

- Most distinctive proposal — "AI for Science & Engineering" is less crowded than Knowledge Grounding
- Strong advisor alignment — maps to construction.ai initiative
- VVUQ (Verification, Validation, and Uncertainty Quantification) gives scientific rigor
- Two concrete applications: construction material takeoff with CV, transportation digital twin
- Different reviewer pool from PA-AKG (different primary topic)

### Known Weaknesses

- Original framing too ambitious (3-4 generic domains)
- Needs reframing around 2 applications + VVUQ (per strategy-pivot.md)
- Simulation integration layer was hand-waved in earlier versions
- Feasibility concern: even 2 domains + VVUQ is ambitious for 1 year
- Abstract writing quality lags behind PA-AKG v2

### Remaining Work

- [x] Reframe around 2 concrete applications (construction CV + transportation digital twin) — done in v4b
- [x] Integrate VVUQ as the unifying validation backbone — done in v4b
- [x] Reduce scope to be clearly feasible in 1 year (2 primary + 1 extension domain)
- [x] Strengthen connection to advisor's construction.ai work
- [x] Polish writing quality — concrete sim tools, tightened prose
- [ ] Confirm reframing direction with advisor (v4 vs v4b) before submission

---

## Proposal 3: SVF — Structured Validation Framework

**Rank**: #3 (may be reserved for other venues)

| Field | Value |
|-------|-------|
| Primary Topic | Foundation Model/Agentic Evaluation |
| Secondary Topic | Responsible Generative AI |
| Abstract Version | v3 (abstract_v3.pdf) |
| Current Status | **POLISHED** — overclaims toned down, coordination developed, scope narrowed |

### Known Strengths

- Addresses growing need for agentic system evaluation
- Combines evaluation + responsible AI — unique angle
- Responsible AI is high priority for Amazon
- Could have broad impact if benchmark suite is adopted

### Known Weaknesses

- "Meta" nature — evaluates systems but doesn't build one (less exciting for funders)
- Overclaimed novelty — "first framework" claim is too strong given existing work
- Coordination reliability dimension underdeveloped
- Needs full benchmark suite — feasibility concern for 1 year
- Weaker Amazon-specific relevance compared to PA-AKG

### Remaining Work

- [x] Tone down "first framework" → "systematic evaluation framework addressing critical gaps"
- [x] Develop coordination reliability: fault injection, cascading error propagation, recovery latency
- [x] Narrow scope to 3 concrete task types (retrieval QA, agent workflows, coordination scenarios)
- [x] Strengthen Amazon angle: production agent platform reference added
- [x] Final language polish: "unlike post-hoc benchmarks" framing

---

## Reviewer Process (Mar 16)

Each abstract will be reviewed with the following evaluation criteria:

1. **Novelty**: Is the contribution clearly new and differentiated from SOA?
2. **Feasibility**: Can this be done in 1 year with the stated team?
3. **Amazon Relevance**: Does this align with Amazon's AI research interests?
4. **CFP Fit**: Does this clearly address the stated primary/secondary topics?
5. **Writing Quality**: Is the abstract clear, concise, and compelling?
6. **Impact**: What is the potential for meaningful research contribution?

### Review Output

For each proposal, the reviewer process should produce:

- Numerical scores (1-5) on each criterion
- Top 3 strengths
- Top 3 weaknesses or concerns
- Specific suggestions for improvement
- Go/no-go recommendation for submission

### Decision Framework

After reviews are complete:

- If all 3 are strong: submit PA-AKG (#1) + AKG-E (#2)
- If AKG-E reviews poorly after reframing: consider PA-AKG + SVF
- If only 1 is strong enough: submit just that one (quality over quantity)

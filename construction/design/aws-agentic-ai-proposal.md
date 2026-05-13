# Design: AWS Agentic AI Spring 2026 Proposal

**Date:** 2026-05-12 (drafted) · 2026-05-13 (submission)
**Author:** Feature Architect (AI-assisted)
**CFP:** AWS AI: Agentic AI Spring 2026 (Amazon Research Awards)
**Portal:** home.academic-research-portal.amazon.science/login
**Deadline:** May 13, 2026 at 11:59 PM PT

## Problem

Multi-agent LLM systems for software engineering have proliferated since 2024 (ToG-3, Youtu-GraphRAG, TeaRAG, AgenticSZZ, RepoUnderstander), but no existing system treats per-claim provenance as a typed, propagated, verifiable artifact across multi-agent message passing. The closest comparator (GraphTracer, Oct 2025) is diagnostic — failure attribution after the fact — not runtime-enforcing. The March 2026 SoK survey explicitly lists "oversight mechanisms for autonomous loops" as an open research gap. PA-AKG closes this gap by making provenance a first-class protocol primitive between agents.

## Goals

- Submit a 4-page proposal + 1-page budget + Brown PI CV to the AWS Agentic AI Spring 2026 portal by **May 13, 2026 at 11:59 PM PT**
- Primary topic: **Multi-agent systems and collaborations**. Secondary: **Data integration / hybrid retrieval (vector + lexical + graph + relational)**.
- Application domain: **Software engineering** via two case studies (AutoPyDep extension and cusati2026fose knowledge-accumulation application).
- Award range: ~$70K cash gift (no F&A) + ~$50K AWS credits ≈ $120K total.

## Non-Goals

- Re-litigating AKG-E content (different research thread; just submitted to Amazon-VT). Brown PI + Cusati student researcher; no Afsari on this proposal.
- Force-fitting Topic 1 (no-code/low-code) or Topic 4 (scientific discovery — overlaps with Amazon-VT submission).
- Production-grade Bedrock deployment as a Year-1 deliverable. Research-prototype quality only.
- Recruiting GRA #2 — single-student team (Cusati) per budget Shape α.

## Decisions Locked

| # | Decision | Source |
|---|----------|--------|
| Q1 | OSS = PA-AKG reference impl on Bedrock + provenance eval harness | Interview Q1 (2026-05-12) |
| Q2 | Case studies = AutoPyDep extension (Brown-led) + cusati2026fose application (Cusati-led) | Interview Q2 (2026-05-12) |
| Q3 | Budget = Shape α — Cusati only full-ride: $60K package + $5K travel + $5K equipment = $70K cash + $50K AWS credits | Interview Q3 (2026-05-12) |
| Q4 | Reuse = A + D — clone LaTeX scaffolding from `akg-e-full-proposal/`; lift §Problem + §Approach verbatim from `abstract_v2`; write fresh everything else | Interview Q4 (2026-05-13) |

## Design Approach

### Document structure (4 pages IEEE 2-column)

| Section | Content | Source | Length |
|---|---|---|---|
| §I Problem & Motivation | RAG context + reliability gap + provenance deficit | Verbatim from abstract_v2 ¶1–¶2 | ~1 col |
| §II Proposed Approach | PA-AKG framework: multi-agent supervisor + retrieval/curation/validation specialists + typed provenance routing. Bedrock multi-agent collaboration as deployment substrate. Explicit differentiation paragraph against ToG-3 / Youtu-GraphRAG / GraphTracer. | Adapted from abstract_v2 ¶3 (lift verbatim with §Approach opening rewritten to lead with multi-agent supervisor pattern) | ~1.5 col |
| §III Methodology | AWS hooks (Bedrock Agents multi-agent collaboration, KB hybrid search, Neptune Analytics graphs, reranking, action groups, optional SageMaker FT). Two case studies. Differentiation paragraph if not in §II. **AWS ML tools list** here. | New | ~1.5 col |
| §IV Evaluation | Provenance fidelity (claim→source traceability), retrieval accuracy, B0/B1/B2 baselines. Two case-study test surfaces: AutoPyDep dependency-resolution eval; cusati2026fose knowledge-accumulation eval. | New | ~1 col |
| §V Risks & Mitigation | Scoping (research prototype not production), single-student team, OSS quality | New | ~0.5 col |
| §VI Team, Timeline, OSS | Brown (PI) + Cusati (student researcher). Year-1 Gantt (Aug 2026 – Jul 2027). **OSS contribution list** here. | New | ~1 col |
| References | Lift abstract_v2 bib + add 6–8 new refs from related-work landscape (SoK 2603, ToG-3, Youtu-GraphRAG, GraphTracer, TeaRAG, AgenticSZZ) | Composite | ~1.5 col |

### Required CFP content checklist (must appear in proposal)

- [ ] **Differentiation from prior work** — explicit paragraph in §II or §III: against ToG-3 (multi-agent dual-evolving), Youtu-GraphRAG (unified agents), GraphTracer (diagnostic-only attribution), TeaRAG (efficiency-focused), AgenticSZZ (SE-specific temporal KG)
- [ ] **List of open-source tools to be contributed** — explicit list in §VI: PA-AKG reference impl (Apache 2 license on Bedrock) + provenance eval harness
- [ ] **List of AWS ML tools to be used** — explicit list in §III: Bedrock Agents (multi-agent collaboration), Bedrock KB (hybrid search), Bedrock KB (Neptune Analytics graphs), Bedrock reranking, Bedrock action groups, optional SageMaker fine-tuning

### Title

**"Multi-Agent Provenance-Aware Retrieval for Trustworthy Software Engineering AI"**

Working alternatives if PI prefers:
- "PA-AKG: A Multi-Agent Provenance-Aware Knowledge Graph System for Software Engineering"
- "Provenance-Aware Multi-Agent Knowledge Graphs for Trustworthy AI in Software Engineering"

### Author block

```latex
\title{Multi-Agent Provenance-Aware Retrieval for Trustworthy Software Engineering AI}
\author{
    \IEEEauthorblockN{Chris Brown (PI)}
    \IEEEauthorblockA{Code World No Blanket \\
                      Department of Computer Science \\
                      Virginia Tech}
    \and
    \IEEEauthorblockN{Jason Cusati (Student Researcher)}
    \IEEEauthorblockA{Code World No Blanket \\
                      Department of Computer Science \\
                      Virginia Tech}
}
```

### Budget (1 page, $70K cash gift, no F&A)

| Category | Amount | Notes |
|---|---|---|
| Cusati GRA — stipend (12 mo) | $30,000 | |
| Cusati GRA — tuition (in-state, 2 sem) | $24,000 | |
| Cusati GRA — fringe / benefits | $6,000 | |
| Conference travel | $5,000 | 1 conf (target: agentic-AI venue) + Amazon visit |
| Equipment | $5,000 | Workstation / GPU upgrade |
| **Total cash gift** | **$70,000** | |

**Plus separately budgeted AWS Promotional Credits ($50K):**

| Service | Allocation | Use |
|---|---|---|
| Bedrock Agents + Multi-Agent Collaboration | $20,000 | Agent runtime |
| Bedrock Knowledge Bases (hybrid search) | $5,000 | Retrieval over SE corpora |
| Neptune Analytics graphs (via Bedrock KB) | $10,000 | KG layer storage + queries |
| SageMaker fine-tuning | $10,000 | Provenance-routing model (stretch) |
| Misc Bedrock (reranking, multimodal, action groups) | $5,000 | Validation tool calls |
| **Total credits** | **$50,000** | |

## Acceptance Criteria

### AC-1: Proposal PDF builds clean
- **Given** `aws-agentic-ai-proposal/main.tex` and `references.bib`
- **When** running `make` in `aws-agentic-ai-proposal/`
- **Then** `main.pdf` is produced with no LaTeX errors, no overfull-hbox over 5pt, 4 pages of body content (refs may overflow)

### AC-2: Required-content checklist satisfied
- **Given** the rendered proposal PDF
- **When** I inspect §II/III for differentiation paragraph, §VI for OSS list, §III for AWS-tools list
- **Then** all three required CFP content elements are present and identifiable by section heading or labeled paragraph

### AC-3: Citations have no hallucinations
- **Given** the `references.bib` file
- **When** I cross-check each entry against the citation matrix and the related-work landscape
- **Then** every entry is real with correct DOI/arXiv ID/venue; preprints are marked; no fabricated authors or titles

### AC-4: Budget builds and totals match
- **Given** `aws-agentic-ai-proposal/budget.tex`
- **When** running `make budget`
- **Then** `budget.pdf` renders on 1 page with cash subtotal = $70,000 and AWS-credits subtotal = $50,000

### AC-5: PDFs published to docs
- **Given** the built PDFs
- **When** running `make publish`
- **Then** `docs/aws-agentic-ai-proposal.pdf` and `docs/aws-agentic-ai-proposal-budget.pdf` exist with current timestamps

### AC-6: Landing page reflects drafting completion
- **Given** the new landing page at `docs/aws-agentic-ai/index.html`
- **When** I inspect the timeline tracker
- **Then** the spec / LaTeX scaffolding / proposal body / budget / publish steps show "Done" status pills; only PI sign-off + portal submission remain "To do"

### AC-7: Memory-bank updated
- **Given** completion of all above
- **When** I read `memory-bank/progress.md` and `memory-bank/activeContext.md`
- **Then** Phase 6 entries reflect drafting completion and call out blocking items for the user (Brown CV, PI sign-off, portal upload)

## Technical Notes

- **LaTeX scaffolding source**: `akg-e-full-proposal/` (clone Makefile, preamble; strip AKG-E content)
- **Verbatim lift source**: `abstract_v2/main.tex` (§Problem ¶1–¶2; §Approach ¶3 with opening rewritten to lead with multi-agent)
- **Citation matrix update**: add `aws-agentic` column to `construction/requirements/citation-matrix.md` and register 6–8 new refs (SoK 2603, ToG-3, Youtu-GraphRAG, GraphTracer, TeaRAG, AgenticSZZ, BedrockAgents docs)
- **Page-limit budget**: 4 pages IEEE 2-column ≈ 8 columns total. Estimated allocation in design table above.

## Dependencies

- `akg-e-full-proposal/main.tex` (scaffolding template)
- `abstract_v2/main.tex` (verbatim source)
- `abstract_v2/references.bib` (citation seed)
- `pdflatex` + `bibtex` available locally (verified — was used for Amazon-VT proposal yesterday)

## Open Questions (deferred to implementation)

- **Final title** — three candidates listed; default to first unless PI prefers otherwise
- **AWS credits allocation precision** — credits paragraph in proposal will summarize in prose; budget table provides specifics
- **Differentiation paragraph length** — fits in §II conclusion OR opens §III; pick at draft time based on column flow
- **Whether to include a TikZ figure** — abstract_v2 had a PNG architecture diagram; for the 4-page proposal, consider a TikZ figure or omit (use prose). Stretch; not on critical path.

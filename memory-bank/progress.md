# Progress

## Completed

### Phase 0: Project Initialization (2026-03-05)
- [x] Created project directory structure
- [x] Set up memory-bank documentation system
- [x] Created construction/ design-first workflow
- [x] Configured .claude/agents (proposal-agent, memory-agent)
- [x] Created CLAUDE.md with CFP details and deadlines
- [x] Analyzed CFP document and captured requirements

### Phase 1: Research Topic Analysis & Selection (2026-03-07)
- [x] Initial analysis of CFP alignment (3 candidates ranked)
- [x] Design document created: `construction/design/initial-topic-analysis.md`
- [x] GitHub repo and Pages site created
- [x] Deeper analysis (literature review, novelty gap, feasibility)
- [x] Final topic selection: **PA-AKG** (Provenance-Aware Agentic Knowledge Graph Systems)
- [x] Primary topic: Knowledge Grounding, Secondary: Agentic AI

### Phase 2a: Abstract v1 — PA-AKG (2026-03-08)
- [x] 1-page abstract draft (problem, approach, contributions, impact)
- [x] Key references identified
- [x] Architecture diagram created
- [x] LaTeX build pipeline with CI
- [x] Published on GitHub Pages dashboard

### Phase 2b: Deep Research & Abstract v2 — PA-AKG (2026-03-09 – 2026-03-10)
- [x] Deep research report on RAG & Graph Retrieval SOA (2023-2026)
- [x] Identified novelty gaps: provenance-aware KG grounding + validation loops
- [x] Curated 2024-2026 citations (GraphRAG, CRAG, AWS Bedrock, OpenTelemetry)
- [x] Abstract v2 with SOA-grounded framing
- [x] Deep research report published as styled HTML on dashboard
- [x] CFP instructions published on dashboard

### Phase 2c: Multi-Proposal Development (2026-03-11 – 2026-03-14)
- [x] Abstract v3: **SVF** (Structured Validation Framework) — Agentic Evaluation + Responsible AI
- [x] Abstract v4: **AKG-E** (Agentic Knowledge Graphs for Engineering) — AI for Science & Engineering + Agentic AI
- [x] CI pipeline fix for multi-abstract builds
- [x] Deep research on all 3 proposal directions
- [x] Submission strategy analysis — which proposals to submit, topic overlap concerns
- [x] Devil's advocate analysis — honest strengths/weaknesses of each proposal
- [x] Strategy pivot — PA-AKG ranked #1, AKG-E #2, SVF #3
- [x] Website restructure — dashboard with ranked proposal cards, dedicated proposal pages
- [x] New pages: proposal-pakg.html, proposal-akge.html, proposal-svf.html
- [x] New pages: devils-advocate.html, submission-strategy.html, topic-analysis.html
- [x] New pages: downloads.html, pa-akg-archive.html, deep-research-report.html
- [x] Navigation bar added across all pages
- [x] Strategy notes documented (docs/strategy-notes.md)

### Phase 2d: Abstract Polish (2026-03-14)

- [x] Polish PA-AKG (v2) — sharpened novelty (unified substrate vs isolated), added Self-RAG citation, concrete eval tasks
- [x] Polish SVF (v3) — toned down overclaims, developed coordination reliability, narrowed scope
- [x] Polish AKG-E (v4) — concrete simulation tools (OpenSeesPy, SUMO), tightened prose, narrowed to 2+1 domains
- [x] Create AKG-E (v4b) — new variant: reframed with 2 focused applications (construction + transportation) + VVUQ backbone

### Phase 2e (partial): v4c Creation (2026-03-15)

- [x] Create AKG-E (v4c) — construction-only variant: drops transportation domain, tightens focus to construction material takeoff with VVUQ backbone (based on v4b)

### Phase 2e (continued): Advisor Edits, Deep Research Synthesis & Site Updates (2026-03-16)

- [x] Apply advisor edits to PA-AKG (v2): motivating example, Amazon KG context, CFP alignment sentence, evaluation rationale, title fix — PR #12 merged
- [x] Create AKG-E v4c with VVUQ backbone, BIM/IFC, FEA, falsifiable hypothesis, Bedrock hook — PR #6 merged
- [x] Create SVF v5: new synthesis from deep-research-svf.md with RAGAS/ARES/TruLens baselines and falsifiable hypotheses — PR #5 merged
- [x] Deploy SVF deep research HTML page (docs/svf-deep-research.html)
- [x] Deploy AKG-E deep research HTML page (docs/deep-research-akge.html)
- [x] Add citation tooltips to all 3 proposal pages
- [x] Add keywords section to AKG-E proposal page
- [x] Link all AKG-E variants (v4, v4b, v4c) on downloads page and proposal-akge.html

### Phase 2e (final): Citation Fixes, v4e Creation & Submission Prep (2026-03-17)

- [x] Fix abstract_v2 citation issues: Yan2024CRAG and Yu2024COSMO corrected
- [x] Add provenance definition sentence to abstract_v2
- [x] Add authors to abstract_v2: Jason Cusati + Chris Brown
- [x] Add authors to all AKG-E variants (v3/v4/v4b/v4c/v4d/v4e): Jason Cusati + Kereshmeh Afsari
- [x] Add authors to SVF (v3/v5): Jason Cusati + Chris Brown
- [x] Create AKG-E v4d: domain-agnostic synthesis + VVUQ + engineering-agent citations (Park2026MCPSIM, LLMAgentsFEM2025, Soman2025ConstructionDT). Title: "Agentic Knowledge Graphs for AI-Accelerated Engineering with Generalizable Simulation-in-the-Loop Validation"
- [x] Create AKG-E v4e (PRIMARY): full professor structure — application challenge (VVUQ gap), RQ1/RQ2 with evaluation criteria, intellectual merit, contributions, practice impact, extensible domain design (construction primary + transportation + energy), Amazon Bedrock fit. Hypothesis reframed as evaluation design target. Title: "Agentic Knowledge Graphs for AI-Accelerated Engineering with Simulation-Grounded Validation"
- [x] Update citation matrix: v4d and v4e columns added; 7 new citation keys registered (Eastman2011BIM, Logg2012FEniCS, Yu2024COSMO, LLMAgentsFEM2025, Park2026MCPSIM, Soman2025ConstructionDT); matrix covers v2–v4e
- [x] Update docs/proposal-akge.html with full v4e professor structure (Problem Statement, Application Challenge, RQ1/RQ2, Three Layers, Construction + Transportation cards, Expandability, Intellectual Merit, Practice Impact, Amazon Fit, Expected Output, updated citations table)
- [x] Update docs/downloads.html: v4e PDF entry added at top
- [x] Merge all changes to main — no open PRs

### Phase 4: Fellowship Application (2026-04-27) — CRITICAL DEADLINE TODAY

- [x] Spec written: `construction/design/fellowship-application-akg-e.md` — completed Apr 27
- [x] Build fellowship LaTeX `abstract_v4e_fellowship/main.tex` — hybrid of AKG-E v4e research vision + net-new student-centric sections (Vision, Training Plan, Qualifications) — completed Apr 27
- [x] Copy `references.bib` from v4e (verbatim) and add `BrownCusati2025SEBeliefs` (applicant's own arXiv paper) — completed Apr 27
- [x] Build fellowship PDF locally (2 pages, body + references) — completed Apr 27
- [x] Publish PDF to `docs/abstract_v4e_fellowship.pdf` — completed Apr 27
- [x] Create internal-use page `docs/fellowship.html` (matches `proposal-akge.html` style) — completed Apr 27
- [x] Update `docs/downloads.html` with new "Fellowship Application" section — completed Apr 27
- [x] Update `docs/index.html` nav-bar with Fellowship link — completed Apr 27
- [x] Update `construction/requirements/citation-matrix.md` with fellowship column — completed Apr 27
- [x] Update `construction/requirements/submission-checklist.md` with fellowship section — completed Apr 27
- [x] Verify v4e directory untouched (`git status abstract_v4e/` clean) — completed Apr 27

### Phase 5: AKG-E Full Proposal Build (2026-04-10 — 2026-05-11)

- [x] AKG-E v4e abstract invited to full proposal (Burrell email, 2026-04-10) — confirmed Apr 10
- [x] Spec authored: `construction/design/full-proposal-akg-e.md` — completed Apr 28; revised May 11 with team / scope / eval / deadline corrections
- [x] LaTeX source authored at `akg-e-full-proposal/main.tex` (3-page body + refs, six sections, IEEE 2-column) — completed May 11
- [x] Budget LaTeX at `akg-e-full-proposal/budget.tex` (1 page DRAFT, $100K total, gift research no F&A) — completed May 11
- [x] Inline Gantt chart added (Table I) — workstreams × Aug 2026 – Jul 2027 — completed May 11
- [x] Authorship resolved: Afsari (PI, ARCADE Lab) + Brown (Co-PI, Code World No Blanket lab) + Cusati (Student Researcher) — completed May 11
- [x] §II / §3.2 contribution framing softened from prescriptive algorithm to coupling interface — completed May 11
- [x] Eval framing: three-tier correctness/calibration/efficiency; abstract's >50% target preserved as correctness floor; B0/B1/B2 ablation — completed May 11
- [x] Scope: 2-domain funded (construction + transportation) + energy as designed extension — completed May 11
- [x] Acronyms audit: every domain-specific term defined at first body-text use — completed May 11
- [x] Brown added 6 references to bib (Brown-Cusati ESEM 2025, Cusati-Brown ICSE-FoSE 2026, 4 Code-World-No-Blanket-lab orphans) in commit a4af8b0 — completed May 11
- [x] Citation audit: no hallucinations; matrix updated with `full` column; brown2025exploring + cusati2026fose registered — completed May 11
- [x] PDFs published to docs/, dedicated full-proposal page at `docs/akg-e-full-proposal.html` with built-in what's-left-to-do tracker, nav added across pages — completed May 11

### Phase 6: AWS Agentic AI CFP — Kickoff & Deep Research (2026-05-12)

A second Amazon proposal effort under the AWS AI: Agentic AI Spring 2026 ARA call. Separate from Amazon-VT (different program, different team). PA-AKG reframed for this CFP. Deadline May 13, 2026 at 11:59 PM PT.

- [x] CFP fetched and analyzed: AWS Agentic AI Spring 2026 (ARA program); 4-page limit + appendices; ~$70K cash + ~$50K AWS credits; gift research (no F&A); decisions Aug 2026 — completed May 12
- [x] Topic-by-topic fit analysis against PA-AKG / AKG-E / SVF / Brown-lab SE thread — completed May 12
- [x] Recommended shape locked: **Shape A** — PA-AKG → Topic 3 (multi-agent) primary + hybrid-retrieval welcome topic secondary + SE as application domain — completed May 12
- [x] Team locked: Brown (PI) + Cusati (student researcher) — Code World No Blanket lab, CS, VT — completed May 12
- [x] Deep research: ARA program rules (eligibility, gift treatment, IP, one-proposal-per-PI-per-call, no explicit ARA↔Amazon-VT restriction) — completed May 12
- [x] Deep research: Bedrock stack mapping (Agents multi-agent collaboration, KB hybrid search, Neptune Analytics graphs, reranking, structured-data NL→SQL, action groups) — completed May 12
- [x] Deep research: related-work landscape 2024–2026 (SoK Mar 2026 + 10 related agentic-RAG / GraphRAG papers; novelty wedge = typed provenance propagation across agents) — completed May 12
- [x] New GitHub Pages site published at `docs/aws-agentic-ai/index.html` with AWS squid-ink + teal palette, hamburger menu for cross-site nav, embedded timeline tracker — completed May 12
- [x] Cross-site hamburger added to `docs/index.html` Amazon-VT header (bi-directional navigation between the two proposal sites) — completed May 12

## In Progress

### Phase 6: AWS Agentic AI CFP — Spec, Draft, Submit (2026-05-12 → 2026-05-13)

- [ ] Decide open-source contribution commitment (PA-AKG impl / eval harness / Brown-lab tool extension)
- [ ] Author spec at `construction/design/aws-agentic-ai-proposal.md`
- [ ] Draft 4-page LaTeX proposal reframing PA-AKG abstract_v2 for Topic 3 + hybrid retrieval
- [ ] Verify proposal against CFP required-content checklist (differentiation from prior, OSS list, AWS ML tools list)
- [ ] Internal review and revisions
- [ ] Brown (PI) sign-off on narrative + budget + OSS commitment
- [ ] Portal submission by **May 13, 2026 at 11:59 PM PT**

### Phase 5 carryover

- [ ] User to confirm whether Amazon-VT full-proposal portal upload was completed on May 11 (materials were staged and PRs merged; submission action is user-side)

## Upcoming

- [ ] Phase 7: AWS Agentic AI award decisions (August 2026)
- [ ] Phase 8: Amazon-VT acceptance notification (June 30, 2026)
- [ ] Phase 9: Project execution if funded (Aug 2026 – Jul 2027)

## Key Milestones

| Milestone | Target Date | Status |
|-----------|------------|--------|
| Project setup | 2026-03-05 | Done |
| Research topic selected | 2026-03-07 | Done |
| Abstract v1 (PA-AKG) complete | 2026-03-08 | Done |
| Deep research & SOA review | 2026-03-10 | Done |
| Abstract v2 (PA-AKG) complete | 2026-03-10 | Done |
| Abstract v3 (SVF) complete | 2026-03-11 | Done |
| Abstract v4 (AKG-E) complete | 2026-03-11 | Done |
| Devil's advocate analysis | 2026-03-14 | Done |
| Strategy pivot & website restructure | 2026-03-14 | Done |
| Polish all 3 abstracts | 2026-03-14 | Done |
| AKG-E v4b variant created | 2026-03-14 | Done |
| AKG-E v4c variant created (construction-only) | 2026-03-15 | Done |
| Advisor edits applied to PA-AKG v2 (PR #12) | 2026-03-16 | Done |
| SVF v5 synthesis from deep research (PR #5) | 2026-03-16 | Done |
| Deep research HTML pages deployed (SVF + AKG-E) | 2026-03-16 | Done |
| Citation tooltips + keywords added to site | 2026-03-16 | Done |
| abstract_v2 citation fixes + authors added | 2026-03-17 | Done |
| AKG-E v4d created (domain-agnostic + VVUQ) | 2026-03-17 | Done |
| AKG-E v4e created (professor structure, PRIMARY) | 2026-03-17 | Done |
| Citation matrix updated (v4d/v4e; 7 new keys) | 2026-03-17 | Done |
| proposal-akge.html + downloads.html updated (v4e) | 2026-03-17 | Done |
| All changes merged to main (no open PRs) | 2026-03-17 | Done |
| Abstract(s) submitted | 2026-03-17 | Done |
| Full proposal invitation | 2026-04-06 | Pending |
| Fellowship application LaTeX + page built | 2026-04-27 | Done |
| **Fellowship application submitted — CRITICAL DEADLINE** | **2026-04-27** | **Pending** |
| Full proposal submitted | 2026-04-27 | Pending |
| Acceptance notification | 2026-06-30 | Pending |

## Known Issues

_None._

---

**Note:** Update after every task completion.

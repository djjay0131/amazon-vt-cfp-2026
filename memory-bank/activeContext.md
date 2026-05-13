# Active Context

_Last updated: 2026-05-13_

## Current Phase

**Phase 6: AWS Agentic AI CFP — Spec, Draft, Submit (deadline May 13, 2026 at 11:59 PM PT)**

A second Amazon proposal effort under the AWS AI: Agentic AI Spring 2026 call (Amazon Research Awards program). Separate from the just-submitted Amazon-VT effort — different program, different team. PA-AKG (provenance-aware agentic knowledge graph) reframed for this CFP's Topic 3 (multi-agent systems) primary + hybrid-retrieval welcome topic secondary, with software engineering as the application domain.

**Three deliverables needed for portal upload by May 13 11:59 PM PT:**

1. **Proposal** — 4 pages + appendices (ARA template `agentic-ai-spring-2026`). Required content sections: (a) differentiation from prior work, (b) list of open-source tools to be contributed, (c) list of AWS ML tools to be used.
2. **Budget** — gift research, no F&A. ARA budget guidance: 1–2 grad students + travel + equipment for 1 year. Award range: ~$70K cash + ~$50K AWS credits.
3. **CV** — Brown (PI). Cusati does not need a CV for this CFP (student researcher, not PI/Co-PI).

**Team (final):** Brown (PI, Code World No Blanket lab, CS, VT) + Cusati (student researcher).

Phase 5 (Amazon-VT AKG-E full proposal) closed yesterday. Portal-submission action (upload of the three documents to the Amazon-VT portal by 11:59 PM PT on May 11) is user-side; PR #32 merging memory-bank updates was the last code action before this Phase 6 pivot.

## Current Workflow

**~~Polish All 3~~ → ~~Run Reviewer Process~~ → ~~Incorporate Feedback~~ → ~~Finalize Citations~~ → ~~Select AKG-E Variant~~ → ~~Abstracts Submitted (Mar 17)~~ → ~~Fellowship Submitted (Apr 27)~~ → ~~Full Proposal Drafted~~ → ~~PI/Co-PI Sign-off~~ → ~~Amazon-VT Portal Upload (May 11)~~ → ~~AWS Agentic AI CFP Analyzed~~ → ~~Site Published~~ → Spec & Draft AWS Agentic AI Proposal → Brown Sign-off → Portal Upload (May 13 11:59 PM PT)**

### Key Phase 6 decisions baked in

- **Recommended shape locked**: PA-AKG reframed for Topic 3 (multi-agent) primary + Welcome topic (data integration / hybrid retrieval: vector + lexical + graph + relational) secondary. Software engineering as application domain (Brown-lab tools as case studies).
- **Team**: Brown PI + Cusati student researcher. No Afsari on this proposal (different program, different research thread).
- **Why not Shape B (AKG-E for Topic 4)**: Same engineering-AKG material was submitted to Amazon-VT yesterday targeting "AI Accelerated Science & Engineering Innovation" — too close to ARA Topic 4 (scientific discovery). Reviewer-overlap optics is a real risk. Different research thread is safer.
- **Why not Shape C (fresh SE-agents proposal)**: No PA-AKG carry-over. Fresh writing in a 24-hour window is high-risk.
- **AWS hooks** (verified against Bedrock docs May 2026): Bedrock Agents multi-agent collaboration, Bedrock KB hybrid search, Bedrock KB Neptune Analytics graphs, Bedrock KB structured-data NL→SQL, Bedrock reranking, Action Groups. Optional: SageMaker fine-tuning of provenance-routing model as Year-1 stretch.
- **Novelty wedge** (verified against Mar 2026 SoK and 10 related 2024–2026 papers): typed propagation of per-claim provenance across multi-agent message passing. Closest comparator (GraphTracer, Oct 2025) is diagnostic, not runtime-enforcing.
- **OSS commitment** (open decision): PA-AKG reference impl, provenance eval harness, or Brown-lab tool extension. Recommendation pending: impl + lightweight harness.
- **Site identity**: AWS squid-ink (#232F3E) + teal (#00C7B7) palette, distinct from VT maroon + Amazon orange. Hamburger menu in header replaces full nav-bar. Cross-site hamburger added to Amazon-VT `index.html` for bi-directional nav.

## ARA program rules verified

- Eligibility: full-time faculty, accredited institution. Brown qualifies.
- One proposal per PI per call (Brown wasn't PI on Amazon-VT → no conflict).
- Awards = one-time unrestricted gift to institution. **Cannot be used for indirect expenses (F&A)** — same gift treatment as Amazon-VT.
- IP: Amazon reserves right to implement similar work. No exclusivity.
- ARA program rules do **not** explicitly restrict ARA↔Amazon-VT cross-submission. Reviewer-optics is the real concern; mitigated here by using different research thread + different team.

## Current Focus

- [x] CFP fetched, analyzed; recommended shape locked — completed May 12
- [x] Deep research published to GitHub Pages: `docs/aws-agentic-ai/index.html` — completed May 12
- [x] Cross-site hamburger navigation between Amazon-VT and AWS Agentic AI sites — completed May 12
- [x] All 4 blocking decisions locked (OSS = D, case studies = D, budget = α, reuse = A+D) — completed May 13
- [x] Spec authored at `construction/design/aws-agentic-ai-proposal.md` — completed May 13
- [x] LaTeX scaffolding cloned into `aws-agentic-ai-proposal/` — completed May 13
- [x] 4-page proposal drafted; §Problem + §Approach lifted from `abstract_v2`; §Methodology, §Eval, §Risks, §Team written fresh — completed May 13
- [x] 1-page budget drafted (Shape α: $70K cash + $50K AWS credits) — completed May 13
- [x] PDFs built (`main.pdf` 4 pages, `budget.pdf` 1 page) and published to `docs/` — completed May 13
- [x] Landing page updated with PDF download buttons + timeline pills flipped to Done for drafting — completed May 13
- [ ] **[CRITICAL]** Internal review against CFP required-content checklist (differentiation / OSS / AWS tools)
- [ ] **[CRITICAL]** Citation audit against citation matrix
- [ ] **[CRITICAL]** Brown (PI) sign-off on narrative + budget + OSS commitment
- [ ] **[CRITICAL]** Brown's PI CV portal-ready
- [ ] **[CRITICAL — DEADLINE TODAY]** Portal submission by May 13, 2026 at 11:59 PM PT

## Proposal Track Record

| Rank | Proposal | Program | CFP Topics | Status |
|---|---|---|---|---|
| #1 | **PA-AKG → AWS Agentic AI** (new) | ARA Spring 2026 | Multi-agent + Hybrid Retrieval | Phase 6 in progress; deadline May 13 |
| #2 | **AKG-E (v4e)** full proposal | Amazon-VT 2026 | AI for Science & Engineering + Agentic AI | Phase 5 closed May 11 (user portal upload was the final action) |
| #3 | **PA-AKG (v2)** abstract | Amazon-VT 2026 | Knowledge Grounding + Agentic AI | Submitted Mar 17 |
| #4 | **AKG-E (v4e)** abstract | Amazon-VT 2026 | AI for Science & Engineering + Agentic AI | Submitted Mar 17 |
| #5 | **AKG-E (v4e)** fellowship | Amazon-VT 2026 | Doctoral fellowship | Submitted Apr 27 |
| #6 | **SVF (v5)** abstract | Amazon-VT 2026 | Agentic Evaluation + Responsible AI | Submission-ready; reserved for other venues |

## Research Directions

### PA-AKG — Provenance-Aware Agentic Knowledge Graph Systems (active for ARA Phase 6)
- ARA Primary Topic: Multi-agent systems and collaborations
- ARA Secondary Topic: Welcome — data integration / hybrid retrieval
- Application domain: software engineering (Brown-lab tools as case studies)
- Novelty wedge: typed propagation of per-claim provenance across multi-agent message passing
- AWS hooks: Bedrock Agents (multi-agent collaboration with supervisor), Bedrock KB (hybrid search + Neptune Analytics graphs), reranking, action groups

### AKG-E — Agentic Knowledge Graphs for Engineering (Phase 5 closed)
- Submitted to Amazon-VT 2026 targeting AI Accelerated Science & Engineering Innovation
- 3-page proposal + 1-page budget + Afsari CV submitted to portal May 11
- Decision expected June 30, 2026

### SVF — Structured Validation Framework (reserved)
- Submission-ready abstract retained for future venues

## What's Working

- Two parallel Amazon proposal sites live and cross-linked via hamburger
- AWS Agentic AI CFP analysis complete with deep research grounding
- Bedrock stack maps 1:1 to PA-AKG architecture (no force-fitting)
- Novelty wedge verified against current literature (March 2026 SoK + 10 recent papers)
- Memory-bank and auto-memory updated; PR ready for push

## What's Next

- Spec authoring for the AWS Agentic AI proposal
- LaTeX draft reframing `abstract_v2` (PA-AKG) to 4 pages with multi-agent emphasis
- Required-content checklist verification (CFP §required content)
- Brown sign-off
- Portal upload by May 13 11:59 PM PT

## Active Decisions

- **Decided**: Shape A locked (PA-AKG → Topic 3 + hybrid retrieval welcome, SE as application domain)
- **Decided**: Brown PI + Cusati student researcher (no Afsari on this proposal)
- **Decided**: AWS site identity (squid-ink + teal palette, hamburger nav)
- **Open**: OSS contribution commitment — leaning toward PA-AKG reference impl + lightweight eval harness
- **Open**: Budget allocation between cash gift and AWS credits utilization
- **Open**: Final proposal title

## Blockers

- AWS Agentic AI portal submission must be completed by **May 13, 2026 at 11:59 PM PT** (deadline tomorrow)
- Brown's PI CV must be portal-ready
- PI sign-off on the OSS commitment and budget

---

**Note:** Update every session with current status.

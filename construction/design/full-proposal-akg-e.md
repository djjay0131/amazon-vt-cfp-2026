# Feature: AKG-E Full Proposal (Amazon-VT 2026-2027)

**Status:** SPECIFIED (revised 2026-05-11)
**Date:** 2026-04-28; revised 2026-05-11
**Author:** Feature Architect (AI-assisted)
**PI:** Kereshmeh Afsari (Associate Professor, ARCADE Lab, Myers-Lawson School of Construction)
**Co-PI / Student Researcher:** Jason Cusati
**Lab:** ARCADE Lab, Virginia Tech
**Submission deadline:** **May 13, 2026** (extended from May 5; ~2 days from this revision)

## Revision Notes (2026-05-11)

Updates from the May 11 working session:

- **Deadline extended**: May 5 → May 13 (+8 days). Submission window is now ~2 days.
- **Execution timeline rescoped**: from a 12-month plan to **3-month aggressive build** inside the 1-year funded window. Months 1–3 are the active build; months 4–12 are dissemination, robustness experiments, scaling, and publications.
- **Personnel**: **2 GRAs full-time** (not 1) + AI-assisted development (Claude) as an explicit methodology contributor.
- **Evaluation framing — three-tier metrics with correctness as the floor**:
  1. **Correctness (non-negotiable floor)**: constraint-violation rate vs codified standards (AWC-NDS / HCM2022 / NERC-TPL). Must approach zero on the benchmark; must beat baselines statistically. Agents that are fast and wrong are unfundable in safety-critical engineering.
  2. **Calibration**: UQ coverage probability — does the 95% CI actually contain the ground truth 95% of the time? Validated against Sandia experimental data + FEA reference designs.
  3. **Efficiency (headline contribution)**: time-to-validated-decision vs the status-quo manufacturer-cycle baseline (weeks-to-months for construction VVUQ done by manufacturers). AKG-E target: agent-loop time (minutes-to-hours) at codified-standard correctness with calibrated UQ.
- **Baselines named precisely** (three-tier ablation): **B0** Claude alone · **B1** Claude + graph-RAG over curated KG · **B2** Claude + graph-RAG + agentic VVUQ loop (full AKG-E).
- **Three domains confirmed**: Construction (primary; LVL VVUQ pipeline as anchor) + Transportation (existing digital-twin proposal as anchor) + **Energy via Sandia partnership** (PDE solvers + experimental data).
- **Net-new contribution clarified**: the agentic **propose → VVUQ → feedback** loop is the novelty. The VVUQ math (Euler-Bernoulli + Monte Carlo) and the KG+multi-agent skeleton already exist in `~/code/construction-ai/` (`construction/design/vvuq-integration-plan.md`) and the `construction-ai-proposal` LaTeX. AKG-E generalizes them into the iterative agentic validation loop and adds the calibrated-UQ + domain-swap dimensions.
- **Reviewer feedback never materialized** as of 2026-05-11; PI followed up with Burrell — proceed without it.

## Problem

The AKG-E abstract (`abstract_v4e/`) was invited to submit a full proposal to the Amazon-VT 2026-2027 CFP. Per the official Amazon invitation (deadline extended to **May 13, 2026**), the full submission must be uploaded to the Amazon research portal and consists of three documents: (i) a 3-page-max proposal plus references, (ii) a 1-page-max budget, and (iii) a CV. The 1-page v4e abstract is the basis but must be expanded ~3× into a full proposal with detailed methodology, evaluation plan, timeline, team capabilities, and intellectual-merit / Amazon-fit framing. Amazon promised to connect a science reviewer ahead of the deadline; as of 2026-05-11 that has not happened — proceed without reviewer feedback while keeping the draft revision-ready.

## Goals

- Produce a 3-page full proposal LaTeX document at `abstract_v4e_full/` (mirroring `abstract_v4e_fellowship/` directory convention) with PI=Afsari, co-PI=Cusati, framed for the ARCADE Lab
- Reuse v4e research vision, three-layer architecture, TikZ figure, RQ1/RQ2, and bibliography — no new bibliography entries unless required by reviewer feedback
- Expand into 6 selectively-chosen sections: Problem & Motivation, Proposed Approach, Research Plan (RQs / Methodology / Evaluation), Timeline & Deliverables, Team & Capabilities, Intellectual Merit & Amazon Fit
- Produce a 1-page draft budget with fellowship-style line items (GRA stipend + tuition, faculty summer salary, materials, travel, indirect costs) and a **prominent LLM-token line item** with rationale
- Stage CV PDF (rebuilt from `~/code/cv/`) for upload alongside proposal and budget
- Build the proposal PDF via the existing per-directory Makefile pattern; publish to `docs/abstract_v4e_full.pdf`
- Publish a new internal-archive page `docs/proposal-akge-full.html` linking the proposal PDF and budget
- Update `docs/downloads.html` and `docs/index.html` nav with the full proposal
- Update `construction/requirements/citation-matrix.md` with a `full` column
- Update `construction/requirements/submission-checklist.md` with full-proposal section (3-document upload tracking, May 5 deadline, reviewer-feedback workflow)
- Update `memory-bank/activeContext.md` and `progress.md` to reflect the full-proposal workstream and that PA-AKG was not invited
- Track reviewer-feedback dependency: keep the draft revision-ready so that any feedback received before May 5 can be incorporated

## Non-Goals

- Performing the portal submission itself (PI/co-PI uploads after artifacts are staged)
- Setting actual budget dollar amounts as binding (numbers are draft placeholders; PI and ARCADE/VT lab admin own final figures and indirect-cost rates)
- Modifying the `abstract_v4e/` project abstract (frozen — already submitted and accepted)
- Modifying `abstract_v4e_fellowship/` (already submitted to fellowship workstream — independent)
- Writing or pursuing a PA-AKG full proposal (PA-AKG was not invited; only AKG-E proceeds)
- Adding new citations beyond v4e bibliography (kept clean unless reviewer feedback specifically demands one — additions tracked through the citation matrix)
- Format compliance against an unreleased Amazon format spec (the invitation states "no required format" for proposal/budget; we follow IEEE 2-column convention used elsewhere in the repo)

## User Stories

- As **Dr. Afsari (PI)**, I want a 3-page proposal that articulates AKG-E's full research plan in ARCADE Lab terms, so that I can submit it to Amazon without rewriting from scratch
- As **Jason Cusati (co-PI)**, I want the proposal to surface my prior work (agentic-KG, VTTI VTSI, VVUQ coursework) as the substrate the project is built on, so that the team's capability is concrete
- As an **Amazon reviewer (matched to this proposal)**, I want a clear statement of methodology, evaluation, and Amazon Bedrock fit, so that I can give targeted feedback before May 5
- As **future-me (post-submission)**, I want the docs site, citation matrix, and memory-bank updated, so that the next session can pick up state without re-reading commit logs

## Design Approach

### Section structure (compressed expansion from v4e)

The 1-page abstract becomes a 3-page proposal via these six sections (target word budgets):

| Section | Source | Words |
|---|---|---|
| 1. Problem Statement and Motivation | REUSED v4e ¶1 + expansion | ~250 |
| 2. Proposed Approach: AKG-E Framework | REUSED v4e ¶2 + figure | ~350 |
| 3. Research Plan (3.1 RQs · 3.2 Methodology · 3.3 Evaluation) | RQs reused; methodology + evaluation are NEW substantive content (see Section 3 content mandate below) | ~800 |
| 4. Timeline, Deliverables, and Risks | NEW (12-month plan, quarterly milestones, risks/mitigation) | ~250 |
| 5. Team and Capabilities | NEW (Afsari + Cusati + ARCADE infrastructure) | ~250 |
| 6. Intellectual Merit and Amazon Fit | REUSED + reframed from v4e closing | ~150 |
| **Total** | | **~2050 words ≈ 3 pages IEEE 2-column** |

### Section 3 content mandate

The Research Plan section (3.2 Methodology and 3.3 Evaluation Plan) is the principal expansion vs. the abstract. To prevent abstract-restatement padding, this section MUST contain the following concrete content — each item is a hard requirement, not a suggestion:

**3.2 Methodology — required content:**
- Agent ↔ VVUQ gate interaction protocol (call-and-response loop: agent emits artifact → gate runs verification checks → returns pass/fail with UQ bounds → agent refines)
- Specific verification checks performed by the gate (governing-equation residuals; code-compliance lookups against the ontology; regulatory-constraint satisfiability)
- Uncertainty propagation strategy through the agent pipeline (Monte Carlo over which inputs/parameters? simulator inputs vs. agent sampling temperature vs. both)
- Construction-pilot algorithmic specifics: BIM/IFC parser, FEA tool-call interface surface, the refinement step that closes the loop

**3.3 Evaluation Plan — required content:**

Three-tier metric framework. Correctness is the non-negotiable floor; calibration proves the UQ is trustworthy; efficiency is the headline contribution given the first two pass.

1. **Correctness (must-pass floor)**: constraint-violation rate vs codified standards — AWC-NDS / IBC2021 (construction); HCM2022 LOS thresholds (transportation); NERC-TPL contingency criteria (energy). Target: approaches zero on benchmark; statistically lower than all baselines.
2. **Calibration**: UQ coverage probability — does the 95% CI from Monte Carlo propagation actually contain the simulator/experimental ground truth 95% of the time? Validated against Sandia experimental data (energy) and FEA reference designs (construction).
3. **Efficiency (headline)**: wall-clock time-to-validated-decision per task vs the status-quo manufacturer-cycle baseline (weeks-to-months for construction VVUQ). AKG-E target: minutes-to-hours per task at codified-standard correctness with calibrated UQ.

**Named baselines** (three-tier ablation):
- **B0**: Claude alone (LLM-only — no retrieval, no validation loop)
- **B1**: Claude + graph-RAG over curated KG (retrieval without the agentic VVUQ loop)
- **B2**: Claude + graph-RAG + agentic VVUQ loop (full AKG-E — this is the contribution)

**Benchmark suite** (tasks span all three domains):
- Construction: header sizing + material takeoff with code-compliance checks. Ground truth: LVL VVUQ pipeline outputs + AWC-NDS reference designs.
- Transportation: signal timing / digital-twin scenarios from the existing transportation proposal. Ground truth: microsimulation outcomes + HCM LOS targets.
- Energy: contingency-analysis tasks on Sandia-provided grid topologies. Ground truth: DOE-lab PDE solver outputs + Sandia experimental measurements.

**Statistical analysis plan**: n=5 seeds minimum per (domain × baseline tier) cell; 95% bootstrap confidence intervals; significance threshold p<0.05 for headline claims; report all three metrics (correctness, calibration, efficiency) for every cell — no cherry-picking which metric to feature per condition.

### Asset copying (not sharing)

Same convention as fellowship: copy not share, to keep build self-contained and avoid cross-directory edits.

- **Architecture figure**: copy v4e TikZ block verbatim into `abstract_v4e_full/main.tex`
- **Bibliography**: copy `abstract_v4e/references.bib` into `abstract_v4e_full/references.bib`
- **Trade-off accepted**: the duplication is acceptable because v4e is frozen post-submission

### Authorship

- v4e (abstract): `\author{Jason Cusati \and Kereshmeh Afsari}` (joint co-authors)
- Full proposal: `\author{Kereshmeh Afsari (PI) \and Jason Cusati (co-PI / student researcher)}` with `\affil{ARCADE Lab, Myers-Lawson School of Construction, Virginia Tech}`
- This signals Afsari as PI for the funded project (correct per CFP eligibility — VT faculty as PI)

### Three-document submission package

The portal requires three uploads. This spec produces the proposal and budget; CV is sourced from `~/code/cv/`.

| Document | Source | Page limit | Tracked here? |
|---|---|---|---|
| Proposal | `abstract_v4e_full/main.tex` → `main.pdf` → `docs/abstract_v4e_full.pdf` | 3 pages + refs | Yes |
| Budget | `abstract_v4e_full/budget.tex` → `budget.pdf` → `docs/abstract_v4e_full_budget.pdf` | 1 page | Yes (draft only) |
| CV | `~/code/cv/build/` (out-of-tree) | n/a | Tracked as dependency in submission checklist |

### Budget structure (draft, fellowship-style)

The 1-page budget is a **draft** for PI/lab-admin review. It lists:

- **Personnel**: GRA stipend (12 months) + tuition + benefits; faculty summer salary (1 month, optional — PI's call)
- **Materials and Computing**:
  - **LLM API tokens** — featured line item with explicit justification paragraph. Rationale: AKG-E exercises agents across RAG, graph queries, simulation feedback, and VVUQ refinement loops; benchmark evaluation requires thousands of agent runs across ablation conditions and random seeds. Token spend should be sized accordingly.
  - AWS Bedrock + cloud compute
  - Simulation software / FEA licenses
- **Travel**: 2 conference venues for presentation + Amazon collaboration travel
- **Indirect costs**: at VT F&A rate (PI/lab-admin to confirm rate; placeholder used)

Dollar amounts in the draft are **placeholders** clearly marked as such — the spec is not the source of truth for figures.

### Reviewer-feedback workflow

The Amazon invitation states reviewers will be connected before the deadline. The spec must accommodate revisions but otherwise mirrors the fellowship workflow (direct push to main, no ceremony):

- **Revision tracking**: keep `construction/reviews/` ready for an `amazon-reviewer-feedback-<date>.md` artifact when feedback arrives; revisions ship as ordinary commits to main
- **Lock window**: one final read-through within ~24 hours of May 5 before portal upload

### Web page (internal-use)

`docs/proposal-akge-full.html` — same internal-archive convention as `docs/fellowship.html`. Lists the three submission documents, the deadline, and team. **Not for Amazon-reviewer consumption** (reviewers go through the portal).

### File layout

```
abstract_v4e_full/
  main.tex          (3-page full proposal LaTeX)
  budget.tex        (1-page budget draft LaTeX)
  references.bib    (copied verbatim from abstract_v4e/)
  Makefile          (mirrors abstract_v2/Makefile; builds main.pdf and budget.pdf)
  (PDF outputs: main.pdf, budget.pdf — published to docs/)

docs/
  abstract_v4e_full.pdf            (NEW — proposal PDF)
  abstract_v4e_full_budget.pdf     (NEW — budget PDF)
  proposal-akge-full.html          (NEW — internal archive page)
  downloads.html                   (UPDATE — add full proposal section)
  index.html                       (UPDATE — add nav link)

construction/requirements/
  citation-matrix.md               (UPDATE — add `full` column)
  submission-checklist.md          (UPDATE — full-proposal section with 3-doc tracking)

construction/reviews/
  amazon-reviewer-feedback-<date>.md  (CREATE WHEN feedback arrives)

memory-bank/
  activeContext.md                 (UPDATE — full-proposal workstream + PA-AKG-not-invited)
  progress.md                      (UPDATE — Phase 5: Full Proposal)
```

## Sample Implementation

See Phase 5 in the conversation log. Skeleton of the proposal LaTeX:

```latex
% abstract_v4e_full/main.tex — 3 pages max + references; IEEE 2-column

\documentclass[conference, 10pt]{IEEEtran}
% ... preamble identical to abstract_v4e ...

\title{Agentic Knowledge Graphs for AI-Accelerated Engineering
       with Simulation-Grounded Validation}
\author{
    \IEEEauthorblockN{Kereshmeh Afsari (PI) \and Jason Cusati (co-PI)}
    \IEEEauthorblockA{ARCADE Lab, Myers-Lawson School of Construction \\
                      Virginia Tech, Blacksburg, VA, USA}
}

\begin{document}
\maketitle

\section{Problem Statement and Motivation}
% REUSED v4e ¶1 + expansion: regulatory consequences of unverified AI
% in construction; Amazon's stake (Bedrock + construction logistics).

\section{Proposed Approach: The AKG-E Framework}
% REUSED v4e ¶2. Three layers (ontology / simulation / VVUQ).
% Insert v4e TikZ figure (copied verbatim).

\section{Research Plan}

\subsection{Research Questions}
% RQ1, RQ2 reused from v4e.

\subsection{Methodology}
% NEW. Per-RQ: RQ1 builds VVUQ-agent integration with typed
% simulator-tool interface; RQ2 implements second domain
% (transportation safety from VTTI work) and runs cross-domain
% ablation.

\subsection{Evaluation Plan}
% NEW. Three-tier metric framework:
%   (1) Correctness — constraint-violation rate vs codified
%       standards (AWC-NDS / HCM2022 / NERC-TPL); must-pass floor.
%   (2) Calibration — 95% CI coverage vs Sandia experimental
%       data + FEA reference designs.
%   (3) Efficiency — time-to-validated-decision vs manufacturer-
%       cycle baseline (status quo: weeks-to-months); AKG-E target
%       is minutes-to-hours at preserved correctness.
% Baselines (3-tier ablation): B0 Claude alone; B1 Claude+graph-RAG;
% B2 full AKG-E (Claude+graph-RAG+agentic VVUQ loop).
% Benchmark suite covers all three domains; n=5 seeds minimum
% per cell; 95% bootstrap CI; p<0.05 significance threshold.

\section{Timeline, Deliverables, and Risks}
% 3-month aggressive build (months 1-3) inside the 1-year funded window:
% Month 1: Generalize the existing LVL VVUQ pipeline
%   (construction-ai/construction/design/vvuq-integration-plan.md)
%   into the pluggable AKG-E framework; refactor KG curation +
%   graph-RAG; implement propose-VVUQ-feedback agent loop.
% Month 2: Implement transportation digital twin per the existing
%   transportation proposal; begin cross-domain ablation runs;
%   stand up benchmark harness.
% Month 3: Energy pilot with Sandia PDE solver + experimental data;
%   complete benchmark suite (3 domains × B0/B1/B2 × n seeds);
%   statistical analysis; write-up + first paper draft.
% Months 4-12 (funded year remainder): dissemination, robustness
% experiments, scaling studies, additional publications, open-source
% release of the framework + benchmark + KG templates.
%
% Personnel: 2 GRAs full-time during the 3-month build, with
% AI-assisted development (Claude) as an explicit force multiplier —
% the proposal itself names this as part of the methodology.
%
% Mandatory: explicit Risks and Mitigation sub-paragraph covering
% (a) the agentic VVUQ loop is slower to converge than expected
% — fallback: tighten the iteration budget and accept best-so-far
% with explicit UQ caveats;
% (b) cross-domain transfer fails on energy in Month 3 — fallback:
% drop energy to "future work" demo, deepen construction and
% transportation ablations;
% (c) Sandia partnership delayed — fallback: synthetic energy PDE
% cases using FEniCS-equivalents, defer experimental validation.

\section{Team and Capabilities}
% Afsari (PI; ARCADE Lab director, BIM and 3D-visualization
% expertise; existing construction.ai initiative). Cusati (co-PI;
% agentic-KG research-progression system; VTTI VTSI safety-index
% work; Brown-Cusati 2025 SE evaluation paper; VVUQ training via
% Roy's coursework). Two GRAs full-time during the 3-month build.
% AI-assisted development (Claude) as an explicit methodology
% contributor.
% External partnership: Sandia National Laboratories contacts
% provide PDE solver access + experimental data for the energy
% domain.
% Working prototypes named: (1) LVL VVUQ pipeline with
% Euler-Bernoulli + Monte Carlo at
% construction-ai/construction/design/vvuq-integration-plan.md;
% (2) construction-ai KG + multi-agent web application (working
% material-takeoff system); (3) existing transportation digital
% twin proposal.
% ARCADE Lab infrastructure: BIM/IFC datasets, simulation
% pipelines, AWS account.

\section{Intellectual Merit and Amazon Fit}
% REUSED + reframed. Intellectual merit: VVUQ-agent
% integration methodology. Broader impact: certified AI
% for safety-critical engineering. Amazon fit: Bedrock
% Knowledge Bases deployment; construction logistics
% workflow relevance.

\bibliographystyle{IEEEtran}
\bibliography{references}
\end{document}
```

Skeleton of the budget LaTeX:

```latex
% abstract_v4e_full/budget.tex — 1 page max
% DRAFT — dollar amounts are placeholders for PI/lab-admin review

\documentclass[10pt]{article}
\usepackage[margin=0.75in]{geometry}
\usepackage{booktabs}
\usepackage{array}

\begin{document}
\section*{Budget --- AKG-E Full Proposal (DRAFT)}

\begin{tabular}{p{4.2in} r}
  \toprule
  \textbf{Category}                                              & \textbf{Amount} \\
  \midrule
  \multicolumn{2}{l}{\textbf{Personnel}} \\
  \quad GRA \#1 (Cusati, 12 mo --- includes 3-mo full-time build) & \$XX,XXX \\
  \quad\quad Stipend + tuition + benefits                        & \$XX,XXX \\
  \quad GRA \#2 (TBD, 12 mo --- includes 3-mo full-time build)   & \$XX,XXX \\
  \quad\quad Stipend + tuition + benefits                        & \$XX,XXX \\
  \quad Faculty summer salary (Afsari, optional)                 & \$XX,XXX \\
  \midrule
  \multicolumn{2}{l}{\textbf{Materials and Computing}} \\
  \quad LLM API tokens (development + benchmark runs)            & \$XX,XXX \\
  \quad AWS Bedrock + cloud compute                              & \$XX,XXX \\
  \quad Simulation software / FEA licenses                       & \$X,XXX \\
  \midrule
  \multicolumn{2}{l}{\textbf{Travel}} \\
  \quad Conference venues (2) + Amazon collaboration             & \$X,XXX \\
  \midrule
  \textbf{Total Direct Costs}                                    & \$XXX,XXX \\
  Indirect Costs (VT F\&A rate)                                  & \$XX,XXX \\
  \textbf{Total Project Cost}                                    & \textbf{\$XXX,XXX} \\
  \bottomrule
\end{tabular}

\section*{Justification --- LLM API Tokens}
AKG-E exercises agents across retrieval-augmented generation, structured
graph queries, simulation feedback, and VVUQ refinement loops. Benchmark
evaluation requires thousands of agent runs across ablation conditions
(LLM-only, RAG-only, GraphRAG, AKG-E) and multiple random seeds for
statistical validity. Token spend is sized for development plus full
benchmark suite execution at production-quality models.

\end{document}
```

## Edge Cases & Error Handling

### Body overrun (proposal body past page 3)
- **Scenario**: Hybrid sections push past page 3 before the bibliography
- **Behavior**: Trim Section 6 (Intellectual Merit + Amazon Fit) first; then tighten Section 4 (Timeline); references are exempt and may overflow
- **Test**: visually verify `\bibliography{}` heading appears on or before page 3 in the rendered PDF

### Budget overrun (budget past 1 page)
- **Scenario**: Budget table + justification paragraph exceeds 1 page
- **Behavior**: Trim the justification paragraph (table is the priority); compress travel/equipment lines
- **Test**: `pdfinfo budget.pdf | grep Pages` returns 1

### v4e accidentally modified
- **Scenario**: An edit slips into `abstract_v4e/` while drafting the full proposal
- **Behavior**: `abstract_v4e/` is frozen — copy assets out, never refactor in
- **Test**: `git status abstract_v4e/` returns clean

### Reviewer feedback arrives mid-draft
- **Scenario**: Amazon connects a reviewer who sends substantive feedback before May 5
- **Behavior**: Capture feedback in `construction/reviews/amazon-reviewer-feedback-<YYYY-MM-DD>.md` with action items; revise the proposal on the same `proposal/akge-full` branch; do not merge to main until final pass
- **Test**: feedback artifact exists; revision commit references the feedback file

### CV PDF not current
- **Scenario**: Same as fellowship — `~/code/cv/build/academic/` lacks a current PDF
- **Behavior**: Rebuild before submission; flag in submission checklist
- **Test**: `~/code/cv/build/academic/<filename>.pdf` exists with date within 14 days of submission

### Budget dollar amounts treated as binding by reviewer
- **Scenario**: Reviewer/PI mistakes the spec's placeholder figures for committed numbers
- **Behavior**: Budget LaTeX explicitly labels itself "DRAFT — for PI/lab-admin review"; submission checklist requires PI sign-off on dollar amounts before portal upload
- **Test**: budget.tex contains "DRAFT" label; submission checklist has explicit PI-sign-off checkbox

## Acceptance Criteria

Acceptance criteria are split into two tiers. **Tier 1 (Blocking)** must clear before portal submission. **Tier 2 (Same-week follow-up)** is required for "feature complete" but does not block submission.

### Tier 1 — Blocking (must clear before portal submit)

### AC-1: Proposal PDF builds with body content fitting in 3 pages
- **Given** `abstract_v4e_full/main.tex` is complete
- **When** the LaTeX build runs
- **Then** `docs/abstract_v4e_full.pdf` exists, builds without errors, includes the AKG-E architecture figure, and the **body content** (everything before `\bibliography{}`) ends on or before page 3 — references may continue on page 4+

### AC-2: Authorship reflects PI structure
- **Given** the proposal PDF is built
- **When** a reader views the title block
- **Then** Kereshmeh Afsari is listed first as **(PI)** with ARCADE Lab / Myers-Lawson School of Construction / Virginia Tech affiliation, Jason Cusati is listed as **(co-PI / student researcher)**, and no other authors appear on the byline

### AC-3: Six-section structure with Methodology and Evaluation as substantive new content
- **Given** the proposal PDF is built
- **When** sections are read
- **Then** all six sections are present (Problem & Motivation, Proposed Approach, Research Plan, Timeline & Deliverables & Risks, Team & Capabilities, Intellectual Merit & Amazon Fit); Section 3 contains three subsections (RQs, Methodology, Evaluation Plan); Section 3.2 covers the agent↔VVUQ-gate protocol (with the propose→VVUQ→feedback loop named explicitly as the net-new contribution), specific verification checks, UQ propagation strategy, and construction-pilot algorithmic specifics (per the Section 3 content mandate); Section 3.3 covers the three-tier metric framework (correctness floor / calibration / efficiency headline), named B0/B1/B2 baselines, the three-domain benchmark suite, and the statistical analysis plan (per the revised Section 3 content mandate)

### AC-RISK: Risks and Mitigation paragraph present in Timeline section
- **Given** the proposal PDF is built
- **When** Section 4 (Timeline, Deliverables, and Risks) is read
- **Then** a Risks and Mitigation sub-paragraph is present that names at least three concrete risks (VVUQ-agent integration timing; cross-domain transfer; reviewer-feedback scope change) with named mitigations

### AC-4: Budget PDF builds at exactly 1 page
- **Given** `abstract_v4e_full/budget.tex` is complete
- **When** the LaTeX build runs
- **Then** `docs/abstract_v4e_full_budget.pdf` exists, is exactly 1 page, contains all five categories (Personnel / Materials and Computing / Travel / Total Direct / Indirect / Total), explicitly labels itself "DRAFT," and includes the LLM-token justification paragraph

### AC-5: LLM-token line item is featured and justified
- **Given** the budget PDF is built
- **When** Section "Materials and Computing" is read
- **Then** "LLM API tokens" appears as an explicit line item separate from cloud compute, and a justification paragraph immediately below the table explains the token-spend rationale (RAG + graph queries + simulation feedback + VVUQ loops × benchmark runs × seeds)

### AC-6: v4e directory is untouched
- **Given** the feature is implemented
- **When** `git status abstract_v4e/` is run
- **Then** there are zero changes inside `abstract_v4e/`

### AC-CV: CV PDF is current and submission-ready
- **Given** the CV repo at `~/code/cv/`
- **When** the team prepares the submission package
- **Then** a recent CV PDF exists (rebuilt within 14 days of submission), reflects Cusati's current PhD year, and has been spot-checked for stale dates / outdated affiliations

### AC-SUB: Submission package staged for portal upload
- **Given** all artifacts are built
- **When** the team prepares to submit
- **Then** `construction/requirements/submission-checklist.md` has a full-proposal section listing: (a) proposal PDF path, (b) budget PDF path, (c) CV PDF path, (d) reviewer-feedback status (as of 2026-05-11: never received; PI follow-up sent to Burrell), (e) PI sign-off on budget figures, (f) portal URL, (g) primary/secondary topic selections (AI Accelerated Science & Engineering / Agentic AI), (h) **May 13 deadline**

### Tier 2 — Same-week follow-up (ships before May 5 but does not block submission)

### AC-7: Internal-archive page published
- **Given** the docs site is rebuilt
- **When** a visitor opens `docs/proposal-akge-full.html`
- **Then** the page renders with title "AKG-E Full Proposal," links to the proposal PDF and budget PDF, lists Afsari + Cusati + deadline, and follows the existing site nav/style

### AC-8: Site navigation and downloads page updated
- **Given** the site is rebuilt
- **When** visitors visit `docs/index.html` and `docs/downloads.html`
- **Then** both pages link to the full proposal page and the proposal/budget PDFs are listed in `downloads.html`

### AC-9: Citation matrix updated
- **Given** `construction/requirements/citation-matrix.md` exists
- **When** the spec is implemented
- **Then** the matrix has a new `full` column showing every citation used in the full proposal; if no new citations were added, the column structure mirrors the existing `v4e` column entries

### AC-10: Memory-bank reflects new state
- **Given** the feature is shipped
- **When** future sessions read `memory-bank/activeContext.md` and `progress.md`
- **Then** the full-proposal workstream is documented; the May 5 deadline is annotated; PA-AKG is noted as not invited; the relationship to v4e (and the fellowship workstream) is stated

### AC-RVW: Reviewer feedback captured if received
- **Given** Amazon connects a reviewer between now and May 5
- **When** feedback is received
- **Then** the feedback is captured in `construction/reviews/amazon-reviewer-feedback-<YYYY-MM-DD>.md` with action items; revisions ship as ordinary commits to main

## Technical Notes

- **Affected components**: `abstract_v4e_full/` (new dir), `docs/proposal-akge-full.html` (new), `docs/abstract_v4e_full.pdf`, `docs/abstract_v4e_full_budget.pdf`, `docs/index.html` (update), `docs/downloads.html` (update), `construction/requirements/citation-matrix.md` (update), `construction/requirements/submission-checklist.md` (update), `memory-bank/activeContext.md` (update), `memory-bank/progress.md` (update)
- **Patterns to follow**: existing `abstract_v*/main.tex` IEEE 2-column convention; `docs/proposal-*.html` page style; citation matrix column structure; fellowship-application implementation as the closest precedent
- **CI**: existing latexmk pipeline only enumerates `abstract abstract_v2 abstract_v3 abstract_v4`; the new directory builds locally and PDFs are committed to `docs/` (same convention as v4e and fellowship)
- **Branching**: direct push to main (same as fellowship); revisions land as ordinary commits as reviewer feedback arrives
- **Time pressure**: 7 days to deadline (May 5); favor solid first draft over perfection so reviewer has something concrete to discuss

## Dependencies

- **AKG-E v4e** (`abstract_v4e/`) — frozen; source of research vision, figure, bibliography, RQs
- **AKG-E fellowship** (`abstract_v4e_fellowship/`) — frozen; contains the 4-thread synthesis story (Research-AI / Construction-AI / VTSI / VVUQ) which can inform Section 5 (Team) but should not be copy-pasted (different audience)
- **`~/code/construction-ai/`** — existing prototype: KG + multi-agent web app for material takeoff. `construction/design/vvuq-integration-plan.md` documents the LVL VVUQ math (Euler-Bernoulli + Monte Carlo) that AKG-E generalizes. Cite as proof of concept; do not modify from this proposal.
- **`~/code/construction-ai-proposal/`** — LaTeX proposal articulating the KG + multi-agent architecture; reference the agentic skeleton that AKG-E extends.
- **Sandia partnership (energy domain)** — PI/co-PI must confirm Sandia contact will provide PDE solver access + experimental data within the 3-month build window. Mitigation if delayed: synthetic FEniCS-equivalent cases.
- **CV repo** (`~/code/cv/`) — required for submission package; must be rebuilt
- **Amazon reviewer** — external dependency; promised but not received as of 2026-05-11; PI follow-up sent to Burrell
- **PI sign-off** — Dr. Afsari must sign off on the proposal (final read) and on the budget (dollar amounts) before submission
- **Amazon research portal** — submission target (https://home.academic-research-portal.amazon.science/login)

## Open Questions

- **Budget dollar amounts** — placeholders only; PI and ARCADE/VT lab admin own final figures (GRA stipend rates × 2, F&A rate, total ask within ~$100K Phase 1 envelope). Spec does not commit numbers.
- **Faculty summer salary line** — included as optional in budget; PI's call whether to include
- **GRA #2 identity** — second GRA's name/CV needed for personnel section and CV bundle if Amazon requires both
- **Sandia named contact** — letter of support or named collaborator for the energy domain? Strengthens the Sandia partnership claim materially
- **Reviewer feedback** — not received as of 2026-05-11; PI followed up with Burrell. If feedback arrives in the next 48 hours, decide between (a) substantive revision pre-submission or (b) submit current draft + send revised version as addendum
- **Whether the docs page should aggregate fellowship + full proposal under one "AKG-E Submissions" parent** or stay separate (current spec keeps them separate; trivial to consolidate later)

---

**Note**: This revised spec assumes ~2 days to the May 13 deadline. Reviewer connection promised by Amazon never materialized as of 2026-05-11. The implementation phase should produce a complete first draft within ~24 hours and reserve the remaining window for PI review + budget finalization + portal upload. Tier 1 ACs are the submission contract; Tier 2 is housekeeping. The narrative anchors — 3-month build, 2 GRAs, AI-assisted dev, three-tier eval (correctness + calibration + efficiency), three working-prototype repos (construction-ai + construction-ai-proposal + transportation digital-twin proposal), Sandia partnership — together carry the feasibility argument.

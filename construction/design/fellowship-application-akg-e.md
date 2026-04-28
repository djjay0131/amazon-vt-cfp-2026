# Feature: Fellowship Application — AKG-E

**Status:** IMPLEMENTED
**Date:** 2026-04-27
**Author:** Feature Architect (AI-assisted)
**Implemented:** 2026-04-27 (same day)
**Applicant:** Jason Cusati (PhD candidate, Virginia Tech)
**Advisor:** Kereshmeh Afsari

## Problem

The Amazon-VT Initiative 2026-2027 Call for Fellowship Nominations closes **today, April 27, 2026**. Jason Cusati is eligible (3rd-year+ PhD at VT, qual exams passed, no other industry-sponsored fellowship) and has a research vision (AKG-E v4e) that aligns with the fellowship's "AI Accelerated Science & Engineering Innovation" topic. However, AKG-E v4e was written as a 1-page **project proposal** co-authored with the advisor — not as a 2-page **personal statement / fellowship application** centered on the PhD student. No fellowship-flavored variant exists in the repository, no submission package is staged, and the existing GitHub Pages site has no fellowship landing page. The applicant must produce a 2-page LaTeX proposal, stage CV + ≤2 letters of recommendation, publish a "Amazon-VT Call for Fellowships" web page, and be ready to submit to the portal this afternoon.

## Goals

- Produce a 2-page LaTeX fellowship proposal (`abstract_v4e_fellowship/`) framed as a doctoral research vision with student-centric personal statement
- Reuse AKG-E v4e research vision, architecture figure, RQ1/RQ2, and bibliography (single source of truth — no drift)
- Add net-new sections: personal statement opener, training plan / advisor fit, qualifications & trajectory
- Build the proposal PDF via the existing CI/LaTeX pipeline
- Publish a new "Amazon-VT Call for Fellowships" page (`docs/fellowship.html`) with the proposal PDF linked
- Update `docs/downloads.html` and `docs/index.html` navigation to link the new page
- Update `construction/requirements/citation-matrix.md` with a fellowship column
- Stage the full submission package (proposal PDF, CV PDF, letters) for portal upload this afternoon
- Update `memory-bank/activeContext.md` and `progress.md` to reflect the fellowship workstream

## Non-Goals

- Writing or soliciting letters of recommendation (applicant handles directly with recommenders — letters are an external dependency, not produced by this work)
- Regenerating the CV from `~/code/cv/` (use the latest already-built PDF; CV maintenance lives in that repo)
- Performing the portal submission itself (applicant uploads manually after artifacts are staged)
- Modifying the AKG-E v4e project abstract (already submitted — frozen)
- Modifying the PA-AKG (v2) project abstract (already submitted — frozen)
- Creating a separate fellowship variant for PA-AKG or SVF (this fellowship targets AKG-E only)
- Adding new citations beyond the v4e bibliography (reuse only — additions risk last-minute typos)

## User Stories

- As **Jason Cusati**, I want a 2-page fellowship proposal that reads as a doctoral research vision (not a project pitch), so that fellowship reviewers see me as the candidate, not the advisor
- As **Jason Cusati**, I want the fellowship PDF published to the project website alongside other proposals, so that I have a stable URL to reference and the work is part of the public record
- As a **fellowship reviewer**, I want a clear personal-statement narrative tying the applicant's trajectory to a concrete AI research contribution, so that I can assess fit in 2 pages
- As **future-me (post-submission)**, I want the citation matrix and memory-bank updated, so that the next session can pick up the project state without re-reading commit logs

## Design Approach

### Hybrid reuse strategy

The fellowship proposal is a **hybrid** of the v4e abstract and net-new student-centric content:

| Section | Source | Word budget |
|---|---|---|
| 1. Research Vision and Motivation | NEW (personal statement) | ~150 |
| 2. Research Problem | REUSED from v4e (lightly edited) | ~250 |
| 3. Approach — AKG-E Framework | REUSED from v4e + figure | ~300 |
| 4. Research Questions (RQ1, RQ2) | REUSED from v4e | ~150 |
| 5. Training Plan and Advisor Fit | NEW (fellowship-specific) | ~200 |
| 6. Qualifications and Trajectory | NEW (sourced from CV repo) | ~150 |
| 7. Expected Impact | REUSED + reframed from v4e | ~100 |
| **Total** | | **~1300 words** ≈ 2 pages |

### Asset copying (not sharing)

To eliminate any risk of accidentally modifying the already-submitted v4e and to keep the build self-contained on a same-day deadline, the fellowship variant copies rather than shares:

- **Architecture figure**: copy the TikZ block verbatim into `abstract_v4e_fellowship/main.tex`. Do NOT extract a shared file — that would require editing v4e
- **Bibliography**: copy `abstract_v4e/references.bib` into `abstract_v4e_fellowship/references.bib`. Use `\bibliography{references}` (local), not the parent path
- **Citations**: only those already in v4e references.bib are valid; spec disallows new citations to keep submission clean
- **Trade-off accepted**: the duplication is acceptable because v4e is frozen post-submission; there will be no drift over the document's lifecycle

### Authorship reframe

- v4e: `\author{Jason Cusati \and Kereshmeh Afsari}` (project proposal — co-authors)
- Fellowship: `\author{Jason Cusati \\ PhD Candidate, Virginia Tech \\ Advisor: Kereshmeh Afsari}` (student is the applicant; advisor named as advisor)

### Build pipeline

Reuse the existing pattern: `abstract_v4e_fellowship/` directory with `main.tex`, build via the existing latexmk-based CI; PDF lands in `docs/abstract_v4e_fellowship.pdf`.

### Web page (internal-use only)

New page `docs/fellowship.html` — "Amazon-VT Call for Fellowships". Note: this page is for **internal/personal-archive use** — Amazon reviewers will not be directed here. As a result, the page does not need disambiguation language explaining the fellowship-vs-project relationship for external readers, and AC-5/AC-6 should be evaluated only for accuracy and link integrity, not for reviewer-facing polish.

- Brief description of the fellowship (topic alignment, applicant)
- Link to the fellowship proposal PDF
- Link to the underlying AKG-E project proposal (v4e) as research-vision reference
- Standard nav header consistent with other proposal pages
- Linked from `docs/index.html` and `docs/downloads.html`

### File layout

```
abstract_v4e_fellowship/
  main.tex
  references.bib  (copied verbatim from abstract_v4e/references.bib)
  (PDF output: docs/abstract_v4e_fellowship.pdf)

docs/
  fellowship.html         (NEW)
  abstract_v4e_fellowship.pdf  (NEW build output)
  downloads.html          (UPDATE — add fellowship entry)
  index.html              (UPDATE — add nav link)

construction/requirements/
  citation-matrix.md      (UPDATE — add fellowship column)
  submission-checklist.md (UPDATE — fellowship section)

memory-bank/
  activeContext.md        (UPDATE — current focus = fellowship submission today)
  progress.md             (UPDATE — Phase 4: Fellowship Application)
```

### Out-of-tree dependencies

- **CV PDF**: latest from `~/code/cv/build/` — applicant pulls manually, not built here
- **Bio content** for sections 5–6: source from `~/code/cv/publications.tex`, `~/code/cv/own-bib.bib`, and `~/code/website/src/` bio content
- **Letters of recommendation**: applicant coordinates with recommenders; tracked as external dependency in the submission checklist

## Sample Implementation

See Phase 5 in the conversation log. Skeleton (illustrative — not to ship):

```latex
% abstract_v4e_fellowship/main.tex
\documentclass[conference, 10pt]{IEEEtran}
% ... preamble identical to abstract_v4e ...

\title{Agentic Knowledge Graphs for AI-Accelerated Engineering: \\
       A Doctoral Research Vision with Simulation-Grounded Validation}
\author{Jason Cusati \\ PhD Candidate, Virginia Tech \\
        Advisor: Kereshmeh Afsari}

\begin{document}
\maketitle

\section*{Research Vision and Motivation}
% NEW — ~150 words. Personal statement: my doctoral research
% investigates X; trajectory ties to advisor's construction.ai initiative.

\section*{Research Problem}
% REUSED from v4e — VVUQ gap for AI engineering outputs.

\section*{Approach: The AKG-E Framework}
% REUSED from v4e. Three layers (ontology, simulation, VVUQ).
\input{../abstract_v4e/figure_akge.tex}

\section*{Research Questions}
% REUSED from v4e — RQ1 (VVUQ adapted to AI agents),
% RQ2 (domain-agnostic architecture validates across domains).

\section*{Training Plan and Advisor Fit}
% NEW — ~200 words. Fellowship enables dissertation timeline,
% Amazon Bedrock industry exposure, advisor expertise in VVUQ
% and construction.ai.

\section*{Qualifications and Trajectory}
% NEW — ~150 words. Pull from ~/code/cv/publications.tex and prior
% repos (e.g., ~/code/agentic-kg/, construction-ai-proposal/).
% Lead with research outputs (papers, projects, prior agentic-AI work);
% qual exam status; expected dissertation timeline. Course names allowed
% only if directly relevant — NO course numbers (they belong on the CV).

\section*{Expected Impact}
% REUSED + reframed from v4e. Bedrock deployment, AKG-E open-source,
% reproducible benchmarks for agentic engineering systems.

\bibliographystyle{IEEEtran}
\bibliography{../abstract_v4e/references}
\end{document}
```

## Edge Cases & Error Handling

### Body overrun (body content past page 2)
- **Scenario**: Hybrid body sections (1–7) push past page 2 before the bibliography
- **Behavior**: Trim section 7 (Expected Impact) first — it's most redundant with v4e; then tighten section 3 (figure caption + prose); references are exempt from the 2-page limit and may overflow to page 3+
- **Test**: visually verify `\bibliography{}` heading appears on or before page 2 in the rendered PDF

### v4e accidentally modified
- **Scenario**: An edit to `abstract_v4e/` slips in while drafting the fellowship variant
- **Behavior**: `abstract_v4e/` is frozen — no edits permitted; copy assets out, never refactor in
- **Test**: `git status` shows no changes to `abstract_v4e/` after the feature is implemented

### Letters not secured by submission window
- **Scenario**: Applicant cannot reach recommenders this afternoon
- **Behavior**: Submit with whatever letters are available (CFP allows up to 2 max — interpretation permits 1 or even 0); flag missing letters in `submission-checklist.md`
- **Test**: Submission checklist explicitly notes letter status before "submit" is checked

### Personal statement reads like project pitch
- **Scenario**: Sections 1, 5, 6 default to plural "we propose" / project-team voice
- **Behavior**: Style review pass — every sentence in NEW sections should use first-person singular ("I", "my research") and tie to applicant trajectory
- **Test**: Manual read-through; spec's acceptance criteria require this

### Citation matrix update collision
- **Scenario**: Adding a fellowship column conflicts with the matrix's structure
- **Behavior**: Append a single column "fellowship" to the existing v2–v4e matrix; do not refactor
- **Test**: Matrix renders cleanly; existing v4e column unchanged

## Acceptance Criteria

Acceptance criteria are split into two tiers. **Tier 1 (Blocking)** must clear before the portal submission is attempted. **Tier 2 (Same-day follow-up)** is required for "feature complete" but does not block submission — if any Tier 2 item slips, submit first and finish the cleanup after.

### Tier 1 — Blocking (must clear before portal submit)

### AC-1: Fellowship proposal PDF builds with body content fitting in 2 pages (references may overflow)
- **Given** `abstract_v4e_fellowship/main.tex` is complete
- **When** the LaTeX build runs
- **Then** `docs/abstract_v4e_fellowship.pdf` exists, builds without errors (cosmetic warnings allowed), includes the AKG-E architecture figure, and the **body content** (everything before `\bibliography{}`) ends on or before page 2 — references may continue on page 3+
- **Test**: visually verify the bibliography heading appears on page 2 (or later, but body must end by page 2); `pdfinfo` page count typically 3 (2 body + 1 refs) or 2 (if refs fit)

### AC-2: Authorship reflects fellowship framing
- **Given** the proposal PDF is built
- **When** a reader views the title block
- **Then** Jason Cusati is listed as the sole applicant with PhD candidate / VT affiliation, and Kereshmeh Afsari is listed as advisor (not co-author)

### AC-3: Personal statement sections present and student-centric
- **Given** the proposal PDF is built
- **When** sections 1, 5, 6 are read
- **Then** they use first-person singular voice, lead section 6 with research outputs (papers, projects, prior agentic-AI work from `~/code/agentic-kg/`, `~/code/construction-ai-proposal/`, etc.) rather than coursework — no course numbers — and explain advisor/training fit; not the v4e project-team voice

### AC-CV: CV PDF is current and submission-ready
- **Given** the CV repo at `~/code/cv/`
- **When** the applicant prepares the submission package
- **Then** a recent CV PDF exists (rebuilt today or verified current within the last 60 days), reflects the applicant's current PhD year + qual exam status, and has been spot-checked for stale dates / outdated affiliations before being attached to the portal submission

### AC-4: Reused content is intact and v4e is untouched
- **Given** sections 2, 3, 4, 7 are reused from v4e
- **When** compared to `abstract_v4e/main.tex`
- **Then** core claims, RQ1/RQ2 wording, figure, and citations are preserved (modulo light edits for narrative flow); no new citations introduced; `git status` shows zero changes inside `abstract_v4e/`

### Tier 2 — Same-day follow-up (ships today but does not block submission)

### AC-5: Fellowship web page is published
- **Given** the docs site is rebuilt
- **When** a visitor opens `docs/fellowship.html` (or its deployed URL)
- **Then** the page renders with title "Amazon-VT Call for Fellowships," links to the fellowship proposal PDF, references the underlying AKG-E v4e research vision, and follows the existing site's nav/style conventions

### AC-6: Site navigation and downloads page updated
- **Given** the site is rebuilt
- **When** a visitor visits `docs/index.html` or `docs/downloads.html`
- **Then** both pages link to `docs/fellowship.html` and `docs/abstract_v4e_fellowship.pdf` respectively, and existing proposal links are unchanged

### AC-7: Submission package staged for portal upload
- **Given** all artifacts are built
- **When** the applicant prepares to submit
- **Then** `construction/requirements/submission-checklist.md` has a fellowship section listing: (a) proposal PDF path, (b) CV PDF path (from `~/code/cv/`), (c) letter-of-recommendation status (count + recommender names + delivery method), (d) portal URL, (e) primary/secondary topic selections (AI Accelerated Science & Engineering / Agentic AI)

### AC-8: Citation matrix updated
- **Given** `construction/requirements/citation-matrix.md` exists
- **When** the spec is implemented
- **Then** the matrix has a "fellowship" column showing every reused citation from v4e is also used in the fellowship doc, no new citations are introduced, and the column structure matches the existing v2–v4e format

### AC-9: Memory-bank reflects new state
- **Given** the feature is shipped
- **When** a future session reads `memory-bank/activeContext.md` and `progress.md`
- **Then** the fellowship workstream is documented as the current focus (or completed, post-submission), the April 27 deadline is annotated correctly, and the relationship to the AKG-E v4e project proposal is stated. Post-submission receipt details (portal confirmation, timestamp) will be added at the time of submission as provided by the applicant — not pre-specified here

## Technical Notes

- **Affected components**: `abstract_v4e_fellowship/` (new dir), `docs/fellowship.html` (new), `docs/index.html` (update), `docs/downloads.html` (update), `construction/requirements/citation-matrix.md` (update), `construction/requirements/submission-checklist.md` (update), `memory-bank/activeContext.md` (update), `memory-bank/progress.md` (update), CI build matrix if abstract directories are enumerated explicitly
- **Patterns to follow**: existing `abstract_v*/main.tex` IEEE 2-column convention, `docs/proposal-*.html` page style, citation matrix column structure
- **Data model changes**: none (no databases — this is a documentation repo)
- **CI**: confirm the existing latexmk pipeline picks up `abstract_v4e_fellowship/` automatically; if abstract dirs are enumerated, add the new dir to the build list
- **Time pressure**: deadline today (2026-04-27 PM); favor speed and reuse over polish where they conflict, but not at AC-3's expense (personal statement voice is non-negotiable)

## Dependencies

- **AKG-E v4e** (`abstract_v4e/`) — must remain frozen; no edits to its `.tex` (already submitted as project proposal)
- **CV repo** (`~/code/cv/`) — source for `publications.tex` content used in section 6; latest CV PDF used in submission package
- **Website repo** (`~/code/website/`) — source for bio content used in sections 1, 5, 6 (the `cv` repo is primary; website is supplemental)
- **Letters of recommendation** — external (recommenders); ≤2 letters; submission can proceed with fewer if necessary
- **Amazon research portal** — submission target (https://home.academic-research-portal.amazon.science/login)
- **Existing CI/LaTeX build** — the project's documented `make`/`latexmk` toolchain

## Open Questions

- **Letter status by submission window** — applicant must confirm with recommenders directly today; not resolvable in spec
- **Whether the CV PDF should also be linked from the new fellowship page** — applicant said "I don't need everything on the website"; current spec links only the proposal PDF, but a CV link can be added trivially if desired during implementation
- **Whether `docs/fellowship.html` should be a hub for future fellowship cycles** (2027-2028, etc.) or a one-shot page for this submission — current spec scopes it to 2026-2027; reframing to a hub would be a follow-up feature, not required today

---

**Note**: This spec is for a same-day submission. The implementation phase should run lean — copy-paste-modify rather than abstract refactor — and prioritize AC-1, AC-2, AC-3, AC-5, AC-7 over the lower-criticality acceptance criteria.

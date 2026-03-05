# AGENTS.md

## Cursor Cloud specific instructions

This is a **documentation-only research proposal repository** (Amazon-VT CFP 2026-2027). There is no application code, no build system, no package manager, no test framework, and no linter.

### Repository structure

- `docs/index.html` — Static landing page (vanilla HTML/CSS, deployed via GitHub Pages)
- `memory-bank/` — Living project documentation (Markdown)
- `construction/` — Design workspace (Markdown)
- `files/` — Reference materials (CFP PDF)
- `.claude/agents/` — AI agent configurations
- `.github/workflows/deploy-pages.yml` — GitHub Pages deployment (deploys `docs/` on push to `main`)

### Running the site locally

Serve the static page with Python's built-in HTTP server:

```
python3 -m http.server 8080 --directory docs
```

No dependencies are required. The page is a single self-contained HTML file with inline CSS.

### No build/lint/test tooling

There are no `package.json`, `requirements.txt`, `Makefile`, or other dependency files. The `.gitignore` lists LaTeX artifacts, suggesting LaTeX may be added later for the proposal document.

# Copilot instructions — Vet Box Tracker

Purpose
- Help agents make focused edits to this small static app (no backend).

Big picture
- Single-page, mobile-first static site: the UI and logic live in `index.html` and the data lives in `inventory.csv`.
- No build step or server: deploys to GitHub Pages (see `README.md` deployment steps).

Key files and responsibilities
- `index.html`: entire app (UI, styles, JS). Entry point for changes; contains these important constants:
  - `GITHUB_OWNER`, `GITHUB_REPO`: change to point Edit / API calls to your repo.
  - `CSV_PATH` (defaults to `inventory.csv`).
  - `DRAWER_LAYOUTS` and `CABINET_IMAGE`: adjust drawer grids and the embedded image.
- `inventory.csv`: authoritative inventory data (CSV headers: Drawer, Compartment, Row, Col, Item, TargetQty). Preserve header names and CSV structure when editing.
- `README.md`: user-facing docs and the exact GitHub Pages enablement steps — mirror any public-facing change here.

Data flow and common edits
- On load, `index.html` reads `inventory.csv` and renders compartments. Editing the CSV updates the app after a refresh.
- Edits methods:
  - Direct GitHub edit: preferred for simple changes (UI exposes an "Edit Inventory" flow that opens the file on GitHub).
  - Local edit: replace `inventory.csv` and push to the repository.
- Changing layout or visuals: modify `DRAWER_LAYOUTS` and `CABINET_IMAGE` inside `index.html` (no other files required).

Project conventions & patterns
- Keep all JS, CSS, and markup inside `index.html`. Avoid introducing new build tooling — this repo is intentionally single-file.
- CSV header names are authoritative: downstream rendering expects exact column names. If you must rename a header, update parsing logic in `index.html` simultaneously.
- Tokens: the UI supports entering a GitHub PAT stored only in the browser — do not hard-code tokens into files.

Developer workflows
- No build/test commands. To preview locally, open `index.html` in a browser (or use a simple static server). For GitHub Pages:
  1. Push to `main`.
  2. Enable GitHub Pages: Settings → Pages → Deploy from branch → Branch: `main`.
- When changing inventory via the UI, the app performs GitHub API commits using the configured `GITHUB_OWNER`/`GITHUB_REPO` and a browser-stored token.

Examples
- Update edit target: change `GITHUB_OWNER`/`GITHUB_REPO` in `index.html` to point to a fork.
- Add a new compartment layout: edit the `DRAWER_LAYOUTS` object in `index.html` and refresh the page to validate rendering.
- Fix missing items: update `inventory.csv` while preserving the header row, commit, and refresh.

Safety notes for agents
- Do not add servers or external dependencies without explicit permission.
- Avoid modifying `inventory.csv` programmatically unless asked — changes are user-visible and may be committed to production.

If anything below is unclear or you'd like more detail (for example, sample `DRAWER_LAYOUTS` or where `DRAWER_LAYOUTS` is defined), tell me which area to expand.

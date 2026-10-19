# Bag & Tag: notes for Claude

**Read the house rules first:** [HOUSE-RULES.md](https://github.com/jcm-book-library/control-room/blob/main/HOUSE-RULES.md) in `control-room` (plain text: https://raw.githubusercontent.com/jcm-book-library/control-room/main/HOUSE-RULES.md). They cover Google Sheet safety, branches and pull requests into `main`, using cheaper models to save usage credits, and the build template. The notes below are this repo's own; where they are more specific, they win. The project charter is `project.json`.

## This repo
- `app.html` is the app source.
- `python3 tools/build-pages.py` rebuilds `index.html` from `app.html` for GitHub Pages.
- `sw.js` is the offline cache: "Bump `VERSION` when shipping changes."
- Data lives in the browser's IndexedDB; an optional Google Sheet (default set by `SHEET_DEFAULT` in `app.html`) holds a second copy.
- Sheet sync: `code` and `ref` columns "are for reading only and are ignored when syncing back."

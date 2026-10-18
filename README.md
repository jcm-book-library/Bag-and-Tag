# Bag & Tag

A teardown and rebuild tracker for big LEGO sets. Log each bag as a stage comes apart, print the bag labels and the master index slip for the tub, then tick the bags off in build order when you rebuild.

Built first for the Millennium Falcon (75192), but every set is its own project.

## What it does
- **Sets (projects).** Name, set number, bag code prefix (`F` for Falcon), piece count, booklets, stages. Switch between as many sets as you like.
- **Bag log.** Codes follow `[Prefix]-[Stage]-[Letter]`, e.g. `F-3-A`. The next free letter is suggested per stage. Each bag has a booklet and step range, a rough piece count, contents notes, a tub, and an optional photo. Only the stage is required.
  - Teardown runs backwards, so a new bag starts with "to step" set one before the last bag's first step, and the same stage and booklet.
  - Over ~300 pieces, it suggests splitting into the next letter.
- **Special bags** `F-SPARE`, `F-PRINT` and `F-DOC` are pinned above the stages.
- **Master index.** Every bag grouped by stage, with a tick box column. Print it for the tub.
- **Labels.** Two lines per label: the bag code, then `Bk 2 · steps 210–268`. Presets for Avery L7160, L7159, L7163, L7173, L7651 (A4), Avery 5160 (US Letter) and plain A4 cut-outs, plus custom sizes, a printer nudge, and "start at label N" for part-used sheets. After printing it offers to mark those bags as printed, so the default selection next time is only new bags.
- **Rebuild.** An "Open next" card in build order (DOC first, then stage by stage, ordered by booklet and step, not by letter), big tick rows, "12 of 34 bags rebuilt" progress, undo, hide rebuilt, and keep-screen-on.

## Files
| File | What it is |
|---|---|
| `app.html` | The app source. Edit this. It is also what gets published as the claude.ai artifact preview. |
| `index.html` | Built from `app.html` for GitHub Pages. Rebuild with `python3 tools/build-pages.py`. |
| `sw.js` | Offline cache, so the app opens without wifi. Bump `VERSION` when shipping changes. |
| `manifest.webmanifest`, `icons/` | Home-screen install and icons. |

## Data
Everything is stored in the browser's IndexedDB on the device you use. Nothing is uploaded. Use **Save backup file** on the home screen before changing devices or clearing browser data, and **Restore from backup** to load it back (photos are included).

## Running it
- **GitHub Pages (recommended):** Settings → Pages → Deploy from branch `main`, folder `/`. Open the site on the tablet or phone you'll work from, then "Add to Home Screen".
- **Locally:** `python3 -m http.server` in this folder, then open http://localhost:8000.

## Printing labels
Print at **Actual size / 100%** with no margins. Print one sheet on plain paper first and hold it against a label sheet up to the light; use the nudge fields if it's slightly off.

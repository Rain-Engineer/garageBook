# R32 Engine Manual — Search

Full-text search over the Nissan Skyline R32 All Engine Manual (580 pages),
with the actual scanned page viewable for every result. Runs entirely in the
browser — no server, no database.

## Structure

    index.html      the app: OCR'd text of all 580 pages + search + viewer
    pages/          p001.webp … p580.webp — one scanned page image each
    README.md       this file

Search matches the embedded page text; clicking a result opens the matching
image from `pages/`. Keep `index.html` and `pages/` together.

## Hosting

Static files — serve the folder as-is. On Azure Static Web Apps set the app
location to `/` with no build step. Only external dependency is Google Fonts
(HTTPS); everything else is local.

## Adding more manuals (later)

Each manual is its own page + its own `pages/` set, built the same way:
diagnose scan vs. text → OCR → render page images → search + viewer.

## Notes

- Search runs on raw OCR text. Printed text, headers, procedures, and torque
  specs are clean; hand-lettered callouts on diagrams can be noisy.
- Multi-word queries require all words on the same page. Use "quotes" for a phrase.
- Page images are grayscale WebP at ~124 DPI (legible, ~100 KB each).

# R32 Engine Manual — Search

A single self-contained web page for full-text searching the Nissan Skyline R32
All Engine Manual. The complete OCR'd text of all 580 pages is embedded directly
in `index.html`, so search runs entirely in the browser with no server, no
database, and no PDF download.

## Files

- `index.html` — the whole app (page text + search + styling in one file, ~0.9 MB)

## Hosting

It's a static file. Serve `index.html` from any static host and it works. The only
external dependency is Google Fonts (loaded over HTTPS); everything else is inline.

## Adding more manuals (later)

Each manual is planned as its own page. When more are added, `index.html` becomes a
small landing page linking to each manual's page (e.g. `r32.html`, `toyota-xxx.html`),
each built the same way: diagnose scan vs. text → OCR if needed → embed text → search.

## Notes

- Search matches raw OCR text. Printed body text, headers, procedures, and torque
  specs are clean; hand-lettered callouts drawn on diagrams can be noisy.
- Multi-word queries require all words on the same page. Use "quotes" for a phrase.

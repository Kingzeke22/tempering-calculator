# Changelog

All notable changes to the Grain Tempering Calculator are listed here, newest first.

Versions follow MAJOR.MINOR.PATCH. Whenever you publish a change, also raise `CACHE_VERSION` in `sw.js` so installed copies update. The cache version is a separate counter from the version below.

## [1.0.0] - 2026-10-22

First release as an installable web app.

### Added
- Offline support and phone install (web app manifest, service worker, icons)
- Light theme (Flour & Linen) and dark theme (Midnight Amber) with a toggle that remembers your choice
- Sticky "Water to add" bar so the answer stays visible while editing on small screens
- Wheat-stalk and water-drop app icon, including a maskable version for Android
- README and this changelog

### Changed
- Grain weight and initial moisture start empty and must be entered; target moisture still defaults to 14.5%
- Results show "--" with a short prompt until weight and moisture are entered
- Reset clears weight and moisture and returns the target to 14.5%
- Larger text and thumb-sized buttons and inputs for phone use
- Formula and M1/M2 labels are plain HTML, replacing raw LaTeX that did not render
- Tempering tips and the formula explanation moved into collapsible sections
- Tailwind CDN and Google Fonts replaced with built-in CSS and system fonts, so nothing loads from the internet
- Service worker only removes its own old caches (names starting with `tempering-`), so other apps on the same github.io address are not affected

### Based on
- The original single-file calculator (same formula and unit conversions; verified 30 lbs from 14.0% to 14.5% gives 79.6 g of water)

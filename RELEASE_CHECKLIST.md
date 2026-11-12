# Release checklist — v1.1.0

## What changed in v1.1.0

- Added a third dashboard, **✅ DONE · LAST 7 DAYS**, between the two to-do boxes and `RAW RECORDING`.
- It lists tasks completed in the rolling 7-day window, using the `✅ YYYY-MM-DD` timestamp that the Tasks plugin writes when a checkbox is ticked.
- No new plugin, JavaScript, CSS, or configuration. The two existing query blocks are untouched.

## Content and safety

- [x] Public template and demo contain only fictional example tasks.
- [x] No screenshots of any real work journal are included.
- [x] No company data, customer or supplier data, personal work notes, tokens or credentials are included.
- [x] `Work_Journal_Template.md` and `Demo_Work_Journal.md` use byte-identical Tasks query blocks (three blocks).
- [x] Query blocks 1 and 2 are byte-identical to the accepted v1.0.0 version.
- [x] Query block 3 uses documented Tasks syntax: `done`, `done after 7 days ago`, `path includes {{query.file.path}}`, `sort by done reverse` (Quick Reference, Sorting, Examples).
- [x] The preview illustration is rendered from `Demo_Work_Journal.md` fictional data only. PNG files contain no text or EXIF metadata.

## Functional acceptance

- [x] The seven v1.0.0 core behaviours were validated by the project owner in a **separate, independent Obsidian vault** with the Tasks plugin.
- [x] For v1.1.0, the two existing query blocks were verified byte-for-byte against that accepted version.
- [x] Static checks passed: query syntax, callout order, three-step install, README/template/demo consistency, sensitive-data scan.
- [ ] The new 7-day module awaits the owner's acceptance test in a fresh Obsidian vault (tick a task, confirm it appears with today's date; change a date to >7 days ago, confirm it drops out).

## Publication

- [x] GitHub repository, files, description and topics configured.
- [x] Release `v1.1.0` created with a downloadable ZIP.
- [x] MIT copyright holder confirmed by the owner: **leeliofree**.
- [x] Final public-file and illustration safety review approved by the owner.
- [x] Repository is Public.

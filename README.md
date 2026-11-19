# NutriCheck — Assignment 2 interaction prototype

**README prose word count (approx.):** 435.

## Status

A local, standalone browser prototype supports choosing three scripted cases, inspecting a nutrition suggestion, editing food name and portion, recalculating illustrative totals, rejecting, confirming, receiving feedback and undoing a local save. The interface is functional. **Image recognition, confidence, nutrition estimates and case inputs are simulated.** There is no camera upload, calibrated model, API call, persistent storage or validated dietary guidance. A live vision-and-nutrition pipeline is planned only.

## Technology and file map

- `index.html`: vanilla HTML/CSS/JavaScript; no package manager, external dependencies, network requests or AI model.
- `architecture.svg`: component/control diagram with implemented, simulated and planned labels.
- `storyboards.svg`: three illustrated scripted interactions.
- `report.md` / `Assignment2_Report.docx`: project rationale and references.
- `tests.md`: manual reproduction checklist and expected results.

## Run or inspect

Download the folder, then open `index.html` in a modern browser (or serve it with `python3 -m http.server 8000` and visit `http://localhost:8000`). Choose cases A–C in the left panel. Edit portion size or name, confirm or reject, then test undo and reset. No API key is required or should be committed.

## Development record

1. **Scope decision:** Reduced Assignment 1's ambitious adaptive visual diet tracker to a reproducible human-control prototype. Reason: avoid unverified claims about visual volume, model confidence and dietary accuracy.
2. **Scenario fixtures:** Added three deterministic cases to expose high-reliability review, ambiguous ingredients and erroneous classification. Checked that cases display distinct warnings and state.
3. **Review and repair:** Added visible name/grams fields, proportional illustrative recalculation, reject, explicit save, confirmation message and undo. Checked the local interaction steps described in `tests.md`.
4. **Boundary and documentation:** Added prominent simulation warnings, a diagram with dashed planned API integration, storyboards and report. Checked that no image is uploaded and no external request appears in the source.

This development record describes design stages, **not a fabricated chronological Git history**. If uploading to GitHub, create genuine commits and link the actual final hash here.

## AI assistance and verification

ChatGPT was used to support prototype development and preparation of the diagrams, report, documentation and example test scenarios. The project distinguishes functional browser interactions from simulated AI outputs and future integrations. Before submission, the prototype interactions, technical descriptions, references and diagrams should be checked against the actual files and test results; any corrections made during this review should be documented. The nutrition values are illustrative, not validated dietary advice.

## Publication information (complete after publication)

- Public repository: **[ADD REAL URL]**
- README URL: **[ADD REAL URL]**
- Submitted commit or release: **[ADD REAL HASH OR RELEASE TAG]**
- No additional ZIP is needed once all project files are in the repository.

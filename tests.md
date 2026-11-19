# Manual acceptance checklist

Open `index.html` in a browser. This checklist describes expected outcomes; tick boxes only after personally testing them.

- [ ] Case A: shows 'Grilled chicken and rice', 250 g and a higher-reliability *simulated* label.
- [ ] Case A: Confirm and save displays a local receipt; Undo reports the entry undone.
- [ ] Case B: changing grams 230 → 180 changes the illustrative kcal/protein/fat values proportionally.
- [ ] Case B: warning mentions hidden dressing; numeric range is explicitly illustrative.
- [ ] Case C: warning mentions possible misidentification; editing the food name changes its saved label.
- [ ] Case C: Reject states no meal was saved (and does not create an entry).
- [ ] Entering 0 or >2000 grams prevents saving, with an input warning.
- [ ] Reset clears receipt and restores selected fixture values.
- [ ] Refresh clears volatile saved state.
- [ ] Inspect source/browser network tab: no API key, external AI request, photo upload or persistent storage.

**Limitation to inspect:** Editing the name does not update the nutrient composition; this is a known prototype constraint.

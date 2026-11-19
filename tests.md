# NutriCheck — Manual Interaction Test Record

**Project:** NutriCheck — Intelligent Interactive Systems Assignment 2

**Test date:** 19 November 2026

**Test method:** Manual browser interaction

**System:** Standalone HTML/CSS/JavaScript prototype

## 1. Testing Objective

The purpose of these tests was to verify whether users could review, correct, reject and undo simulated AI-generated nutrition suggestions.

The tests evaluated interface behaviour and feedback, not the accuracy of food recognition or nutritional predictions.

## 2. Completed Tests

| Test ID | Scenario | Action | Observed Result | Status |
|---|---|---|---|---|
| T01 | Scenario A | Select the higher-reliability scenario | Grilled chicken and rice displayed with 250 g and illustrative nutrition values | PASS |
| T02 | Scenario B | Select the uncertain scenario | Salad with dressing displayed with a warning about potentially hidden dressing | PASS |
| T03 | Scenario B | Change portion size from 230 g to 300 g | Illustrative nutritional values updated in response to the changed portion | PASS |
| T04 | Scenario C | Change food name from Pasta with tomato sauce to Beef noodles and confirm | Save confirmation displayed Beef noodles, 280 g | PASS |
| T05 | Scenario C | Reject the suggestion | System displayed: "Suggestion rejected. No meal was saved." | PASS |
| T06 | Scenario C | Save an entry and select Undo last save | System displayed: "Previous local save undone. No meal remains saved." | PASS |

## 3. Additional Checks

The following checks are included for further verification and are not recorded as completed tests.

- [ ] Entering an invalid portion such as 0 g prevents saving.
- [ ] Entering a portion above 2000 g prevents saving.
- [ ] Reset restores the original scenario values and clears feedback.
- [ ] Refreshing the browser clears the volatile saved state.
- [ ] Inspect browser network activity to confirm that no external AI request or image upload occurs.

## 4. Observed Limitation

Changing the food name from Pasta with tomato sauce to Beef noodles did not automatically change the nutritional composition.

This is consistent with the prototype's current implementation, which uses predefined illustrative values rather than a live nutrition database.

A future implementation would need to retrieve or recalculate nutrition values when food classification changes.

## 5. Relevant IIS Design Concepts

**Visibility of System Status:** The interface provides explicit feedback after saving, rejecting and undoing.

**Human Control and Error Recovery:** Users can correct a suggested food label, reject an incorrect suggestion and reverse a local save.

**Gulf of Evaluation:** Visible nutritional estimates and scenario-specific warnings help users inspect the system's proposal before accepting it.

**Uncertainty Communication:** Scenario B demonstrates a warning for ambiguous ingredients. Its uncertainty values are illustrative rather than statistically calibrated.

## 6. Test Conclusion

The observed tests passed for scenario selection, portion editing, food-label correction, rejection and undo feedback.

These observations provide evidence of developed interaction behaviour. They do not establish AI prediction accuracy, dietary validity, usability improvements or effectiveness with real users.

Further testing would be needed before deployment beyond the current educational prototype.

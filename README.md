# NutriCheck — Assignment 2 Interaction Prototype

**README prose word count (approx.):** 510 words.

## 1. Project Status

NutriCheck is a browser-based interactive prototype developed for the Intelligent Interactive Systems module at the University of Birmingham.

The prototype explores how users can review, correct and control AI-generated food recognition and nutrition suggestions, particularly when predictions are uncertain or incorrect.

The implemented interface supports:

- Three predefined food recognition scenarios.
- Displaying simulated food recognition and nutritional information.
- Editing food names and portion sizes.
- Proportional recalculation of illustrative nutritional values.
- Accepting or rejecting suggestions.
- Explicit save confirmation and undo functionality.
- Contextual warnings for uncertain predictions.

**Current limitations:** Food recognition, confidence labels and nutritional estimates are simulated. The prototype does not use a live computer-vision model, nutritional database, camera input, external API or persistent storage.

Future development could integrate image recognition, calibrated uncertainty estimates and validated nutritional information.

## 2. Technology Stack

- **HTML5:** Interface structure and interactive forms.
- **CSS3:** Visual layout, feedback and responsive presentation.
- **JavaScript:** Scenario selection, input handling, nutritional recalculation and interaction state management.
- **SVG:** System architecture diagram and interaction storyboards.
- **AI tools:** ChatGPT assisted with prototype development, documentation and design illustrations.

The prototype requires no external libraries, API keys or installation of additional packages.

## 3. Project Files

| File | Description |
|---|---|
| `index.html` | Functional interactive prototype |
| `architecture.svg` | System architecture and information flow |
| `storyboards.svg` | Three illustrated interaction scenarios |
| `tests.md` | Manual testing checklist and expected results |
| `report.md` | Assignment 2 report and references |

## 4. How to Run

1. Download or clone this GitHub repository.
2. Open `index.html` in a modern web browser.
3. Select Scenario A, B or C.
4. Review the simulated food suggestion.
5. Modify the food name or portion size.
6. Confirm, reject, undo or reset the interaction.

Alternatively, run a local HTTP server:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

No API key is required.

## 5. Development Record

**Stage 1 — Project scope**

The initial proposal from Assignment 1 focused on adaptive confidence-driven nutrition tracking. The scope was narrowed to an interactive prototype demonstrating user control and error recovery without claiming validated AI prediction accuracy.

**Stage 2 — Scenario development**

Three deterministic scenarios were created to represent different interaction conditions:

- Scenario A: Higher-reliability food suggestion.
- Scenario B: Uncertainty caused by potentially hidden ingredients.
- Scenario C: Incorrect suggested food classification.

Each scenario provides distinct interface feedback.

**Stage 3 — Interaction design**

Editable food labels and portion sizes were introduced alongside explicit confirmation, rejection and undo actions. These choices support user control, visibility of system status and recovery from incorrect AI suggestions.

**Stage 4 — System documentation**

The architecture diagram distinguishes implemented interface behaviour, simulated AI functionality and planned integrations. Three storyboards illustrate how users interact with the system.

**Stage 5 — Manual interaction verification (19 November 2026)**

The browser prototype was manually tested using its predefined scenarios.

| Test | Observed result | Status |
|---|---|---|
| Scenario B: Change portion from 230 g to 300 g | Illustrative nutritional values updated | PASS |
| Scenario C: Change food label to Beef noodles | Updated name appeared in save confirmation | PASS |
| Scenario C: Reject suggestion | System confirmed that no meal was saved | PASS |
| Scenario C: Undo previous save | System confirmed that the local save was undone | PASS |

These checks support the implemented interaction behaviour. They do not validate AI recognition accuracy or nutritional estimates.

## 6. AI Assistance and Verification

ChatGPT was used to assist with prototype development, interface implementation, system diagrams, storyboards, report preparation and documentation.

The generated materials were reviewed through manual interaction testing. The portion-editing, correction, rejection and undo behaviours described above were checked in the browser.

The system distinguishes simulated AI outputs from functional interaction controls. Nutritional values and reliability labels are illustrative and should not be used for real dietary decisions.

## 7. Publication Information

**Public GitHub repository:**

https://github.com/jxy661/NutriCheck-IIS

**README:**

https://github.com/jxy661/NutriCheck-IIS/blob/main/README.md

**Initial project commit:**

`77670502076997fcfcdfee049a135a7e1b044930`

**Submitted final commit:** To be recorded after final documentation updates.

All necessary prototype and documentation files are maintained in the repository. No additional ZIP is required for the current project.

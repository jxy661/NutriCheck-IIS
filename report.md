# NutriCheck: A Human-Controlled Prototype for Reviewing Image-Based Nutrition Estimates

**Assignment 2 — Project Report**  
**Total counted words: 1199**  
**Abstract words: 192 | Main report words: 1007**  
**Repository:** [INSERT PUBLIC GITHUB URL AFTER PUBLISHING]  
**README:** [INSERT README URL AFTER PUBLISHING]  
**Submitted commit:** [INSERT EXACT COMMIT HASH AFTER PUBLISHING]

## Abstract

Image-based food logging promises to reduce manual entry, but a recognisable food label does not establish its portion size or hidden ingredients. A single nutrition estimate may therefore appear more certain than its evidence warrants. NutriCheck explores how a person can inspect, correct and accept a system suggestion without being forced through the same level of checking every time. Building on my first literature review, I developed a browser-based interaction prototype with three scripted cases: an easily recognised meal, a salad with potentially hidden dressing, and an incorrect food label. The prototype displays a proposed food and portion, offers contextual warnings for ambiguous cases, recalculates illustrative nutrition values after portion edits, and requires explicit confirmation before a temporary entry is recorded. Rejection, visible feedback and undo support recovery. All recognition outputs, reliability categories and nutritional values are simulated fixtures rather than model predictions; the application does not accept photographs, call an AI service or persist dietary records. This deliberately limited scope makes user control and error handling inspectable before integrating a calibrated vision and nutrition pipeline. The project demonstrates the interaction loop, not the accuracy or health suitability of automated dietary assessment.

## Design rationale and project explanation

### Problem, evidence and revised scope

Assignment 1 proposed an adaptive confidence-driven interface for nutrition tracking. Its feedback rated literature synthesis as limited and warned that a reference might be suspect. I revisited the evidence rather than treating every earlier claim as established. Mezgec and Koroušić Seljak (2017) investigate image recognition of food and drinks; recognition performance should not be mistaken for validated portion measurement. Buçinca, Malaya and Gajos (2021) find that cognitive forcing can reduce overreliance on AI advice, but also increases effort. These studies address different tasks, so neither proves that a specific correction widget improves food logging. They instead motivate a testable interaction question: can selective review expose uncertainty without making every entry burdensome?

The deliverable is consequently a small, inspectable simulation rather than an unsupported full AI nutrition tracker. Three predefined cases allow reviewers to reproduce the same states. A real camera, food classifier, ingredient detection, nutrition database and calibrated probabilities are planned, not implemented. This change also avoids presenting invented confidence scores as scientific measures.

### Make inferences visible, not authoritative

Lecture 02 defines an intelligent interactive system through sensing, uncertain interpretation, action and a closed human loop. NutriCheck currently simulates sensing and interpretation; the real interaction occurs when the user examines a proposal, changes it and receives an updated state. The system explicitly labels the prediction as simulated. Lecture 08 explains why fluent outputs are not evidence; although outside the requested Weeks 1–4 emphasis, its point reinforces the boundary: the prototype never claims to have visually inspected an image.

The prominent food name, editable grams and illustrative nutrient totals narrow Norman's (2013) gulf of evaluation (Lecture 06): the user can see what the system proposes and what changes after an edit. I avoided an unexplained percentage confidence badge. Instead, the prototype uses qualitative, scenario-specific reliability labels and directly names uncertainty, such as hidden dressing. These labels are design prompts, not calibrated measurements. A future model would need independent evaluation before probability-based ranges or thresholds could be defensible.

### Selective attention and workload

Lecture 04 shows that feedback must compete for attention; information being visible does not guarantee that it will be noticed. The higher-reliability script therefore has a short, quiet review path. The ambiguous scripts display a warning next to the relevant fields. This is intended to direct attention to the uncertainty that matters, rather than repeatedly showing a general disclaimer. It does not claim that the warning improves detection without a user study.

Lecture 05 distinguishes recognition from recall and describes limited working memory. NutriCheck shows the current food, portion and estimates together, rather than requiring users to remember a spoken result or enter everything from scratch. Three grouped quantities make the proposal reviewable. Editable values remain on screen while the user corrects them. The trade-off is that extra prompts could become irritating; the prototype deliberately avoids forcing a confirmation after every individual field edit.

### Control, error recovery and action boundaries

The primary interaction follows Amershi et al.'s (2019) guidance to make capabilities clear (G1), support efficient correction (G9), explain behaviour (G11), and show consequences (G16). The user can correct a mislabelled food, change grams, reject a suggestion or explicitly save it. Confirmation is required for a save even in the straightforward scenario. A receipt states that the record exists only in the current page session, and undo removes that saved state. These choices follow the human-control emphasis in Lecture 03 and the distinction between slips, mistakes and system inference errors in Lecture 06.

The interface does not silently substitute its estimate for the person's judgement. This is a deliberate mixed-initiative decision: the system offers a bounded suggestion; the user decides whether to act. However, a choice to confirm is not proof that the estimate is correct. With no real nutritional model, correcting the food name does not recompute food-specific composition; only portion scaling is implemented. This limitation is visible in the README and must be addressed before any real dietary use.

### Architecture and development evidence

Figure 1 distinguishes four connected parts: scripted case input, simulated prediction data, implemented review controls, and a volatile local save/undo state. The browser executes deterministic calculations when grams change. There is no remote model, data transmission or persistent database. Keeping the proposal separate from the saved entry allows an error to be rejected before it becomes a record. The planned model API is drawn with a dashed edge rather than implying an existing integration.

The development record in the README explains the scope reduction from Assignment 1, creation of repeatable fixtures, addition of warnings and correction controls, and explicit labelling of simulated outputs. The three storyboards show acceptance, portion correction and label rejection. They demonstrate possible interactions but not measured user performance. The artefacts can be inspected by opening `index.html` locally, without dependencies or an API key.

### Demonstrating the interaction

In storyboard A, the reviewer selects the recognisable-meal fixture, checks the suggested portion and saves it; the receipt and undo button make the consequence observable. In storyboard B, a warning about hidden dressing prompts the reviewer to reduce the proposed grams. The nutrient numbers change proportionally, and the interface does not pretend to infer previously unseen oil. In storyboard C, the label is deliberately wrong. The reviewer can replace the label or reject the suggestion entirely, with no automatic save. These contrastive cases illustrate both a normal path and two repair paths. They also expose an unresolved design issue: changing a label without accessing a nutrient database cannot produce a trustworthy new estimate.

### Limitations and next evaluation

This prototype establishes interaction behaviour, not classifier accuracy, calibrated uncertainty, lower fatigue or improved trust. Nutrition values are invented examples and must not guide health decisions. Future work should connect a validated source, test whether uncertainty labels correspond to errors, and compare selective review with an always-confirm baseline. A small within-participant study could measure correction accuracy, time, inappropriate acceptance and perceived effort, including cases where the prediction is confidently wrong. Such results would determine whether adaptive review supports calibrated reliance rather than merely giving that impression.

## Figures

**Figure 1.** System architecture, indicating implemented review and undo, simulated inference and planned model integration (see `architecture.svg`).

**Figure 2.** Three scripted journeys covering straightforward acceptance, uncertain-portion correction and incorrect-label recovery (see `storyboards.svg`).

## References

Amershi, S. et al. (2019) ‘Guidelines for Human-AI Interaction’, *Proceedings of CHI 2019*. https://doi.org/10.1145/3290605.3300233

Buçinca, Z., Malaya, M.B. and Gajos, K.Z. (2021) ‘To Trust or to Think: Cognitive Forcing Functions Can Reduce Overreliance on AI in AI-Assisted Decision-Making’, *Proceedings of the ACM on Human-Computer Interaction*, 5(CSCW1). https://doi.org/10.1145/3449287

Mezgec, S. and Koroušić Seljak, B. (2017) ‘NutriNet: A Deep Learning Food and Drink Image Recognition System for Dietary Assessment’, *Nutrients*, 9(7), 657. https://doi.org/10.3390/nu9070657

Norman, D.A. (2013) *The Design of Everyday Things*, revised and expanded edn. Basic Books.

University of Birmingham (2026) *Intelligent Interactive Systems*, Lectures 02–06 and 08, course materials supplied for the module.

# Visual review and acceptance gates

A screen is not finished when the code compiles. It is finished when the running interface communicates the right hierarchy, behaves correctly, and remains legible across the supported environments.

## Required review loop

### 1. Prepare representative content

Use realistic content and values. Include:
- A short and a long title.
- A long description or translated string.
- Large and small numeric values.
- Empty and populated list states.
- At least one error or unavailable state.
- The longest expected label or identifier.

Placeholder data that is too short can hide layout defects.

### 2. Capture representative viewports

At minimum, when the environment supports them:
- Small phone width around 360 dp.
- Common phone width around 390–400 dp.
- Large phone width.
- Tablet or expanded window if supported.
- Landscape if supported.

Capture light and dark themes. Check large system text and reduced motion. Do not infer one theme from the other.

### 3. Inspect the running app

Review the screenshots at actual rendered size. Check:
- First-glance hierarchy: can a user identify the screen purpose and primary action immediately?
- Alignment: do edges, baselines, icon centers, and control positions line up?
- Rhythm: are related items close and separate groups clearly distinct?
- Density: is the amount of information appropriate for the task frequency?
- Typography: are titles, body text, metadata, and numbers clearly differentiated?
- Copy density: does every visible string serve navigation, identity, value, action, feedback, or essential guidance?
- Explanatory noise: are there subtitles beneath obvious headings, descriptions beneath every setting, duplicated labels, decorative captions, or tiny gray filler text?
- Surfaces: do containers clarify grouping, or are they redundant?
- Color: is accent reserved for meaningful emphasis and are semantic states clear?
- Shape: are radii consistent and appropriate to the platform?
- Interaction: do pressed, selected, focused, disabled, and loading states read correctly?
- Safe areas: is anything hidden under system bars, a keyboard, or a fixed bottom control?
- Text resilience: do long strings, localization, and larger font sizes clip or overlap?
- Scroll behavior: can users reach the final content and operate controls near the edges?

### 4. Run a visible-copy audit

Inventory every visible string, including subtitles, captions, metadata, helper text, and footnotes. Classify each as navigation, identity, value, action, feedback, or essential guidance. Delete anything that does not fit. Remove repeated information and explanations that merely restate an obvious control. Keep only the shortest copy needed for permissions, destructive actions, advanced settings, validation, errors, and useful empty states.

Do not make the interface cryptic: preserve visible form labels, meaningful status, and accessibility semantics. Read [copy-discipline.md](copy-discipline.md) for the complete rules.

### 5. Exercise interactions

Test at least:
- Primary navigation and back.
- The main action on the screen.
- One selection or toggle.
- One sheet or dialog if present.
- Form entry and keyboard behavior if present.
- Loading and error feedback if asynchronous work exists.
- Scroll behavior and fixed controls.

### 6. Fix in impact order

Fix issues in this order:
1. Broken task flow, incorrect information hierarchy, or inaccessible controls.
2. Clipping, overlap, unreachable content, safe-area problems, or broken navigation.
3. Weak contrast and unreadable typography.
4. Inconsistent spacing, alignment, or component geometry.
5. Redundant cards, borders, shadows, and accent fills.
6. Decorative details and motion polish.

After fixes, capture screenshots again. Do not claim the visual issue is resolved based only on source edits.

## Review score

Score each area from 0 to 5:

| Area | 0 | 3 | 5 |
|---|---|---|---|
| Task clarity | Primary task is unclear | Main task is discoverable | Main task and next action are immediately clear |
| Hierarchy | Competing elements | Mostly clear hierarchy | Strong, calm reading order |
| Layout and rhythm | Arbitrary or broken | Mostly consistent | Deliberate spacing, alignment, and density |
| Typography | Inconsistent or clipped | Readable but uneven | Clear roles, resilient text, excellent scanning |
| Copy discipline | Explanatory clutter or missing essential labels | Mostly concise, with some redundant copy | Every visible string earns its place |
| Color and surfaces | No semantic logic | Mostly coherent | Restrained, accessible, meaningful |
| Components | Inconsistent patterns | Reuse with some drift | Consistent components with correct states |
| Platform behavior | Breaks conventions | Mostly native | Natural navigation, gestures, insets, and input |
| Accessibility | Major barriers | Basic support | Contrast, semantics, scaling, and motion are verified |
| Visual polish | Generic or unfinished | Usable and coherent | Distinctive and carefully refined |

Maximum: 50 points.

Suggested acceptance:
- 44–50: ready for delivery, provided no critical blocker remains.
- 37–43: good, but fix the lowest-scoring high-impact areas.
- Below 37: revise the design direction or implementation before delivery.

A score is a review aid, not a substitute for judgment. Never average away a critical defect.

## Critical blockers

Any of these blocks delivery regardless of score:
- A primary action is missing, ambiguous, or non-functional.
- Text or controls are clipped in a supported viewport.
- A critical control is unreachable or hidden by the keyboard/system UI.
- Normal text or meaningful icons have insufficient contrast.
- A critical state is communicated only by color.
- Back navigation or modal dismissal traps the user.
- Repeated explanatory microcopy or duplicated small captions dominate the screen and obscure its hierarchy.
- The UI has not been run and the final response claims visual verification.

## Honest reporting

If runtime screenshots or device testing were unavailable, state exactly what was checked:
- Static code review.
- Build or compile result.
- Unit or UI test result.
- Screenshot verification: not run.

Never say "looks good on device" without device evidence.

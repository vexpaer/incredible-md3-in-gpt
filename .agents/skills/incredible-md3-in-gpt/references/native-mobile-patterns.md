# Native mobile patterns

Use these patterns as decision aids, not rigid templates. Choose the pattern that matches the user's task, the platform, and the amount of information on screen.

## Navigation

Start from the user's mental model:
- Use a small set of primary destinations for distinct top-level tasks.
- Use tabs for sibling views within one destination, not as a substitute for information architecture.
- Use a navigation drawer or rail when the number of destinations and screen width justify it.
- Keep back behavior predictable and preserve context when users return from details or editors.
- Do not add a bottom navigation bar to every app by default.
- Do not overload a navigation bar with secondary actions.
- On larger windows, reconsider the navigation pattern rather than stretching a phone layout.

For Android, follow current Android navigation guidance and system back behavior. For iOS, follow HIG navigation conventions and platform gestures. For cross-platform apps, adapt where user expectations differ.

## Settings

Settings are usually a scannable list, not a dashboard of cards.

Recommended structure:
- Group related settings under clear section headings.
- Use a concise title and optional supporting description.
- Put the current value or control at the trailing edge when it remains understandable.
- Use dividers or spacing to distinguish groups; avoid wrapping every row in an independent card.
- Keep destructive actions visually distinct and confirm only when the consequence warrants it.
- Use a detail page or sheet for complex settings instead of crowding the root settings list.
- Make state changes visible and reversible when possible.

A settings row should answer: what does this control change, what is its current state, and what happens when I activate it?

## Dashboards

A dashboard should surface the few facts and actions users need repeatedly.

- Put the highest-value status or action first.
- Use a clear reading order; avoid making every module equally prominent.
- Use cards only when a module is a meaningful independent group.
- Keep metric labels close to values and use tabular numerals for changing numbers.
- Avoid a grid of equal cards if the information has a natural ranking or sequence.
- Allow optional modules only when personalization is a real product need.
- Design empty, disconnected, loading, and error states as part of the dashboard.

For data-heavy dashboards, choose a compact density and strong typographic hierarchy rather than inflating every metric into a hero.

## Lists and detail views

Lists should make comparison and scanning easy.

- Choose row height based on content, not a universal fixed value.
- Use consistent leading alignment for icons, titles, metadata, and values.
- Place secondary actions in a predictable overflow or context menu.
- Use dividers only when they improve grouping or scanning.
- Support long titles, multi-line descriptions, and large text.
- Keep list selection visible without recoloring the entire list.
- In detail screens, group related fields and make the primary action obvious.

## Forms and editors

- Use visible labels; placeholders are examples or hints, not the only label.
- Group fields by meaning and sequence.
- Explain constraints before users make an error.
- Validate near the relevant field and preserve valid input after errors.
- Use appropriate keyboard types and input actions.
- Keep the primary submit action visible when the keyboard is open, without obscuring fields.
- Distinguish saving, saved, failed, and unsaved states.
- Provide cancel or back behavior that makes data-loss consequences clear.
- Use a sheet for a focused task; use a full screen when the task is complex or requires substantial context.

## Dialogs and sheets

Use a dialog for a short, focused decision. Use a sheet for a task that benefits from seeing the underlying context or has a natural partial-height presentation.

- Keep one primary decision or action per dialog.
- Make dismissal and cancellation behavior predictable.
- Do not put a long, multi-field form into a tiny alert dialog.
- Respect keyboard insets and safe areas.
- Ensure content remains scrollable when the keyboard and window leave insufficient room.
- Use a scrim that separates the modal from the underlying content without destroying context.
- Choose detents or heights based on the task and content; do not use arbitrary fixed heights that clip text.

## Loading, empty, offline, and error states

A polished app defines more than the successful state.

- Loading: communicate that work is happening; preserve layout stability.
- Empty: explain why there is no content and offer the next useful action when one exists.
- Offline: distinguish unavailable network data from an empty result.
- Error: describe the problem in user language and provide a recovery action where possible.
- Permission required: explain why the permission is needed at the moment it becomes relevant.
- Success: confirm the completed action and expose the resulting state.
- Disabled: show why an action cannot be taken when that reason is not obvious.

Avoid skeletons or spinners as decoration. Choose feedback based on expected wait, content structure, and platform convention.

## Adaptive layouts

Responsive means the content fits. Adaptive means the interaction model remains usable.

Test and adapt for:
- Compact and expanded window widths.
- Portrait and landscape.
- Phones, tablets, and foldables when supported.
- Split-screen or resizable windows when supported.
- Keyboard and pointer input where relevant.
- System text scaling and localization.

Do not simply stretch a phone column across a tablet. Reconsider navigation, content width, multi-pane layouts, and the amount of simultaneous information.

## Touch, accessibility, and system behavior

- Use touch targets of at least 48 dp on Android and 44 pt on iOS as a baseline.
- Keep sufficient spacing between adjacent controls.
- Provide visible feedback for every interactive control.
- Give icon-only actions accessible names and expose selected, checked, expanded, and disabled states.
- Do not rely on color alone.
- Respect safe areas, system bars, and gesture insets.
- Preserve platform back gestures and do not capture system gestures unnecessarily.
- Support larger text without clipping or overlap.
- Respect reduced-motion settings.
- Check screen-reader order and semantics.

## Platform and framework routing

- Android native: use current Android Design guidance and Material 3 / Material 3 Expressive where appropriate.
- Jetpack Compose: use MaterialTheme semantic roles and current Compose APIs; check official docs for experimental APIs.
- Flutter: use adaptive/responsive guidance, MediaQuery, and layout constraints; do not hardcode phone dimensions.
- SwiftUI: use HIG, Dynamic Type, safe areas, and adaptive layout APIs.
- React Native: inspect whether the app is intended to feel native on iOS, Android, or both; use platform-specific behavior where needed.

Do not assume a web CSS pattern maps cleanly to a native framework. If the stack is unknown and implementation-specific guidance would change the solution, inspect the project or ask one focused question.

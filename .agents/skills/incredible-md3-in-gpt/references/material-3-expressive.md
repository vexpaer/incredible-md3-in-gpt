# Material 3 Expressive: practical design guidance

Material 3 Expressive (M3 Expressive) is an expansion of Material Design 3, not a separate unrelated design system. Google's current Jetpack Compose documentation describes it as research-backed updates to theming, components, motion, typography, and more, while retaining Material You personalization such as dynamic color.

Use it as a richer design vocabulary. Do not interpret "expressive" as permission to add decoration everywhere.

## 1. What becomes more expressive

M3 Expressive develops several parts of the system together:

- **Color:** richer tonal palettes and more contextual color roles, while semantic foreground/background relationships remain coherent.
- **Typography:** stronger hierarchy and variable-font expression where supported.
- **Shape:** a broader shape language, expressive containers, and shape relationships or morphing.
- **Components:** more differentiated component forms and layouts that help important actions stand out.
- **Motion:** more spatial transitions, spring behavior, and motion that communicates relationships and state.
- **Layout:** stronger hierarchy and more deliberate use of space, especially around high-value actions and content.

These dimensions should reinforce one another. A large expressive shape with no semantic purpose, an animated switch that adds delay, or a saturated accent behind every card is not good M3 Expressive design.

## 2. Expression should strengthen hierarchy

Start from the user task and decide where expression has the highest value.

Good candidates:
- The primary action or current mode.
- A meaningful status or milestone.
- A distinctive empty state.
- A key transition between related surfaces.
- A content type whose identity benefits from stronger typography or shape.

Keep routine information quiet. Repeated rows, dense technical data, logs, and frequently used settings usually benefit from restrained typography, neutral surfaces, and compact controls. Give one or two moments emphasis rather than making every element compete.

Do not force a hero moment onto every screen.

## 3. Color: richer roles, not more random colors

- Define light and dark semantic schemes together.
- Use dynamic color when wallpaper personalization supports the product; retain a stable brand seed when identity or status recognition requires it.
- Use primary, secondary, and tertiary roles for deliberate hierarchy, not as arbitrary decoration.
- Keep surface roles coherent and preserve legible on-color pairings.
- Reserve error, warning, and success for their semantic meanings.
- Do not fill every card or list row with primaryContainer, secondaryContainer, or tertiaryContainer.
- Verify contrast after dynamic color is applied; a user-selected seed must not make error and warning indistinguishable.

A richer palette should make information easier to understand, not make the screen busier.

## 4. Shape: build relationships, not a pile of rounded rectangles

- Use a small, deliberate shape vocabulary.
- Choose shape according to component role, size, and containment.
- Let related shapes communicate grouping or interaction.
- Use expressive shapes for a few meaningful containers, illustrations, or transitions.
- Consider shape morphing only when it clarifies a state change or spatial relationship.
- Do not make every card, button, chip, and sheet maximally rounded.
- Avoid mixing arbitrary radii with system shape tokens.

FlClash's UI work guide is a useful example: it references a Material 3 Expressive shape from `material_new_shapes` for an empty-state glyph while keeping the surrounding interface disciplined. Pair this with Apple's product principles and restrained minimalism: expressive moments should strengthen the task hierarchy, not turn every surface into decoration.

## 5. Typography: create hierarchy without inflating everything

- Use expressive type roles for moments that deserve attention.
- Keep utility data, settings labels, logs, and secondary metadata compact and readable.
- Use variable font axes only when the platform and chosen font actually support them.
- Do not make every page title oversized.
- Do not add explanatory subtitles to create a false sense of hierarchy; use size, weight, spacing, alignment, and surface structure.
- Test localization and enlarged system text.

Typography should make the important content recognizable at a glance.

## 6. Motion: spatial, purposeful, interruptible

- Prefer motion that explains where content came from, where it goes, or how state changed.
- Use spring motion when it makes direct manipulation or spatial transitions feel responsive.
- Use shape morphing for related states, not as a perpetual flourish.
- Keep taps and primary actions responsive; decorative motion must not delay task completion.
- Respect reduced-motion preferences.
- Ensure interrupted or reversed transitions leave state correct.
- Avoid animating every card or row as it enters the screen.

Motion should improve orientation and feedback, not demand attention.

## 7. Platform and framework implementation

### Android native / Jetpack Compose

Use the current official [Material 3 in Compose documentation](https://developer.android.com/develop/ui/compose/designsystems/material3). It documents both Material You and M3 Expressive support. Check the actual dependency version and API stability before using a component or expressive API; do not invent API names or assume every API is stable.

Use the system's MaterialTheme roles and components where they fit. Customize tokens and component choices through a shared theme instead of styling screens independently.

### Flutter

Flutter apps do not automatically receive every Jetpack Compose M3 Expressive component. Inspect the current Flutter and package APIs before implementation. FlClash is a useful case study because it builds its own reusable UI layer and uses expressive shape elements alongside a custom surface and interaction system.

Do not claim full framework conformance just because a few expressive shapes or animations are present.

### iOS / SwiftUI

Use Apple Human Interface Guidelines and native SwiftUI behavior as the platform authority. Borrow transferable M3 Expressive ideas—clearer hierarchy, purposeful shape, meaningful motion, and thoughtful typography—without forcing Android-specific controls or navigation onto iOS.

### Cross-platform

Share semantic design tokens and product identity, but adapt navigation, sheets, system bars, gestures, and component behavior to each platform. Do not mistake identical screenshots for consistency.

## 8. A restrained expressive design recipe

For a utility or productivity app:
1. Keep the main canvas and repeated rows neutral.
2. Use expressive typography for the one most important value or page heading only when the content warrants it.
3. Use one distinctive shape or visual treatment for a meaningful primary action or status.
4. Use motion for state changes and navigation, not ambient decoration.
5. Keep settings and technical information compact.
6. Apply the minimal-copy policy: no explanatory microcopy unless it changes a decision or enables a safe action.
7. Review the full screen at real phone size. If the expressive treatment competes with the task, reduce it.

For a media, creative, or lifestyle app, the product may support more expressive color, typography, and motion. The same hierarchy and accessibility rules still apply.

## 9. Review checklist

- [ ] Is the visual direction intentionally M3 Expressive, or is classic M3 the better fit?
- [ ] Does each expressive treatment reinforce a real task or hierarchy?
- [ ] Are color roles semantic and contrast-safe in light, dark, and dynamic themes?
- [ ] Are shapes consistent and meaningful rather than randomly rounded?
- [ ] Does typography distinguish important content without inflating every heading?
- [ ] Does motion communicate state or spatial relationships?
- [ ] Are routine settings and dense information kept calm and compact?
- [ ] Have platform-specific conventions and actual API support been checked?
- [ ] Has the minimal visible-copy audit passed?
- [ ] Has the running UI been inspected at representative phone sizes?

## Sources

- [Material Design 3 in Jetpack Compose](https://developer.android.com/develop/ui/compose/designsystems/material3) — official explanation of M3 Expressive as an expansion of Material Design 3, including theming, components, motion, typography, and Material You personalization.
- [A more personal, expressive phone experience](https://blog.google/products-and-platforms/platforms/android/material-3-expressive-android-wearos-launch/) — Google's Android announcement describing how M3 Expressive builds on Material You for phones and adds spring motion, dynamic color, responsive components, and emphasized typography.
- [Benefits of expressive design](https://developer.android.com/design/ui/wear/guides/get-started/benefits) — Google's research background and guidance to start from user needs, prioritize functionality, preserve accessibility, and iterate.
- [Levels of expression](https://developer.android.com/design/ui/wear/guides/get-started/levels-expression) — examples of foundational, excellent, and transformative expression across components, color, typography, shape, motion, and adaptive design.
- [FlClash surface rules](https://github.com/chen08209/FlClash/blob/main/.agents/surfaces.md) — surface levels, tonal hierarchy, state color, and elevation.
- [FlClash UI work skill](https://github.com/chen08209/FlClash/blob/main/.agents/skills/ui-work/SKILL.md) — the explicit Material 3 Expressive empty-state shape reference.


## 10. Keep expressive treatments compatible with minimalism

Use M3 Expressive as a richer vocabulary inside a restrained composition. Choose one or two moments where expressive shape, typography, color, or motion makes the task or state easier to recognize. Keep repeated rows, settings, logs, and dense data calm.

Apple-inspired product principles can guide purpose, agency, simplicity, and craft across platforms, but use the target platform's own navigation and component conventions. See [apple-design-principles.md](apple-design-principles.md).

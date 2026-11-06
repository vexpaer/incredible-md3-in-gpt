# Apple design principles and platform-aware minimalism

This guide translates Apple's current Human Interface Guidelines (HIG) design principles into practical product-design requirements for this mobile skill.

Apple's current design-principles page uses eight principles: **Purpose, Agency, Responsibility, Familiarity, Flexibility, Simplicity, Craft, and Delight**. The page's change log records its reintroduction on June 8, 2026. Use this current framework rather than treating the older Clarity / Deference / Depth triad as the complete current model.

## 1. The eight principles as implementation requirements

### Purpose — make the product useful

- Identify the user's primary job before drawing screens.
- Prioritize the tasks people return to most often.
- Remove features, labels, and visual treatments that do not support a real user need.
- Give the first screen a clear purpose and a useful next action.

### Agency — keep people in control

- Let people reach the task directly; do not force unnecessary onboarding or predetermined flows.
- Make navigation, dismissal, cancellation, and back behavior predictable.
- Provide undo or recovery for actions that can be reversed.
- Confirm destructive actions when the consequence warrants it.
- Show meaningful progress and current state. Never leave a control apparently active without feedback.

### Responsibility — earn trust

- Ask for permissions at the point of need and explain the reason in plain language.
- Collect and expose only the information the product needs.
- Make privacy-sensitive behavior, recording, sharing, and destructive operations understandable.
- Design safe defaults and accessible states from the beginning.

### Familiarity — build on learned patterns

- Use established platform conventions for common actions and controls.
- Keep visually similar controls behaviorally consistent.
- Use recognizable labels and icons; do not invent metaphors for familiar actions without a strong reason.
- Keep action placement and navigation behavior predictable.

### Flexibility — adapt to real contexts

- Support the screen sizes, orientations, text sizes, and input modes in scope.
- Preserve user context when layouts adapt.
- Support accessibility settings, keyboard and pointer input where relevant, and reduced motion.
- Offer customization when users have genuinely different workflows; do not add preference controls without a real need.

### Simplicity — remove friction

- Make the next useful action easy to find.
- Use concise, plain-language labels and a strong information hierarchy.
- Remove redundant steps, repeated information, and decorative UI.
- Keep necessary context visible when it helps people make an informed decision.
- Do not hide essential functionality behind obscure gestures, nested menus, or unlabeled icons.

Apple explicitly distinguishes simplicity from minimalism: a visually sparse interface can still be difficult if it hides functionality. In this skill, minimalism is a visual discipline; simplicity is the quality of the complete user experience.

### Craft — finish every detail

- Align typography, spacing, icons, and component geometry precisely.
- Make controls responsive and transitions smooth without sacrificing performance.
- Design loading, empty, error, offline, disabled, and success states.
- Verify behavior on real device sizes and with accessibility settings.
- Iterate after inspecting the running interface; a successful build is not proof of good design.

### Delight — create a fitting emotional quality

- Decide what the product should make people feel: calm, confident, focused, energetic, or something else grounded in its purpose.
- Create memorable moments through useful feedback, thoughtful transitions, and careful details.
- Do not add confetti, decorative motion, or novelty for its own sake.
- Delight should emerge from the quality of the whole experience.

## 2. Apple-inspired minimalism as the default visual posture

Use **restrained, product-specific minimalism** as the default visual direction. It should feel intentional, calm, legible, and carefully crafted.

### Composition

- Establish one clear focal point per screen. A second emphasis is acceptable only when the task genuinely has two equally important parts.
- Keep the surrounding interface quiet so the primary content or action stands out.
- Use whitespace, alignment, typography, and tonal contrast before adding borders or cards.
- Group related content without wrapping every row or section in a separate container.
- Use a small, coherent set of surface levels.
- Keep repeated settings, logs, and dense data visually calm and scannable.

### Color

- Start with a compact set of brand anchor colors, then map them to semantic roles and complete light/dark schemes.
- Prefer neutral or subtly tinted backgrounds. Reserve saturated color for a meaningful action, selected state, or semantic status.
- Avoid using gradients, blur, glow, and multiple accent colors as empty decoration.
- Preserve contrast and do not encode state through color alone.

### Typography

- Use a deliberate type scale and a small number of type families.
- Give headings, body text, values, and controls distinct roles.
- Avoid oversized titles on operational screens and decorative labels above ordinary content.
- Preserve readable text sizes and system text scaling. Never create minimalism by shrinking important text.

### Shape, materials, and motion

- Use a small shape vocabulary; do not maximize corner radii on every element.
- Use borders, shadows, blur, and translucent materials only when they communicate grouping, hierarchy, or layering.
- Prefer immediate, subtle interaction feedback.
- Keep non-interactive motion rare. Use animation to explain state or spatial change, not to keep the screen moving.
- Respect reduced-motion preferences.

### Functional minimalism

- Keep common actions discoverable and close to the content they affect.
- Do not remove labels from controls when their meaning is not universally obvious.
- Do not collapse useful information into extra taps just to make the first screen look empty.
- Do not sacrifice accessibility, status visibility, error recovery, or user control for visual sparseness.
- Apply the minimal-copy policy in [copy-discipline.md](copy-discipline.md).

## 3. Apple-inspired does not mean copying Apple's interface

Apple HIG is the platform authority for iOS and Apple platforms. For Android, current Android Design guidance and Material 3 / Material 3 Expressive remain the platform authorities. The eight principles above are useful product-design qualities across platforms, but native interaction patterns are not interchangeable.

- **iOS / SwiftUI:** use HIG navigation, system controls, sheets, gestures, safe areas, Dynamic Type, and accessibility behavior. Prefer native components unless the product has a strong reason to depart.
- **Android / Jetpack Compose:** use Android navigation and system-back behavior, Material components, semantic MaterialTheme roles, and M3 Expressive APIs where supported. Do not transplant iOS navigation or control conventions.
- **Flutter / cross-platform:** share brand tokens and product principles, then adapt navigation, sheets, gestures, system bars, and controls to each platform. Inspect actual framework support rather than claiming full conformance to another platform's design system.

Borrow Apple's attention to clarity, agency, consistency, adaptability, and craft. Do not copy Apple's exact screens, assets, iconography, typography, or system chrome into another platform.

## 4. Review checklist

- [ ] Is the screen serving a clear user purpose?
- [ ] Can users act, cancel, go back, and recover from mistakes?
- [ ] Are permissions, privacy-sensitive behavior, and consequential actions transparent?
- [ ] Do familiar controls behave consistently and predictably?
- [ ] Does the layout adapt to supported sizes, input modes, and accessibility settings?
- [ ] Is the next action easy to find without hiding useful functionality?
- [ ] Are alignment, typography, feedback, and performance carefully finished?
- [ ] Does delight come from product-relevant quality rather than decoration?
- [ ] Is there one clear visual focal point?
- [ ] Does every visible container, border, shadow, color accent, and animation have a job?
- [ ] Has minimalism preserved discoverability, readable information, and accessibility?
- [ ] Does the implementation follow the actual target platform's design conventions?

## Sources

- [Apple Human Interface Guidelines: Design principles](https://developer.apple.com/design/human-interface-guidelines/design-principles/) — Apple's current eight principles and their practical guidance.
- [WWDC26: Principles of great design](https://developer.apple.com/videos/play/wwdc2026/250/) — Apple's explanation of purpose, agency, responsibility, familiarity, flexibility, simplicity, craft, and delight.
- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/) — platform-specific foundations, patterns, components, and accessibility.
- [Android design for mobile](https://developer.android.com/design/ui/mobile) — Android platform guidance.
- [Material 3 in Jetpack Compose](https://developer.android.com/develop/ui/compose/designsystems/material3) — Material You and M3 Expressive implementation guidance.

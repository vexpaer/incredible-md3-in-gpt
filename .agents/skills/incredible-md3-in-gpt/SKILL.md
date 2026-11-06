---
name: incredible-md3-in-gpt
description: Use when designing, implementing, redesigning, or reviewing a native mobile app UI for Android or iOS, especially when Material Design 3 or Material 3 Expressive is requested or the result looks generic. Covers visual direction, M3 Expressive, design tokens, native patterns, FlClash-inspired surface hierarchy, adaptive layouts, accessibility, minimal UI copy, and screenshot-based quality review.
---

# Incredible MD3 in GPT

Act as the product's design lead and mobile UI engineer. Produce a distinctive, coherent, production-ready mobile interface. Do not treat a component library's defaults as a finished design.

## Core rule

**Material 3 is the foundation; Material 3 Expressive is the richer design vocabulary; the product's visual identity is the result.** The product's tasks, information architecture, platform conventions, and visual hierarchy determine which components and treatments to use.

Priorities, in order:

1. Task clarity and information hierarchy.
2. Platform behavior and accessibility.
3. A coherent visual system.
4. Distinctive product character.
5. Decorative effects.

A visually striking screen that obscures the task, breaks native behavior, or fails at text scaling is not a good result.

## When to use

Use this skill for:
- Creating a new Android or iOS app, or a cross-platform mobile app.
- Designing or redesigning screens, navigation, settings, dashboards, lists, forms, dialogs, sheets, or onboarding.
- Making an MD3 implementation look less generic and more intentional.
- Reviewing an existing app that feels cluttered, bland, inconsistent, or "AI-generated".
- Defining or repairing color, typography, shape, spacing, elevation, icon, and motion tokens.

Do not use it for backend-only changes or non-visual refactors.

## Required workflow

### 1. Understand the product before choosing a style

Inspect the existing repository and read its project instructions first. Detect the actual framework and platform from the project; never assume Flutter, Compose, SwiftUI, or React Native.

Establish:
- What the app does and who uses it.
- The three most important user tasks.
- The primary action on each screen.
- The information that must be visible at a glance.
- Usage context: one-handed use, frequent use, outdoor use, work use, media consumption, or another concrete context.
- Supported platforms, screen sizes, orientations, system themes, and text scaling.
- Existing brand assets, constraints, and components that should be preserved.

If the request already gives enough context, make a design decision and proceed. Ask only when a missing product fact would materially change the design.

### 2. Research references, not just screenshots

For a new app or product-wide redesign, use at least two relevant reference sources. For a narrow component or interaction fix, one targeted official source plus the existing project's nearby implementation is enough.

1. **Platform authority:** current official guidance for the target platform. Use Android Design and Material 3 for Android, Apple HIG for iOS, and Flutter adaptive guidance for Flutter apps. For a cross-platform app, check both Android and iOS behavior.
2. **Product benchmark:** inspect a well-designed app with a comparable information architecture or interaction model. Use FlClash as a useful reference for utility apps, dashboards, settings, themes, and cross-platform adaptation. Select a different benchmark when the product category calls for it.

When available, consult complementary agent guidance:
- UI/UX Pro Max for relevant UX rules, native-app checks, and stack-specific implementation notes.
- Anthropic Frontend Design for a deliberate, product-specific visual direction.
- Taste-Skill for thinking about design variance and visual density.
- Supanova's redesign workflow for diagnosing an existing UI before changing it.

Claude Design is also a useful workflow reference: derive a design system from the real codebase and design files, use screenshots and existing components as context, explore alternatives when the direction is uncertain, then refine with precise element-level feedback and direct layout adjustments. Keep the design system and implementation in sync. Borrow this workflow, not Claude Design's generated visual aesthetic.

These are complementary references, not prerequisites. Do not install dependencies or copy their skill files just to use this skill. Do not apply landing-page rules to native app screens.

For each benchmark, inspect more than its hero or home screen when possible: look at settings, lists, details, dialogs, empty states, theme behavior, and small-screen behavior. Record the design decisions that are relevant to this product. Do not copy layouts, brand assets, code, or distinctive screens.

### 3. Write a visual thesis before implementation

Create a one-sentence visual thesis describing the intended product character and why it fits the app. Example: "A quiet, precise network utility with neutral surfaces, compact status information, and one confident accent."

Then decide:
- Visual character: restrained, editorial, technical, warm, playful, expressive, or another specific direction.
- Information density: spacious, balanced, or compact, based on actual task frequency and content volume.
- Primary accent and semantic status colors.
- Surface hierarchy and containment strategy.
- Type scale and numeric treatment.
- Shape language and corner-radius scale.
- Icon family and stroke/fill rules.
- Motion character and feedback behavior.

Do not combine several unrelated visual styles. Do not choose a style because it is trendy.

### 3.1 Enforce a minimal visible-copy budget

Default to **almost no explanatory microcopy**. A screen should contain only the words needed to identify content, label controls, show values, expose actions, communicate meaningful state, or explain a consequential/non-obvious choice.

Do not add a subtitle beneath every title, descriptions beneath every setting, captions that repeat visible labels, decorative eyebrow text, marketing slogans, or paragraphs explaining obvious controls. Never add small gray text merely to make a screen look more complete. Never shrink type to fit unnecessary copy.

Use a supporting sentence only when it changes a decision or enables a safe next action: permissions, destructive actions, unfamiliar advanced settings, non-obvious consequences, field constraints, errors, or an empty state with a useful next step. Keep it short and next to the relevant control.

Keep accessibility semantics even when visible copy is minimal: icon-only controls need accessible names, form fields need labels, and selected/error states must be exposed to assistive technology.

Read references/copy-discipline.md and run its screen-level copy audit before delivery.

### 4. Define semantic tokens and a component grammar

Before styling multiple screens, define shared tokens for:
- Color roles in light and dark themes.
- Typography roles, weights, and numeric styles.
- Spacing and layout insets.
- Shapes and corner radii.
- Surface levels and elevation.
- Icon sizes and stroke weights.
- Motion durations, easing, and reduced-motion behavior.

Use semantic names such as page, surface, raised surface, inset surface, primary action, selected state, success, warning, and error. Map those roles to the actual framework's theme system. Avoid arbitrary per-screen hex values, radii, shadows, and spacing.

Create a small set of reusable product components only after the visual rules are clear. Reuse nearby project conventions where they are sound; do not introduce a second design system for one screen.

Read references/design-foundations.md before making product-wide visual decisions.

### 5. Use Material 3 deliberately

Use MD3 color roles, typography, shape, state layers, and component behavior as a coherent system. Consider M3 Expressive as the preferred richer direction when it serves the product and platform. Customize the system to fit the product rather than accepting every default.

Rules:
- Prefer a balanced tonal palette with a restrained neutral surface family.
- Use primary color for meaningful emphasis: primary actions, selected states, and focused affordances. Do not paint every card, row, or icon with the accent.
- Pair foreground and container roles correctly, such as onPrimary on primary and onPrimaryContainer on primaryContainer.
- Use tonal elevation to establish surface hierarchy; reserve pronounced shadows for genuinely floating elements.
- Use the type scale as a hierarchy, not as a requirement to display oversized headings on every screen.
- Apply dynamic color when it supports the product and platform. Preserve brand identity when dynamic color would make the UI unstable or incoherent.
- Treat Material 3 Expressive as a first-class design direction, not a mandate to maximize decoration. Choose the degree of expression based on product tasks and platform.
- Prefer native components when their behavior fits. Customize them through the shared theme before creating one-off replacements.

Read references/design-foundations.md and references/material-3-expressive.md for the implementation rules. Use the M3 Expressive guide when choosing expressive color, typography, shapes, components, or motion.

### 6. Apply the FlClash lessons selectively

Study references/flclash-case-study.md. Treat it as a Material You / Material 3 product with explicit M3 Expressive shape usage and Apple-influenced interaction patterns. The most reusable lessons are:
- Let surface tone and spacing establish structure; reserve strong color for state and action.
- Give surfaces a small, consistent hierarchy rather than nesting cards indefinitely.
- Use neutral surfaces as the default canvas; a seed color does not need to tint every surface.
- Use shadows to explain floating or exceptional elevation, not as decoration on every list row.
- Build a reusable component system with consistent typography, glyphs, shapes, and interaction feedback.
- Treat theme preview, dark mode, and adaptive layouts as product features.
- Separate app-wide primitives from feature-specific widgets.

These are principles to adapt, not FlClash's exact palette, dimensions, or layout. A different product may need a different density, surface system, or accent strategy.

### 7. Design complete mobile behavior

Design each screen for its real content and states:
- Initial, loading, refreshing, empty, populated, error, offline, permission-required, disabled, selected, and success states where relevant.
- Short and long text, localization, user font scaling, and narrow widths.
- Keyboard appearance, validation, cancellation, and focus behavior for forms.
- Predictable back navigation, system gestures, and state restoration.
- Safe areas, status/navigation bars, and gesture insets.
- Touch feedback, disabled feedback, progress, and recoverable errors.
- Tablet, foldable, landscape, and resizable windows when in scope.

Use platform-appropriate touch targets: generally at least 48 dp on Android and 44 pt on iOS. Do not make a critical action gesture-only. Do not rely on hover for touch devices.

Read references/native-mobile-patterns.md when designing navigation, settings, lists, forms, dashboards, or sheets. Read references/material-3-expressive.md before applying expressive treatments.

### 8. Implement, run, inspect, and refine

Do not stop after generating source code.

1. Implement the visual system and screens using the detected stack.
2. For a major redesign, explore two or three genuinely different directions when the best direction is uncertain; choose one against the product tasks and visual thesis. Do not create alternatives just to generate more work.
3. Run the app in a real device or emulator/simulator when available.
4. Inspect screenshots at a small phone width, a common phone width, and a large width. Include tablet or landscape when supported.
5. Inspect both light and dark themes. Check larger system text and reduced motion.
6. Exercise primary interactions: navigation, back, sheets, forms, selected states, loading, errors, and scrolling.
7. Give local feedback against the exact screen or element that needs work; use broad changes for structural revisions and precise edits for spacing, alignment, labels, or control behavior.
8. Run the copy audit. Remove redundant explanations and secondary lines that do not help a real decision.
9. Fix the largest visual defects first: hierarchy, spacing, density, typography, surface contrast, alignment, clipping, copy noise, and inconsistent components.
10. Capture screenshots again after fixes.

Use the project's available screenshot or UI-testing tools. For native apps, prefer emulator/simulator or device screenshots; a web preview alone does not verify native behavior. If the environment cannot run the app, perform a static review and clearly state that visual verification was not possible.

Read references/visual-review.md before final delivery.

## Anti-patterns to actively reject

- A screen made from identical rounded cards because "MD3 uses cards".
- A large hero title on a utility screen that needs operational information.
- Accent-colored backgrounds on every section, row, icon, or control.
- Random gradients, neon glows, glass blur, decorative grain, or shadows without a product reason.
- Inconsistent radii, arbitrary spacing, mixed icon families, emoji used as functional icons, or mismatched stroke weights.
- Every action styled as the primary button.
- Repeating the same layout on every screen regardless of content.
- Tiny secondary text, low-contrast gray, truncated labels, or fixed heights that break with larger text.
- Explanatory microcopy under every heading, descriptive sentences on obvious settings rows, duplicated labels, decorative captions, or paragraphs that narrate an obvious interface.
- Adding visible copy to fill empty space, or shrinking type to fit copy that should have been removed.
- Removing essential permission, validation, destructive-action, error, or accessibility information in the name of minimalism.
- Web-only interaction patterns forced into native apps.
- A single screenshot used to claim the entire app is polished.
- Invented placeholder data that hides real content-density problems.

## Completion criteria

A design task is complete when:
- The visual thesis and semantic tokens are coherent.
- Screens reflect the product's real task hierarchy.
- The UI behaves correctly on the target platform.
- Relevant states and accessibility needs have been addressed.
- Visible copy has passed the minimal-copy audit; every remaining explanatory line earns its place.
- The app has been run and visually inspected, or the lack of runtime verification is explicitly reported.
- The final summary names the main design decisions, files changed, tests run, and any remaining visual risks.

# FlClash case study: product design beyond the default component library

Reference: [chen08209/FlClash](https://github.com/chen08209/FlClash)

FlClash is a cross-platform proxy client built with Flutter. Its README describes the product as using Material You design with Apple-style interaction, including dynamic color, light and dark themes, continuous corners, sheets that snap between heights, and layouts that adapt from phones to desktops. Its current agent-maintained surface guide also explicitly uses a Material 3 Expressive shape for an empty-state glyph. The most accurate reading is therefore a Material You / MD3 foundation, selected M3 Expressive visual elements, and Apple-influenced interaction conventions—not a stock implementation of every M3 Expressive component.

The useful lesson is not that every app should look exactly like FlClash. The lesson is that a strong product can use Material foundations while maintaining its own deliberate rules for surfaces, typography, components, interaction, and adaptation.

## Material 3 Expressive in the implementation

The current `.agents/surfaces.md` describes an empty-state glyph placed inside a Material 3 Expressive shape from `material_new_shapes`, with animated entrance choreography. This is a concrete M3 Expressive reference in the source tree. The rest of the interface remains deliberately controlled by FlClash's own semantic surface levels, seeded color scheme, state marks, and component system.

This distinction matters: FlClash uses expressive elements selectively. It does not make every surface, row, and control loud. Its strongest lesson is how to combine expressive moments with a quiet, tightly controlled interface.

## What to study

### 1. Surface hierarchy carries structure

FlClash documents a small hierarchy of page, card, block, inset, and floating surfaces in its repository's .agents/surfaces.md.

The design intent:
- Surface fills and tonal steps establish grouping.
- Strong accent color is reserved for meaningful state and action.
- Neutral surfaces prevent the brand seed from tinting the entire interface.
- Nested containers are limited; the deepest level is a stopping point, not an invitation to keep nesting.
- Shadows are used selectively for floating elements and a few deliberate dashboard surfaces, not indiscriminately on every list row.

Apply this as a design question: can users understand the grouping through tone, spacing, and typography without another border or card?

### 2. Color communicates state

The FlClash surface guide describes a clear separation between structure and state. The app uses selected marks, semantic status colors, and primary emphasis for the relevant item or action instead of recoloring every surrounding container.

Useful questions for another product:
- What is the one selected item in this group?
- Which state is success, warning, or error?
- Which action is primary on this screen?
- Can a user identify state without color alone?

Do not reuse its exact colors or thresholds. Define status semantics from the new product's domain.

### 3. The theme is a product feature

The theme screen in lib/views/theme.dart includes live previews for theme modes and visual choices. This makes the effect of a setting visible before the user commits to it.

The theme manager in lib/manager/theme_manager.dart centralizes color scheme, font family, locale, and system UI behavior. This is a useful architectural signal: theme behavior belongs to the app's shared design system, not scattered per-screen overrides.

### 4. Components have a clear ownership boundary

The repository's .agents/skills/ui-work/SKILL.md describes a reusable UI layer:
- Generic components live in the prism_ui package.
- App-level glyphs, fonts, and illustrations live in the app UI layer.
- Feature-specific widgets live with app features.
- Settings rows use shared configuration-item patterns.
- Text and glyphs use shared type and icon systems.
- Sheets, forms, and modal behavior have explicit rules.

This prevents screens from independently inventing their own controls and interaction patterns.

### 5. Dashboard components are modular

The dashboard widget registry and dashboard style definitions show a deliberate separation between:
- Which dashboard modules exist.
- The widget that renders each module.
- The shared color, type, shape, and shadow tokens used by those modules.

The dashboard can vary its information modules without each module inventing a new design language.

### 6. Interaction details matter

The UI work guide documents details such as press feedback, modal scrims, sheet detents, keyboard-aware layout, form-sheet behavior, and platform-specific glyph treatment. These small behaviors are part of the product's quality, even when they are not obvious in a static screenshot.

## How to apply the lessons

For a new app:
1. Define the app's own surface roles and color semantics.
2. Build reusable primitives for the repeated patterns in the product.
3. Keep feature-specific UI separate from app-wide primitives.
4. Design settings and theme controls as first-class product experiences.
5. Test modal, keyboard, navigation, and press behavior on the actual target platform.

For a redesign:
1. Identify the current hierarchy and repeated component patterns.
2. Find where card wrappers, shadows, accent fills, or borders are doing no useful work.
3. Improve the shared component system before patching individual screens.
4. Preserve the app's task model and domain semantics.
5. Verify the changed screens in the running app.

## Source map

- [FlClash README](https://github.com/chen08209/FlClash/blob/main/README.md) — platform scope and stated design direction.
- [Surface design rules](https://github.com/chen08209/FlClash/blob/main/.agents/surfaces.md) — surface levels, tonal hierarchy, state color, elevation, and the explicit Material 3 Expressive shape usage.
- [UI work skill](https://github.com/chen08209/FlClash/blob/main/.agents/skills/ui-work/SKILL.md) — component ownership and interaction conventions.
- [Theme settings](https://github.com/chen08209/FlClash/blob/main/lib/views/theme.dart) — live theme previews and settings UI.
- [Theme manager](https://github.com/chen08209/FlClash/blob/main/lib/manager/theme_manager.dart) — centralized theme and system UI behavior.
- [Dashboard style](https://github.com/chen08209/FlClash/blob/main/lib/views/dashboard/style.dart) — shared dashboard color, shape, shadow, and type tokens.
- [Dashboard widget registry](https://github.com/chen08209/FlClash/blob/main/lib/views/dashboard/widget_registry.dart) — modular dashboard composition.

## License and reuse

FlClash is distributed under GPL-3.0. This case study records design observations and links to upstream sources. It does not include FlClash source code, assets, screenshots, or copied component implementations. If a future contribution wants to reuse upstream code or assets, inspect the upstream license and comply with it separately.

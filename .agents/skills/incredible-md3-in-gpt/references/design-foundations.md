# Design foundations: turning MD3 into a product identity

Material Design 3 is a system of design decisions: color, type, shape, components, state, motion, and adaptive behavior. A good app uses those decisions consistently while making a product-specific visual choice. A default theme with every component enabled is only a starting point.

## 1. Start with a visual thesis

Write one sentence that describes the product's visual character and the user need behind it. The thesis should constrain later decisions.

Examples:
- A network utility should feel precise, calm, and operational; status and control need to scan quickly.
- A reading app should prioritize long-form typography, quiet surfaces, and persistent reading position.
- A creative tool can use more expressive color and motion, but its canvas and controls must remain legible.

Translate the thesis into a few explicit choices:
- Density: spacious, balanced, or compact.
- Contrast: soft, balanced, or high.
- Accent: restrained, vivid, or multi-accent with a clear semantic purpose.
- Surface: flat, lightly layered, or strongly layered.
- Shape: crisp, soft, or expressive.
- Motion: minimal, responsive, or expressive.

Do not pick a style from a gallery without checking whether it serves the product's tasks.

## 2. Color: semantic roles before hex values

Use a semantic color scheme instead of styling components with unrelated literal colors.

Typical roles include:
- Primary and on-primary for the most important action or active emphasis.
- Primary container and on-primary-container for a contained emphasis.
- Secondary and tertiary roles for supporting emphasis where the product needs them.
- Surface, surface-container variants, and on-surface roles for content hierarchy.
- Outline and outline-variant for boundaries that genuinely need a line.
- Error, success, and warning roles for status and feedback.

Rules:
1. Define both light and dark mappings together.
2. Use matching foreground/background pairs. A readable color by itself can become unreadable on the wrong container.
3. Keep most app surfaces neutral or subtly tinted. A brand seed does not need to color every surface.
4. Reserve strong accent color for primary actions, selected states, and important status.
5. Do not communicate success, failure, or selection with color alone; add labels, symbols, or other cues.
6. Check text and icon contrast in the actual rendered theme, including translucent overlays.
7. Dynamic color is a platform capability, not an unconditional product requirement. Decide whether user wallpaper colors should override the brand palette.

Do not choose colors independently per screen. A palette is only coherent when all semantic roles are mapped consistently.

## 3. Surface hierarchy: make containment earn its place

A card is useful when it groups content or actions into a meaningful unit. It is not a default wrapper for every section.

A practical surface vocabulary might include:
- Page: the primary canvas.
- Group or card: a meaningful content group raised from the page.
- Block: a nested region within a group.
- Inset: a small well for a control, value, or compact mark.
- Floating: menus, dialogs, popovers, or other elements that sit above content.

Use only the levels the product needs. Most screens should not require every level. If the hierarchy becomes difficult to explain, remove a container rather than adding another.

Use surface tone, spacing, and typography to establish grouping. Use borders only when a boundary must remain visible. Use shadows to communicate actual floating elevation or a deliberate exceptional layer, not as a universal card decoration.

A useful FlClash-inspired principle is to let neutral tonal surfaces carry structure while accent colors communicate state. Adapt the principle to the product; do not copy FlClash's exact surface values.

## 4. Typography: hierarchy is more than size

Define roles for display, headline, title, body, and label text. Map them to the platform's typography system.

- Use size, weight, color, and spacing together to create hierarchy.
- Avoid making every page title oversized.
- Keep body copy comfortable at the user's preferred text size.
- Use tabular numerals for changing metrics, counters, latency, time, and other values that should not visually jump.
- Keep labels concise, but preserve the full value where truncation would hide meaning.
- Test long translations, large accessibility text, and narrow screens.
- Avoid mixing typefaces without a clear role for each family.

Typography should help users distinguish what something is, what it means, and what they can do with it.

## 5. Shape and spacing

Define a small shape scale and use it consistently. Large radii are not automatically more modern. Apply a shape because it expresses containment, hierarchy, or a platform convention.

Use a 4 dp / 8 dp spacing foundation as a starting point, then define named tokens for:
- Compact control spacing.
- Row and component padding.
- Section separation.
- Screen gutters.
- Large layout breaks.

Use larger gaps between different information groups than between items inside one group. Avoid arbitrary one-off values. A consistent rhythm makes the interface feel composed even when its layouts differ.

## 6. Elevation and depth

Material 3 uses tonal elevation as an important way to distinguish surfaces; shadows remain useful for floating elements.

- Prefer tonal differences for ordinary content hierarchy.
- Reserve strong shadows for menus, dialogs, floating controls, or a small number of intentionally elevated cards.
- Do not stack shadow on every row in a scrolling list.
- In dark mode, check whether a shadow is actually visible. A lighter surface may communicate elevation more clearly.
- Avoid adding blur or glass effects unless the product has a real layering need and the text remains readable.

## 7. Components and state layers

Choose a component by the job it performs, not because it is available in the library.

For each interactive component, define:
- Default.
- Pressed.
- Focused.
- Selected or checked.
- Disabled.
- Loading, when applicable.
- Error or success, when applicable.

Use the platform's native state feedback where possible. Keep press feedback immediate and avoid changing layout bounds in a way that makes nearby content jump.

Build shared product components only after identifying repeated patterns. A shared component should encode real design decisions, not merely wrap a framework component with a new name.

## 8. Icons and imagery

- Use one coherent vector icon family.
- Standardize icon sizes and stroke/fill treatment by role.
- Use filled icons only where selection or emphasis calls for them.
- Never use emoji as a substitute for a functional system icon.
- Give icon-only controls accessible labels.
- Use imagery only when it contributes meaning, context, or brand character. Decorative imagery should not compete with the task.

## 9. Motion

Motion should explain state change, spatial relationships, or progress.

- Define shared duration and easing tokens, but allow different motion for different distances and tasks.
- Give immediate feedback to taps; avoid making users wait for decorative animation.
- Prefer animating opacity and transforms over expensive layout changes.
- Respect reduced-motion preferences.
- Do not animate every element on screen.
- Ensure interrupted animations leave the correct semantic state and do not trap focus.

## 10. What not to inherit from AI-generated templates

Avoid:
- The same large rounded card around every section.
- A gradient or glass background by default.
- Oversized headings on dense utility screens.
- A bento grid where a list or table would communicate better.
- Too many accent colors with no semantic roles.
- Every action styled as a filled primary button.
- Inconsistent icon families, arbitrary radii, and random spacing.
- A dark mode that is simply the light theme inverted.
- A visual system that looks polished in one screenshot but breaks with real data.

The goal is a small, explainable set of decisions that makes every screen feel like part of the same product.

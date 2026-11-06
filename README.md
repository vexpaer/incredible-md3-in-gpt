# Incredible MD3 in GPT

**A mobile-first design skill for AI agents that need to build native app interfaces that feel designed, not generated.**

Material Design 3 gives an app a coherent design language; Material 3 Expressive expands it with richer theming, components, motion, and typography. This skill teaches an agent how to turn those systems into a distinctive, usable product: research the right references, define a deliberate visual system, design around real tasks, implement platform-aware components, and verify the result with screenshots.

## Install

Using the open Agent Skills CLI:

    npx skills add vexpaer/incredible-md3-in-gpt --skill incredible-md3-in-gpt

Install globally for future projects:

    npx skills add vexpaer/incredible-md3-in-gpt --skill incredible-md3-in-gpt -g

To target Codex explicitly:

    npx skills add vexpaer/incredible-md3-in-gpt --skill incredible-md3-in-gpt -a codex

The CLI requires Node.js 22.20 or later. You can also install interactively and choose your agent. The skill is stored in the standard .agents/skills directory, with the CLI handling each agent's native location.

## What it changes

Most weak AI-generated mobile UIs follow the same recipe: default Material components, oversized rounded cards, a bright accent on every surface, repeated settings rows, and no real visual QA.

This skill changes the workflow:

1. Understand the product, its primary tasks, platform, and existing code before styling.
2. Study at least one authoritative platform guideline and one relevant, high-quality product reference.
3. Define a visual thesis and semantic design tokens before building screens.
4. Use Material 3 as a foundation and Material 3 Expressive as a first-class, selectively applied design direction—not as a finished visual identity.
5. Borrow the strongest product-design lessons from FlClash: tonal surface hierarchy, restrained state color, reusable primitives, deliberate theme behavior, and adaptive layouts.
6. Design real screen states and platform interactions, not just a static happy-path mockup.
7. Keep visible copy minimal: remove explanatory subtitles and helper text unless they change a decision or enable a safe action.
8. Run the app, inspect screenshots at multiple sizes and themes, fix defects, and inspect again.

## Design philosophy

- **Product first:** task clarity and information hierarchy outrank decoration.
- **MD3 + M3 Expressive:** use semantic color roles, expressive typography, shape, motion, components, elevation, and state layers deliberately.
- **A distinct visual point of view:** make deliberate choices for the product instead of accepting framework defaults.
- **Restraint:** cards, borders, shadows, gradients, blur, animation, and visible copy each need a reason. No explanatory microcopy by default.
- **Native behavior:** respect Android and iOS conventions instead of forcing one platform's patterns everywhere.
- **Evidence-based polish:** a UI is not visually verified until the running app has been inspected.

## Reference projects and guidance

The skill is an original synthesis informed by:

- [UI/UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) — searchable design guidance, stack-specific recommendations, and a native/mobile pre-delivery checklist.
- [Anthropic Frontend Design](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design) — intentional visual direction and resistance to generic templates.
- [Taste-Skill](https://github.com/Leonxlnx/taste-skill) — adjustable design variance and visual-density thinking.
- [Supanova Design Skill](https://github.com/uxjoseph/supanova-design-skill) — design diagnosis and focused redesign workflow; its landing-page-specific prescriptions are not treated as mobile-app rules.
- [Claude Design](https://claude.com/product/design) — importing real design systems, grounding prototypes in code and screenshots, targeted iteration, and design-to-code handoff.
- [FlClash](https://github.com/chen08209/FlClash) — a real cross-platform app that combines Material You foundations with a carefully maintained product-specific UI system.
- Official [Android design guidance](https://developer.android.com/design/ui/mobile), [Material 3 in Compose](https://developer.android.com/develop/ui/compose/designsystems/material3), [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/), and [Flutter adaptive design](https://docs.flutter.dev/ui/adaptive-responsive).

These projects are references, not dependencies. Their code, assets, and distinctive screens are not bundled or copied into this repository.

## Contents

- .agents/skills/incredible-md3-in-gpt/SKILL.md — the portable agent skill.
- .agents/skills/incredible-md3-in-gpt/references/design-foundations.md — how to turn MD3 into a coherent visual system.
- .agents/skills/incredible-md3-in-gpt/references/material-3-expressive.md — M3 Expressive principles and Android, Flutter, and iOS implementation guidance.
- .agents/skills/incredible-md3-in-gpt/references/flclash-case-study.md — design and architecture lessons from FlClash.
- .agents/skills/incredible-md3-in-gpt/references/native-mobile-patterns.md — navigation, lists, settings, forms, dashboards, states, and adaptive behavior.
- .agents/skills/incredible-md3-in-gpt/references/visual-review.md — screenshot workflow, acceptance gates, and a scoring rubric.
- .agents/skills/incredible-md3-in-gpt/references/copy-discipline.md — strict rules for minimal visible copy and removing explanatory microcopy.
- .agents/skills/incredible-md3-in-gpt/references/research-sources.md — source index and attribution notes.
- templates/design-brief.md — a compact brief to complete before implementation.
- templates/visual-review.md — a repeatable review report.

## License

MIT. See [LICENSE](LICENSE).

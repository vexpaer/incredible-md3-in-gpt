# Incredible MD3 in GPT

**A mobile-first design skill for AI agents that need to build native app interfaces that feel designed, not generated.**

Material Design 3 gives an app a coherent design language. This skill teaches an agent how to turn that language into a distinctive, usable product: research the right references, define a deliberate visual system, design around real tasks, implement platform-aware components, and verify the result with screenshots.

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
4. Use Material 3 as a foundation, not as a finished visual identity.
5. Borrow the strongest product-design lessons from FlClash: tonal surface hierarchy, restrained state color, reusable primitives, deliberate theme behavior, and adaptive layouts.
6. Design real screen states and platform interactions, not just a static happy-path mockup.
7. Run the app, inspect screenshots at multiple sizes and themes, fix defects, and inspect again.

## Design philosophy

- **Product first:** task clarity and information hierarchy outrank decoration.
- **MD3 as a system:** use semantic color roles, type roles, shape, elevation, and state layers consistently.
- **A distinct visual point of view:** make deliberate choices for the product instead of accepting framework defaults.
- **Restraint:** cards, borders, shadows, gradients, blur, and animation each need a reason.
- **Native behavior:** respect Android and iOS conventions instead of forcing one platform's patterns everywhere.
- **Evidence-based polish:** a UI is not visually verified until the running app has been inspected.

## Reference projects and guidance

The skill is an original synthesis informed by:

- [UI/UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) — searchable design guidance, stack-specific recommendations, and a native/mobile pre-delivery checklist.
- [Anthropic Frontend Design](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design) — intentional visual direction and resistance to generic templates.
- [Taste-Skill](https://github.com/Leonxlnx/taste-skill) — adjustable design variance and visual-density thinking.
- [Supanova Design Skill](https://github.com/uxjoseph/supanova-design-skill) — design diagnosis and focused redesign workflow; its landing-page-specific prescriptions are not treated as mobile-app rules.
- [FlClash](https://github.com/chen08209/FlClash) — a real cross-platform app that combines Material You foundations with a carefully maintained product-specific UI system.
- Official [Android design guidance](https://developer.android.com/design/ui/mobile), [Material 3 in Compose](https://developer.android.com/develop/ui/compose/designsystems/material3), [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/), and [Flutter adaptive design](https://docs.flutter.dev/ui/adaptive-responsive).

These projects are references, not dependencies. Their code, assets, and distinctive screens are not bundled or copied into this repository.

## Contents

- .agents/skills/incredible-md3-in-gpt/SKILL.md — the portable agent skill.
- references/design-foundations.md — how to turn MD3 into a coherent visual system.
- references/flclash-case-study.md — design and architecture lessons from FlClash.
- references/native-mobile-patterns.md — navigation, lists, settings, forms, dashboards, states, and adaptive behavior.
- references/visual-review.md — screenshot workflow, acceptance gates, and a scoring rubric.
- references/research-sources.md — source index and attribution notes.
- templates/design-brief.md — a compact brief to complete before implementation.
- templates/visual-review.md — a repeatable review report.

## License

MIT. See [LICENSE](LICENSE).

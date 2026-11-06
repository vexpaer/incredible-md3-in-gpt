# Research sources and attribution

This skill is an original, mobile-focused synthesis. The sources below informed its workflow and design principles. It does not bundle external skill files, source code, product assets, or screenshots.

Last source review: 2026-11-06.

## Official platform and framework guidance

### Android and Material

- [Android design for mobile](https://developer.android.com/design/ui/mobile) — current Android foundations, styles, layout, behaviors, components, and accessibility.
- [Material 3 in Jetpack Compose](https://developer.android.com/develop/ui/compose/designsystems/material3) — official Material You and Material 3 Expressive implementation; explains M3 Expressive as an expansion covering theming, components, motion, typography, and more.
- [A more personal, expressive phone experience](https://blog.google/products-and-platforms/platforms/android/material-3-expressive-android-wearos-launch/) — Google's Android phone announcement: M3 Expressive builds on Material You with more personalization, spring motion, responsive components, and emphasized typography.
- [Material components for mobile](https://developer.android.com/design/ui/mobile/guides/components/material-overview) — containment, navigation, selection, and input patterns.
- [Android layout and navigation patterns](https://developer.android.com/design/ui/mobile/guides/layout-and-content/layout-and-nav-patterns) — adaptive navigation and layout choices.

### Apple

- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/) — platform foundations, patterns, components, and accessibility.
- [Apple HIG: Layout](https://developer.apple.com/design/human-interface-guidelines/layout) — adaptation to window size, orientation, text size, and system environment.

### Flutter

- [Flutter adaptive and responsive design](https://docs.flutter.dev/ui/adaptive-responsive) — adapting layouts and interaction models across screen sizes and input modes.

## Agent design references

- [UI/UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) — searchable UI/UX recommendations and stack-specific guidance. Its [native/mobile pro rules](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/.claude/skills/ui-ux-pro-max/references/pro-rules.md) informed the mobile review topics: touch targets, safe areas, dark-mode contrast, accessibility semantics, and interaction states. The project is MIT-licensed.
- [Anthropic Frontend Design](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design) — a useful reference for deliberate visual direction and product-specific design decisions. Consult its current license terms before reusing any of its text or files.
- [Taste-Skill](https://github.com/Leonxlnx/taste-skill) — design-variance and visual-density controls, plus anti-generic design thinking. The project is MIT-licensed.
- [Supanova Design Skill](https://github.com/uxjoseph/supanova-design-skill) — a redesign diagnosis workflow and aesthetic critique. Its repository is oriented toward landing pages; this skill borrows only the general idea of diagnosing before changing and does not adopt its web-specific prescriptions.
- [Claude Design: launch announcement](https://www.anthropic.com/news/claude-design-anthropic-labs) — design-system extraction from code and design files, prototype exploration, inline comments, direct editing, custom controls, and handoff to implementation.
- [Claude Design: staying on brand](https://claude.com/resources/articles/claude-design-stays-on-brand-for-daily-work) — importing real GitHub design systems and components, checking generated output against the system, keeping design and code synchronized, and refining layouts directly.
- [Claude Design Help Center guide](https://support.claude.com/en/articles/14604416-get-started-with-claude-design) — using codebases, screenshots, and reference material; exploring alternatives; choosing broad chat feedback versus targeted inline comments and direct canvas edits.

### How this skill uses Claude Design

Claude Design is treated as a workflow reference, not a visual style to imitate. The useful practices are:
- Derive the design system from the actual codebase and design files instead of inventing tokens from scratch.
- Ground the first design in real screenshots, assets, and existing components.
- Explore multiple directions when the design direction is genuinely uncertain.
- Separate structural feedback from element-level corrections.
- Refine with targeted comments or direct layout edits, then keep the implementation synchronized with the design system.
- Check generated work against the existing design system before delivery.

This skill translates those practices into repository inspection, screen references, semantic-token checks, targeted screenshot review, and implementation verification. It does not require Claude Design or copy its generated aesthetic.

## Product case study

- [FlClash](https://github.com/chen08209/FlClash) — cross-platform Flutter proxy client. Its README describes a Material You visual foundation with Apple-style interaction.
- [FlClash surface rules](https://github.com/chen08209/FlClash/blob/main/.agents/surfaces.md) — a detailed example of tonal surface hierarchy, restrained state color, selective elevation, and a concrete Material 3 Expressive shape used in an empty state.
- [FlClash UI work skill](https://github.com/chen08209/FlClash/blob/main/.agents/skills/ui-work/SKILL.md) — component ownership, reusable UI primitives, glyphs, typography, sheets, and interaction conventions.
- [FlClash theme settings](https://github.com/chen08209/FlClash/blob/main/lib/views/theme.dart) — theme previews and user-facing theme controls.
- [FlClash theme manager](https://github.com/chen08209/FlClash/blob/main/lib/manager/theme_manager.dart) — centralized theme and system UI behavior.
- [FlClash dashboard style](https://github.com/chen08209/FlClash/blob/main/lib/views/dashboard/style.dart) — semantic colors, typography, shape, and shadow tokens.
- [FlClash dashboard widget registry](https://github.com/chen08209/FlClash/blob/main/lib/views/dashboard/widget_registry.dart) — modular dashboard composition.

FlClash is GPL-3.0. This repository documents design observations and links to upstream sources; it does not copy FlClash implementation code or assets.

### Material 3 Expressive guidance

- [Material 3 Expressive design guidance](https://developer.android.com/design/ui/wear/guides/get-started/benefits) — Google's research rationale and practical advice: start from user needs, prioritize functionality, preserve accessibility, and iterate.
- [Levels of expression](https://developer.android.com/design/ui/wear/guides/get-started/levels-expression) — a useful taxonomy across components, color, typography, shape, motion, and adaptive behavior. These Wear-specific examples are design references, not phone-specific requirements.

## Agent Skills distribution

- [Vercel Agent Skills CLI](https://github.com/vercel-labs/skills) — installable portable skills for Codex, Claude Code, Cursor, and other agents.
- [Skills CLI commands](https://github.com/vercel-labs/skills/blob/main/docs/commands.md) — repository-based installation, skill selection, and agent targeting.

## Attribution policy

- Link to the source when a design principle is derived from a specific project.
- Do not copy large passages, proprietary skill files, source code, images, or screenshots into this repository.
- If a future contribution reuses external code or text, verify the upstream license and include the required notices.
- Treat upstream projects as evolving references; re-check official documentation before relying on version-specific details.

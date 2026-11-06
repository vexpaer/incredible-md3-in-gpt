# Copy discipline: minimal visible text, maximum clarity

## The rule

**Every visible string must earn its place. If it does not help the user identify, choose, act, understand an important state, or recover from a problem, remove it.**

Default to a quiet interface with very little explanatory copy. Do not fill a screen with small descriptions to make it appear helpful, complete, or polished. Users should understand the interface from its hierarchy, labels, values, controls, and feedback.

This is a strong product preference, not permission to hide information that users need for safety, consent, or a consequential decision.

## What belongs on screen

Keep visible text to the minimum needed for these jobs:

1. **Navigation:** where the user is and how to move.
2. **Identity:** the name of a screen, section, setting, or object.
3. **Value:** the current value, status, or result.
4. **Action:** what a control will do.
5. **Feedback:** what just happened, what is pending, or what failed.
6. **Essential guidance:** the shortest explanation needed to make a non-obvious or consequential choice safely.

If a string does not fit one of these jobs, delete it.

## Default: no explanatory microcopy

Do not add these by default:

- A descriptive sentence under every screen title.
- A second explanatory line under every setting or list row.
- A paragraph explaining what a page or obvious control does.
- Captions that repeat a visible heading, label, value, icon, or status.
- Decorative eyebrow labels, category tags, slogans, or marketing phrases.
- Repeated "Your …" or "Manage …" phrases that add no information.
- A helper sentence that merely paraphrases a switch, dropdown, or button label.
- Multiple layers of headings, subtitles, captions, and footnotes for one small content group.
- Tiny gray text used to squeeze unnecessary explanations into the layout.

Do not invent text just to occupy whitespace. Do not reduce font size to make redundant copy fit.

## When explanatory text is justified

Use a short, contextual explanation only when removing it would make a meaningful difference to the user's decision or next action.

Valid cases:
- A permission request needs to explain why access is required.
- An advanced or unfamiliar setting has a non-obvious consequence.
- A destructive or irreversible action needs a consequence summary.
- A form field has a constraint that cannot be expressed by its label or input type.
- An error needs to explain the failure and the available recovery.
- An empty state needs one useful next step.
- A safety-critical or legally significant choice requires explicit context.

Keep it specific and short. Put the explanation beside the decision it affects. Do not turn it into a general paragraph about the product.

## Examples

### Settings row

**Avoid**

- Network mode
- Choose how your device routes traffic through the proxy network.

**Prefer**

- Network mode · Rule ›

The value or selected option can appear at the trailing edge. No sentence is needed when the setting name and value are self-explanatory.

### Theme setting

**Avoid**

- Appearance
- Customize the visual appearance of the app to match your personal preferences.

**Prefer**

- Appearance · Dark ›

### Obvious switch

**Avoid**

- Background animation
- Enable a subtle animated background effect for a more immersive experience. [switch]

**Prefer**

- Background animation [switch]

### Destructive action

**Keep the necessary explanation**

- Delete profile?
- This permanently removes the profile and its local configuration.
- Cancel · Delete

Here the consequence changes the decision, so the sentence earns its place.

## Screen-level copy audit

Before calling a screen finished:

1. Inventory every visible text element, including captions, metadata, helper text, and footnotes.
2. Classify each as navigation, identity, value, action, feedback, or essential guidance.
3. Delete any string that cannot be classified.
4. Remove duplicate information shown in both a label and a subtitle, or in both an icon and a caption.
5. Remove descriptions from rows whose names and current values already explain the control.
6. Shorten the remaining copy to concrete nouns and verbs.
7. Inspect the screen again at actual phone size. Check whether secondary text has become visual noise.

Do not impose a universal word count. A data-heavy screen may need many meaningful labels; a simple settings screen may need almost no supporting text.

## Accessibility without visual clutter

Minimal visible copy must not remove accessibility semantics.

- Icon-only controls still need meaningful accessibility labels.
- Expose selected, checked, expanded, disabled, and error states to assistive technology.
- Use visible labels for form fields; placeholders alone are not labels.
- Keep text legible at normal and enlarged system text sizes.
- Do not communicate state through color alone.
- Use tooltips or accessibility hints for secondary explanation when appropriate, rather than permanently displaying paragraphs on a frequently used screen.

The target is a clear interface, not an unlabeled interface.

## Review questions

- Can the user understand this screen without reading a paragraph?
- Does every secondary line provide information that is not already visible?
- Does each setting really need a subtitle?
- Are labels, values, and section titles duplicated?
- Is the small text actually important, or is it decorative explanation?
- Could the same meaning be communicated by a concise label, a value, or a native control?
- Have essential consequences, validation, and accessibility semantics been preserved?

When in doubt, remove the explanatory line, then test whether the interface remains understandable. Restore it only if the test shows a real information gap.

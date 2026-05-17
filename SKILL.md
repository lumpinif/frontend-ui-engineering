---
name: frontend-ui-engineering
description: Modern frontend UI engineering guidelines for building and reviewing clear, accessible, maintainable product interfaces. Use when creating, modifying, or reviewing UI components, pages, layouts, HTML, CSS, JavaScript, TypeScript, accessibility, responsive behavior, interaction states, motion, performance, or frontend UX quality.
---

# Frontend UI Engineering

## Credits

This skill synthesizes and modernizes principles from two excellent open-source frontend guides:

- Nicolas Gallagher's `idiomatic-css`: https://github.com/necolas/idiomatic-css
- Benjamin De Cock's `frontend-guidelines`: https://github.com/bendc/frontend-guidelines

Use this skill as a practical UI engineering baseline, not as a verbatim copy of either source.

## Operating Mode

Apply these rules when building or reviewing frontend UI. Favor clear, native, maintainable implementation over cleverness, visual tricks, or framework-specific shortcuts.

When creating UI, implement the user-facing experience directly. When reviewing UI, lead with concrete issues and fixes. For deeper review tasks, read `references/review-checklist.md`.

## Priority Order

1. Make the interface semantically correct and accessible.
2. Make behavior explicit, predictable, and testable.
3. Make layout stable across real viewport sizes.
4. Make styling readable, consistent, and easy to override.
5. Make performance good through simple structure before micro-optimization.
6. Make visual polish support the product, not distract from it.

If rules conflict, choose clarity and user correctness over brevity, novelty, or personal style.

## HTML

- Prefer native semantic elements before adding ARIA: `button`, `a`, `main`, `nav`, `section`, `article`, `header`, `form`, `label`, `fieldset`, `table`.
- Use a real `button` for actions and a real `a` with `href` for navigation.
- Give every interactive control a clear accessible name.
- Associate every input with a visible or programmatic label.
- Keep heading levels meaningful. Do not skip levels for visual sizing.
- Avoid non-semantic wrappers unless they serve layout, grouping, or styling.

## CSS

- Let the project formatter own whitespace, indentation, quote style, and semicolons.
- Keep CSS readable enough that code review can focus on behavior, not formatting.
- Use shallow, intention-revealing selectors. Prefer class names that describe the UI role.
- Avoid selectors tightly coupled to DOM depth, sibling position, or incidental markup.
- Avoid `!important`, IDs for styling, and specificity escalation.
- Prefer normal document flow, Flexbox, and Grid before absolute positioning.
- Use a consistent box model for the project. Avoid local box-model surprises.
- Keep declaration order consistent. Prefer grouping by purpose: positioning, layout, sizing, spacing, visual style, motion.
- Use comments to explain non-obvious constraints or browser behavior. Do not comment what the property already says.

## JavaScript And TypeScript

- Prefer readable TypeScript over clever expression tricks.
- Use small named functions when they clarify intent or isolate behavior.
- Use array methods for simple transformations. Use `for...of` when branching, early continuation, async sequencing, or step-by-step clarity is better.
- Prefer explicit control flow over short-circuit side effects.
- Keep UI state single-sourced. Do not duplicate derived state unless there is a clear performance or UX reason.
- Avoid broad dependencies for behavior the platform or a small local helper can provide clearly.
- Validate external input at boundaries. Preserve error context instead of hiding failures.

## Accessibility

- Keyboard users must be able to reach, understand, operate, and leave every interactive surface.
- Keep focus visible. Do not remove outlines without an equivalent visible replacement.
- Dialogs and popovers must manage focus intentionally and restore focus on close.
- Form errors must identify the failing field, explain the problem, and remain available after focus changes.
- Do not rely on color alone to communicate state.
- Respect `prefers-reduced-motion` for non-essential motion.

## Interaction States

- Design and implement the real lifecycle: default, hover, focus, active, loading, disabled, empty, error, success, and pending states when relevant.
- Disabled controls must explain what prevents action when the reason is not obvious.
- Loading UI should preserve layout size to avoid avoidable shifts.
- Empty states should tell users what is true now and what action is available next.
- Error states should be specific, recoverable, and close to the affected control.

## Motion And Performance

- Animate `transform` and `opacity` by default.
- Avoid animating layout properties such as `width`, `height`, `top`, `left`, `margin`, or `padding`.
- Use transitions for ordinary state changes. Use keyframe animations only when continuous or staged motion is truly needed.
- Do not add `will-change` permanently or as a generic hack.
- Improve perceived speed by avoiding render-blocking scripts and by keeping initial UI useful quickly.
- Optimize images, network work, and layout thrashing before micro-optimizing JavaScript.

## Responsive UI

- Build layouts that adapt, not layouts that merely shrink.
- Define stable dimensions for fixed-format UI such as grids, boards, toolbars, cards, and icon buttons.
- Prevent text from overflowing buttons, cards, table cells, navigation, and controls.
- Do not hide critical functionality on mobile unless an equivalent path remains obvious.
- Test narrow, medium, and wide viewports for overlap, clipping, wrapping, and tap target quality.

## Product Copy

- Use clear, natural, user-facing English.
- Prefer literal labels over clever or branded internal terms.
- Keep one stable term for one concept across UI, code, schemas, and documentation.
- Put the next action in the UI when a user is blocked.

## Review Mode

When the user asks for a UI review, audit, polish pass, accessibility check, or best-practices review:

1. Read `references/review-checklist.md`.
2. Inspect the relevant files or running UI.
3. Report issues before summaries.
4. Include file and line references when reviewing code.
5. Prefer minimal, targeted fixes over unrelated refactors.

For implementation tasks, apply the checklist mentally without loading the reference unless the task is explicitly a review or audit.

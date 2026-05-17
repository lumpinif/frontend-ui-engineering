# Frontend UI Engineering Review Checklist

Use this checklist for explicit UI review, audit, polish, or best-practices tasks. Report concrete findings first, ordered by user impact and maintainability risk.

## 1. Product Fit

- The first screen shows the actual product or task, not marketing filler unless a landing page was requested.
- The UI answers what the user can do now, what changed, and what to do next.
- User-facing copy is clear, native-level English.
- The same concept uses the same term everywhere.

## 2. HTML Semantics

- Actions use `button`; navigation uses `a href`.
- Landmarks and document regions use meaningful elements.
- Inputs have labels.
- Headings form a useful structure.
- Tables, lists, and forms use native elements before custom roles.

## 3. Accessibility

- Every interactive control has an accessible name.
- Keyboard tab order is logical.
- Focus is visible and not trapped accidentally.
- Dialogs trap focus only while open and restore focus on close.
- Icon-only controls have labels; decorative icons are hidden from assistive tech.
- Errors are connected to fields and do not rely only on color.
- Important async state is announced or visible in persistent UI.

## 4. CSS Maintainability

- Formatting is handled by the project formatter.
- Selectors are shallow and intention-revealing.
- Styles do not depend on fragile DOM depth or incidental sibling order.
- Specificity stays low; no unnecessary IDs or `!important`.
- Layout uses normal flow, Flexbox, or Grid before absolute positioning.
- Declaration ordering is consistent enough to scan.
- Comments explain non-obvious reasons, not obvious properties.

## 5. Layout And Responsiveness

- The layout works at narrow, medium, and wide viewport widths.
- Text does not overflow, clip, or overlap.
- Touch targets are large enough for real mobile use.
- Fixed-format UI has stable dimensions.
- Critical actions remain available on mobile.
- Empty, loading, and error states preserve layout enough to avoid jarring shifts.

## 6. Interaction States

- Controls have default, hover, focus, active, disabled, and loading treatment where relevant.
- Disabled states explain why the action is unavailable when not obvious.
- Empty states explain the current condition and next action.
- Error states are specific, local, and recoverable.
- Pending states prevent duplicate submission when needed.

## 7. Motion And Performance

- Motion supports state change or spatial continuity.
- Non-essential motion respects reduced-motion preferences.
- Animations use `transform` and `opacity` by default.
- No layout-thrashing animation for ordinary UI.
- Images are appropriately sized and not blocking core UI.
- Scripts do not block initial rendering without a valid reason.

## 8. JavaScript And TypeScript

- Control flow is explicit and readable.
- Derived UI state is not duplicated unnecessarily.
- Simple transformations use array methods; complex branching can use `for...of`.
- Event handlers keep side effects clear.
- External input is validated at boundaries.
- Errors retain useful context.
- Dependencies are justified by product value or complexity reduction.

## 9. Final Review Output

For each issue, include:

- Severity or priority.
- Exact file and line when reviewing code.
- What is wrong.
- Why it matters.
- The smallest useful fix.

If no issues are found, say that clearly and mention any remaining validation gap, such as missing browser, screen reader, or viewport testing.

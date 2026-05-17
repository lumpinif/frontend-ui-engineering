# Frontend UI Engineering

`frontend-ui-engineering` is an agent skill for building and reviewing clear, accessible, maintainable frontend product interfaces.

It turns practical frontend UI engineering principles into concise instructions an AI coding agent can apply while creating components, pages, layouts, HTML, CSS, JavaScript, TypeScript, responsive behavior, accessibility, interaction states, motion, and UI review feedback.

## Credits

This skill synthesizes and modernizes ideas from two excellent open-source frontend guides:

- Nicolas Gallagher's `idiomatic-css`: https://github.com/necolas/idiomatic-css
- Benjamin De Cock's `frontend-guidelines`: https://github.com/bendc/frontend-guidelines

This repository does not redistribute either guide as copied source material. It adapts shared principles into a modern frontend UI engineering guideline written in its own structure and wording.

## What This Skill Optimizes For

- Semantic, accessible HTML before ARIA or custom widgets.
- Readable CSS with stable formatting, shallow selectors, and low specificity.
- Practical TypeScript and JavaScript that favors clarity over clever tricks.
- Complete UI states: loading, empty, error, disabled, pending, success, focus, hover, and active.
- Responsive layouts that adapt without overlap, clipping, or hidden critical actions.
- Motion that supports state and performance instead of decorative churn.
- UI review feedback that names concrete issues and small fixes.

## Structure

```text
frontend-ui-engineering/
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
`-- references/
    `-- review-checklist.md
```

`SKILL.md` contains the core rules the agent should apply during normal UI work.

`references/review-checklist.md` is loaded only for explicit review, audit, polish, or best-practices tasks.

`agents/openai.yaml` contains optional UI metadata for compatible skill surfaces.

## Example Prompts

```text
Use $frontend-ui-engineering to review this settings page for accessibility and maintainability.
```

```text
Use $frontend-ui-engineering while building this dashboard so the HTML, CSS, states, and responsive behavior stay production-ready.
```

```text
Use $frontend-ui-engineering to polish this form interaction and error state.
```

## Design Philosophy

The skill treats frontend UI as product engineering. A good interface is not only visually polished; it is semantic, understandable, keyboard-accessible, responsive, observable through its states, and easy for the next engineer to change safely.

The highest-level rule is simple: choose user correctness and long-term clarity over cleverness, novelty, or personal style.

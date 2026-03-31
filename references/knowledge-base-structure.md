# Knowledge Base Structure Reference

Use this reference when the user wants a maintainable team knowledge base rather than only a one-time onboarding page.

## Goal

The landing page should help someone orient quickly. The split Markdown pages should help the team maintain, extend, and trust the documentation over time.

## Default Deliverable Set

Use this file set unless the repo is tiny and clearly needs less:

```text
index.html
01-overview.md
02-core-flow.md
03-module-map.md
04-change-guide.md
05-debugging.md
06-sources-and-gaps.md
```

## Page Roles

### `index.html`

Use as the front door.

It should answer:

- What is this service or app?
- How do I get my bearings?
- What should I read first?
- What are the most common task and debug entry points?

Do not overload it with every detail. It should be skimmable in 5-10 minutes.

### `01-overview.md`

Use for:

- system purpose
- runtime model
- upstream and downstream boundaries
- local run/test commands
- day-one versus later learning guidance

### `02-core-flow.md`

Use for:

- one or two important request or user flows
- main actors and files
- data handoffs
- critical failure points

This page should be more explicit than the landing page and easier to keep up to date when flows change.

### `03-module-map.md`

Use for:

- important directories
- architectural zones
- where to start reading
- where tests live
- what to ignore at first

### `04-change-guide.md`

Use for:

- common task recipes
- "if you want to change X, start here"
- likely file touchpoints
- adjacent tests or config to update

This is often the highest leverage page after overview.

### `05-debugging.md`

Use for:

- symptom-based troubleshooting
- logs, traces, scripts, and test entry points
- common root causes
- triage order

Prefer direct operational guidance over theory.

### `06-sources-and-gaps.md`

Use for:

- listing the files used as evidence
- separating evidence-backed claims from assumptions
- documenting missing setup, process, or org knowledge
- telling the team what to add next

This page is mandatory in knowledge-base mode unless the user explicitly says not to include it.

## Writing Rules

- The split pages should not duplicate the landing page paragraph by paragraph.
- Link decisions back to real files and modules.
- Prefer change entry points over abstract architecture narration.
- If a page would mostly repeat boilerplate, shorten it.
- If the repo lacks operational context, say so directly.

## Maintenance Rules

- Write pages so a teammate can update only one page after a local change.
- Avoid entangling unrelated topics in the same page.
- Separate code facts from team-process facts.
- Keep a visible backlog of missing information instead of pretending the codebase answers everything.

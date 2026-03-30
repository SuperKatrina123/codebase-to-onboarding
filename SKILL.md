---
name: codebase-to-onboarding
description: "Turn any codebase into a practical onboarding page for new team members. Use this skill whenever someone wants to explain a repo to a new engineer, create a newcomer guide, generate an internal onboarding page, map the architecture for teammates, or help someone become productive quickly in an existing codebase. Also trigger when users mention 'make onboarding docs from this repo,' 'turn this codebase into a team onboarding page,' 'explain this project for a new teammate,' 'new engineer handoff,' or 'repo walkthrough for onboarding.' The output should be a polished single-page HTML onboarding guide with setup steps, repo map, key flows, debugging entry points, common tasks, and team conventions."
---

# Codebase-to-Onboarding

Transform any codebase into a practical, beautiful onboarding page for new team members. The output should be a single self-contained HTML file that helps a newcomer understand what the system does, how to run it locally, where key logic lives, how one or two important workflows move through the code, where to make common changes, and how to debug the most likely problems.

The goal is not to teach computer science. The goal is to help a new teammate become productive quickly and confidently.

## First-Run Welcome

When the skill is first triggered and the user has not specified a codebase yet, introduce yourself like this:

> **I can turn a codebase into a practical onboarding page for new team members.**
>
> Point me at:
> - **A local folder** — e.g. "turn ./my-project into an onboarding page"
> - **A GitHub repo** — e.g. "make onboarding from https://github.com/org/repo"
> - **The current project** — e.g. "turn this repo into onboarding docs"
>
> I will inspect the codebase, identify the setup flow, key directories, core system flows, common change points, and debugging entry points, then generate a single-page HTML onboarding guide your team can open in a browser.

If the user provides a GitHub link, clone it first into a temporary directory before analysis. If they say "this codebase" or similar, use the current working directory.

## Who This Is For

The target learner is a **new teammate** joining an existing project. They may be:

- A new engineer joining the team
- A contractor picking up the repo quickly
- A product-minded builder who can code but lacks context on this specific system
- A cross-functional teammate who needs working architectural understanding

Assume they are capable, but context-poor. They do not need a beginner programming course. They need:

- A fast mental model of what the product does
- A reliable way to run the project locally
- A map of the important files and modules
- A way to trace the most important user flows through the system
- Confidence about where to make common changes
- A practical debugging starting point when things break
- Enough vocabulary and system understanding to ask good questions in the team

The tone should feel like a senior teammate giving a high-quality handoff: warm, direct, practical, and concrete.

## Core Outcome

By the end of the onboarding page, a new teammate should be able to answer:

- What does this system do?
- How do I run it locally?
- Which directories and modules matter most?
- What happens during one core user flow?
- Where would I make common product changes?
- If something breaks, where should I look first?
- What conventions or patterns does this codebase expect me to follow?

If the page does not help the learner answer those questions, it is incomplete.

---

## The Process (4 Phases)

### Phase 1: Codebase Analysis

Read the README, package manifests, entry points, main routes, core services, configuration files, tests, and any docs already present. Figure out what the product does from the codebase itself.

Extract:

- Product purpose in plain language
- Local setup and run commands
- Main directories and what each one is responsible for
- Core architectural layers and actors
- One or two critical user or system flows
- Common change surfaces (UI text, API endpoint, data model, business logic, config)
- Debugging entry points (logs, error boundaries, tests, dev scripts, health checks)
- Team conventions visible in the repo (folder patterns, naming, test style, config organization, env setup, CI expectations)
- Sharp edges and newcomer traps

Do not dump the entire file tree. Curate. Show only the parts a newcomer actually needs in week one.

### Phase 2: Onboarding Design

Turn the analysis into a focused onboarding journey. Organize the page into 6-8 modules. The arc should move from orientation to action:

| Module Position | Purpose | Why it matters |
|---|---|---|
| 1 | What this project is and why it exists | Gives the newcomer a product-level mental model |
| 2 | How to run it locally | Gets them unblocked fast |
| 3 | Repo map and key modules | Helps them navigate confidently |
| 4 | One important flow through the system | Builds causal understanding |
| 5 | Common tasks and where to edit | Makes them productive |
| 6 | Debugging and failure points | Helps them recover when stuck |
| 7 | Team conventions and delivery path | Helps them contribute cleanly |

Adapt this to the codebase. A tiny library may need fewer sections. A full-stack app may need one extra module for infra or deployment boundaries.

Each module should contain:

- 2-5 short screens or blocks
- At least one diagram, map, checklist, code translation, or flow visual
- At least one "what you should remember" takeaway
- Practical language tied to real work

Optional quizzes are allowed, but they should test practical onboarding judgment, not trivia.

### Phase 3: Build the Onboarding Page

Generate a single HTML file with embedded CSS and JavaScript. Read:

- `references/design-guidelines.md`
- `references/onboarding-elements.md`

Build in this order:

1. Foundation: shell, navigation, progress, responsive layout, scroll behavior
2. Orientation modules: product overview, setup, repo map
3. System understanding modules: core flow, common tasks, debugging
4. Conventions module: code style clues, testing, contribution path
5. Final polish: mobile readability, visual consistency, accessibility, smooth interaction

### Phase 4: Review and Hand Off

After generating the HTML, open it for review. Summarize:

- What the product is
- What the most important newcomer knowledge is
- Which modules are most useful for day one versus week one
- Any gaps caused by missing docs or ambiguous code

If the repo lacks enough setup or convention information, say so clearly in the output rather than guessing.

---

## Recommended Module Types

These are the default building blocks for a strong onboarding page:

### 1. Project Snapshot

Explain in plain language:

- What the product does
- Who uses it
- The main value of the system
- The big moving parts at a glance

This section should feel like "what am I looking at?" in under one minute.

### 2. Getting Started Checklist

Include:

- Required tools
- Install steps
- Env file expectations
- Main run command
- Test command
- Common setup failures

This should be highly skimmable and operational.

### 3. Repo Map

Show a visual tree or grouped cards for the most important folders. Explain:

- Where frontend lives
- Where backend lives
- Where shared types or utilities live
- Where config lives
- Where tests live
- Which folders a newcomer can ignore at first

### 4. Core Flow Walkthrough

Trace one meaningful path, such as:

- User signs in
- User creates an item
- API request reaches the server
- Background job processes data
- UI fetches and renders a result

This section should answer: "When the product does the thing it is known for, what happens under the hood?"

### 5. Common Tasks

Give newcomers concrete recipes:

- Change a label or UI copy
- Add a field to a form
- Add a backend endpoint
- Extend a data model
- Update configuration

For each task, point to likely files and explain why those are the right starting points.

### 6. Debugging Playbook

Show where to look first when:

- The app does not start
- A request fails
- Data does not appear
- A UI interaction stops working
- Tests fail unexpectedly

This is often the highest-value section in the whole page.

### 7. Team Conventions

Infer visible conventions from the codebase and present them explicitly:

- Folder organization patterns
- Naming conventions
- Testing habits
- State management patterns
- API client patterns
- Error handling style
- Configuration expectations

Do not invent conventions that are not visible in the repo.

---

## Content Principles

### Prioritize action over theory

This is onboarding, not a course. Every section should help the newcomer do something useful sooner.

### Curate aggressively

A newcomer does not need every folder and every abstraction. Highlight the 20% of the repo that explains 80% of the work.

### Show real paths through the code

Do not describe architecture in generic terms alone. Trace actual files, modules, and flows.

### Prefer operational language

Use phrasing like:

- "If you want to change X, start here"
- "If this breaks, check these layers in order"
- "This folder matters because..."
- "You can ignore this until you touch..."

### Surface newcomer traps

If there are likely gotchas, call them out:

- Hidden env requirements
- Non-obvious startup order
- Generated files
- Required background services
- Fragile mocks or fixtures
- Parallel backend/frontend setup

### Explain the why behind repo structure

Do not just say what a folder contains. Explain why the team likely separated concerns that way.

---

## Required Elements

Every onboarding page must include all of the following:

- **Project Snapshot**
- **Getting Started Checklist**
- **Repo Map**
- **At least one Core Flow visualization**
- **At least one Code ↔ Plain English translation block**
- **Common Tasks section**
- **Debugging Playbook**
- **Team Conventions section**

These are the backbone of the onboarding experience.

Optional elements:

- Scenario quiz
- Architecture diagram
- Day-one / week-one checklist
- Ownership map if visible from codebase structure or docs
- Release pipeline summary if it is clearly visible in CI or scripts

---

## Implementation Rules

- Output must be a single self-contained HTML file
- Use `scroll-snap-type: y proximity`, not `mandatory`
- Use responsive layouts that stack cleanly on mobile
- Keep text blocks short and scannable
- Prefer cards, diagrams, annotated trees, and checklists over long prose
- Use original code snippets exactly as they appear in the codebase
- Never fabricate setup commands, services, owners, or workflows
- If information is missing, state "not obvious from the repository" rather than guessing
- Wrap all JavaScript in an IIFE
- Use `requestAnimationFrame` for scroll-linked UI work
- Use `passive: true` on scroll listeners

---

## Common Failure Modes

### Too much explanation, not enough orientation

If the page reads like a tutorial instead of a teammate handoff, it has drifted off target.

### Dumping the file tree

A raw directory listing is not onboarding. Curate the important zones and explain why they matter.

### Guessing setup steps

Never invent commands or requirements just to make the onboarding page look complete.

### Missing common tasks

Newcomers need to know how to make typical changes, not just admire the architecture.

### Vague debugging advice

"Check the logs" is weak. Point to actual scripts, files, layers, or commands when visible.

### Overclaiming conventions

Only describe conventions you can infer from code, config, tests, scripts, or docs.

### No distinction between day one and later

A good onboarding page tells the newcomer what matters immediately versus what can wait.

---

## Reference Files

The `references/` directory contains supporting guidance:

- `references/design-guidelines.md` — layout, typography, hierarchy, and visual tone for onboarding pages
- `references/onboarding-elements.md` — implementation patterns for checklists, repo maps, flow walkthroughs, debug playbooks, common-task cards, and code translation blocks

Use these references during build so the final page feels like a polished internal product, not a generic wall of text.

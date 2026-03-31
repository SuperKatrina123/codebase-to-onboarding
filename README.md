# Codebase to Onboarding

A skill that turns any codebase into a practical onboarding page or starter team knowledge base for new team members.

Instead of generating a general tutorial, this skill creates either:

- a single-page HTML onboarding guide for fast orientation
- or, when the user wants a team knowledge base, a landing page plus split Markdown docs

The content is focused on helping a newcomer become productive quickly:

- understand what the system does
- run it locally
- navigate the important folders
- trace one or two critical flows
- find the right place for common changes
- debug common failures
- infer team conventions from the repository

## Who this is for

This skill is designed for:

- new engineers joining a team
- contractors or contributors picking up a repo fast
- product-minded builders who can code but lack project context
- cross-functional teammates who need architectural understanding

It is not trying to teach computer science from scratch. It is trying to provide a high-quality teammate handoff.

## Output

### Mode A: Onboarding Page

The default output is a single self-contained HTML onboarding page with:

- a project snapshot
- a getting-started checklist
- a repo map
- a core flow walkthrough
- common-task entry points
- a debugging playbook
- a team-conventions section

### Mode B: Team Knowledge Base

When the user's end goal is a maintainable team knowledge base, the output should be a bundle with:

- `index.html` as the landing page
- `01-overview.md`
- `02-core-flow.md`
- `03-module-map.md`
- `04-change-guide.md`
- `05-debugging.md`
- `06-sources-and-gaps.md`

The landing page should optimize for quick orientation. The Markdown pages should optimize for long-term maintenance and linking.

## How to use

Place this folder where your skill runner expects custom skills, then invoke it on:

- the current repo
- a local path
- a GitHub repository URL

Typical usage patterns:

- "Turn this codebase into an onboarding page"
- "Create onboarding docs for this repo"
- "Build a team knowledge base from this repo"
- "Make a newcomer guide from this project"
- "Explain this repo for a new teammate"
- "Generate a team onboarding page from this codebase"

## Suggested trigger phrases

Short triggers:

- "turn this into onboarding"
- "make onboarding for this repo"
- "create newcomer docs"
- "repo onboarding page"
- "new engineer handoff"
- "team knowledge base from this repo"

More explicit triggers:

- "Turn this codebase into a team onboarding page"
- "Build a team knowledge base from this repository"
- "Create an onboarding guide for a new engineer joining this project"
- "Explain this repository like I just joined the team"
- "Make a single-page onboarding doc from this repo"
- "Build an internal onboarding page for this codebase"
- "Map this repo for a newcomer and show where common changes happen"
- "Generate onboarding docs with setup, repo map, and debugging tips"

## Example prompts

For the current project:

```text
Turn this codebase into an onboarding page for a new teammate.
```

For a local folder:

```text
Make onboarding docs from ./apps/dashboard and focus on day-one setup plus common frontend changes.
```

For a GitHub repo:

```text
Create a newcomer onboarding page from https://github.com/example/repo and include a repo map, a core request flow, and likely debugging entry points.
```

For a team knowledge base:

```text
Build a team knowledge base from ./services/bff. I want a landing page plus split Markdown docs the team can keep updating.
```

For a more product-oriented handoff:

```text
Explain this repository like I just joined the team. Show what the product does, how to run it, where the main logic lives, and where I would go to add a small feature.
```

## Example output structure

### Landing page

A strong onboarding landing page will usually look like this:

### 1. Project Snapshot

- what the product does
- who uses it
- key system pieces at a glance

### 2. Day-One Checklist

- tools required
- install steps
- env setup
- run command
- smoke-test command

### 3. Repo Map

- important folders
- what each one is responsible for
- what to ignore at first

### 4. Core Flow Walkthrough

- one meaningful user or system journey
- the main actors involved
- important files touched along the way

### 5. Common Tasks

- change UI text
- add a field
- extend an endpoint
- update validation
- tweak config

### 6. Debugging Playbook

- app won't start
- request fails
- data does not show up
- UI interaction breaks
- tests fail

### 7. Team Conventions

- naming patterns
- folder patterns
- test placement
- data flow conventions
- error handling style

### Split knowledge-base pages

In knowledge-base mode, add split pages such as:

- `01-overview.md`
- `02-core-flow.md`
- `03-module-map.md`
- `04-change-guide.md`
- `05-debugging.md`
- `06-sources-and-gaps.md`

## What makes this skill useful

The skill is opinionated in a practical way:

- it curates instead of dumping the whole file tree
- it prioritizes action over theory
- it avoids inventing missing setup details
- it explains where to make changes, not just what the architecture is
- it tries to reduce newcomer overwhelm by separating "learn now" from "learn later"
- it can bridge from a one-time onboarding page to maintainable team docs

## File structure

```text
codebase-to-onboarding/
├── README.md
├── SKILL.md
└── references/
    ├── design-guidelines.md
    ├── knowledge-base-structure.md
    └── onboarding-elements.md
```

## Notes

- If setup or team conventions are not obvious from the repository, the skill should say so clearly rather than guessing.
- The most valuable sections are usually `Getting Started Checklist`, `Repo Map`, `Core Flow Walkthrough`, and `Debugging Playbook`.
- In knowledge-base mode, the most valuable extra page is usually `06-sources-and-gaps.md`.
- You can refine the skill later after testing it on real repos from your team.

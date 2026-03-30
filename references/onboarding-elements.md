# Onboarding Elements Reference

Use these elements to make the onboarding page practical and easy to navigate.

## 1. Getting Started Checklist

Best for:

- Tool requirements
- Install steps
- Env setup
- Start commands
- Smoke-test commands

Structure:

- Requirement
- Command
- Why it matters
- Common failure note

## 2. Repo Map

Best for:

- Highlighting important folders
- Separating "learn now" from "ignore for now"
- Showing architectural zones

Good formats:

- Annotated file tree
- Folder cards by responsibility
- Layered diagram (UI / API / data / infra)

## 3. Core Flow Walkthrough

Best for:

- A product-critical path
- Request/response flow
- User interaction to persistence cycle

Recommended ingredients:

- Trigger
- Main actors
- File touchpoints
- Data handoff
- Failure points

## 4. Common Task Cards

Best for:

- "Change UI copy"
- "Add a field"
- "Extend an endpoint"
- "Adjust validation"
- "Update config"

Each card should include:

- Task name
- Where to start
- Likely files
- Why those files matter
- What else might need updating

## 5. Debugging Playbook

Best for:

- Startup failures
- Missing data
- Broken interaction
- API errors
- Test failures

Recommended format:

- Symptom
- First place to look
- Second place to look
- Useful command or file
- Typical root cause

## 6. Code ↔ Plain English Translation

Use for:

- Entry points
- Data-fetching code
- Route handlers
- State transitions
- Important glue code

Rules:

- Use exact code from the repo
- Pick short, high-signal snippets
- Explain why the snippet matters in the system

## 7. Day-One vs Later Callout

Helpful for reducing overwhelm.

Examples:

- Learn today
- Skim this later
- Ignore until you touch billing

## 8. Conventions Grid

Best for surfacing patterns such as:

- Naming style
- Folder rules
- Test placement
- API client pattern
- Error handling style
- State management pattern

Only include conventions that are visible from the repository.

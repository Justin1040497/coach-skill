# Planning Mode

Use this reference only when the user explicitly asks for:

- a project plan
- module breakdown
- architecture direction
- ownership split
- roadmap
- overall build order
- saving the plan to the target project's `docs/plan/` directory

Do not use this reference for a small local coding, debugging, or review question.

## Start Flow

Follow this order:

1. Ask only the minimum questions needed to write a useful plan.
2. Do not guess if a key detail is missing.
3. Once the scope is clear enough, ask whether the user wants the plan saved as a Markdown file.
4. Save the plan only after the user confirms.

Useful questions usually include:

- what the project or feature is trying to achieve
- what type of project this is
- what the main business flow looks like
- what the main content or modules are
- what already exists
- what the current blocking point is
- what stack is already chosen, if any
- what part the user wants to own personally
- what part they are okay with AI accelerating

Do not turn a local problem into a full roadmap unless the user asks for that.

## Architecture First

If the user is in the early stage of the project, do this before writing the task list:

1. understand the project type
2. understand the core business flow
3. understand the main modules or content areas
4. recommend an architecture
5. explain why that architecture fits this project

Do not recommend an architecture before you understand the actual project.

If the project already exists, identify the current architecture first, then explain whether the plan should keep it, refine it, or change it.

## Save Path

When the user confirms, save the plan to:

- `<project-root>/docs/plan/YYYY-MM-DD-<feature-name>.md`

This path is in the user's project workspace, not in the skill's own directory.

Use a short kebab-case name for `<feature-name>`.

If the user does not provide a name, derive one from the actual scope of the plan.

If the target project does not already have `docs/plan/`, create it in the project before saving the plan.

## Planning Rules

- Keep the plan scoped to the user's actual ask.
- Keep the steps concrete. Avoid vague phrases like "improve architecture" or "optimize performance".
- Each task should be one meaningful chunk of work. If a task is too large to explain clearly, split it.
- Each task must have a finish line.
- At the beginning of the plan, state what architecture the project uses or should use, and explain why.
- Use plain language.
- Keep the skill's original user/AI boundary intact.

## Ownership Labels

Every task in the plan must include exactly one ownership label.

Use these labels:

- `User-owned`
- `AI-guide-only`
- `AI-accelerated`
- `AI-direct`

Choose the label using the skill's original boundary rules:

- `User-owned`: project goal, scope, technical choices, architecture, module boundaries, core business logic, performance strategy, debugging, final review
- `AI-guide-only`: important work the user should implement personally while AI only gives hints, checkpoints, review, or questions
- `AI-accelerated`: reusable components, ordinary data flow, validation, admin workflows, and other meaningful but non-core implementation work
- `AI-direct`: scaffolding, repetitive pages, boilerplate, docs, test skeletons, and refactor grunt work

Do not use ownership labels as urgency levels. They are about who should lead the task.

## TDD

TDD means `Test-Driven Development`.

The basic loop is:

1. write a failing test
2. write the minimum code to make it pass
3. refactor while keeping the behavior the same

This is often called:

- `Red`: test fails
- `Green`: make it pass
- `Refactor`: clean it up

Use TDD when:

- the expected behavior is already clear
- the task is mostly logic or data rules
- the result can be checked by tests without too much ambiguity

Do not force TDD when:

- the task is early exploration
- the UI is still moving around quickly
- the requirement is not stable enough yet

Even when a task is not a good fit for TDD, it still needs a finish line. In that case, use acceptance criteria or test cases in plain language.

## Plan Output

When writing the plan, include only the parts that help the user move forward.

Common sections:

- goal
- scope
- what already exists
- architecture
- why this architecture fits
- who owns what
- ordered tasks
- finish line for each task
- risks or unclear parts

If the user only asked for a narrow plan, keep it narrow.

## Plan Header Template

Use a lightweight header like this:

```md
# <Feature Name> Plan

**Goal:** <one-sentence goal>
**Scope:** <what this plan covers>
**Current Context:** <what already exists or what is blocked>
**Architecture:** <recommended architecture or current architecture>
**Why this architecture:** <why it fits this project now>
**Plan Saved:** <yes/no>
```

## Task Template

Use this shape for each task:

```md
### Task N: <Task Name>

**Ownership:** <User-owned | AI-guide-only | AI-accelerated | AI-direct>
**Why this label:** <short reason>
**Goal:** <what this task is for>
**Finish line:**
- <acceptance criterion or test case>
- <acceptance criterion or test case>

**Suggested checks:**
- <test command, manual check, or review question>

**Notes:**
- <only if needed>
```

## Good vs Bad Task Wording

Good:

- Define the login states and verify loading, success, and failure are all handled.
- Split the order page into request state, filter state, and display state, then verify each one can change independently.
- Extract the shared table component and verify both pages can render with the same API.

Bad:

- Improve architecture
- Add validation
- Optimize performance
- Clean up the code

## After Saving

After saving the plan:

- tell the user the exact path
- summarize the first task briefly
- ask whether they want to execute the tasks one by one in the current thread

# Coach

`Coach` is a project-guidance skill for learning projects, portfolio projects, internship projects, campus recruitment projects, competition projects, and interview-prep projects.

After it triggers, it first scans the project, understands what the project contains, maps functional modules, names the architecture, and then asks whether the user wants to continue building, organize the project, or solve a specific problem.

## Core Positioning

`Coach` helps the user understand, split, and explain a project before deciding how to change it.

It focuses on:

- what the project is
- which features already exist
- how complete those features appear
- which functional modules the project contains
- which architecture term best describes the project
- whether the user wants to continue, organize, or fix a module
- whether the module flow and edge cases are clear before implementation

## Default Flow

After triggering, `Coach` will:

1. Decide whether the current directory is a project.
2. Scan it directly if it is a project; otherwise ask for the project path.
3. Summarize project type and current features.
4. Split the project into functional modules.
5. Name the project architecture with professional terms.
6. Ask whether the user wants to continue building, organize the project, or solve a problem.
7. Discuss the plan after the user chooses a module.
8. Provide both a Mermaid flowchart and a text visual flowchart after the plan is clear.
9. Ask whether the user wants to implement it themselves or have the Agent implement it according to the confirmed flowcharts.

## Functional Module Mapping

`Coach` splits by what the project does, not by architecture layers.

For example, a note-taking project may contain:

- editor system
- image handling system
- undo/redo system
- local storage system
- search and categorization system

It should not split the project into:

- domain layer
- application layer
- infrastructure layer
- repository interface
- repository implementation

Architecture layers can be mentioned in the architecture section, but they are not functional modules.

## Module Change Flow

When the user wants to add, change, or update a module, `Coach` first clarifies:

- module goal
- user interaction flow
- inputs and outputs
- state changes
- data creation, saving, recovery, and deletion timing
- errors and edge cases
- relationships with other modules
- what is out of scope

If a key detail is unclear, `Coach` asks instead of guessing.

## Flowcharts

After the plan is confirmed, `Coach` provides both:

- Mermaid flowchart
- text visual flowchart

The text visual flowchart uses indentation, arrows, and `Y/N` branches for quick reading.

## Execution Choice

After the flowcharts, `Coach` asks:

```text
Do you want to implement this yourself, or should the Agent implement it according to the confirmed flowcharts?
```

If the user implements:

- provide implementation steps
- provide checkpoints
- provide acceptance criteria
- do not provide full code
- do not edit files

If the Agent implements:

- strictly follow the confirmed plan and flowcharts
- do not add unrelated features
- ask when key details are unclear
- verify syntax, framework, package, or toolchain issues with official documentation or reliable sources
- create `docs/logs/` at the project root and write a completion log

## Completion Log

After Agent implementation, the log must include:

- behavior summary
- which plan or flowchart was followed
- modified files
- added files
- purpose of each added file
- deleted files
- explicitly say `No deleted files` if none were deleted
- unfinished items or points needing user confirmation
- validation method or test result

## Final User Summary

After writing the log, `Coach` also gives the user a very easy-to-understand final summary.

This summary is not the log and should not just list files. It is a plain-language feature summary the user can reuse in a project review or interview.

It should explain:

- what feature or problem was completed
- what technical approach or architecture was used
- why that approach fits this project
- what important cases or constraints were considered
- why another approach was not used
- how the feature works at a high level
- what the user can say if someone asks how this feature was built

Keep this summary very plain and avoid unnecessary technical wording. If a technical term is useful, explain it immediately in simple words.

After the summary, `Coach` asks whether the user understood it and gives several interview-style questions.

The questions may test simple ideas, but should sound slightly professional so the user can practice common interview wording. Examples:

- Why did you choose this implementation approach?
- What problem does this module solve in the overall workflow?
- Which edge cases did you consider?
- What happens if the operation fails halfway?
- If the data size or requirements grow, how would this design change?

## File Structure

- `SKILL.md`: core skill rules and routing
- `agents/openai.yaml`: display name, default prompt, and metadata
- `references/planning.md`: project scanning, functional module mapping, and architecture naming
- `references/coaching.md`: module planning, flowcharts, execution choice, and Agent implementation
- `references/review-checklist.md`: checks for project maps, module plans, and completed work

## Chinese Readme

See [README.md](./README.md).

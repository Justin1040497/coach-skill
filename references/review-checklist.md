# Review Checklist

Use this checklist when reviewing a project map, module plan, flowchart, or completed Agent implementation.

The goal is to keep the work project-aware, module-focused, and aligned with confirmed user intent.

## Project Map Check

Check whether the first project summary answered:

- what type of project this is
- which features already exist
- how complete those features appear
- which functional modules the project contains
- which architecture term best describes the project
- what the user wants to do next

The map should describe the current project, not start with unsolicited criticism.

## Functional Module Check

Good module splits describe behavior areas:

- editing
- image handling
- undo/redo
- local storage
- import/export
- task processing
- draft recovery
- authentication
- search/filtering

Poor module splits confuse architecture with features:

- domain
- application
- infrastructure
- repository interface
- repository implementation
- DTOs

If the split is too fine, merge small items into a behavior area the user can reason about.

## Architecture Check

The architecture section should use professional terms such as:

- layered architecture
- MVVM
- MVC
- MVP
- Clean Architecture
- feature-first architecture
- component-based architecture
- client-server architecture
- event-driven architecture

If the label is approximate, say it is approximate.

## Module Plan Check

Before implementation, verify that the plan covers:

- target behavior
- user interaction flow
- inputs and outputs
- state changes
- data lifecycle
- error and edge-case handling
- related modules
- out-of-scope items

For file/task/draft/cache/storage modules, lifecycle and recovery rules are required.

## Flowchart Check

A valid plan should include both:

- Mermaid flowchart
- text visual flowchart with arrows, indentation, and `Y/N` branches

The implementation must follow these flowcharts unless the user confirms a change.

## Execution Check

Before files are edited, the user must choose:

- user implements
- Agent implements

If the user implements, provide steps and checks, not full code.

If the Agent implements, verify:

- the change stayed inside the confirmed scope
- unclear key details were asked about
- syntax/framework/toolchain issues were checked against official docs or reliable sources
- low-value style-only issues did not distract from the module goal

## Completion Log Check

After Agent implementation, confirm there is a log under:

`docs/logs/`

The log must include:

- behavior summary
- which plan or flowchart was followed
- modified files
- added files
- purpose of each added file
- deleted files
- `No deleted files` if none were deleted
- unfinished items or points needing user confirmation
- validation method or test result

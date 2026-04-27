# Project Discovery And Module Mapping

Use this reference when the skill first triggers, or when the user asks to understand, plan, continue, organize, or troubleshoot a project.

## Project Detection

First decide whether the current working directory is a project.

Common project signals:

- `README`, `docs/`, `.git/`
- `package.json`, `vite.config.*`, `next.config.*`
- `pubspec.yaml`
- `pom.xml`, `build.gradle`, `settings.gradle`
- `Cargo.toml`, `go.mod`, `pyproject.toml`
- `src/`, `lib/`, `app/`, `test/`, `tests/`

If the current directory has clear project signals, scan it. If not, ask the user for the project path.

## What To Scan

Read enough to understand the project, without loading irrelevant files.

Prefer:

- file tree
- README and docs
- dependency and build configuration
- app entry points
- routing/navigation
- major pages or screens
- state management
- data models
- services/API/storage
- tests, if present

Avoid starting with code-quality critique. The first output should be a project map.

## First Output Shape

After scanning, answer in this order:

1. `Project Type`
2. `Current Features`
3. `Feature Completion`
4. `Functional Modules`
5. `Architecture`
6. `Next Choice`

Keep the summary grounded in actual files. If something is inferred, say it is inferred.

## Functional Module Mapping

Split by what the project does, not by architecture folders.

Good functional modules:

- editor system
- image handling system
- undo/redo system
- local storage system
- search and filtering system
- import/export system
- compression task system
- draft recovery system
- authentication system
- notification system

Bad functional modules:

- domain layer
- application layer
- infrastructure layer
- controller folder
- repository interface
- repository implementation
- DTO folder

Architecture layers can be mentioned in the architecture section, but they are not the functional module map.

Do not split too finely. A module should represent a meaningful behavior area that a user or developer can discuss as one unit.

## Architecture Naming

Use professional architecture terms after the functional module map.

Common labels:

- layered architecture
- MVVM
- MVC
- MVP
- Clean Architecture
- feature-first architecture
- component-based architecture
- client-server architecture
- event-driven architecture

If the project partially matches a pattern, write that clearly.

Example:

`The project is closest to layered architecture with some MVVM-style screen organization. It does not look like strict Clean Architecture because the boundaries between domain and infrastructure are not fully isolated.`

## Ask User Intent

End the first project map by asking what the user wants to do next:

- continue building the project
- organize existing work
- solve a specific problem

Also ask which functional module they want to work on and what they want that module to become.

Do not proactively decide that a module is bad. Ask for the desired change, target behavior, or problem first.

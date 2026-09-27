# Team Engineering Principles

This repository defines the working principles, engineering conventions, and project workflow of Buckyball.

## 1. Project Management

We use GitHub Projects as the source of truth for project progress.

All actionable work should be represented by an Issue or Pull Request and tracked on the project Kanban board.

The default workflow is:

Backlog → Todo → In Progress → Review → Done

### Rules

- Every meaningful task should have a corresponding Issue.
- Each Issue should describe the expected result clearly.
- Work in progress should be visible on the Kanban board.
- Pull Requests should be linked to the corresponding Issue.
- A task is considered complete only after the related code has been reviewed, tested, and merged.
- The README describes the project; the Kanban board tracks project progress.
- Completed, cancelled, or obsolete tasks should be closed instead of remaining in active columns.

## 2. Keep It Simple

Follow the KISS principle.

Prefer the simplest implementation that clearly solves the problem.

- Do not introduce unnecessary abstractions.
- Avoid creating large collections of small helper functions.
- Do not add wrappers merely to hide straightforward logic.
- Introduce a helper only when it represents a stable, reusable abstraction.
- Prefer readable and direct code over clever code.

## 3. Fail Fast

Do not silently hide unexpected states.

- Do not add speculative fallbacks.
- Do not silently recover from invalid input or inconsistent state.
- Raise an explicit error when behavior does not match the expected contract.
- Error messages should identify the failed operation and the relevant context.
- A failure should be visible during development and testing.

## 4. Make Deliberate Breaking Changes

Do not preserve compatibility by default.

When the current design is incorrect, unnecessarily complex, or difficult to maintain, prefer a clear and decisive change.

- Avoid compatibility layers unless compatibility is an explicit requirement.
- Do not retain obsolete APIs only because they already exist.
- Update all affected code, tests, and configuration together.
- Document a breaking change when it affects other users or projects.

## 5. Documentation Ownership

Documentation should describe the intended and verified behavior of the project.

- AI must not independently author project documentation.
- AI may update documentation after a code change to synchronize it with the verified implementation.
- Synchronization must preserve the existing document structure, format, and terminology.
- Human contributors remain responsible for the meaning and final review of documentation.
- Do not rewrite unrelated documentation during a code change.

## 6. Configuration and Environment Variables

Minimize user-defined configuration.

- Prefer explicit defaults and configuration that can be understood from the code.
- Do not introduce a custom environment variable unless it is necessary.
- Avoid configuration that is difficult to discover, validate, or maintain.
- Every required environment variable must have a clear name, purpose, type, and example.
- Fail clearly when a required configuration value is missing or invalid.

## 7. Definition of Done

A task is complete only when:

- The implementation satisfies the Issue requirements.
- The code follows these principles.
- Relevant tests or validation have passed.
- The Pull Request has been reviewed.
- Documentation has been synchronized when necessary.
- The Issue and Kanban card accurately reflect the final status.

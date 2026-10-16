# Code Refactoring Prompt — Tekstain Nexus ESG Platform

Act as a senior software engineer. Refactor the selected code to improve readability, maintainability, consistency, and testability **without changing its intended behavior**.

## Instructions
1. Review the relevant project files and existing tests first. Follow the project's PRD, `Frontend_PRD.md`, `Architecture.md`, and `Kwoledge_base.md` where available; do not invent new requirements.
2. Identify duplicated logic, overly complex functions, unclear naming, poor separation of concerns, and avoidable performance issues.
3. Make small, focused changes. Preserve existing APIs, user workflows, data formats, permissions, and database behavior unless explicitly authorized to change them.
4. Do not add features, change product scope, remove safeguards, or introduce unnecessary dependencies.
5. Treat security, organization-level data isolation, auditability, data validation, and carbon-accounting calculations as high-risk areas. Preserve deterministic calculations and traceability to activity data, units, emission factors, and calculation versions.
6. Add or update tests where needed to demonstrate that behavior remains unchanged. Run relevant tests, linting, and type checks when available. Do not claim checks passed unless they were actually run.
7. If a change could alter behavior, data integrity, security, calculations, or compatibility, explain the risk and ask for authorization before proceeding.

## Expected Output
- Brief summary of the refactoring goals.
- Files and components changed, with reasons.
- Important behavior-preservation considerations.
- Tests and checks run, including actual results.
- Remaining risks or recommended follow-up work.

**Scope:** Refactor only the code explicitly selected or necessary for the agreed task. Do not generate unrelated files or implement new functionality.

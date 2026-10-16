# Gap Analysis Implementation Prompt — Tekstain Nexus ESG Platform

Act as a senior software engineer and QA engineer. Use the findings from `gap_analysis.md` together with the project PRD, `Frontend_PRD.md`, `Architecture.md`, `Kwoledge_base.md`, the current source code, and existing tests to address identified implementation gaps.

## Implementation Instructions

1. **Start with the highest-priority tests.** Address Critical gaps first, then High, Medium, and Low, while respecting dependencies and security risks.
2. Implement tests one at a time or in logical, tightly related groups. After each test or group, run the relevant test suite and make sure it passes before proceeding.
3. Where a gap lacks a test, create an appropriate test before changing the implementation. Test the expected behavior stated in the project requirements; do not weaken, delete, or alter a valid test merely to make it pass.
4. Make the smallest safe code changes needed to satisfy the requirements and tests. Preserve existing behavior unless a documented requirement or confirmed gap requires a change.
5. Follow the current architecture and coding conventions. Avoid unrelated refactoring, new features, unnecessary dependencies, and broad rewrites.
6. Pay particular attention to tenant data isolation, authorization, privacy, audit trails, ESG data validation, carbon calculation accuracy and traceability, report integrity, and error handling.
7. For carbon calculations, use the defined calculation logic and documented emission factors. Do not invent emission factors, regulatory requirements, or framework mappings.
8. Do not hard-code secrets or expose confidential organizational data. Keep authorization and important data-integrity rules enforced on the server side.
9. If a requirement is ambiguous, a dependency is missing, or a safe fix cannot be verified, explain the issue and avoid guessing. Continue with independent, well-defined high-priority work where possible.
10. Do not claim that tests pass unless you actually ran them. Report any tests that could not be run and why.

## Working Process

For each gap or logical group:

1. Identify the gap ID, priority, evidence, expected behavior, and dependencies from `gap_analysis.md`.
2. Inspect the relevant implementation and existing tests.
3. Add or update focused tests that capture the required behavior.
4. Run the relevant tests and record the initial result.
5. Implement the smallest necessary fix.
6. Rerun the focused tests, then the broader relevant suite to check for regressions.
7. Review the changes for security, data integrity, maintainability, and alignment with project documentation.
8. Mark the gap as resolved only when the required behavior is verified; otherwise record the remaining work and evidence.

## Required Final Report

When the work is complete, provide:

- Gaps addressed, identified by gap ID and priority.
- Tests added or changed.
- Commands run and actual pass/fail results.
- Files changed and a brief explanation of each change.
- Any regressions, unresolved gaps, blocked tests, or assumptions.
- The next recommended gaps to address, ordered by priority and dependency.

Begin with the highest-priority actionable gap and its tests. Work incrementally, keep the tests passing after each logical group, and do not attempt to fix every gap in one unverified batch.

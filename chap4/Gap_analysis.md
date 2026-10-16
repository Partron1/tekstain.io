# Gap Analysis Prompt — Tekstain Nexus ESG Platform

Act as a senior business analyst and software architect. Review the available project documents and implementation, including the main PRD, `Frontend_PRD.md`, `Architecture.md`, `Kwoledge_base.md`, and relevant source code and tests.

## Objectives

1. Compare the documented requirements and architecture with the current implementation.
2. Identify missing, incomplete, inconsistent, duplicated, or unsupported requirements and components.
3. Check critical areas: user workflows, ESG data collection, carbon calculation traceability, report generation, multi-tenant data isolation, permissions, privacy, audit trails, error handling, accessibility, and testing.
4. Separate confirmed findings from assumptions. Cite the relevant requirement, document section, file, or code location for each finding.
5. Prioritize each gap as **Critical**, **High**, **Medium**, or **Low**, and explain its impact, evidence, and recommended next action.
6. Identify dependencies and suggest a practical order for addressing the gaps.

## Required Output

Provide:

- **Executive summary** of overall alignment and the most important risks.
- **Gap table** with: ID, category, requirement/source, current state, evidence, gap, priority, impact, recommended action, and dependencies.
- **Unverified items** that need confirmation rather than being treated as facts.
- **Prioritized action plan** grouped into immediate fixes, MVP blockers, and later improvements.

Do not invent requirements, assume undocumented features exist, or claim tests were run unless you actually ran them. Do not modify files, write code, or implement fixes during the analysis. If a referenced document or source file is unavailable, state that limitation clearly. Follow the project documents where they provide direction, and flag conflicting instructions instead of silently resolving them.

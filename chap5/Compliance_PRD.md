# Compliance PRD Generation Prompt — Tekstain.io

Act as a senior product manager, ESG compliance analyst, privacy specialist, and software requirements engineer. Create a concise but implementation-ready **Compliance Product Requirements Document (PRD)** for the Tekstain Nexus ESG and Carbon Management Platform, designed initially for SMEs and larger organizations in Ghana, with possible future expansion to other African markets.

## Objective
Define how the platform should help organizations manage compliance-related information, evidence, obligations, controls, and reporting workflows. The platform may support compliance work, but must not claim to guarantee legal compliance or replace qualified legal advice, independent assurance, or regulator approval.

## Instructions
1. Review the available project documents first, including the main PRD, `Frontend_PRD.md`, `Architecture.md`, and `Knowledge_base.md`, if they are available. Reuse confirmed decisions and flag contradictions or missing decisions rather than silently resolving them.
2. Research current requirements using authoritative sources when web research is available. Prioritize official Ghanaian legislation and regulators, official reporting-framework publishers, and primary standards sources.
3. Clearly distinguish **binding legal obligations**, **sector-specific requirements**, **voluntary frameworks**, **customer or investor expectations**, and **recommended good practice**. Do not assume all organizations have the same obligations.
4. For every legal or regulatory requirement, record the jurisdiction, affected organization types, source and link, publication/effective date or version where available, verification date, and any uncertainty requiring professional review. Do not invent laws, citations, reporting deadlines, or compliance claims.
5. Keep the MVP practical. Prioritize obligation tracking, evidence/document management, assigned responsibilities, due dates, review workflows, status tracking, audit trails, and clear reporting of missing or unverified information. Place advanced features in later phases unless the project documents establish that they are essential.
6. Treat ESG frameworks and carbon-accounting methodologies as distinct from laws. Include framework mappings only where verified; document partial mappings and limitations.
7. Protect confidential business information and personal data. Specify access controls, organization-level data isolation, data minimization, retention/deletion rules, secure evidence storage, audit logging, and controls for sending data to third-party AI services. Flag legal questions that need qualified review.
8. AI may summarize verified sources, organize evidence, identify gaps, and draft explanations. AI must not invent obligations, determine legal compliance autonomously, or present unverified content as authoritative. Require human review of compliance interpretations and report disclosures.
9. Do not generate application code. Focus on product requirements and testable behavior.

## Required PRD Sections
1. Document purpose, scope, assumptions, and terminology.
2. Compliance problem statement and target users.
3. Supported jurisdictions and organization types for the initial release.
4. Compliance requirement categories and source-verification process.
5. MVP scope, priorities (P0/P1/P2), and out-of-scope items.
6. Functional requirements with unique IDs and acceptance criteria.
7. Compliance register fields, such as requirement title, source, jurisdiction, applicability, owner, due date, evidence, status, reviewer, and last verification date.
8. Evidence collection, document versioning, review, approval, and audit-trail workflows.
9. Alerts, reminders, overdue handling, and escalation rules.
10. User roles and permissions, including organization-level isolation.
11. Dashboard, reporting, exports, and disclosure-status rules.
12. AI usage, source attribution, human-review requirements, and failure handling.
13. Privacy, security, retention, and access-control requirements.
14. Core data entities and integration dependencies.
15. Testing strategy and measurable acceptance criteria.
16. Risks, assumptions, unresolved legal questions, and a phased implementation roadmap.
17. References: authoritative source title, publisher, link, version/date, and verification date.

## Output Requirements
- Use clear, direct, implementation-oriented language and tables where helpful.
- Assign unique identifiers to requirements and tests (for example, `COMP-FR-001` and `COMP-TC-001`).
- Make acceptance criteria testable, preferably in Given/When/Then form.
- Label recommendations and assumptions explicitly.
- Mark requirements **Needs legal review** wherever applicability or interpretation is uncertain.
- Do not claim the product is legally compliant simply because a checklist, report, or workflow exists.
- End with a concise readiness assessment identifying the decisions and evidence needed before implementation.

Generate the Compliance PRD only after reviewing the available project context and verifying material regulatory claims where possible.

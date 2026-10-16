# Architecture Design Generator Prompt

## Purpose

Use this prompt to generate or update a practical, implementation-oriented solution architecture for the **Tekstain.io ESG and Carbon Management Platform**. The architecture must be grounded in the project documents that are actually available, and should be suitable for planning an MVP and guiding AI-assisted development.

> **Important:** This file is a reusable prompt. It is not the final architecture design. Follow the instructions below when using it with an AI assistant that can read the project files.

---

## Master Prompt

### 1. Your role

Act as a senior Solution Architect, Application Security Architect, Data Architect, Cloud Engineer, and ESG/Carbon Accounting Systems Specialist. Create a coherent architecture design for the Tekstain.io ESG and Carbon Management Platform.

Your job is to translate the product requirements into a secure, understandable, maintainable system design. Do not start writing application code. Define the system structure, major components, interactions, responsibilities, data flows, architectural decisions, risks, and implementation sequence first.

### 2. Read the project sources first

Inspect the project documents that are actually available. Use the following sources where present:

1. `Tekstain_Nexus_ESG_Platform_PRD.md` — primary source for product goals, personas, requirements, MVP scope, workflows, and acceptance criteria.
2. `Frontend_PRD.md` — primary source for frontend responsibilities, screens, navigation, interaction patterns, and UI states.
3. `Kwoledge_base.md` or `Knowledge_base.md` — consolidated project context, if available. Note that the filename may contain the spelling `Kwoledge_base.md`.
4. `Architecture.md` — existing architecture proposal, if available; assess it and improve or update it rather than duplicating it without review.
5. Other project decisions, notes, schemas, or implementation files, if available and relevant.

Only claim to have reviewed files that are available. Do not fabricate details from unavailable documents.

Treat the PRD as the primary source for product requirements. Use the Frontend PRD for UI-specific requirements and the knowledge base for summarized context. Use an existing `Architecture.md` as a proposal to review, not as unquestionable fact.

### 3. Product context

The product is a proposed ESG and Carbon Management SaaS platform called **Tekstain.io**, initially focused on SMEs and larger organizations in Ghana, with possible future expansion to other African markets.

The platform is intended to help organizations collect, validate, manage, analyze, and report environmental, social, and governance (ESG) data; track relevant sustainability indicators; calculate supported greenhouse gas emissions; manage evidence; review submissions; monitor selected targets; and generate structured ESG reports.

The system should be practical for a founder-led or small-team MVP. Favor simplicity, affordability, security, clear module boundaries, and data integrity over unnecessary infrastructure or premature scaling.

This context is a summary only. Confirm feature scope and business rules from the available source documents.

### 4. Architecture principles

Use these principles when making decisions:

- **Requirements-first:** map important architecture choices to explicit product requirements.
- **MVP-first:** design for the smallest useful release, with clear future extension points.
- **Prefer simplicity:** consider a modular monolith before microservices unless the requirements provide a strong reason otherwise.
- **Secure by design:** enforce authorization on the server and isolate each customer's data.
- **Reliable data lineage:** preserve sources, units, reporting periods, validations, approvals, calculation methods, and report versions.
- **Deterministic calculations:** carbon arithmetic and other critical business rules must run through defined, tested application logic, not free-form AI responses.
- **Configurable where valuable:** metrics, supported emission factors, reporting-period settings, and framework mappings should be designed for controlled updates where the sources justify this.
- **Human review:** material ESG disclosures and AI-generated content must remain reviewable and distinguishable from approved data.
- **Cost-aware operations:** avoid managed services, queues, microservices, or analytics infrastructure without a clear MVP need.
- **Observable and testable:** important operations should be logged appropriately and covered by automated tests.
- **Portable and maintainable:** avoid unnecessary vendor lock-in and document material provider dependencies.
- **Evidence-based claims:** do not state that the system guarantees compliance, certification, assurance, or emission reductions unless the requirements and external processes support that statement.

### 5. Label decisions and uncertainties

For architecture choices, use these labels where applicable:

- **Confirmed requirement:** explicitly supported by a project source.
- **Proposed decision:** a recommended implementation choice that needs approval.
- **Assumption:** used because project information is incomplete.
- **Open question:** needs a decision or further validation.
- **Future option:** not needed for the MVP but may be considered later.

If project sources conflict, record the conflict and explain the decision needed. Do not silently reconcile, replace, or invent requirements. Keep the proposed design internally consistent, and state where a recommendation goes beyond the source documents.

### 6. Required architecture deliverable

Produce a detailed Markdown architecture document named **`Architecture.md`**. It must be readable by a founder, product owner, frontend developer, backend developer, data engineer, security reviewer, and AI coding assistant.

Include these sections, adapting their level of detail to the confirmed MVP scope:

1. **Document control** — title, version, status, date, source files reviewed, and decision status.
2. **Executive summary** — recommended architectural style and the main reasons for it.
3. **Architecture goals and constraints** — product goals, technical constraints, assumptions, and explicit non-goals.
4. **Requirements traceability** — map high-priority product requirements to the components or architectural controls that support them. Preserve requirement IDs where the source provides them.
5. **Architecture decisions** — decision log with context, options considered, recommendation, rationale, trade-offs, status, and consequences.
6. **System context diagram** — actors, application, database, file storage, authentication, and any justified external services.
7. **Logical component architecture** — frontend, backend/application layer, domain modules, persistence, background processing if required, integrations, and operational tooling.
8. **Deployment architecture** — environments, hosting boundaries, networking/trust boundaries where relevant, secrets, storage, backup, and release pipeline.
9. **Frontend architecture** — route/layout structure, feature/module boundaries, client-versus-server responsibilities, forms, validation, shared components, data fetching, loading/empty/error states, and accessibility considerations based on `Frontend_PRD.md`.
10. **Backend and domain architecture** — module responsibilities, service boundaries, authorization flow, validation, transactions, error handling, and how modules communicate.
11. **Data architecture** — logical entities, major relationships, tenancy model, data ownership, migrations, soft deletion or retention where appropriate, and audit events. Provide a Mermaid ER diagram or a clear text relationship summary.
12. **ESG data lifecycle** — collection, validation, evidence attachment, submission, review, approval, correction, and downstream use in dashboards and reports.
13. **Carbon accounting architecture** — supported activity data, deterministic calculation flow, unit conversions, emission-factor selection, geographic and reference-year metadata, formula/version tracking, rounding rules where specified, recalculation behavior, and immutable history for finalized outputs. Do not invent emission factors or calculation methods.
14. **Reporting architecture** — report readiness checks, eligible data selection, framework mapping where supported, snapshot/version strategy, PDF generation, export permissions, and correction/re-issuance behavior.
15. **AI integration architecture** — use cases, service boundary, data minimization, grounding in authorized records, prompt/input protection, output review, traceability, failure behavior, and a way to operate without AI. Keep AI separate from numerical carbon calculations and authorization decisions.
16. **Identity, roles, and tenant isolation** — roles and permission enforcement, organization membership checks, cross-tenant protection, consultant access if required, private file authorization, and database-level controls where supported by the selected stack.
17. **Security and privacy design** — trust boundaries, threat scenarios, sensitive data, secrets management, encryption in transit/at rest where supported, secure uploads, rate limiting, audit logging, retention/deletion, backup protection, and legal questions requiring validation. Do not claim that a design is compliant or secure merely because controls are listed.
18. **API and integration design** — major application interfaces, request/response responsibilities, validation boundaries, idempotency for relevant writes, error format, external-service adapters, and manual import/upload fallbacks. Do not invent available APIs.
19. **Non-functional requirements** — availability, performance, scalability, accessibility, maintainability, recoverability, observability, and testability. Clearly mark any numeric target as proposed unless confirmed in the source documents.
20. **Environment and delivery strategy** — development, test/staging, production, configuration, migrations, CI/CD, release checks, rollback, and separation of test data from production data.
21. **Testing strategy** — unit, integration, end-to-end, permissions/tenant-isolation, carbon calculation, report accuracy, upload security, accessibility, and recovery tests.
22. **Operational model** — logs, monitoring, alerting, backup verification, restore drills, incident response, data corrections, and service dependency failure behavior.
23. **MVP implementation sequence** — ordered phases and dependencies, from foundational infrastructure through the first complete user journey.
24. **Risks, assumptions, and open questions** — likelihood/impact where useful, mitigation, owner or responsible function, and what needs validation.
25. **Definition of architecture readiness** — explicit checks required before implementation and production deployment.
26. **Appendices** — glossary, reference links from project sources, and any supporting diagrams.

Use diagrams and tables where they improve comprehension. Prefer Mermaid diagrams for system context, component flows, deployment, major workflows, and entity relationships. Ensure diagram syntax is valid and that diagrams agree with the written architecture.

### 7. Technology selection

Do not assume the project has already committed to a particular technology provider or stack. If the project sources already identify a selected technology, label it accurately as confirmed or proposed according to the source.

Where a choice remains open, compare realistic options briefly and recommend a default based on:

- Founder/small-team development effort.
- Total operating cost and free-tier limitations where relevant.
- Data integrity and transaction support.
- Authentication and authorization capabilities.
- Tenant isolation options.
- Private file storage and upload controls.
- Support for reporting and PDF exports.
- AI integration and ability to keep AI optional.
- Observability, backup, recovery, portability, and vendor lock-in.
- Ease of testing and future maintenance.

Cover frontend, backend/application services, relational database, identity, object storage, deployment, email delivery, report generation, background jobs if justified, and optional AI. Do not over-engineer the MVP. For each recommendation, state its rationale, trade-offs, and unresolved provider-specific validation.

### 8. ESG and carbon accounting design safeguards

The architecture must preserve the distinction between:

- Raw activity data.
- User-entered values and imported values.
- Supporting evidence.
- Validation results and review status.
- Emission factors and their sources/versions.
- Calculation inputs, formulas, units, and outputs.
- Estimates or proxies versus values based on stronger source data.
- AI-generated draft narratives versus human-approved report disclosures.
- A system-generated report versus an externally audited or assured report.

Requirements:

1. Critical business rules and permissions must execute server-side.
2. Emissions calculations must be deterministic, repeatable, unit-checked, and testable.
3. Every emissions result must preserve enough provenance to explain how it was produced.
4. Updating an emission factor must not silently rewrite a previously finalized report or erase historical calculation provenance.
5. Reports must not fabricate missing disclosures or convert missing data into zero.
6. Any recalculation or correction of finalized results must have a controlled, auditable process.
7. AI must not invent emission factors, source evidence, numerical results, legal obligations, or compliance claims.
8. AI-generated material must be reviewable and clearly identifiable until approved.
9. Unknown or incomplete reporting requirements must be recorded as open questions for domain or legal review.

Do not select or create actual Ghanaian emission-factor values unless a source document provides them or the task explicitly includes verified external research. Even when sources provide factors, preserve their source, geographic applicability, unit, reference year, method, and version.

### 9. Security and multi-tenancy safeguards

Treat the browser as untrusted. Do not rely on hiding UI controls, client-side route protection, or browser-provided organization IDs as the only security control.

For every protected operation, describe how the server:

1. Establishes the authenticated user.
2. Resolves the requested organization and verifies active membership.
3. Checks the user's permission for the specific operation.
4. Validates input and any referenced record ownership.
5. Performs the operation safely and records relevant audit events.

Explicitly address cross-tenant authorization failures, private document access, report downloads, exports, background tasks, and consultant access if applicable. Where a database row-level security (RLS) policy or similar control is proposed, explain which checks remain in the application layer and how both layers will be tested.

Do not place API secrets in frontend code. Do not log passwords, access tokens, document contents, or unnecessary personal information. Flag provider-specific security configurations that must be verified before production.

### 10. Output quality rules

The architecture document must:

- Be specific enough to guide implementation, but must not include application source code.
- Separate requirements from recommendations and decisions from assumptions.
- Prioritize the first usable MVP over speculative future capabilities.
- Explain important trade-offs rather than listing technologies without justification.
- Identify dependencies between the product, frontend, backend, database, storage, identity, carbon calculations, and reports.
- Avoid repeating the PRD verbatim; summarize requirements only where needed to explain architecture.
- Preserve terminology and requirement IDs from project sources.
- Avoid unsupported claims about legal compliance, framework conformity, certification, assurance, or production readiness.
- Include source references or links only when they are actually present in the source files or verified through explicitly requested research.
- Ensure each important system component has a clear responsibility and security boundary.
- Mark all unresolved implementation choices that could materially affect cost, privacy, data integrity, or rework.

If two design approaches are plausible, give the recommended option first and a concise alternative with the conditions under which it would become preferable.

### 11. Final review checklist

Before delivering `Architecture.md`, verify:

- The design is traceable to the available PRD and Frontend PRD.
- MVP features and future features are separated.
- No unavailable file is claimed as reviewed.
- Technology choices are labeled accurately as confirmed, proposed, assumptions, or open questions.
- System, component, deployment, and data diagrams agree with the text.
- Tenant isolation and server-side authorization are explicit.
- Carbon calculations are deterministic and traceable.
- Report snapshots and versions preserve history.
- AI is optional and cannot silently modify trusted calculations or approved results.
- Errors, outages, corrections, backup, and recovery are addressed.
- Testable architecture acceptance criteria are included.
- Important unresolved decisions are presented clearly at the end.

### 12. Execution instruction

Read the available project source documents first. Then create or update **`Architecture.md`** with the architecture design described above. If `Architecture.md` already exists, evaluate it against the source requirements, retain valid decisions, correct unsupported assumptions only when the source supports the correction, and clearly document unresolved conflicts. Do not generate application code, frontend components, database migrations, or deployment files as part of this task.

If a critical decision cannot be inferred safely, record it as an open question and proceed with a clearly labeled provisional recommendation rather than inventing a confirmed decision.

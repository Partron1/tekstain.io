# Tekstain Nexus ESG Platform — Project Knowledge Base

**Document:** Project Knowledge Base  
**File purpose:** Persistent context for AI assistants, product contributors, designers, developers, testers, and sustainability reviewers working on Tekstain Nexus.  
**Version:** 1.0  
**Prepared:** 14 October 2026  
**Status:** Working knowledge base; based on the current draft PRD, Frontend PRD, and Architecture Design.  
**Primary market:** Ghana  
**Product type:** Proposed multi-tenant ESG and carbon-management SaaS web application

> **Status warning:** This knowledge base consolidates current project intent and proposed decisions. It does not mean that customer demand, pricing, applicable legal obligations, reporting mappings, emission factors, hosting providers, or technical performance have been validated. Treat statements marked *proposed*, *candidate*, *conditional*, or *to be confirmed* accordingly.

---

## 1. Purpose of This Knowledge Base

Use this document as the shared project context when planning features, generating designs, creating code, writing tests, preparing customer materials, or making product decisions for Tekstain Nexus.

It provides a concise reference to:

- What the product is and the problem it aims to solve.
- Who the intended users are.
- Which capabilities belong in the initial MVP and which should be deferred.
- How ESG data, evidence, review, carbon calculations, dashboards, and reports should work together.
- The system's security, privacy, data-quality, and AI guardrails.
- Which architecture and technology choices are proposals rather than approved decisions.
- What must be validated before production use.

This knowledge base supplements rather than replaces the full project documents. Consult the detailed requirements and acceptance criteria in the following source documents when implementing a specific feature.

## 2. Source Documents and Order of Precedence

The current project documents are:

1. **`Tekstain_Nexus_ESG_Platform_PRD.md`** — primary product requirements, MVP boundaries, user roles, data dictionary, carbon accounting rules, reporting, testing, risks, assumptions, and roadmap.
2. **`Frontend_PRD.md`** — frontend navigation, screen-level behavior, user interface states, responsive design, accessibility, and frontend acceptance criteria.
3. **`Architecture.md`** — proposed system components, request lifecycle, domain modules, data architecture, security boundaries, deployment practices, and architecture decisions requiring confirmation.
4. **`Kwoledge_base.md`** — compact cross-functional context and operating guidance for AI tools and project contributors.

When documents differ, do not silently choose a convenient interpretation. Record the inconsistency, inspect the detailed requirement, and request or document a product/architecture decision. As a working rule:

- The **PRD** defines required product behavior and scope.
- The **Frontend PRD** defines how users experience that behavior in the UI.
- The **Architecture Design** defines how the system is proposed to implement it.
- This **Knowledge Base** summarizes the shared context and guardrails.

If a later approved decision changes the documents, update this knowledge base so the project context remains consistent.

---

## 3. Product Identity and Vision

### 3.1 Product name

**Tekstain Nexus ESG and Carbon Management Platform**

### 3.2 Product category

An ESG data management, carbon accounting, sustainability performance monitoring, and reporting SaaS product.

### 3.3 Primary market

Ghana, initially serving small and medium-sized enterprises (SMEs). The product may later support larger companies, multi-site organizations, ESG consultants, suppliers, and organizations in other African markets, subject to validation and country-specific configuration.

### 3.4 Product vision

Make sustainability information accessible and actionable for Ghanaian businesses by combining structured ESG data collection, transparent carbon calculations, evidence management, workflow automation, and carefully controlled AI assistance.

### 3.5 Core value proposition

Help a business move from scattered ESG information to a traceable, reviewable first ESG report without managing the entire process through disconnected spreadsheets and documents.

The product should make it easier for an organization to:

1. Set up its reporting profile and period.
2. Identify relevant ESG topics and candidate metrics.
3. Collect selected environmental, social, and governance data.
4. Attach supporting evidence and retain source details.
5. validate records and route them through review and approval.
6. Calculate supported greenhouse gas emissions transparently.
7. Understand completeness, missing data, estimates, and review status.
8. Generate a structured report based on the available information.
9. Identify practical improvements and, in later phases, track targets over time.

### 3.6 Product success principle

Success means users can produce a more organized, traceable, and useful sustainability information set with less avoidable manual work. Generating a report or calculating emissions does **not** itself prove that a customer reduced emissions, is sustainable, achieved legal compliance, or received independent assurance.

---

## 4. Problem Context and Product Hypotheses

The product is intended to address the possibility that sustainability-related information is scattered across utility bills, fuel receipts, spreadsheets, HR summaries, procurement records, waste records, policies, and other documents. Organizations may not know what data to collect, how to validate it, what evidence to retain, or how to communicate results and limitations.

These are **hypotheses to validate with prospective customers**, not universal claims about all Ghanaian SMEs. Do not present the project brief as proof of a validated market size, confirmed willingness to pay, or a verified regulatory need.

Discovery should test:

- How target businesses currently collect ESG or operational information.
- Which reports or data requests they actually need to respond to.
- Which records are readily available and reliable.
- Which parts of the process consume the most time.
- Which features customers value enough to use repeatedly or pay for.
- Which sectors can provide suitable data for an initial pilot.

---

## 5. Target Users and User Goals

### 5.1 SME owner or managing director

**Primary goal:** Understand organizational ESG status and obtain a useful report without needing to become an ESG technical expert.

Needs a simple overview of reporting completeness, key available metrics, material data gaps, selected carbon results, and next actions.

### 5.2 ESG or sustainability manager

**Primary goal:** Coordinate ESG data collection, review performance, manage evidence, understand emissions calculations, and prepare reports.

Needs metric configuration, reporting-period context, data status, review workflows, drill-down to source records, and report generation.

### 5.3 Finance or operations contributor

**Primary goal:** Submit operational evidence and data accurately with minimal repetition.

Likely records include electricity bills, fuel purchases, utility data, vehicle/fuel logs, procurement data, and other operating records.

### 5.4 HR contributor

**Primary goal:** Provide appropriate aggregated workforce and workplace indicators while preserving employee privacy.

Potential data includes headcount, training, turnover, and occupational health and safety indicators where definitions and privacy controls have been agreed.

### 5.5 ESG consultant

**Primary goal:** Assist one or more explicitly authorized clients with data collection, review, gap identification, and report preparation.

Multi-client consultant workspaces are a future capability unless a pilot requirement makes them necessary. Consultants must only access clients that explicitly authorize them.

### 5.6 Platform administrator

**Primary goal:** Maintain platform-level configuration, approved metric definitions, templates, factor references, and system operations.

Administrative access must be separate from normal customer permissions and carefully restricted.

### 5.7 General UX rule

Do not assume every user knows ESG terminology. Use plain language, explain units and statuses, and disclose what an assessment or report does and does not establish.

---

## 6. Product Principles — Non-Negotiable Rules

1. **Evidence before narrative.** Material figures and claims must come from recorded information, a defined calculation, or an explicitly identified qualitative input/inference. Never invent supporting evidence.
2. **Calculation transparency.** Emissions results must be reproducible from the activity data, units, factor, conversion method, methodology, and formula version used.
3. **Missing is not zero.** Blank, zero, not applicable, not available, not yet collected, and estimated are different states.
4. **Human approval.** AI-generated narrative and reports remain drafts until an authorized person reviews and approves them.
5. **Secure by default.** Tenant isolation, least-privilege access, private document storage, and server-side authorization are foundational.
6. **Progressive complexity.** Show only relevant and implemented features; keep advanced options out of the way until needed.
7. **Framework-aware, not framework-confused.** Reporting frameworks are not interchangeable. Mappings must be reviewed, versioned, and described accurately.
8. **No unsupported green claims.** Do not state that an organization is sustainable, compliant, net zero, certified, verified, assured, or aligned with a target-setting standard unless the relevant evidence and method support that exact claim.
9. **Traceability over cosmetic precision.** A dashboard must not hide uncertainty behind attractive charts or unsupported scores.
10. **Validate before expanding.** Build for the clearest user problem; avoid premature integrations, excessive Scope 3 breadth, and enterprise complexity.

---

## 7. MVP Scope

### 7.1 P0 — Core MVP/pilot capabilities

The initial pilot should prioritize:

- Secure sign-up/sign-in and account recovery through an approved authentication approach.
- Organization profile and reporting-period setup.
- A lightweight preliminary ESG assessment.
- A curated, limited set of ESG metric definitions and data forms.
- Draft, submit, review, request-changes, approve, and reject workflows where applicable.
- Private document/evidence uploads and links to associated records.
- Server-side validation and basic data-quality indicators.
- Basic dashboard with reporting status and selected indicators.
- Limited, reviewed carbon calculations for sources whose methods and emission factors have been approved.
- Template-based draft ESG report generation, preferably PDF-first.
- Role-based access control and tenant isolation.
- Audit events for material changes and workflow actions.
- Data export for core customer records where feasible.
- Testing for access control, data integrity, calculations, and reports before handling confidential pilot data.

### 7.2 Conditional P0 capabilities

Carbon calculations are P0 only for source types with reviewed methodology, correct unit handling, suitable factor sources, and test cases. If those conditions are not met for a source, keep that calculation disabled rather than fabricate a result.

CSV import may be included in the first pilot if actual customer spreadsheets show it is important and it can be implemented with useful validation. Otherwise, deliver it shortly after the core form workflow stabilizes.

### 7.3 P1 — After core workflow is reliable

- CSV import enhancements.
- AI-assisted report drafting and explanations.
- A limited, verified Scope 3 category if pilot data and approved factors support it.
- Sustainability targets and improvement actions.
- Basic notifications.
- Additional framework mappings that are reviewed and maintained.
- Subscription and billing features for a validated paid release.
- Multi-site or consultant workflow improvements if customer evidence justifies them.

### 7.4 P2 — Future or explicitly out of MVP

- All 15 Scope 3 categories implemented in full.
- Automatic invoice OCR treated as an authoritative data source.
- Direct utility, bank, accounting, or other external integrations without a verified API and clear business case.
- Public report publishing.
- Live external benchmarks or generalized ESG ratings.
- Carbon-credit marketplace or offset trading.
- Product life-cycle assessment.
- Full formal double materiality assessment without an approved methodology.
- Full enterprise group consolidation.
- Automated legal compliance determination.
- Independent assurance or certification services.
- WhatsApp/SMS automation unless separately justified and reviewed.
- Advanced BI/data warehouse or real-time streaming infrastructure.

### 7.5 MVP outcome test

A pilot organization should be able to create an account, set up its organization and reporting period, complete preliminary onboarding, enter selected data, attach evidence, review data quality, calculate supported emissions, inspect the dashboard, and export a reviewable report without the application fabricating missing disclosures.

---

## 8. Core Product Modules

### 8.1 Authentication and membership

Users sign in securely and are attached to an organization through an explicit membership record. Tenant membership and permissions must be checked by server-side services for every protected action.

### 8.2 Organization and reporting periods

Store the organization's identity, industry/context, country, reporting objectives, financial/reporting period, and carbon boundary choices where applicable. Ghana and GHS should be supported as options. Currency is not an environmental physical unit. The initial pilot can be single-organization/single-site, while the data model should not block future sites.

### 8.3 ESG onboarding and metric selection

Use a short preliminary questionnaire to understand business activity, reporting purpose, and data availability. The assessment can recommend candidate metrics, but authorized users should be able to review selections. Do not describe a simple questionnaire as a complete formal materiality assessment or double materiality assessment.

### 8.4 ESG data collection

Each submission should identify the metric definition, organization, reporting period, value or status, unit where relevant, source details, contributor, workflow status, and supporting evidence when required. Use clear server-side validation rules. Drafts must not silently flow into approved report totals.

### 8.5 Evidence and document management

Documents are supporting records, not automatic proof of accuracy. Store metadata such as filename, type, uploader, upload time, period, associated metric/submission, review status, and reviewer comments where appropriate. Files must remain private and be retrieved only after authorization checks.

### 8.6 Review and approval

Use explicit states such as Draft, Submitted, Under Review, Changes Requested, Approved, and Rejected, as appropriate to the workflow. Preserve important status changes and reviewer actions in an audit trail. Editing a record after approval must follow a defined revision/re-review process.

### 8.7 Carbon accounting

Provide a transparent, deterministic calculation engine for supported sources. Store activity data, unit, emission factor/version, factor source, method, conversion, formula version, result, reporting period, quality/estimate notes, and approval state. A language model must not be the source of an authoritative numeric calculation.

### 8.8 Dashboard

Show status-aware metrics, reporting-period context, missing or flagged data, records awaiting review, evidence coverage, and supported calculated results. Allow authorized users to drill down into source records. Avoid arbitrary ESG scores and unsupported benchmarks.

### 8.9 Reporting

Generate a report from eligible records and calculations for a defined organization and reporting period. Apply readiness checks, preserve a snapshot of the source data/methods used, version reports, and expose data gaps or limitations. A PDF-first report is the initial recommendation. Do not claim audit, assurance, certification, or regulatory approval without evidence of the relevant external process.

### 8.10 AI-assisted intelligence

AI may assist with explanations, gap identification, anomaly flagging, document summarization, and draft report text. These functions should be introduced only when privacy, source grounding, review, and failure controls have been designed. AI content must remain distinct from approved data and final disclosures.

---

## 9. Initial ESG Metric Candidates

The exact metric list must be finalized based on pilot sector, customer data availability, reporting purpose, method quality, and approved scope. The following are candidate metrics from the current PRD, not mandatory for every organization.

| Metric ID | Candidate metric | Unit/type | Initial position |
|---|---|---|---|
| ENV-001 | Purchased electricity consumption | kWh | P0; evidence from utility bill or meter record recommended |
| ENV-002 | Stationary fuel use (e.g., generator/boiler) | Litres, mass, or energy unit depending on fuel | P0 for supported fuel types and validated units/factors |
| ENV-003 | Company vehicle fuel use | Unit depends on fuel | P0 if pilot data and boundaries support it |
| ENV-004 | Water withdrawal/consumption | m³ or documented bill unit | P0/P1 based on pilot need and conversion support |
| ENV-005 | Waste generated by type | kg or tonnes | P1 initially |
| ENV-006 | Waste treatment/disposal route | Categorized route and quantity when available | P1 initially |
| ENV-007 | Refrigerant top-up/leak data | kg by refrigerant | P2 initially; requires specific factors/methods |
| ENV-008 | Purchased goods/services spend or quantity | Currency or physical quantity by category | P1; never convert spend to emissions without approved matching factor/method |
| ENV-009 | Business travel | Distance/trip/activity | P1; depends on available activity information and method |
| ENV-010 | Employee commuting | Survey-based activity data | P2 initially |
| SOC-001 | Total employee headcount | Count, with period and employee/contractor definition | P0 |
| SOC-002 | Employee training | Hours or participants | P1 |
| SOC-003 | Work-related injuries/incidents | Count and/or defined rate | P1; definitions and privacy protections required |
| SOC-004 | Employee turnover | Percentage with defined formula | P1 |
| SOC-005 | Workforce composition | Aggregated counts/percentages | P2 initially; privacy review required |
| GOV-001 | Code of conduct/ethics policy adopted | Yes/no plus date/link | P0 |
| GOV-002 | Anti-bribery/corruption policy or controls | Yes/no plus description | P1 |
| GOV-003 | Whistleblowing/grievance channel | Yes/no plus description | P1; avoid unnecessary case-level personal data |
| GOV-004 | ESG oversight responsibility assigned | Role/description | P0 |
| GOV-005 | Relevant compliance incidents | Count/qualitative description | P2 initially; restrict access |
| SYS-001 | Data collection completion | % of selected metrics submitted/approved | P0; operational completeness, not ESG performance score |
| SYS-002 | Evidence coverage | % of submissions with evidence where required | P0; evidence presence does not prove accuracy |

Each metric definition should include at least: stable metric ID, name, plain-language description, ESG category, value type, unit, precision, validation rules, reporting frequency, evidence expectations, applicability guidance, data source, directly reported/calculated flag, version, active dates, review owner, and only verified framework references.

### 9.1 Values and states must remain distinct

The data model and UI must be able to distinguish, where relevant:

- Actual reported value.
- Zero as a valid measured value.
- Not applicable, with reason if required.
- Not available, with reason where useful.
- Not yet collected.
- Estimated, with method and assumptions.
- Draft or incomplete.
- Submitted for review.
- Approved or rejected.

Do not use a single blank or zero value to represent all these states.

---

## 10. Carbon Accounting Knowledge

### 10.1 Proposed methodology baseline

The current PRD names the GHG Protocol Corporate Accounting and Reporting Standard as the principal design reference for corporate inventories and the GHG Protocol Corporate Value Chain (Scope 3) Standard for value-chain emissions when supported features are implemented. Specialist review is required before claiming conformity. Standards, guidance, and consultations can change; track official versions and updates before approving production methodology.

### 10.2 Scopes

- **Scope 1:** Applicable direct emissions from owned or controlled sources, potentially including selected stationary fuel combustion and company-controlled road vehicles.
- **Scope 2:** Indirect emissions associated with purchased electricity and any other applicable purchased energy included in the selected method. Purchased electricity is the proposed initial candidate where an appropriate factor has been verified.
- **Scope 3:** Other indirect value-chain emissions. The data model should be extensible for all 15 categories, but MVP claims and calculations must be limited to the categories actually implemented and reviewed.

Do not imply that the initial set of sources represents an organization's complete greenhouse gas inventory.

### 10.3 Formula and units

For a validated factor:

`Emissions (kgCO2e) = Activity data (in the factor's required unit) × Emission factor (kgCO2e per activity unit)`

`Emissions (tCO2e) = Emissions (kgCO2e) ÷ 1,000`

Convert activity data into the factor's exact reference unit using a defined, tested conversion before multiplication. Reject incompatible activity types, units, locations, factor periods, or other critical metadata. Do not let an AI model improvise a factor or authoritative total.

### 10.4 Emission-factor library

A factor entry should preserve:

- Factor ID and version.
- Activity/source type and fuel or energy type, where applicable.
- Numerical value and unit.
- Gas coverage / CO2e basis where relevant.
- Geography and applicability.
- Reference year and publication/source.
- Calculation method and limitations.
- Effective dates and approval state.
- Reviewer and approval record where appropriate.

Prefer appropriate Ghana-specific factors when available and validated. If a suitable Ghana-specific factor is unavailable, document the selected alternative and limitations. **Do not invent factors or label unverified factors as official.**

### 10.5 Boundary, method, and history

Record organizational consolidation approach and covered sources before marking an inventory ready for reporting. Record material boundary/method changes between reporting periods and warn when comparisons may not be like-for-like. Recalculations after factor changes must preserve previous approved results and report versions rather than silently overwrite historical results.

### 10.6 Estimates and quality

Label estimated data and record the estimation method, assumptions, and limitations. Do not hide uncertainty. Missing data must not automatically be treated as zero. Where input or factor quality is insufficient, flag or disable the calculation instead of generating false precision.

### 10.7 Scope 2 methods

Location-based and market-based results are distinct and must not be treated as interchangeable. Only offer market-based calculations when suitable contractual/supplier-specific information and the applicable method requirements are supported. Otherwise, do not show a market-based result.

### 10.8 Calculation acceptance test

For valid activity data and an applicable, versioned factor, the system should validate units, apply the defined formula and conversions, store the result and provenance, link it to a reporting period and source activity, and display relevant quality/estimation limitations. Invalid or incompatible factors must be rejected.

---

## 11. ESG Standards and Regulatory Claims

The current project documents identify the following as candidate references for review and mapping:

- GHG Protocol.
- Global Reporting Initiative (GRI) Standards.
- IFRS Sustainability Disclosure Standards, including IFRS S1 and IFRS S2.
- United Nations Sustainable Development Goals (SDGs).
- Relevant Ghanaian company, environmental, labor, data protection, and sector-specific requirements, where applicable.

The presence of a framework name in this knowledge base does not mean that every part of it is implemented or that it applies to every customer. Any reporting mapping must identify the relevant standard/version, disclosure or metric, source, limitations, and review status.

Distinguish carefully between:

1. Legal obligations confirmed as applicable to a specific organization.
2. Sector-specific legal requirements.
3. Voluntary standards or frameworks.
4. Investor, lender, buyer, or supply-chain expectations.
5. Good-practice recommendations.
6. Open legal/regulatory questions.

Verify current claims using authoritative sources before treating them as binding requirements. Do not state that a generated report guarantees compliance. Legal interpretation and formal assurance may require qualified external professionals.

---

## 12. AI Guardrails

AI capabilities are optional and should be phased in only after the data, calculation, and reporting foundation is reliable. The architecture proposal treats AI as a gated capability, and it may be disabled during the pilot.

### 12.1 Allowed or potentially allowed uses

Subject to source grounding, privacy, validation, and human review, AI may:

- Summarize validated ESG information.
- Explain observed changes between reporting periods.
- Identify potential gaps or anomalous records for review.
- Summarize uploaded documents as a draft aid.
- Draft ESG report narratives for human editing.
- Explain ESG terminology and help users understand data requirements.
- Suggest follow-up questions when data is incomplete.
- Propose improvement opportunities while separating evidence from inference.

### 12.2 Prohibited or constrained behavior

AI must not:

- Invent organization data, documents, evidence, policies, regulatory obligations, emission factors, or numeric results.
- Replace deterministic carbon calculations with language-model guesses.
- Silently change an approved metric, result, report, or factor.
- Present unsupported interpretations as facts.
- Declare that a customer is compliant, certified, net zero, sustainable, or independently assured without appropriate support.
- Treat uploaded file text as trusted instructions to override system policies.
- Expose one tenant's confidential data to another tenant.
- Send confidential information to an external AI provider without approved data-flow, minimization, retention, and contractual controls.

### 12.3 Required output handling

AI output must be identifiable as draft/generated content, linked to the relevant reporting context where possible, editable by an authorized user, and subject to review before inclusion in an approved report. If information is insufficient, the system must say so and request data or mark the point as unresolved. AI failures must not block core manual workflows unnecessarily.

---

## 13. Frontend and UX Knowledge

### 13.1 Initial navigation

The proposed MVP navigation includes:

1. Dashboard.
2. Organization.
3. ESG Assessment.
4. Data Collection.
5. Carbon Accounting.
6. Documents & Evidence.
7. Reports.
8. Tasks/Reviews.
9. Settings.
10. Administration, visible only to authorized platform administrators.

Show future modules such as targets, subscription management, or advanced integrations only when implemented and enabled.

### 13.2 Key screens

- Sign-in/account access.
- Organization setup and reporting period.
- ESG onboarding/assessment.
- Dashboard.
- Data collection list.
- Metric submission form.
- Documents and evidence library.
- Tasks/review queue.
- Carbon accounting.
- Report builder and report library.
- Settings/administration.

Consult `Frontend_PRD.md` for detailed required fields, actions, empty/loading/error states, and acceptance criteria for each screen.

### 13.3 Interface rules

- Make the active organization and reporting period clear.
- Use plain language for non-specialists.
- Display units alongside values.
- Distinguish missing data from zero.
- Show methodology, reporting period, and limitations for important carbon values.
- Show whether records are draft, submitted, flagged, approved, or rejected.
- Provide helpful validation and error messages.
- Do not expose future features as if they work.
- Design responsively for desktop and mobile browsers.
- Aim for WCAG 2.2 Level AA accessibility, as stated in the current Frontend PRD, and validate with accessibility tests.
- A hidden button or client-side route check is not an authorization control; the server must enforce permissions.

---

## 14. Roles, Permissions, and Tenant Isolation

Roles proposed in the project documents include:

- Platform Super Administrator.
- Organization Owner.
- Organization Administrator.
- ESG Manager.
- Data Contributor.
- Data Reviewer/Approver.
- Read-Only Viewer.
- Explicitly Authorized ESG Consultant.

The detailed permission matrix is in the PRD and Frontend PRD. Apply least privilege; give users only the actions they need.

### Mandatory tenant rules

- Every organization-specific record must belong to a known tenant/organization.
- The server must resolve the authenticated identity and confirm active membership for each protected action.
- Do not trust an organization ID, role, storage key, or approval state simply because it came from the browser.
- Enforce access checks at the API/domain layer and database/storage boundary as supported by the selected provider.
- Documents remain private and require authorization for retrieval.
- Consultants can access only client organizations that have explicitly delegated access.
- Unauthorized responses must not disclose confidential information about another organization.
- Sensitive employee information should be minimized, aggregated where possible, and restricted to authorized roles.

Tenant isolation and private file retrieval must be tested before the product handles customer-confidential pilot records.

---

## 15. Proposed Architecture and Technology

### 15.1 Architecture style

The current recommendation is a **secure modular monolith** for the MVP: one main application deployment with clear domain boundaries, server-side APIs/business rules, and independently testable modules. Do not introduce microservices, streaming infrastructure, or a data lake without a demonstrated need.

### 15.2 Proposed logical components

- Responsive browser frontend.
- Server routes/API layer with request validation.
- Authentication/session adapter.
- Authorization and tenant access checks.
- Organization and reporting-period service.
- Metric definition and assessment service.
- Data submission and validation service.
- Evidence/document service.
- Review workflow service.
- Deterministic carbon calculation module.
- Dashboard/query service.
- Report readiness, snapshot, versioning, and PDF service.
- Optional AI adapter.
- Administration/configuration service.
- Audit logging, monitoring, backup, and recovery controls.

### 15.3 Candidate technology stack — not finalized

The Architecture Design discusses these candidates:

- Frontend: Next.js and TypeScript.
- Database: PostgreSQL.
- Authentication: Supabase Auth or an equivalent managed identity provider.
- Evidence storage: private object storage from the chosen platform/cloud provider.
- Server/business logic: Next.js server routes/actions organized around domain services.
- Carbon engine: deterministic TypeScript module initially; another language such as Python only if there is a reviewed reason.
- PDF reports: server-side HTML-to-PDF or a tested PDF library.
- AI: provider behind a narrow adapter interface and disabled until controls are approved.
- Email: verified transactional email service or managed equivalent.
- Hosting and monitoring: select after provider, privacy, cost, logging, backup, restore, and deployment due diligence.

These are recommendations, not confirmed providers or final commitments. Do not hard-code a provider choice into every module before ADR-001 is decided.

### 15.4 Trust boundaries and request lifecycle

For a protected action:

1. Receive the frontend request.
2. Validate the session and resolve the authenticated user.
3. Check active organization membership and permission on the server.
4. Validate the payload using a typed schema.
5. Apply domain business rules.
6. Read/write records or invoke the calculation, storage, or report service.
7. Return a defined response or safe error.
8. Record material actions in the audit trail.

The browser is untrusted. Critical rules must not exist only in UI code.

### 15.5 Environments and operations

Maintain separate development, staging, and production environments. Use version-controlled code, database migrations, automated checks, controlled releases, logging, error monitoring, backup alerts, and tested restore procedures. Do not copy production personal/confidential data into development unless appropriately sanitized and authorized.

---

## 16. Logical Data Architecture

The current PRD and architecture discuss the following principal entities. Not all entities need to be implemented in the first release.

### Core MVP candidates

- Users and/or authentication identities.
- Organizations.
- Organization memberships and role assignments.
- Reporting periods.
- ESG assessments and assessment versions.
- Metric definitions.
- Organization metric selections.
- Metric submissions/records.
- Source/data-source metadata.
- Evidence documents and associations.
- Review records/actions.
- Emission factors and factor versions.
- Emissions calculations and provenance.
- Reports and report versions/snapshots.
- Audit events.

### Future or optional entities

- Organization sites/facilities and multi-site consolidation.
- Reporting-framework disclosures and mappings.
- Sustainability targets and improvement actions.
- Tasks and notifications.
- Subscription and billing records.
- AI-generated draft records and usage data.
- Consultant/client delegation structures, if not needed at pilot launch.

### Data integrity rules

- Use stable identifiers and relationships rather than embedding core business relationships only in free text.
- Associate records with the correct organization and reporting period.
- Store explicit units and validation rules.
- Preserve submission and review history for material changes.
- Version emission factors, formula logic, metric definitions, and reports where changes affect results.
- Preserve enough calculation provenance to reproduce a result.
- Preserve the data/method snapshot used to generate a finalized report.
- Never silently overwrite an approved result or report version.
- Apply server-side validation and database constraints where appropriate.

Consult the full PRD Section 18 and the Architecture Design Section 8 for the logical data model and proposed relationships.

---

## 17. Report Generation Rules

A report is produced for a specific organization, reporting period, and selected reporting objective/framework profile.

A report may include, as relevant and supported:

- Organization profile.
- Reporting period and organizational boundary.
- Methodology and reporting basis.
- Executive summary.
- ESG governance/management approach.
- Environmental indicators.
- Carbon inventory and calculation methods.
- Social indicators.
- Governance indicators.
- Material topics, where assessed using an appropriate method.
- Targets/progress, when enabled.
- Risks and improvement recommendations.
- Data quality, estimates, omissions, and limitations.
- Framework mapping/disclosure index, only where implemented and verified.
- Supporting references and appendices.

### Report safeguards

- Use only approved/eligible records according to the report status rules.
- Make unsupported or missing disclosures visible, omit them, or mark them unresolved; never fill gaps with fabricated values.
- Distinguish directly reported figures, calculated figures, estimates, qualitative disclosures, AI-generated drafts, and approved statements.
- Preserve report versions and source snapshots.
- Define what internal organizational approval means. It is not the same as independent external assurance.
- Make export permissions explicit and preserve methods, units, reporting period, and provenance in exports where practical.

---

## 18. Security, Privacy, and Auditability

Security and privacy are product requirements, not optional future enhancements.

### Required safeguards

- Secure authentication and account recovery.
- Server-side role/permission checks.
- Organization-level data isolation.
- Private document storage and authorized downloads.
- Secrets and API keys kept out of browser bundles and source control.
- Secure communication and standard web application protections.
- Data minimization and appropriate retention/deletion policies.
- Appropriate access controls for HR, incident, and other sensitive information.
- Audit records for material changes, approvals, factor/configuration updates, report finalization, exports where required, and other critical actions.
- Safe logs that do not expose credentials, confidential file contents, or unnecessary personal information.
- Backup and restoration procedures that are tested, not merely configured.
- Separate development, staging, and production environments.

The current documents flag Ghanaian data-protection obligations and other local requirements for authoritative review. Do not invent legal conclusions. Privacy, retention, hosting location, cross-border data transfers, and any relevant professional/legal review remain to be confirmed before production deployment.

---

## 19. Error Handling and Failure Behavior

The application should remain honest and recoverable when data or services fail.

Examples:

- **Missing value:** Show it as missing, not zero.
- **Invalid unit:** Reject or request correction before calculation.
- **No valid emission factor:** Do not calculate; explain that the source is not currently supported.
- **Incomplete evidence:** Warn or prevent approval according to the metric's evidence rules.
- **Duplicate submission:** Detect likely duplicates or require explicit review.
- **Reporting-period mismatch:** Reject or flag for correction.
- **Changed organizational boundary:** Record the change and warn about cross-period comparisons.
- **Updated factor:** Preserve prior results and approved report versions; create a reviewed recalculation where required.
- **AI provider unavailable:** Keep manual workflows usable and indicate that AI assistance is unavailable.
- **File parsing fails:** Retain the original file if safely stored, report the error, and allow manual entry; do not invent extracted values.
- **Report export fails:** Preserve report state/source snapshot and offer a safe retry path.
- **Permission denied:** Show a safe message without revealing records belonging to another tenant.
- **Approved record correction:** Use a controlled revision and review process, with audit history.

---

## 20. Testing and Definition of Done

Testing must cover unit, integration, end-to-end, access-control/security, and user-acceptance behavior as appropriate. Tests are especially important for multi-tenancy, emissions calculations, factor versioning, report generation, and AI boundaries.

### Critical test areas

1. An unauthorized user cannot access another organization's data by changing a route or record identifier.
2. A contributor cannot perform reviewer/admin actions by calling a protected API directly.
3. A document cannot be downloaded without a valid authorization check.
4. Invalid or incompatible units/factors are rejected.
5. A carbon result records the correct activity data, factor version, formula version, period, and provenance.
6. Updating a factor does not silently mutate a finalized historical result/report.
7. Missing data is never automatically converted to zero.
8. Draft or rejected submissions do not appear as approved values in finalized reports.
9. A report does not invent missing disclosures and preserves its source snapshot/version.
10. AI-generated text is marked as draft, grounded in available data, editable, and reviewed before approval.
11. Audit records preserve relevant actions and timestamps without exposing secrets.
12. Backup restoration and core recovery procedures are exercised before production use.

A feature is not done merely because a page exists. It is done when its business rules, validation, permissions, loading/empty/error states, audit behavior where required, tests, and acceptance criteria are satisfied.

---

## 21. Success Measures

Candidate product metrics include:

- Organizations completing onboarding.
- Time to first useful dashboard.
- Percentage of organizations submitting their first dataset.
- Repeat submissions and reporting periods completed.
- Time spent preparing a report compared with the customer's prior process.
- Percentage of numerical disclosures tied to approved records or reproducible calculations.
- Data-completion and evidence-coverage rates, with their denominator/method defined.
- Number of calculation corrections and unresolved data-quality issues.
- User satisfaction, willingness to pay, trial-to-paid conversion, retention, and cancellation once a commercial offer is tested.

Distinguish product engagement and reporting completeness from actual environmental or social impact. Do not claim emissions reductions solely because emissions were reported or calculated.

---

## 22. Delivery Roadmap

### Phase 0 — Discovery and risk reduction

- Validate customer segment and report purpose.
- Confirm candidate MVP metric set.
- Review methods and emission-factor sources for initial carbon activities.
- Sketch core user journeys and screens.
- Compare hosting/database/auth/storage providers.
- Identify data protection, retention, and deployment questions.
- Record decisions and remaining risks.

### Phase 1 — Foundation

- Repository, environments, CI, migrations.
- Authentication and organization membership.
- Organization profile and reporting periods.
- Preliminary ESG assessment and metric selection.
- Submissions, server validation, and workflow states.
- Private evidence storage.
- Audit events for material actions.

### Phase 2 — Carbon, dashboard, and report MVP

- Approved factor library and deterministic calculation module for selected sources.
- Unit and formula tests; provenance persistence.
- Status-aware dashboard and drill-down.
- Report readiness, source snapshot, versioning, PDF export.
- End-to-end workflow and failure testing.

### Phase 3 — Pilot stabilization

- Usability tests with selected organizations.
- Improve core workflows based on observed friction.
- Add CSV import/notifications if validated as needed.
- Test backup, restore, support, monitoring, and retention procedures.

### Phase 4 — Commercial and regional expansion

Consider subscription management, consultant multi-client spaces, multi-site support, targets/actions, AI-assisted drafts, more framework mappings, broader Scope 3, integrations, and country-specific configuration only when customer need, methods, risks, and operating costs justify them.

Do not assign precise delivery dates without known team capacity, budget, and dependency information.

---

## 23. Decisions Still Open

The following are unresolved in the current project documents and should not be treated as settled:

| ID | Decision | Why it matters | Next action |
|---|---|---|---|
| ADR-001 | Final hosting, database, authentication, and storage provider | Cost, privacy/data transfer, access controls, backup and recovery | Compare realistic providers and test tenant/storage policies |
| ADR-002 | Initial pilot sector and report purpose | Determines metrics, sources, and report structure | Interview prospective pilot organizations and report recipients |
| ADR-003 | Initial carbon sources and approved emission-factor library | Determines whether calculations can be enabled credibly | Compile source register, review methods, approve units/factors and tests |
| ADR-004 | Single-site vs multi-site MVP | Affects forms, schema, dashboard and complexity | Start with one site unless pilot evidence requires otherwise |
| ADR-005 | Whether AI is enabled in the pilot | Privacy, cost, accuracy and trust risk | Keep disabled until review and data-flow controls pass |
| ADR-006 | CSV import at first release | Depends on real customer spreadsheet needs | Test sample spreadsheets and validate implementation effort |
| ADR-007 | Retention/deletion policy | Privacy, legal, cost and operational impact | Inventory data categories and obtain appropriate review |
| ADR-008 | Report formats and approval semantics | Affects workflow, snapshots and customer expectations | Confirm PDF-first approach and define what organizational approval means |
| ADR-009 | Background job mechanism | Adds infrastructure but may be needed for long-running tasks | Start simple; introduce a queue when measured need exists |
| ADR-010 | Performance, availability, RPO/RTO targets | Affects hosting cost and production operations | Set targets after provider evaluation and realistic load assumptions |

Other validation work includes market willingness-to-pay, customer discovery, framework applicability, local legal obligations, data protection, current standards versions, and sector-appropriate carbon methods/factors.

---

## 24. Guidance for AI Assistants and Vibe-Coding Tools

When asked to design, implement, refactor, or document this project, follow these instructions:

1. **Read the relevant source PRD before implementation.** Use `Frontend_PRD.md` for screen behavior and `Architecture.md` for system design.
2. **Stay inside the approved scope.** Do not silently add major features, external integrations, billing, all Scope 3 categories, multi-site consolidation, or advanced analytics to the MVP.
3. **Keep assumptions visible.** Label a proposed behavior as an assumption or ask for a decision when the choice materially affects security, calculations, schema, or reporting.
4. **Do not invent legal or standards claims.** Verify authoritative current sources if asked for research; otherwise flag for review.
5. **Do not invent emission factors or customer data.** If a method/factor is missing, make the relevant calculation unavailable and explain what must be provided.
6. **Use deterministic business logic for calculations.** Do not make carbon arithmetic depend on free-form AI output.
7. **Enforce security on the server.** Never rely only on frontend hiding, client route guards, user-supplied tenant IDs, or UI role labels.
8. **Preserve traceability.** Keep relationships among data, period, source/evidence, factor version, formula version, reviewer action, and report snapshot.
9. **Represent data states honestly.** Missing, zero, estimated, unavailable, not applicable, draft, submitted, and approved must not be conflated.
10. **Do not fake future functionality.** If a feature is not implemented, do not display it as operational.
11. **Include tests for critical behavior.** Prioritize access isolation, unit conversions, factor compatibility, report correctness, and status transitions.
12. **Protect confidential data.** Do not expose secrets in client code or logs. Use minimized data for external services only after the required controls are approved.
13. **Keep architecture simple.** Prefer a modular monolith and clearly defined domain services for the MVP; do not add unnecessary microservices or infrastructure.
14. **Deliver changes incrementally.** Explain which requirement is addressed, files/components affected, assumptions, tests performed, and remaining gaps.
15. **Do not claim production readiness without evidence.** Note untested areas and unresolved decisions.

### Preferred implementation response format

For significant implementation tasks, provide:

- Objective and related requirement IDs.
- Scope and assumptions.
- Proposed change or architecture.
- Data/API implications.
- Security and privacy implications.
- Error and edge-case handling.
- Tests and acceptance criteria.
- Known limitations and decisions required.

---

## 25. Glossary

- **ESG:** Environmental, Social, and Governance topics and performance information.
- **PRD:** Product Requirements Document; describes the product, user needs, scope, requirements, and acceptance criteria.
- **MVP:** Minimum Viable Product; the smallest useful version built to validate product value and workflows.
- **Tenant / organization:** A customer workspace whose records must be isolated from other organizations.
- **Reporting period:** The defined timeframe to which an ESG submission, calculation, or report applies.
- **Metric definition:** Versioned description of a metric, its type, unit, validation, frequency, evidence expectations, and applicability.
- **Submission:** An organization's reported value or status for a metric and period, including workflow state and source information.
- **Evidence:** A document or record supporting a submission; its presence does not guarantee correctness.
- **Activity data:** A measured or estimated quantity associated with an emissions source, such as kWh or litres of fuel.
- **Emission factor:** A sourced coefficient used to convert activity data into a greenhouse gas emissions result.
- **Scope 1:** Direct emissions from sources owned or controlled by the organization, under the selected accounting boundary and method.
- **Scope 2:** Indirect emissions from purchased/acquired electricity and other applicable energy, according to the selected methodology.
- **Scope 3:** Other indirect value-chain emissions; the complete standard has 15 categories, but MVP coverage is limited to implemented categories.
- **CO2e:** Carbon dioxide equivalent, a unit used to express greenhouse gas emissions on a comparable basis under the method used.
- **Factor version:** A specific version of an emission factor with source, applicability, units, and reference period.
- **Calculation provenance:** The stored activity data, factor, units/conversions, formula/method version, and related metadata needed to reproduce a calculation.
- **Tenant isolation:** Controls preventing users from accessing another organization's data without explicit authorization.
- **Audit event:** A record of an important system or user action, including relevant actor, entity, time, and action.
- **Report snapshot:** A preserved representation of the source data and calculation state used to create a particular report version.
- **Framework mapping:** A documented relationship between a platform metric/disclosure and a reporting framework's relevant disclosure; a mapping is not itself proof of compliance.
- **AI-generated draft:** Text produced with AI assistance that remains subject to review and approval and is not the authoritative source for numerical calculations.

---

## 26. Final Reference Rule

Use this knowledge base to preserve continuity, but consult the detailed PRD, Frontend PRD, and Architecture Design for exact implementation requirements. When evidence, methodology, regulatory applicability, or technical decisions are missing, clearly mark the gap and route it for validation. The product must prefer a transparent limitation over an unsupported ESG claim or an untraceable carbon result.

# Tekstain Nexus ESG and Carbon Management Platform
## Frontend Product Requirements Document (Frontend PRD)

**Document status:** Draft for founder review and MVP validation  
**Version:** 0.1  
**Prepared:** 14 October 2026  
**Parent document:** `Tekstain_Nexus_ESG_Platform_PRD.md`  
**Product owner:** Tekstain Nexus  
**Primary market:** Ghana  
**Product type:** Multi-tenant SaaS web application

> **Source and scope note:** This document extracts and organizes the frontend-facing requirements from the parent PRD. It is focused on user interface, navigation, interactions, screen states, user workflows, accessibility, and presentation of data. Backend, database, authorization, and calculation services remain responsible for enforcing business rules and security. The frontend must not be treated as the security boundary.

---

## 1. Frontend Purpose

Build a clear, accessible, responsive web interface that enables Ghanaian SMEs and other authorized organizations to set up an ESG workspace, collect and review selected ESG information, inspect supported carbon calculations, monitor reporting completeness, and generate an evidence-based draft ESG report.

The frontend should make ESG processes understandable to users who may not have specialist sustainability knowledge. It must present what is known, missing, estimated, submitted, flagged, or approved without making unsupported ESG or compliance claims.

### 1.1 Primary MVP outcome

An authorized pilot user can:

1. Sign in and access the correct organization workspace.
2. Set up the organization profile and reporting period.
3. Complete a preliminary ESG assessment and select relevant metrics.
4. Enter selected ESG data and attach supporting evidence.
5. Save drafts, submit records for review, and correct records when requested.
6. Inspect dashboard status and drill into underlying records they are permitted to see.
7. View supported emissions calculations with units, reporting period, factor/method information, and limitations.
8. Generate, review, approve, and export a draft or approved-by-organization PDF report.

### 1.2 Product principles reflected in the UI

- **Evidence before narrative:** Material claims and figures should be traceable to source records or calculations.
- **Missing is not zero:** Blank, zero, not applicable, not available, not yet collected, and estimated must remain distinct.
- **Plain language:** Explain ESG terms and user actions clearly.
- **Human approval:** Draft content and calculations requiring review must not appear approved by default.
- **Transparent calculations:** Display units, reporting period, methodology, factor/source information, and relevant estimation or quality notes.
- **Secure by default:** Only show records and actions the current user is authorized to access; backend services must enforce this independently.
- **Progressive complexity:** Display only active, relevant features; do not expose future modules as functioning features.
- **No unsupported green claims:** Do not imply that an organization is compliant, sustainable, net zero, certified, verified, or assured unless an appropriate process and evidence support that status.

---

## 2. Target Users and UI Permissions

The interface must adapt its available navigation, actions, and record visibility to the user's organization membership and role. Hiding a button is not authorization; APIs and data services must independently reject unauthorized actions.

| Role | Frontend needs | Typical permitted actions |
|---|---|---|
| Organization Owner/Admin | Organization setup, reporting periods, users, dashboard, all relevant ESG modules, reports | Create/edit profile; manage members where enabled; create or edit records; submit/review/approve according to permissions; generate and approve reports; export data |
| ESG Manager | Data overview, metric selection, submissions, review queue, carbon accounting, reports | Create/edit records; coordinate submissions; run supported calculations; review/approve if granted; generate reports |
| Contributor | Assigned data and clear submission instructions | Create/edit assigned draft records, attach evidence, submit, and respond to review comments |
| Reviewer | Review queue and record/evidence detail | Inspect submitted records, comment, approve, reject, or request changes when permitted |
| Read-only Viewer | Read-only organization data and reports allowed by role | View permitted records, dashboard, and reports; no editing or exporting by default unless granted |
| Explicitly Authorized ESG Consultant | Client workspace(s) specifically granted to them | Access only delegated client records/actions; report approval only where the client formally delegates that authority |
| Platform Administrator | Platform configuration interface separate from customer navigation | Manage platform configuration, approved metric definitions, report templates, and emission-factor library where authorized |

### 2.1 Access and tenant-visibility rules

- Show the active organization clearly in the app shell.
- Only display organizations/workspaces for which the user has an active membership or explicit delegation.
- All organization-specific pages and records must be scoped to the active organization.
- A user from one organization must not see another organization's records by changing a URL or identifier. Backend authorization must enforce this; frontend routing is not a substitute.
- Do not show admin-only navigation to ordinary customer roles.
- Sensitive HR information should be aggregated and restricted; the MVP should not expose unnecessary employee-level health or personal details.
- When access is denied, show a safe message without revealing confidential information about another tenant.

---

## 3. Information Architecture and Navigation

Use a simple, consistent application shell with a clear page title, active organization context, and visible reporting-period context on relevant pages.

### 3.1 Initial navigation

1. **Dashboard** — reporting status, headline indicators, pending tasks, and data quality.
2. **Organization** — profile, sites when enabled, organizational boundary, and reporting periods.
3. **ESG Assessment** — onboarding responses and selected metrics.
4. **Data Collection** — metrics grouped by Environmental, Social, and Governance, with submissions grouped or filterable by status.
5. **Carbon Accounting** — supported sources, factors, calculations, methods, and limitations.
6. **Documents & Evidence** — uploaded files and links to related submissions.
7. **Reports** — draft, under-review, approved, and previous report versions.
8. **Tasks/Reviews** — assigned submissions and review queue.
9. **Settings** — users, roles, organization settings, and preferences.
10. **Administration** — platform-only configuration, visible only to authorized administrators.

Targets, subscription management, advanced integrations, and other future modules must appear only when implemented and enabled for the user. Do not display inactive modules as working features.

### 3.2 Global UI elements

- Organization/workspace context.
- Reporting period selector or clearly displayed current period wherever period-specific data appears.
- Navigation with current section indicated.
- User/account menu and sign-out action.
- Consistent page headings and primary action placement.
- Inline status labels and validation messages.
- Loading, empty, success, and error feedback.
- Confirmation prompts for potentially destructive or consequential actions.

---

## 4. Screen Requirements

The following screens are required for the MVP unless otherwise indicated. Layout and visual styling should be finalized during UX design; the parent PRD does not prescribe a fixed brand palette or exact visual design.

### 4.1 Sign-in and account access

**Goal:** Let an authorized user securely access their account.

**Core interactions:**
- Sign in.
- Register where registration is enabled.
- Request password recovery.
- Follow password reset or account recovery flow.
- Sign out.

**UI states:**
- Initial/ready.
- Submitting/loading.
- Invalid credentials or validation error.
- Recovery request accepted.
- Recovery failure or expired/invalid reset link.
- Network/service error.

**Frontend requirements:**
- Validate required fields and show clear, field-specific feedback.
- Do not reveal whether an arbitrary email address has an account during recovery.
- Do not expose passwords, session tokens, or secrets in client logs or UI messages.
- Do not rely on client-side route guards as the only protection for authenticated pages.

### 4.2 Organization setup and reporting period

**Goal:** Establish the organization workspace and the reporting context used by submissions and reports.

**Core fields, as applicable:**
- Legal or trading name.
- Country, including Ghana.
- Industry/business activity.
- Organization size.
- Location and relevant contact details.
- Currency option, including GHS.
- Reporting period and financial year.
- Reporting objective or selected reporting framework/profile.
- Organizational boundary choices and covered sources when carbon accounting is enabled.
- Sites/facilities when the feature is enabled.

**Core interactions:**
- Create or edit organization profile.
- Define and update a reporting period.
- Select reporting objective/profile.
- Record the organizational boundary and included sources where relevant.

**UI states:**
- Incomplete setup.
- Editing.
- Saving/loading.
- Saved successfully.
- Field validation errors.
- Invalid reporting-period dates.
- Read-only state when the user lacks edit permission.

**Rules:**
- Clearly distinguish currency from physical measurement units used for environmental or emissions data.
- Explain organizational-boundary choices in accessible language.
- If a boundary changes between periods, make the change visible and flag that comparisons may not be directly comparable.
- A selected framework/profile must not be presented as proof of compliance.

### 4.3 ESG onboarding and assessment

**Goal:** Help the organization identify an initial set of relevant ESG topics and available data.

**Core interactions:**
- Answer questions about business activity, organization size, reporting objective, and data availability.
- Save progress and return later.
- Review suggested candidate metrics.
- Mark suggested metrics relevant, not applicable, not available, or not yet collected, with a reason where required.
- Review and confirm the initial data checklist.

**UI states:**
- Not started.
- In progress/draft.
- Completed.
- Needs review.
- Saved/resumed.

**Rules:**
- Present recommendations as suggestions that an authorized user can review and change.
- Label the assessment as preliminary ESG screening. Do not imply that it constitutes a complete formal materiality or double-materiality assessment.
- Clearly distinguish unavailable information from a zero value.

### 4.4 Dashboard

**Goal:** Help users understand reporting status, outstanding work, and supported sustainability indicators for the selected reporting period.

**Required content:**
- Reporting status by Environmental, Social, and Governance category.
- Selected headline indicators where approved data exists.
- Missing, submitted, flagged, and approved information shown distinctly.
- Pending submissions and review tasks relevant to the user.
- Data completeness indicators for the selected metrics.
- Evidence coverage where the system has a defined method for calculating it.
- Supported Scope 1 and Scope 2 totals, and Scope 3 only where implemented and supported.
- Estimation/methodology limitations for emissions indicators.

**Core interactions:**
- Filter or switch reporting period.
- Navigate to a category, task, metric, or review item.
- Drill from summary indicators into underlying source records when permitted.

**UI states:**
- No data yet.
- Partial data.
- Data available with unresolved warnings.
- Data ready for review/reporting.
- Loading/error.

**Rules:**
- Show units and the reporting period with numerical indicators.
- Do not show arbitrary ESG performance scores or unsupported benchmarks.
- Label emissions as “calculated emissions for supported sources” unless completeness criteria for the selected inventory have been met.
- Do not imply that reporting activity by itself demonstrates real-world environmental improvement.

### 4.5 Data Collection list

**Goal:** Let users find the relevant metrics and see the state of each submission.

**Required features:**
- Group metrics by Environmental, Social, and Governance.
- Show the metric name, plain-language description, unit, reporting period, source/evidence expectation, and current status.
- Provide status filters or groupings for draft, submitted, under review, changes requested/rejected, and approved.
- Show whether information is not applicable, unavailable, not yet collected, estimated, or reported where relevant.
- Display the next action needed for incomplete or returned records.

**Core actions:**
- Open a metric form.
- Create or continue a draft.
- Open submitted information.
- Attach or inspect evidence.
- Review comments and resubmit when permitted.

### 4.6 Metric submission form

**Goal:** Enable a user to submit valid, traceable information for a defined metric and reporting period.

**Required information where applicable:**
- Metric name and definition.
- ESG category.
- Reporting period.
- Value and unit.
- Data source or source description.
- Site/source boundary where enabled.
- Evidence link or uploaded file.
- Status/reason for unavailable or not-applicable data.
- Estimate method/assumptions when a metric is estimated.
- Submitter and review status as system-managed metadata.

**Core actions:**
- Save draft.
- Validate.
- Submit for review.
- Attach evidence.
- Respond to reviewer comments and resubmit.

**UI states:**
- Empty form.
- Draft.
- Validation error.
- Warning requiring attention.
- Submitted/under review.
- Changes requested.
- Rejected.
- Approved/read-only.

**Rules:**
- Show inline validation beside the relevant field and summarize issues before submission.
- Distinguish hard errors that block submission from warnings that remain visible for review.
- Preserve original source values and units if a normalized/converted value is displayed.
- Do not turn a blank or unavailable value into zero.
- Draft, rejected, and unapproved values must not be displayed as approved results in finalized totals.
- Once approved, editing must follow the correction/revision workflow rather than silently overwriting the approved record.
- The backend remains responsible for authoritative validation and state-transition enforcement.

### 4.7 Documents & Evidence library

**Goal:** Let authorized users upload, locate, inspect, and link supporting evidence to ESG submissions.

**Examples of source documents:** Electricity bills, fuel receipts/logs, water bills, waste contractor records, procurement records, aggregated HR records, occupational health and safety records, sustainability policies, governance policies, supplier information, and relevant permits/certificates.

**Required information:**
- Document name/file type.
- Reporting period.
- Document category/type.
- Upload date and uploader.
- Related metric/submission link.
- Review status or relevant notes where available.

**Core actions:**
- Upload permitted file.
- View document metadata.
- Open a permitted file securely.
- Link evidence to a submission.
- Replace or request removal according to available permissions and policy.

**UI states:**
- Upload in progress.
- Upload success.
- Unsupported file type/size.
- Upload failure/retry.
- No documents.
- No permission.

**Rules:**
- Clearly communicate file type/size restrictions once defined by implementation.
- Do not indicate that evidence has been accepted or that data is approved merely because a file uploaded successfully.
- Private file access must be authorized by server/storage controls; public file URLs must not be assumed safe.
- Material evidence replacement/deletion must show confirmation and preserve the required history.

### 4.8 Tasks and review queue

**Goal:** Give reviewers a clear queue of records needing review and allow contributors to understand requested corrections.

**Reviewer actions:**
- Open a submitted record.
- Inspect value, unit, reporting period, source, evidence, and warnings.
- Approve, reject, or request changes when authorized.
- Add a comment/reason.

**Contributor actions:**
- View review feedback.
- Edit a record with changes requested.
- Resubmit for review.

**UI states:**
- Empty queue.
- Pending review.
- In review.
- Approved/resolved.
- Changes requested.
- Rejected.
- Error/loading.

**Rules:**
- State labels and available actions must match the user's permissions and the record's current state.
- Reviewer decisions must show confirmation and remain visible in history.
- A rejected or returned record must not disappear silently from the review history.

### 4.9 Carbon Accounting

**Goal:** Allow authorized users to enter or inspect supported activity data and transparently review emissions calculations.

**UI must present, where applicable:**
- Supported activity/source type.
- Activity data and original unit.
- Reporting period and organizational boundary.
- Emissions scope/category.
- Emission factor value, unit, source, reference year/version, geographic applicability, and relevant method/gas information.
- Defined unit conversion and formula/method information.
- Calculated result and unit (kgCO2e or tCO2e as appropriate).
- Estimate/proxy status, data-quality rating, and limitations.
- Supporting evidence and review/approval status.

**Core actions:**
- Select a supported source and reporting period.
- Enter/select activity data and original unit.
- Inspect the applicable approved factor.
- Request or view a calculation.
- Inspect the calculation result and provenance.
- Submit or review the calculation where the workflow supports it.

**UI states:**
- No supported factor available.
- Incompatible units.
- Missing/invalid activity data.
- Calculation successful.
- Estimate/proxy limitation.
- Pending review.
- Approved.
- Error.

**Rules:**
- Never invent a missing emission factor or allow the frontend to calculate authoritative emissions from unconstrained AI-generated text.
- Distinguish location-based and market-based Scope 2 methods where implemented; do not present them as equivalent.
- Show only Scope 3 categories actually implemented and supported.
- Keep gross emissions separate from offsets/credits; offsets are outside the MVP functionality.
- Prior or finalized results must not be silently changed when factors or source records are updated; the UI should surface new versions and their relationship to older versions.
- When a required factor is unavailable, explain that the calculation cannot be completed under the current supported method.

### 4.10 Report builder and reports library

**Goal:** Generate a reviewable report from approved, traceable information and export the PDF.

**Core interactions:**
- Select organization and reporting period.
- Select reporting objective/profile where available.
- Review readiness, missing data, and unresolved warnings.
- Preview eligible report sections.
- Generate a draft.
- Inspect content, figures, methods, boundaries, and limitation statements.
- Submit for review or approve where authorized.
- Export PDF.
- Open prior report versions.

**Possible report sections when supported by the selected objective and data:**
- Cover page and report status.
- Organization profile.
- Reporting purpose, period, and boundary.
- Methodology and limitations.
- Executive summary based on supported information.
- ESG oversight and management approach.
- Environmental data/performance.
- Greenhouse gas inventory for supported sources.
- Selected social and governance indicators.
- Goals/actions if supported.
- Data completeness and quality statement.
- Missing data, exclusions, and estimates.
- Verified framework mapping index, where in scope.
- Methodology/factor references and appendices.

**UI states:**
- Readiness check in progress.
- Data gaps or blocking issues.
- Generation in progress.
- Generation failure/retry.
- Draft.
- Under review.
- Approved by organization.
- Superseded by newer version.

**Rules:**
- Display reporting period, reporting basis, relevant boundaries, methods, estimates, missing data, and quality limitations.
- Unsupported disclosures must remain flagged/omitted or explicitly marked unavailable; do not fabricate content.
- Clearly distinguish draft from approved-by-organization content.
- Do not imply independent assurance or certification unless genuine external evidence has been recorded.
- Show report version, creation time, period, status, and relevant source snapshot/reference details.
- Corrections should create a new identifiable report version rather than silently overwrite a finalized report.
- PDF is P0. CSV/XLSX exports are P1; DOCX is P2 unless separately prioritized.

### 4.11 Settings and administration

**Customer settings, according to permission:**
- Organization profile and reporting settings.
- User/membership management where enabled.
- Role assignment where enabled.
- User preferences where implemented.

**Platform administration, restricted to authorized administrators:**
- Organizations and accounts.
- Metric definitions and their versions.
- Report templates.
- Approved emission-factor library.
- Framework/disclosure configuration.
- Platform configuration and operational administration.

Show confirmation and success/failure feedback for consequential changes. Configuration changes must not silently reinterpret historical submissions or reports. The parent PRD defines billing/subscription administration as a later or manually handled capability for the pilot.

---

## 5. Frontend Functional Requirements

Priority definitions: **P0** = required for the MVP pilot; **P1** = follow-up after core workflows are stable; **P2** = future capability.

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---:|---|
| UI-AUTH-001 | Provide sign-in and account recovery screens | P0 | Forms validate required fields and show safe, understandable success/error feedback |
| UI-NAV-001 | Show role-appropriate navigation and active organization context | P0 | Customer users see only applicable navigation; active organization is clear |
| UI-ORG-001 | Provide organization profile and reporting-period forms | P0 | Required fields and date ranges are validated; saved state is visible |
| UI-ONB-001 | Provide resumable preliminary ESG assessment | P0 | Progress is saved; selected/recommended metrics are reviewable; assessment is labelled preliminary |
| UI-DATA-001 | Provide category-based metric list with status filtering | P0 | Metrics can be found by ESG category/status; key period/unit/status is visible |
| UI-DATA-002 | Provide metric form with draft, validate, submit, and correction states | P0 | UI shows field errors/warnings and state-appropriate actions; approved records are read-only unless correction flow is invoked |
| UI-DATA-003 | Distinguish zero, missing, not applicable, unavailable, not collected, and estimated | P0 | All statuses render distinct labels and are not conflated in dashboard/report views |
| UI-EVID-001 | Provide evidence upload and linked-document views | P0 | Upload progress/errors are shown; evidence is linked to the relevant record; successful upload does not imply approval |
| UI-REV-001 | Provide review queue and record review view | P0 | Reviewer sees source data/evidence and may take only authorized actions; comments/history are visible |
| UI-DASH-001 | Provide period-specific ESG dashboard | P0 | Submitted, missing, flagged, and approved data are visually distinct; indicators display units/period |
| UI-DASH-002 | Provide drill-down from dashboard indicators to authorized source records | P0 | Links resolve only to permitted records; no data is disclosed through identifiers or URLs |
| UI-CARBON-001 | Present supported emissions sources, calculations, and provenance | P0 for enabled carbon sources | Result, unit, factor reference, formula/method, period, estimate/limitations, and status are shown |
| UI-REPORT-001 | Provide report readiness review and draft generation flow | P0 | Gaps and unresolved warnings are visible before finalization; unsupported disclosures are not fabricated |
| UI-REPORT-002 | Provide report version list, approval status, and PDF export | P0 | Status/version/time/period are visible; a newer version does not silently replace a prior one |
| UI-RESP-001 | Support responsive layouts for phone and desktop viewports | P0 | Core journeys remain usable without horizontal overflow in supported viewports |
| UI-ACCESS-001 | Meet the WCAG 2.2 AA implementation goal | P0 target | Keyboard navigation, visible focus, labels, contrast, semantic errors, and screen-reader spot checks are completed |
| UI-IMPORT-001 | Provide CSV import template, preview, and row-level errors | P1 | Invalid rows are explained and user can cancel before committing imported records |
| UI-AI-001 | Present AI narrative and gap summaries as reviewable drafts | P1, only after AI is approved | Draft status and underlying data references/limitations are visible; human review is required |
| UI-EXPORT-001 | Provide CSV/XLSX data export interface | P1 | Only authorized, tenant-scoped data is exported with metric names, units, and periods where available |
| UI-TARGET-001 | Provide sustainability targets and action-plan screens | P1 | Expose only after target functionality and progress formulas are implemented and approved |

---

## 6. UI State and Status Conventions

Use consistent labels and behavior across the application. Exact colors, icons, and tokens are a design-system decision, but color must never be the only means of conveying status.

### 6.1 Data-submission states

- **Draft:** not submitted; excluded from approved totals and finalized report data.
- **Submitted:** sent for review.
- **Under Review:** currently being checked.
- **Changes Requested:** returned with comments for correction.
- **Rejected:** not approved; remains visible in history and is excluded from approved results.
- **Approved:** accepted for eligible dashboard/report use, subject to other report rules.

### 6.2 Data availability/value states

- **Reported value**
- **Zero** (an actual reported/measured zero)
- **Not applicable** (reason where required)
- **Not available** (reason where required)
- **Not yet collected**
- **Estimated** (method and assumptions recorded)

These value states are separate from workflow states. For example, a record can be an estimate and still be awaiting review.

### 6.3 Report states

- **Draft**
- **Under review**
- **Approved by organization**
- **Superseded**
- **Externally assured** only as metadata when a genuine independent assurance process and evidence are recorded; not an automatic platform result.

### 6.4 Feedback patterns

- Show field-specific error messages and explain how to resolve them.
- Distinguish blocking validation errors from non-blocking warnings.
- Keep warnings visible until resolved or explicitly accepted where the workflow permits.
- Confirm important actions such as approval, report finalization, or evidence removal.
- Give a clear next step after submission, successful save, review return, or error.
- Preserve drafts and warn before losing unsaved edits where practical.

---

## 7. UX, Responsive Design, and Accessibility

### 7.1 Usability requirements

- Use plain language suitable for users who are not ESG specialists.
- Explain metric definitions and units close to the input fields.
- Show reporting period, data source expectations, and whether the metric is directly reported or calculated.
- Use concise tables and meaningful charts rather than decorative visualizations.
- Make incomplete tasks and the next required action visible.
- Avoid unnecessary data entry and show only relevant/active features.
- Ensure dashboard values can be traced to underlying records where the user's permissions allow it.
- Support loading, empty, partial-data, success, and error states on all core screens.
- Maintain consistent labels, input behavior, status display, and action placement.

### 7.2 Responsive layouts

- Support common desktop and phone browser viewports.
- Core journeys—sign-in, organization setup, onboarding, metric submission, evidence upload, dashboard review, and report access—must remain usable on smaller screens.
- On narrow screens, tables may use responsive layouts or horizontal scrolling where appropriate, but primary actions and status information must remain discoverable.
- Do not rely on hover-only interactions.

### 7.3 Accessibility target

Target WCAG 2.2 Level AA as an implementation goal. Validate at minimum:

- Keyboard navigation and logical focus order.
- Visible focus indicators.
- Accessible labels and instructions for form fields.
- Semantic identification of errors and success messages.
- Sufficient text and UI contrast.
- Screen-reader spot checks on core workflows.
- Status communication that does not rely on color alone.

Automated accessibility checks are useful but do not replace manual testing.

---

## 8. Frontend Data Handling and Trust Boundaries

These are UI implementation requirements, not a replacement for backend controls.

1. Do not embed API keys, service-role keys, storage secrets, or other privileged credentials in browser code.
2. Do not assume values such as organization ID, role, approval status, emission factor, or report status are trustworthy merely because they came from client state or a hidden form field.
3. Treat server responses as authoritative for permissions, validation, calculation results, and record state.
4. Present server validation errors in a useful way without leaking stack traces, secrets, or sensitive information.
5. Handle expired sessions and denied requests safely, and avoid leaking cross-tenant record existence.
6. Show private documents only through an authorized retrieval path. Do not make evidence files public for convenience.
7. Avoid placing confidential record contents in browser logs, analytics payloads, error reports, or URLs.
8. For calculations, display the result returned by the defined calculation service; do not implement a second inconsistent emissions formula only in the UI.
9. For AI features, display AI content as draft, preserve a clear review step, and do not let generated text modify approved metric values.
10. If an AI or external service is unavailable, core non-AI workflows must remain usable.

---

## 9. Frontend Testing and Acceptance

### 9.1 Required test layers

- Component/unit tests for form validation, status rendering, navigation, and conditional UI behavior.
- Integration tests for forms, data services, file uploads, report generation, and error handling.
- End-to-end tests for onboarding through report export using test organizations and seeded data.
- Permission-focused UI tests for role-specific actions, alongside independent server-side authorization tests.
- Responsive layout checks on desktop and phone-sized viewports.
- Accessibility checks using keyboard navigation, visible focus, labels, contrast, and screen-reader spot checks.
- Regression tests confirming that old report versions remain identifiable after corrections.

### 9.2 Core end-to-end acceptance journeys

**Journey A — Onboarding**
1. User signs in.
2. User creates an organization and reporting period.
3. User completes preliminary assessment.
4. User reviews initial metric suggestions.
5. User reaches the dashboard and sees the workspace status.

**Pass conditions:** Progress saves; required fields are validated; the assessment is labelled preliminary; suggested metrics can be reviewed.

**Journey B — Data submission and review**
1. Contributor opens a metric.
2. Contributor enters a value and source information.
3. Contributor attaches evidence.
4. Contributor saves draft or submits.
5. Reviewer inspects the data and evidence.
6. Reviewer requests changes or approves.
7. Contributor can see the comment and resubmit where necessary.

**Pass conditions:** Units, period, source and status are visible; hard errors block invalid submission; warning states remain visible; history is retained.

**Journey C — Carbon calculation**
1. Authorized user opens a supported activity source.
2. User enters activity data and unit.
3. User inspects the applicable factor/method.
4. User requests calculation.
5. UI displays result, unit, period, factor provenance, and limitations.

**Pass conditions:** Incompatible units or a missing factor are clearly flagged; no factor or emissions value is invented by the UI; estimate/proxy results are labelled.

**Journey D — Report generation**
1. Authorized user selects a reporting period.
2. User checks data completeness and unresolved warnings.
3. User generates a draft report.
4. User reviews methods, values, missing data, and limitations.
5. Authorized representative approves the report where ready.
6. User exports PDF and can identify its version/status.

**Pass conditions:** Unsupported disclosures are not fabricated; the report shows period and reporting basis; status is explicit; previous versions remain identifiable.

**Journey E — Access control**
1. User accesses an organization to which they belong.
2. User attempts a page/action outside their role.
3. User attempts a route containing another tenant's identifier.

**Pass conditions:** UI offers only role-appropriate actions, but server-side tests independently deny all unauthorized operations; no other tenant's content is revealed.

### 9.3 Definition of Done for frontend screens

A screen is ready when:
- Its primary user goal and required actions are implemented.
- Loading, empty, success, validation, and error states are handled as applicable.
- Role and record-state behavior is correct.
- The screen displays relevant reporting period, units, and data status.
- Keyboard and responsive behavior have been checked.
- Automated tests cover critical interactions.
- It does not present unsupported ESG, carbon, framework, or compliance claims.

---

## 10. Frontend MVP Priorities

### P0 — Required for MVP pilot

- Sign-in/account recovery and protected app shell.
- Organization profile and reporting period setup.
- Preliminary ESG assessment.
- Metric list and metric submission forms.
- Draft/save/submit and correction states.
- Evidence upload and linked evidence metadata.
- Review queue and reviewer comments/actions.
- Basic ESG dashboard with status indicators and permitted drill-down.
- Carbon calculation presentation for explicitly supported factors/sources.
- Report readiness check, draft/report review, approved status, PDF export, and version list.
- Role-aware navigation/actions and safe unauthorized-access handling.
- Responsive layouts and baseline accessibility work.

### P1 — After core workflows stabilize

- CSV import interface with preview and row-level error handling.
- AI-assisted narrative/gap summaries presented as reviewable drafts.
- CSV/XLSX export screens.
- Sustainability target/action-plan interface.
- Expanded member invitations or consultant management if customer discovery validates the need.

### P2 — Future

- OCR/document extraction interface.
- Advanced integrations.
- Full multi-site consolidation UI.
- Broad framework mapping management for customers.
- ESG benchmarking/scoring interfaces without a validated method.
- Carbon credit/offset marketplace.

---

## 11. Out of Scope for Frontend MVP

- A complete enterprise multi-site consolidation experience.
- Every GHG Protocol Scope 3 category.
- Live utility, bank, accounting, supplier, or government integrations unless separately selected and verified.
- Automatic OCR as an authoritative data source.
- Public publishing of customer reports.
- Carbon-credit marketplace or automatic netting of offsets against gross emissions.
- A formal double-materiality assessment experience unless its methodology and evidence requirements are separately defined.
- Automatic legal-compliance determinations or unsupported ESG scores/benchmarks.
- Payment and subscription checkout unless required for the initial paid launch.

---

## 12. Open Decisions That Affect Frontend Design

Resolve these with the product owner before final visual design and implementation:

1. Which industry/sector and customer use case will the first pilot prioritize?
2. What is the primary report purpose: internal baseline, customer request, lender/financing, or voluntary framework-based report?
3. Which reporting objective/framework profile will the first release support?
4. Which activity types and emission factors have been approved for the first carbon screens?
5. Will multi-site data be required in the pilot, or will a single default site be sufficient?
6. Is CSV import required on day one, based on real customer spreadsheets?
7. Will AI be enabled for pilot users, or remain disabled until data and report controls are validated?
8. Which user roles can approve individual records and final reports for the first pilot?
9. Which document types and maximum file sizes will be allowed?
10. What retention, export, and deletion policy should the interface explain to customers?

---

## 13. Final Frontend Acceptance Standard

The frontend MVP is acceptable for a pilot when a target user can complete the onboarding, data submission, evidence, review, supported carbon, dashboard, and report-export journeys with understandable feedback; all important states are clearly distinguished; the interface adapts to the user's permissions; and no screen silently turns missing data into zero, estimated values into verified facts, draft text into approved disclosure, or calculated results into claims of environmental improvement or regulatory compliance.

**Implementation reminder:** This Frontend PRD is a UI requirements baseline extracted from the parent PRD. It does not replace backend/API specifications, schema design, server-side validation, carbon methodology review, security testing, or regulatory review.

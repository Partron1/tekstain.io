MASTER PROMPT: PRODUCT REQUIREMENTS DOCUMENT (PRD)
Tekstain Nexus — ESG and Carbon Management Platform
1. YOUR ROLE
Act as a senior Product Manager, ESG and Sustainability Consultant, Carbon Accounting Specialist, Business Analyst, UX Researcher, Software Architect, and SaaS Product Strategist.
Your task is to develop a comprehensive, technically informed, business-oriented Product Requirements Document (PRD) for an ESG and Carbon Management Platform designed primarily for small and medium-sized enterprises (SMEs) and larger organizations in Ghana.
The PRD must be detailed enough to guide product design, database planning, frontend and backend development, AI-assisted software development, quality assurance, and the eventual commercialization of the platform.
Write the PRD as a professional product specification that a founder, developer, designer, sustainability consultant, and business stakeholder can use to understand the product and its requirements.
Do not begin writing software or generating application code. First, define the product requirements, user needs, features, workflows, business rules, technical expectations, and acceptance criteria.
Where information is missing, make reasonable assumptions, label them clearly, and continue. Do not invent regulatory requirements, reporting obligations, data, or third-party integrations.
________________________________________
2. PRODUCT BACKGROUND
Working product name: Tekstain Nexus ESG and Carbon Management Platform.
Product category: ESG reporting, sustainability data management, carbon accounting, and environmental performance intelligence SaaS.
Primary market: Ghana.
Potential expansion market: Other African countries, subject to localization and validation of applicable regulations, reporting requirements, and data sources.
Primary customers:
- Small and medium-sized enterprises.
- Large companies and corporate organizations.
- Manufacturing and processing businesses.
- Retail and wholesale businesses.
- Agriculture and agribusiness companies.
- Logistics and transportation businesses.
- Hospitality and service businesses.
- Professional service providers.
- Sustainability and ESG consultants managing reporting for multiple clients.
Core business objective:
Build an accessible, affordable, user-friendly ESG platform that helps organizations collect, organize, analyze, monitor, and report environmental, social, and governance information.
The platform should help organizations understand their sustainability performance, identify operational inefficiencies, estimate their greenhouse gas emissions, discover improvement opportunities, and produce structured ESG reports.
The platform should reduce the complexity, cost, and time associated with ESG data management and reporting, especially for SMEs that lack dedicated sustainability teams.
The product should use appropriate automation, data analytics, and carefully controlled AI capabilities to turn organizational data into useful sustainability insights.
The platform should be designed as a commercial SaaS product with a clear path from a minimum viable product (MVP) to a more comprehensive enterprise solution.
________________________________________
3. PRODUCT VISION
Develop a reliable ESG intelligence platform that makes sustainability data understandable and actionable for African businesses.
The product should move beyond merely generating ESG reports. It should help organizations establish a continuous process for:
1.	Collecting sustainability-related data.
2.	Assessing the completeness and quality of that data.
3.	Calculating relevant environmental and operational metrics.
4.	Monitoring environmental, social, and governance performance.
5.	Identifying risks, trends, inefficiencies, and improvement opportunities.
6.	Generating evidence-based ESG reports.
7.	Tracking improvement targets and progress over time.
8.	Supporting management decisions using sustainability information.
The platform should be simple enough for an SME without an ESG specialist but flexible enough to support the needs of larger organizations.
________________________________________
4. PROBLEM STATEMENT
Many organizations, especially SMEs, face challenges when trying to manage sustainability performance and prepare ESG reports.
Potential challenges include:
- ESG information being scattered across spreadsheets, invoices, utility bills, internal reports, and other documents.
- Limited knowledge of ESG reporting concepts and standards.
- Difficulty identifying which information must be collected.
- Inconsistent data collection and reporting processes.
- Limited ability to calculate and monitor greenhouse gas emissions.
- Difficulty identifying environmental impacts across organizational operations and value chains.
- Limited visibility into waste generation, water use, energy consumption, and resource efficiency.
- Inadequate systems for monitoring employee-related, workplace, and governance indicators.
- High costs associated with specialized ESG consultants and enterprise reporting software.
- Difficulty identifying missing data and supporting evidence.
- Challenges tracking sustainability targets and measuring progress.
- Limited access to clear, understandable insights that connect sustainability performance with operational efficiency and business decisions.
Treat these challenges as product hypotheses to be validated rather than universal facts about every organization.
Explain how the proposed product will address these problems.
Identify the most important problems to solve in the MVP and distinguish them from needs that can be addressed in future releases.
________________________________________
5. TARGET USERS AND PERSONAS
Define the primary user personas and their responsibilities, goals, frustrations, permissions, and platform needs.
At a minimum, include the following:
Persona A: SME Owner or Managing Director
Needs a clear understanding of the organization's sustainability performance without needing extensive ESG expertise.
Persona B: Sustainability or ESG Manager
Needs to coordinate data collection, evaluate ESG performance, monitor targets, and prepare reports.
Persona C: Finance or Operations Officer
Needs to submit energy bills, fuel expenses, procurement information, operational records, and other relevant data.
Persona D: Human Resources Manager
Needs to provide employee-related, occupational health and safety, workforce, and other relevant social information.
Persona E: ESG Consultant
Needs to manage multiple client organizations, collect supporting documentation, review data, and prepare reports.
Persona F: Platform Administrator
Needs to manage organizations, subscriptions, users, permissions, platform configuration, and operational monitoring.
For every persona, explain:
- Primary goals.
- Main tasks.
- Problems experienced.
- Required features.
- Data access requirements.
- Relevant permissions.
- Expected benefits.
Recommend additional personas only where there is a clear product justification.
________________________________________
6. DEFINE THE MVP SCOPE
Before specifying individual features, identify the smallest commercially useful version of the platform.
The MVP must focus on solving a clear customer problem without attempting to implement every possible ESG capability at launch.
Evaluate the following candidate capabilities for inclusion in the MVP:
1.	User registration, authentication, and account management.
2.	Organization registration and profile setup.
3.	ESG assessment and onboarding questionnaire.
4.	Organization-specific ESG data collection.
5.	Manual data entry and structured forms.
6.	Spreadsheet and CSV data imports.
7.	Document uploads for supporting evidence.
8.	Environmental data management.
9.	Basic Scope 1 and Scope 2 greenhouse gas emissions calculations.
10.	A clearly defined, limited set of Scope 3 calculation categories where suitable data and reliable emission factors are available.
11.	Social and governance indicators.
12.	Data completeness and quality checks.
13.	ESG performance dashboard.
14.	Carbon emissions dashboard.
15.	AI-assisted data interpretation and report drafting.
16.	ESG report generation.
17.	Reporting-period management.
18.	Sustainability targets and basic progress tracking.
19.	Role-based access control.
20.	Administrative management.
21.	Subscription and billing capabilities, if required for the initial commercial release.
Classify each capability as one of the following:
- P0 — Essential for MVP: Required for the initial product to deliver its core value.
- P1 — Important: Valuable shortly after launch but not essential to validate the initial product.
- P2 — Future enhancement: Defer until product-market fit, technical readiness, or customer demand justifies it.
Provide a rationale for every major prioritization decision.
Do not assume every candidate feature belongs in the MVP.
Explicitly identify features that would create unnecessary complexity, excessive operating costs, or unacceptable implementation risks during the initial build.
Define the boundaries of the MVP, including what the first release will not do.
________________________________________
7. CORE FUNCTIONAL REQUIREMENTS
Develop detailed functional requirements for the modules below.
For each module, provide:
- Purpose.
- Target users.
- Functional requirements.
- User interactions.
- Required inputs.
- Processing and business rules.
- Expected outputs.
- Permissions.
- Error and exception handling.
- Dependencies.
- Acceptance criteria.
- MVP priority.
Assign unique requirement identifiers, such as FR-AUTH-001 or FR-CARBON-001.
Module 1: Authentication and Account Management
Specify requirements for:
- User registration.
- Secure login and logout.
- Password recovery.
- Email verification where appropriate.
- Account profile management.
- Organization invitations.
- User deactivation.
- Session management.
- Optional multi-factor authentication.
- Secure account recovery.

Clearly identify requirements that are essential at launch and those that can be introduced later.
Module 2: Organization Management
Each customer organization must have a structured profile.
Consider fields such as:
•	Legal or registered business name.
•	Trading name.
•	Country of operation.
•	Physical business location.
•	Industry and business activity.
•	Organization size.
•	Number of employees.
•	Reporting period.
•	Financial year.
•	Relevant operating sites.
•	Contact details.
•	ESG contact person.
•	Applicable reporting frameworks.
•	Selected organizational and operational boundaries.
•	Available sustainability policies and certifications.
Separate mandatory fields from optional fields.
Explain how the system handles organizations with multiple branches, sites, facilities, or subsidiaries.
For the MVP, recommend a practical approach to multi-site organizations without creating unnecessary complexity.
Module 3: ESG Onboarding and Assessment
Create an onboarding workflow that helps an organization identify the ESG information relevant to its business.
The questionnaire should adapt to the organization's industry, size, operations, and available information.
It should help users identify:
•	Relevant environmental topics.
•	Relevant social topics.
•	Relevant governance topics.
•	Available internal records.
•	Missing information.
•	Initial sustainability priorities.
•	Potential material sustainability issues requiring further assessment.
Distinguish preliminary ESG screening from a formal materiality assessment.
Do not represent an automated questionnaire as a complete double materiality assessment or professional assurance engagement unless the required methodology and evidence support that claim.
Explain how the onboarding results determine which data collection forms, metrics, and reporting sections are presented to the organization.
Module 4: ESG Data Collection
Design a structured data collection system that minimizes user confusion.
Support suitable combinations of:
•	Form-based data entry.
•	Spreadsheet imports.
•	CSV imports.
•	Document uploads.
•	Recurring data submissions.
•	Manual adjustments with recorded reasons.
•	Review and approval workflows.
•	Assignment of data collection tasks.
Organize data collection into Environmental, Social, and Governance categories.
Potential environmental data includes:
•	Electricity consumption.
•	Generator fuel consumption.
•	Company vehicle fuel consumption.
•	Purchased fuels and other relevant energy sources.
•	Refrigerants and relevant fugitive emissions.
•	Water withdrawal and consumption, where data is available.
•	Waste generation and disposal.
•	Wastewater.
•	Purchased materials and goods.
•	Business travel.
•	Employee commuting.
•	Upstream and downstream transportation.
•	Other relevant Scope 3 activities.
Potential social data includes:
•	Workforce headcount.
•	Workforce composition and diversity, subject to appropriate privacy controls.
•	Employee training.
•	Employee turnover.
•	Occupational health and safety.
•	Working conditions.
•	Relevant labor practices.
•	Employee complaints and grievance mechanisms.
•	Community engagement.
•	Relevant supply-chain social indicators.
Potential governance data includes:
•	Board or management oversight.
•	Business ethics policies.
•	Anti-bribery and corruption controls.
•	Whistleblowing arrangements.
•	Risk management.
•	Data protection policies.
•	Regulatory and compliance management.
•	Sustainability responsibilities.
•	Relevant governance incidents.
These are candidate metrics, not a mandatory checklist for every organization.
Explain how the platform selects, labels, and prioritizes metrics based on reporting objectives, industry context, applicable frameworks, materiality, and available data.
For every metric, define its name, description, unit of measurement, reporting period, data source, collection method, validation rules, and supporting evidence requirements where applicable.
Module 5: Supporting Documents and Evidence Management
Specify how users upload and manage documents that support reported information.
Potential supporting evidence includes:
•	Electricity bills.
•	Fuel purchase receipts.
•	Fuel logs.
•	Water bills.
•	Waste contractor records.
•	Procurement records.
•	HR records.
•	Occupational health and safety records.
•	Sustainability policies.
•	Governance policies.
•	Supplier information.
•	Environmental permits and relevant certificates.
•	Other records required to substantiate ESG disclosures.
For each evidence record, consider storing:
•	Document type.
•	Original filename.
•	Upload date.
•	Reporting period.
•	Relevant ESG metric.
•	Submitting user.
•	Review status.
•	Reviewer comments.
•	Source organization or department.
•	Document version where applicable.
Specify secure access controls, permitted file types, file-size limits, retention rules, and appropriate handling of confidential information.
The platform must not assume that uploading a document automatically proves the accuracy of the underlying data.
Module 6: Data Quality, Validation, and Review
Design data quality mechanisms that help organizations identify errors before generating reports.
Potential validation checks include:
•	Missing required values.
•	Invalid formats.
•	Incorrect units.
•	Duplicate records.
•	Implausible values.
•	Negative values where prohibited.
•	Reporting-period inconsistencies.
•	Incomplete supporting evidence.
•	Unclear source information.
•	Inconsistent organizational boundaries.
•	Large year-on-year changes that require review.
•	Missing information needed for an emissions calculation.
Distinguish between:
•	Hard validation errors that prevent submission.
•	Warnings that require review.
•	Missing information that limits reporting completeness.
•	Reviewer comments and unresolved queries.
Specify data states such as Draft, Submitted, Under Review, Changes Requested, Approved, and Rejected.
Define who can edit, submit, review, approve, and finalize records.
Maintain an audit trail for material changes to data and calculations.
Module 7: Carbon Accounting and Greenhouse Gas Emissions
Design a transparent carbon accounting module aligned with relevant principles of the GHG Protocol, with applicable calculation methods selected according to the activity data, reporting objectives, and available emission factors.
The platform must clearly distinguish between activity data, emission factors, calculated emissions, estimates, and externally verified results.
Scope 1
Consider applicable direct emissions from sources owned or controlled by the organization, such as:
•	Stationary fuel combustion.
•	Company-owned or controlled vehicles.
•	Relevant fugitive emissions.
•	Other applicable direct emission sources.
Scope 2
Consider indirect emissions associated with purchased electricity and any other applicable purchased energy included in the selected accounting methodology.
Explain how the platform can support location-based Scope 2 calculations and, where reliable contractual data and the applicable methodology allow, market-based calculations.
Do not present the two methods as interchangeable.
Scope 3
Design the data model to support the 15 GHG Protocol Scope 3 categories.
However, implement and expose only those categories that can be supported by the selected data collection methods and calculation functionality.
Potential initial categories include:
•	Purchased goods and services.
•	Fuel- and energy-related activities not included in Scope 1 or Scope 2.
•	Upstream transportation and distribution.
•	Waste generated in operations.
•	Business travel.
•	Employee commuting.
Assess these categories for MVP suitability.
Explain how other categories can be added progressively.
Calculation requirements
For each supported emissions source, specify:
•	Activity type.
•	Activity data.
•	Unit of measurement.
•	Reporting period.
•	Organizational boundary.
•	Applicable emissions scope and category.
•	Emission factor.
•	Emission factor source.
•	Geographic applicability.
•	Emission factor reference year.
•	Gas coverage where relevant.
•	Global warming potential basis where applicable.
•	Conversion methodology.
•	Calculation result in kgCO2e or tCO2e.
•	Estimation methodology, if applicable.
•	Data quality rating.
•	Supporting evidence.
•	Calculation date.
•	Formula version.
•	Reviewer and approval status.
Use dimensional consistency checks to reduce calculation errors.
Do not hard-code unexplained emission factors into the application.
Maintain a version-controlled emission-factor library that records the source, publication or reference year, geographic applicability, units, relevant gases, and applicable methodology.
Where available, prefer appropriate Ghana-specific emission factors for Ghanaian activities. If reliable Ghana-specific factors are unavailable, document the alternative factor, its geographic relevance, and the limitations of using it.
Do not invent Ghanaian emission factors or imply that an unverified factor is official.
The calculation engine should clearly identify when a result is based on incomplete data, estimated activity, a proxy factor, or a default assumption.
Specify how calculations are recalculated when an approved factor changes and how previous reporting results are preserved for auditability.
Include example calculations in the PRD, clearly labeled as illustrative.
Carbon accounting limitations
Explain the platform's proposed approach to:
•	Organizational boundaries.
•	Operational boundaries.
•	Base-year selection.
•	Reporting-period comparisons.
•	Estimation and data-quality limitations.
•	Missing data.
•	Corrections and recalculations.
•	Scope 2 methodology selection.
•	Emission-factor updates.
•	Third-party verification.
•	Carbon credits and offsets, if supported in a future release.
Do not imply that the platform provides audited, assured, certified, or regulator-approved emissions results merely because it calculates them.
Module 8: ESG Standards and Reporting Frameworks
Design the platform so that ESG metrics can be mapped to applicable reporting frameworks without treating every framework as identical.
Evaluate the relevance of:
•	Global Reporting Initiative (GRI) Standards.
•	IFRS Sustainability Disclosure Standards, including IFRS S1 and IFRS S2.
•	GHG Protocol.
•	United Nations Sustainable Development Goals (SDGs).
•	Relevant Ghanaian laws, regulatory requirements, and sustainability reporting guidance, where applicable.
Distinguish between:
1.	General ESG metrics.
2.	Metrics required by a selected reporting framework.
3.	Metrics relevant to a particular industry.
4.	Metrics relevant to an organization's material sustainability topics.
5.	Voluntary disclosures.
6.	Disclosures that may be mandatory for a particular organization under applicable rules.
Verify current regulatory claims and standards using authoritative sources before treating them as binding requirements.
Do not claim that following a selected framework automatically makes an organization compliant with every applicable law or reporting obligation.
For each supported framework, specify:
•	Applicable metrics and disclosures.
•	Mapping rules.
•	Required data.
•	Reporting logic.
•	Known gaps.
•	Framework version or effective date.
•	Relevant source documentation.
•	Validation approach.
Where mapping between frameworks is imperfect, document the limitation instead of presenting it as an exact equivalence.
Design the system to support additional frameworks through configuration and structured mappings rather than requiring a complete redesign.
Module 9: ESG Dashboard
Design a dashboard that communicates the organization's sustainability performance clearly.
Potential dashboard components include:
Environmental indicators
•	Total Scope 1 emissions.
•	Total Scope 2 emissions.
•	Supported Scope 3 emissions.
•	Total reported emissions.
•	Emissions intensity, where the denominator and methodology are appropriate.
•	Electricity consumption.
•	Fuel consumption.
•	Water metrics.
•	Waste generation and treatment.
•	Progress toward environmental targets.
Social indicators
•	Relevant workforce metrics.
•	Training indicators.
•	Occupational health and safety metrics.
•	Employee turnover.
•	Other selected social indicators.
Governance indicators
•	Policy adoption.
•	Assigned governance responsibilities.
•	Selected compliance indicators.
•	Relevant risk-management indicators.
•	Status of assigned governance actions.
Data quality indicators
•	Data collection completion rate.
•	Missing information.
•	Records awaiting review.
•	Evidence coverage.
•	Outstanding data-quality warnings.
•	Metrics ready for reporting.
Define how dashboard values are calculated and explain how the user can navigate from a summary indicator to the underlying records and supporting evidence, subject to permission controls.
Avoid creating an impressive-looking dashboard with undefined metrics or arbitrary scores.
For every proposed score, KPI, and benchmark, define the methodology or mark it as a future feature requiring validation.
Module 10: AI-Assisted ESG Intelligence
Design AI functionality that converts validated organizational data into useful explanations and draft reporting content.
Potential capabilities include:
•	Summarizing ESG performance.
•	Explaining significant changes between reporting periods.
•	Identifying data gaps.
•	Highlighting unusual values for human review.
•	Suggesting relevant improvement opportunities.
•	Drafting ESG report sections.
•	Summarizing uploaded documents.
•	Identifying possible relationships between operational activities and environmental impacts.
•	Helping users understand ESG terminology and reporting concepts.
•	Recommending follow-up questions when data is incomplete.
For each AI feature, specify its inputs, outputs, limitations, failure handling, and validation requirements.
Establish the following rules:
1.	AI must not silently invent organizational data, emission factors, policies, metrics, evidence, or regulatory obligations.
2.	AI-generated claims must be grounded in available records or clearly identified as general guidance or assumptions.
3.	Calculated emissions must come from the defined calculation engine rather than an unconstrained language-model estimate.
4.	AI-generated findings should identify the relevant reporting period and supporting data where possible.
5.	Material recommendations should distinguish observed evidence from inference.
6.	AI must identify when insufficient data prevents a reliable conclusion.
7.	Users must be able to review and edit AI-generated report content.
8.	The platform must preserve the distinction between draft AI content and approved disclosures.
9.	Confidential organizational data must be protected when external AI services are used.
10.	Uploaded content must not automatically be treated as trusted instructions for the AI system.
11.	AI output must not be represented as professional assurance, legal advice, or a guarantee of regulatory compliance.
12.	Where AI outputs influence important decisions, define appropriate human oversight.
Specify how the application should control AI usage, prevent unauthorized data exposure, record relevant AI-generated content, and handle incorrect or unsupported outputs.
Recommend which AI capabilities belong in the MVP and which should be postponed.
Module 11: ESG Report Generation
This is a central product capability.
Design a report-generation workflow that produces a structured ESG report from the organization's collected, reviewed, and approved information.
The report should adapt to the organization's reporting objectives, selected framework, reporting period, and available data.
Specify a practical report structure that may include:
1.	Cover page.
2.	Organization profile.
3.	Reporting period and reporting boundary.
4.	Methodology and reporting basis.
5.	Executive summary.
6.	ESG governance and management approach.
7.	Environmental performance.
8.	Greenhouse gas emissions and carbon accounting methodology.
9.	Social performance.
10.	Governance performance.
11.	Material sustainability topics, where assessed.
12.	Targets and progress.
13.	Key risks and opportunities.
14.	Improvement initiatives and recommendations.
15.	Data quality and limitations.
16.	Framework mapping or disclosure index, where supported.
17.	Supporting references and relevant evidence.
18.	Appendices.
Do not assume every report must contain every section. Explain how sections change based on available information, selected reporting objectives, and applicable requirements.
The report must distinguish between:
•	Reported figures.
•	Calculated figures.
•	Estimates.
•	Qualitative disclosures.
•	AI-generated draft text.
•	User-approved statements.
•	Missing information.
•	Unsupported disclosures.
The report-generation process must not turn missing data into fabricated results.
Specify how the platform should respond when data is incomplete or a disclosure cannot be supported.
Include:
•	Draft reports.
•	Report review and approval.
•	Reporting-period locking or finalization.
•	Report versioning.
•	Regeneration after approved corrections.
•	PDF export.
•	An editable or machine-readable export where practical.
•	Report download permissions.
•	Version-specific records of the information used to generate the report.
If DOCX, spreadsheet, or other export formats are recommended, explain their value and prioritize them appropriately.
Do not describe the report as audited, independently assured, certified, or regulator-approved unless that status has been established through a relevant external process.
Module 12: Sustainability Targets and Improvement Plans
Specify how organizations can establish and monitor selected ESG improvement objectives.
Examples include:
•	Reducing electricity consumption.
•	Reducing fuel use.
•	Reducing greenhouse gas emissions.
•	Improving waste segregation.
•	Reducing water consumption.
•	Improving employee training participation.
•	Addressing identified governance gaps.
Define target name, baseline, target value, measurement unit, baseline period, target period, responsible person, supporting data, and progress status.
Explain how progress will be calculated and how the system handles missing or revised baseline data.
Do not imply that every target is science-based or aligned with a recognized target-setting framework unless the required methodology has been implemented.
Module 13: Notifications and Task Management
Consider notifications for:
•	Upcoming data submissions.
•	Overdue submissions.
•	Missing information.
•	Review requests.
•	Changes requested by reviewers.
•	Approved or rejected submissions.
•	Reporting deadlines.
•	Target milestones.
•	Completed reports.
Define notification channels, delivery rules, user preferences, and failure handling.
Treat SMS, WhatsApp, and other external communication integrations as separate capabilities requiring provider selection, cost assessment, consent considerations, and implementation planning.
Module 14: Administration and Subscription Management
Specify administrative features for managing:
•	Organizations.
•	Users and roles.
•	Access permissions.
•	Supported frameworks.
•	Emission factors.
•	Reporting templates.
•	Industry-specific questionnaires.
•	Metric definitions.
•	System configuration.
•	Subscription plans.
•	Usage limits.
•	Audit records.
•	Operational errors.
Develop an appropriate SaaS pricing structure for evaluation, potentially distinguishing between:
•	Free or trial access.
•	SME subscriptions.
•	Professional subscriptions.
•	Enterprise plans.
•	ESG consultant or multi-client plans.
Do not invent validated market prices. Recommend pricing research and indicate which prices require customer validation.
Define which commercial features belong in the MVP and which should be deferred.
________________________________________
8. USER ROLES AND PERMISSIONS
Create a role and permission matrix.
Evaluate roles such as:
•	Platform Super Administrator.
•	Organization Owner.
•	Organization Administrator.
•	ESG Manager.
•	Data Contributor.
•	Data Reviewer or Approver.
•	Read-Only Viewer.
•	External ESG Consultant.
Specify which roles can:
•	View organizational data.
•	Edit data.
•	Upload documents.
•	Assign tasks.
•	Submit records.
•	Review submissions.
•	Approve records.
•	Manage users.
•	Configure reporting settings.
•	Manage emission factors, where authorized.
•	Generate reports.
•	Approve reports.
•	Export data.
•	Manage subscriptions.
Explain how organization-level access is isolated from other organizations.
Users belonging to one customer organization must not be able to access another organization's confidential records without explicit authorization.
Include a permission model for consultants working with multiple clients.
Define how role changes, user removal, account suspension, and organization ownership transfer are handled.
________________________________________
9. END-TO-END USER WORKFLOWS
Document the most important workflows.
At a minimum, describe the following:
Workflow A: New Organization Onboarding
Registration → Verification, where required → Organization profile → ESG questionnaire → Reporting setup → Dashboard.
Workflow B: ESG Data Submission
Select reporting period → Open assigned metric → Enter or import data → Attach evidence → Validate information → Submit for review.
Workflow C: Data Review
Open submitted record → Inspect value and evidence → Approve, reject, or request changes → Record reviewer action → Update status.
Workflow D: Carbon Calculation
Identify supported emissions source → Enter activity data → Select applicable factor and methodology → Validate units and inputs → Calculate emissions → Save calculation provenance → Review result.
Workflow E: Report Generation
Select organization and reporting period → Select reporting framework or reporting objective → Check data completeness → Review supported disclosures → Generate draft → Review and correct → Approve → Export report.
Workflow F: Progress Monitoring
Define baseline → Set target → Assign responsibility → Collect updated data → Calculate progress → Review performance → Record actions.
Workflow G: ESG Consultant Workflow
Create or access an authorized client workspace → Request information → Review submissions → Identify gaps → Prepare draft report → Obtain authorized approval → Deliver the report.
For each workflow, specify:
•	User role.
•	Starting conditions.
•	Steps.
•	Application responses.
•	Validation rules.
•	Possible errors.
•	Alternative paths.
•	Completion conditions.
•	Acceptance criteria.
Identify dependencies between the workflows.
________________________________________
10. INFORMATION ARCHITECTURE AND UX REQUIREMENTS
Propose a clear information architecture for the web application.
Evaluate navigation items such as:
•	Dashboard.
•	My Organization.
•	ESG Assessment.
•	Data Collection.
•	Carbon Accounting.
•	ESG Performance.
•	Documents and Evidence.
•	Reports.
•	Targets and Action Plans.
•	Tasks and Notifications.
•	Settings.
•	Administration.
Recommend a structure that reflects the MVP rather than exposing every planned future capability.
Describe the primary screens and their purposes.
For each major screen, define:
•	Main user goal.
•	Key components.
•	Primary actions.
•	Required information.
•	Loading and empty states.
•	Error states.
•	Permission-dependent behavior.
•	Mobile responsiveness.
UX requirements:
•	Use clear language suitable for users who are not ESG specialists.
•	Explain technical concepts in accessible language.
•	Display units next to numerical values.
•	Clearly distinguish missing data from zero values.
•	Show the reporting period and relevant methodology for important metrics.
•	Provide contextual help and understandable error messages.
•	Allow users to save drafts where appropriate.
•	Make incomplete tasks visible.
•	Minimize unnecessary data entry.
•	Support accessible navigation and readable visualizations.
•	Avoid presenting unsupported scores or misleading performance comparisons.
•	Design for modern desktop and mobile browsers.
Do not assume the complete visual design is part of the PRD. Define functional UX requirements and provide suggested screen descriptions that can later be translated into wireframes.
________________________________________
11. DATA MODEL AND DATABASE REQUIREMENTS
Recommend a logical data model that can support the MVP and future expansion.
Identify the principal entities, their relationships, required fields, and important constraints.
Evaluate entities including:
•	Users.
•	Organizations.
•	Organization Memberships.
•	Roles and Permissions.
•	Organization Sites.
•	Reporting Periods.
•	ESG Assessments.
•	ESG Metrics.
•	Metric Definitions.
•	Metric Submissions.
•	Data Sources.
•	Evidence Documents.
•	Review Records.
•	Emission Factors.
•	Emissions Calculations.
•	Reporting Frameworks.
•	Framework Disclosures.
•	Metric-to-Framework Mappings.
•	ESG Reports.
•	Report Versions.
•	AI-Generated Drafts.
•	Sustainability Targets.
•	Improvement Actions.
•	Notifications.
•	Subscription Records.
•	Audit Events.
Do not assume that every candidate entity must be implemented in the MVP.
For every selected entity, specify:
•	Purpose.
•	Primary identifier.
•	Important fields.
•	Relationships.
•	Required fields.
•	Uniqueness constraints.
•	Validation rules.
•	Lifecycle or status fields.
Explain how the model supports:
1.	Multiple organizations.
2.	Multiple reporting periods.
3.	Repeated submissions for the same metric.
4.	Evidence linked to relevant records.
5.	Versioned emission factors.
6.	Reproducible emissions calculations.
7.	Report versioning.
8.	Data correction and audit trails.
9.	Framework mappings.
10.	Future expansion into additional countries.
Use a relational data model unless a clear reason supports another approach.
Recommend a suitable database architecture, but distinguish logical product requirements from technology implementation choices.
Include a text-based entity relationship summary or Mermaid ER diagram if useful.
________________________________________
12. TECHNICAL AND SYSTEM REQUIREMENTS
Recommend a practical architecture for building a secure, maintainable, commercially viable SaaS product.
Evaluate appropriate technology choices based on:
•	Development complexity.
•	Cost of operation.
•	Security.
•	Scalability.
•	Data integrity.
•	Ease of maintenance.
•	AI integration.
•	Document management.
•	Reporting and export capabilities.
•	Availability of suitable hosting services.
•	Suitability for an initial founder-led build.
The architecture discussion should consider:
•	Frontend application.
•	Backend or application services.
•	Relational database.
•	Authentication provider or authentication service.
•	File storage.
•	API layer.
•	Background jobs.
•	Carbon calculation service.
•	AI integration layer.
•	Report generation service.
•	Email notifications.
•	Logging and monitoring.
•	Backup and recovery.
Do not assume a particular technology stack has already been selected.
Compare realistic alternatives where a decision could materially affect cost or implementation complexity.
Recommend a default stack and explain the trade-offs.
If using a low-code, no-code, or AI-assisted development approach, explain where such tools are appropriate and where custom logic is necessary.
In particular, do not outsource critical carbon calculations, authorization, or data-integrity rules to unconstrained AI-generated logic.
Identify external services that require separate credentials, paid accounts, usage limits, or contractual review.
________________________________________
13. NON-FUNCTIONAL REQUIREMENTS
Define measurable non-functional requirements wherever possible.
Cover the following.
Security
•	Secure authentication.
•	Role-based access control.
•	Organization-level data isolation.
•	Secure document storage.
•	Protection of credentials and API keys.
•	Secure communications.
•	Protection against common web application vulnerabilities.
•	Appropriate handling of sensitive employee information.
Privacy
•	Data minimization.
•	Purpose limitation.
•	Appropriate user access.
•	Data retention and deletion policies.
•	Confidentiality of organizational information.
•	Secure use of external AI services.
•	Appropriate treatment of employee and other personal data.
Assess relevant Ghanaian data protection obligations using authoritative sources. Identify legal questions that require qualified professional review.
Reliability
•	Handling of failed operations.
•	Recovery from interrupted submissions.
•	Transactional consistency where required.
•	Appropriate backup and recovery procedures.
•	Monitoring of critical services.
Performance
Propose realistic performance targets for:
•	Page loading.
•	Dashboard rendering.
•	Data validation.
•	File uploads.
•	Emissions calculations.
•	Report generation.
State the assumptions behind performance targets and define how they should be tested.
Scalability
Define how the architecture can support increasing numbers of organizations, users, records, emissions calculations, and generated reports.
Maintainability
Require modular components, consistent error handling, documented business rules, automated tests, and manageable configuration.
Accessibility
Recommend an appropriate accessibility target, such as WCAG 2.2 Level AA, and explain how it should be validated.
Auditability
Ensure that important actions can be traced to the relevant user, record, time, and action.
Do not present proposed performance or availability targets as proven capabilities.
________________________________________
14. GHANA-SPECIFIC REQUIREMENTS
The platform must be designed with Ghanaian operating conditions and customer needs in mind.
Evaluate the following requirements:
•	Ghanaian organization and contact information.
•	Ghana cedi (GHS) as an available currency.
•	Metric units.
•	Ghana-specific organizational and industry classification options.
•	Reporting periods aligned with customer financial years.
•	Local electricity and fuel data collection.
•	Ghana-relevant environmental and operational information.
•	Local supplier and value-chain information where available.
•	Accessibility across varying levels of digital literacy.
•	Compatibility with commonly used office documents and spreadsheets.
•	Affordable implementation and operating costs.
•	Suitable options for businesses with limited sustainability expertise.
Evaluate relevant Ghanaian ESG, environmental, company-reporting, labor, data protection, and carbon-related requirements using authoritative and current sources when producing the final PRD.
For each legal or regulatory claim, identify the source, date or applicable version, affected organizations, and how the requirement relates to the product.
Distinguish between:
1.	Confirmed legal obligations.
2.	Applicable sector-specific obligations.
3.	Voluntary frameworks.
4.	Investor or supply-chain reporting expectations.
5.	Good-practice recommendations.
6.	Matters requiring legal or regulatory confirmation.
Do not assume that every Ghanaian business is subject to the same reporting requirements.
Do not assume that a platform-generated report satisfies every legal, regulatory, investor, lender, or customer requirement.
If the final PRD is generated in an environment without web research, identify these matters for verification rather than inventing citations or presenting uncertain claims as facts.
________________________________________
15. INTEGRATION REQUIREMENTS
Identify integrations that could improve the product.
Potential integration categories include:
•	Email delivery.
•	Spreadsheet import and export.
•	Document storage.
•	AI language models.
•	Accounting and financial systems.
•	Utility or energy data.
•	Business management systems.
•	Visualization and analytics tools.
•	Payment providers.
•	External reporting systems.
For each proposed integration, explain:
•	Business value.
•	Required data.
•	Authentication requirements.
•	Data flow.
•	Security implications.
•	Approximate implementation complexity.
•	External dependencies.
•	Operating cost considerations.
•	MVP priority.
Distinguish required integrations from optional future integrations.
Do not assume that a Ghanaian utility, government agency, bank, accounting provider, or reporting framework offers a usable API without verification.
Where no reliable integration exists, propose practical manual import or upload alternatives.
________________________________________
16. REPORTING, EXPORTS, AND INTEROPERABILITY
Specify how users can access and export their organizational data.
Evaluate support for:
•	PDF reports.
•	CSV data exports.
•	Spreadsheet templates.
•	Structured data exports.
•	Supporting document downloads, subject to permissions.
•	Framework mapping tables.
•	Carbon calculation summaries.
Define how exported data preserves metric names, reporting periods, units, calculation methods, and provenance information.
Explain how the platform can avoid locking customers into an inaccessible proprietary data format.
Define appropriate access controls, export limits, and logging requirements.
________________________________________
17. BUSINESS MODEL AND COMMERCIAL REQUIREMENTS
Describe how the platform can become a sustainable SaaS business.
Evaluate the needs of:
•	Individual SMEs.
•	Larger organizations.
•	ESG consulting firms.
•	Organizations managing multiple branches or facilities.
Recommend subscription packaging based on actual differences in product value and usage.
Potential pricing dimensions include:
•	Number of organizations.
•	Number of users.
•	Number of reporting periods.
•	Number of sites.
•	Available ESG modules.
•	AI usage.
•	Report generation.
•	Storage requirements.
•	Consultant or multi-client access.
Avoid arbitrary paywalls that prevent users from accessing essential functions without a clear business rationale.
Identify the most important customer value propositions and the assumptions requiring validation.
Include a plan for validating the product with prospective Ghanaian customers before significant investment in advanced features.
________________________________________
18. ANALYTICS AND PRODUCT SUCCESS METRICS
Define measurable indicators that can determine whether the product is useful and commercially viable.
Evaluate:
Activation
•	Organizations completing onboarding.
•	Time required to reach the first useful dashboard.
•	Percentage of organizations submitting their first dataset.
Engagement
•	Active organizations.
•	Repeat data submissions.
•	Reporting periods completed.
•	Relevant features used.
Reporting performance
•	Reports generated.
•	Time required to prepare a report.
•	Percentage of report disclosures supported by approved data.
•	Number of unresolved data-quality issues before report finalization.
Carbon accounting
•	Supported emissions sources recorded.
•	Percentage of calculated emissions linked to identifiable factors and activity data.
•	Number of emissions calculations requiring corrections.
•	Completeness of available Scope 1, Scope 2, and supported Scope 3 data.
Customer value
•	Time saved on ESG data collection.
•	Reduction in repetitive manual reporting tasks.
•	Customer satisfaction.
•	Customer retention.
•	Willingness to pay.
Commercial performance
•	Trial-to-paid conversion.
•	Customer acquisition cost, where measurable.
•	Recurring revenue.
•	Subscription cancellation rate.
For each metric, define its calculation, measurement frequency, source, and limitations.
Distinguish between platform engagement and actual environmental or social impact.
Do not claim that the platform has reduced a customer's emissions simply because the customer has reported or calculated them.
________________________________________
19. EDGE CASES AND FAILURE SCENARIOS
Identify important scenarios the product must handle.
Consider:
•	A user submits incomplete information.
•	A user uploads the wrong document.
•	A spreadsheet contains incorrect units.
•	A metric is entered twice.
•	A submission covers an incorrect reporting period.
•	A customer changes its organizational boundary.
•	An emission factor is updated after a report is finalized.
•	A report contains unsupported disclosures.
•	A customer has no available Scope 3 information.
•	Two users edit the same record.
•	A reviewer rejects a submission.
•	A user loses access to an organization.
•	A customer cancels a subscription.
•	A generated report fails to export.
•	An AI service becomes unavailable.
•	A document cannot be parsed.
•	A source of activity data is later found to be unreliable.
•	A finalized reporting result must be corrected.
For each material scenario, specify expected system behavior, data protection considerations, user communication, and recovery procedures.
________________________________________
20. TESTING AND ACCEPTANCE CRITERIA
Define testable acceptance criteria for every high-priority functional requirement.
Use a structured format.
Requirement ID: FR-CARBON-001
Requirement: The system shall calculate emissions from supported activity data and a selected applicable emission factor.
Given: An authorized user has entered valid activity data and selected an applicable, versioned emission factor.
When: The user requests an emissions calculation.
Then:
•	The system validates the activity-data unit.
•	The system confirms that the emission factor has compatible units.
•	The system performs the calculation using the specified methodology.
•	The system stores the calculated result and unit.
•	The system records the factor reference and calculation version.
•	The result is linked to its reporting period and source activity.
•	The system displays any applicable estimation or data-quality limitations.
This example is illustrative. Adapt the final criteria to the actual approved calculation methodology.
Create acceptance criteria for:
•	Authentication.
•	Organization creation.
•	Data submission.
•	Document uploads.
•	Data validation.
•	Review and approval.
•	Carbon calculations.
•	Dashboard values.
•	AI-generated text.
•	Report generation.
•	Access control.
•	Data exports.
•	Audit trails.
Specify unit, integration, end-to-end, security, and user-acceptance testing requirements.
Where exact numerical thresholds are unknown, recommend a target and label it as a proposal requiring validation.
________________________________________
21. IMPLEMENTATION ROADMAP
Divide implementation into practical phases.
Phase 0: Discovery and Validation
•	Customer interviews.
•	Requirements validation.
•	Regulatory and framework research.
•	Competitor and market research.
•	Initial data dictionary.
•	UX sketches.
•	Technical feasibility review.
Phase 1: MVP Foundation
•	Authentication.
•	Organization management.
•	Core ESG data collection.
•	Supporting document management.
•	Initial data validation.
•	Basic ESG dashboard.
•	Limited and properly defined carbon calculations.
•	Basic ESG report generation.
Phase 2: MVP Improvement
•	Enhanced review workflows.
•	Additional relevant ESG metrics.
•	Improved data quality controls.
•	AI-assisted report drafting.
•	Targets and action plans.
•	More flexible reporting options.
Phase 3: Commercial Expansion
•	Subscription management.
•	Multi-site functionality.
•	Consultant workspaces.
•	Additional reporting framework mappings.
•	Advanced analytics.
•	Broader Scope 3 support.
•	Additional integrations.
Phase 4: Regional Expansion
•	Additional country configurations.
•	Country-specific factors and datasets.
•	More reporting frameworks.
•	Localization.
•	Regional market validation.
Revise this sequence where justified by dependencies or customer evidence.
For each phase, identify:
•	Objectives.
•	Features.
•	Dependencies.
•	Deliverables.
•	Acceptance criteria.
•	Major risks.
•	Exit conditions.
Do not invent precise completion dates without information about the available team, budget, and development capacity.
________________________________________
22. RISKS, ASSUMPTIONS, AND OPEN QUESTIONS
Create an assumption and risk register.
Evaluate risks relating to:
•	Limited availability of reliable ESG data.
•	Incorrect emission factors.
•	Unsupported reporting claims.
•	Weak customer data quality.
•	Regulatory uncertainty.
•	Privacy and security.
•	AI hallucinations.
•	Expensive third-party services.
•	Overly complex onboarding.
•	Low customer adoption.
•	Scope creep.
•	Poor data model design.
•	Excessive dependence on one AI provider.
•	Difficulty validating the commercial model.
•	Lack of customer willingness to pay.
For each significant risk, specify:
•	Description.
•	Likelihood.
•	Potential impact.
•	Mitigation.
•	Owner or responsible function.
•	Evidence needed to resolve the risk.
Maintain separate lists for:
1.	Product assumptions.
2.	Technical assumptions.
3.	Market assumptions.
4.	Regulatory assumptions.
5.	Unresolved decisions.
Rank open questions by their potential impact on the MVP architecture, budget, customer value, and compliance risk.
________________________________________
23. REQUIRED PRD OUTPUT STRUCTURE
Produce the completed PRD using the following structure.
1.	Document Control and Version History
2.	Executive Summary
3.	Product Vision and Objectives
4.	Problem Statement
5.	Market Context and Target Customers
6.	User Personas
7.	User Needs and Jobs to Be Done
8.	Product Scope
9.	MVP Definition and Prioritization
10.	Out-of-Scope Features
11.	Functional Requirements
12.	ESG Data Dictionary
13.	Carbon Accounting Requirements
14.	ESG Framework and Disclosure Mapping
15.	AI Requirements and Guardrails
16.	End-to-End User Workflows
17.	User Roles and Permission Matrix
18.	Information Architecture
19.	Screen and UX Requirements
20.	Logical Data Model
21.	Technical Architecture Recommendations
22.	Non-Functional Requirements
23.	Ghana-Specific Requirements
24.	Security and Privacy Requirements
25.	Integrations
26.	Reporting and Export Requirements
27.	Business Model and Commercial Assumptions
28.	Product Analytics and Success Metrics
29.	Edge Cases and Error Handling
30.	Testing Strategy
31.	Acceptance Criteria
32.	Implementation Roadmap
33.	Risk and Assumption Register
34.	Open Questions and Decisions
35.	Definition of Done
36.	Appendices and Reference Sources
Use tables where they improve clarity, particularly for functional requirements, prioritization, user permissions, data fields, risks, and acceptance criteria.
Use unique identifiers for requirements, metrics, user stories, and test cases.
Ensure that requirements are sufficiently specific to be converted into development tasks.
Avoid unnecessary repetition.
________________________________________
24. ADDITIONAL REQUIRED DELIVERABLES
At the end of the PRD, produce the following companion deliverables.
A. MVP Feature Matrix
Create a table containing:
•	Feature ID.
•	Feature name.
•	User problem addressed.
•	Target user.
•	Priority.
•	Dependencies.
•	Complexity estimate.
•	Acceptance criteria.
•	Reason for inclusion or exclusion.
Use relative complexity estimates such as Low, Medium, and High rather than unsupported development-hour estimates.
B. Development-Ready User Stories
Write user stories using this format:
"As a [user role], I want to [perform an action], so that [business outcome]."
Each story must include its own acceptance criteria.
Prioritize the stories required to build the MVP.
C. Initial ESG Data Dictionary
Provide a structured table of proposed MVP metrics.
Include:
•	Metric ID.
•	Metric name.
•	ESG category.
•	Description.
•	Unit.
•	Reporting frequency.
•	Required or optional status.
•	Data collection method.
•	Supporting evidence.
•	Validation rules.
•	Applicable framework mapping, if verified.
•	Calculation method, if applicable.
•	Known limitations.
Clearly distinguish calculated metrics from directly reported metrics.
Do not treat the illustrative metric list in this prompt as a complete universal reporting requirement.
D. Core Database Entities
Identify the entities required for the MVP and explain their relationships.
Distinguish between entities required immediately and entities that can be introduced later.
E. Critical User Journeys
Identify the five most important user journeys for the initial release.
Explain how each journey delivers the product's core value.
F. Initial Test Plan
Provide test cases for the highest-risk requirements, especially:
•	Organization-level data isolation.
•	Data validation.
•	Carbon calculation accuracy.
•	Emission-factor versioning.
•	Report accuracy.
•	AI-generated content review.
•	Audit trails.
•	Unauthorized access prevention.
G. First Development Backlog
Convert the MVP into a logical sequence of epics and development tasks.
Include:
•	Epic ID.
•	Epic name.
•	User story.
•	Task description.
•	Dependencies.
•	Priority.
•	Definition of done.
Order the backlog according to dependencies, starting with the foundation required for the first usable product.
Do not generate application code or implementation files at this stage.
________________________________________
25. QUALITY CONTROL REQUIREMENTS
Before finalizing the PRD, review it against the following standards.
Product clarity
•	Is the target customer clearly defined?
•	Is the core problem specific?
•	Is the product's value proposition understandable?
•	Is the MVP small enough to build and validate?
•	Are future features separated from launch requirements?
Functional completeness
•	Are the principal user journeys covered?
•	Are data submission, validation, review, and approval rules clear?
•	Can a developer identify the expected behavior of each major feature?
•	Are edge cases and error states addressed?
ESG and carbon accounting integrity
•	Are activity data and emissions calculations distinguished?
•	Are calculation assumptions and emission factors traceable?
•	Are reporting standards and legal obligations correctly distinguished?
•	Are data-quality limitations visible?
•	Are unsupported disclosures prevented or flagged?
•	Are auditability and report versioning adequately specified?
AI reliability
•	Can AI-generated content be traced to source information?
•	Are unsupported claims handled appropriately?
•	Can users review AI-generated content?
•	Are privacy and security risks addressed?
•	Are deterministic calculations separated from AI interpretation?
Technical readiness
•	Is the logical data model sufficient for the MVP?
•	Are organization isolation and role permissions addressed?
•	Are integration dependencies identified?
•	Are the technical recommendations consistent with the stated product requirements?
Commercial readiness
•	Is the target market clear?
•	Is the product's primary customer value identifiable?
•	Are key market assumptions listed for validation?
•	Are operating costs and third-party dependencies acknowledged?
Implementation readiness
•	Are requirements prioritized?
•	Are acceptance criteria testable?
•	Are dependencies explicit?
•	Is the development roadmap realistic in scope?
•	Can the PRD be converted into an engineering backlog?
Include a final PRD quality review highlighting unresolved decisions, missing information, and high-risk assumptions.
Do not claim that the PRD is ready for production development if important architectural, data-integrity, regulatory, or security decisions remain unresolved.
________________________________________
26. FINAL INSTRUCTIONS
Produce a comprehensive, structured, implementation-oriented PRD.
Use professional but accessible language.
Be precise about what the system must do rather than describing only what the product should ideally achieve.
Distinguish business requirements, functional requirements, technical recommendations, and implementation decisions.
Use current authoritative sources to verify material claims about reporting frameworks, Ghanaian regulations, and relevant carbon accounting methodologies whenever web research is available.
Provide references for claims that depend on external facts. Do not invent sources, citations, legal requirements, APIs, datasets, or emission factors.
When a decision depends on incomplete information, state the assumption, explain its implications, and recommend the next validation step.
Prioritize correctness, data integrity, usability, security, affordability, and a realistic MVP over unnecessary feature breadth.
The final document should be suitable for use by a founder and a development team building the first version of Tekstain Nexus.
Start by defining the product scope and assumptions. Then produce the complete PRD in the required structure.


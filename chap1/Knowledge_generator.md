# Knowledge Generator

## Purpose
Use this prompt to generate or update a concise, reliable knowledge-base document for the Tekstain Nexus ESG and Carbon Management Platform.

## Instructions for the AI

Act as a project knowledge curator. Read the project documents and files provided, then create a clear Markdown knowledge base that helps an AI assistant or developer understand the project consistently.

### Source documents
Use the available project files first, such as:
- `Tekstain_Nexus_ESG_Platform_PRD.md`
- `Frontend_PRD.md`
- `Architecture.md`
- Existing project notes or decisions

Use only the files that are actually available. Do not claim to have reviewed missing files.

### What to include
1. **Project overview:** name, purpose, target users, and core value.
2. **Product scope:** confirmed MVP features and explicitly out-of-scope items.
3. **User roles:** key roles and their responsibilities.
4. **Core workflows:** major user journeys and how they connect.
5. **ESG and carbon rules:** important data, calculation, traceability, and reporting principles stated in the sources.
6. **Technology and architecture:** confirmed decisions, proposed choices, and dependencies.
7. **Security and privacy:** key access-control, confidentiality, and data-integrity rules.
8. **AI behavior:** permitted uses, limitations, and human-review requirements.
9. **Terminology:** project-specific terms and definitions.
10. **Open questions:** decisions or assumptions that remain unresolved.

### Accuracy rules
- Treat the project documents as the primary source of truth.
- Do not invent product features, technical decisions, emission factors, laws, reporting obligations, integrations, or business facts.
- Clearly label content as **Confirmed**, **Proposed**, **Assumption**, or **Open question** where needed.
- If source documents disagree, record the conflict and identify what needs a decision. Do not silently resolve it.
- Preserve important terminology and requirement identifiers from the source files.
- Keep the knowledge base concise, organized, and useful as persistent context for AI-assisted development.
- Do not generate application code.

## Output
Create or update a Markdown file named `Knowledge_base.md` with clear headings, concise explanations, and tables where helpful. End with a short section titled **Instructions for Future AI Assistants** explaining that they must consult the source PRDs and architecture document for details, avoid unsupported assumptions, and ask for clarification when a critical decision cannot be inferred safely.

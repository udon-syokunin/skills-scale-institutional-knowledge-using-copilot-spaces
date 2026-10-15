# OctoAcme — Roles and Personas

This document describes key personas used across OctoAcme program management processes. Each persona includes a short purpose statement, responsibilities, decision authority, escalation path, and primary peers/stakeholders. These additions are intended to reduce ambiguity in handoffs and improve program delivery.

---

## Delivery Coordinator
Purpose: Coordinate schedules and program-level logistics to keep multiple teams aligned and unblocked.

Responsibilities:
- Maintain program-level trackers (milestones, dependencies, action items).
- Coordinate meeting logistics and agendas (planning, stand-ups, release planning).
- Track cross-team dependencies and follow up on outstanding actions.
- Surface schedule conflicts and propose mitigation approaches.
- Keep documentation of decisions and agreed-upon changes to timelines.

Decision authority:
- Operational scheduling decisions (meeting times, cadence).
- Minor sequencing adjustments to non-critical tasks in coordination with PM.

Escalation path:
- Escalate unresolved dependencies or repeated blockers to the Project Manager -> Program Sponsor.

Primary peers/stakeholders:
- Project Manager, Product Owner, Engineering Leads, Delivery teams.

Interactions with existing roles:
- Works daily with the Project Manager to align timelines and reporting.
- Syncs with Product Owner on scope-driven schedule changes.
- Coordinates with Engineering Lead to understand technical constraints that affect timing.

---

## Technical Architect
Purpose: Define and guide solution architecture and ensure consistency across teams.

Responsibilities:
- Establish and communicate architectural principles and patterns.
- Review designs and major technical decisions for architectural fit.
- Define non-functional requirements (security, performance, scalability).
- Provide implementation guidance and approve major changes to architecture.
- Maintain architecture artifacts and reference diagrams.

Decision authority:
- Approve architecture-level changes and accept/reject proposed deviations that affect cross-team architecture.

Escalation path:
- Escalate unresolved architecture disputes to Engineering Lead -> Program Architect Committee (if applicable).

Primary peers/stakeholders:
- Engineering Leads, Release/DevOps Manager, QA Lead, Product Owner.

Interactions with existing roles:
- Works with Engineering Leads to ensure teams implement agreed architecture.
- Provides guidance to Release/DevOps Manager for infrastructure and deployment considerations.
- Collaborates with Product Owner to ensure features align with architectural constraints.

---

## Release / DevOps Manager
Purpose: Own CI/CD, release readiness, and safe deployments into environments.

Responsibilities:
- Manage CI/CD pipelines, release gating and deployment runbooks.
- Define and maintain release checklists and rollback plans.
- Coordinate release windows and communicate release status.
- Monitor environment stability and lead post-deployment validation.
- Maintain environment access, secrets handling, and deployment automation.

Decision authority:
- Gate or approve production deployments on readiness criteria.
- Trigger rollback when release health metrics breach thresholds.

Escalation path:
- Escalate unresolved production issues to Engineering Lead -> Program Manager -> Incident Commander.

Primary peers/stakeholders:
- Technical Architect, QA Lead, Site Reliability teams, Engineering Leads.

Interactions with existing roles:
- Coordinates with Technical Architect on infrastructure changes.
- Works with QA Lead to ensure release criteria and test coverage are met.
- Provides deployment status updates to Project Manager and Product Owner.

---

## QA / Testing Lead
Purpose: Define and drive testing strategy and ensure product quality before release.

Responsibilities:
- Define test strategy (automation, manual, performance, regression).
- Maintain test plans, acceptance criteria, and quality metrics.
- Coordinate test execution and triage defects with engineering.
- Validate release candidates against acceptance criteria.
- Drive improvements in test coverage and testing practices.

Decision authority:
- Approve or reject a release candidate based on test results and acceptance criteria.

Escalation path:
- Escalate critical quality risks to Product Owner -> Project Manager for scope or schedule decisions.

Primary peers/stakeholders:
- Product Owner, Engineering Leads, Release/DevOps Manager.

Interactions with existing roles:
- Works with Product Owner to translate acceptance criteria into test cases.
- Coordinates with Engineering Leads and Release/DevOps to schedule testing and pre-release validations.

---

## Business Analyst / Requirements Owner
Purpose: Capture, clarify, and maintain requirements so that delivery matches stakeholder needs.

Responsibilities:
- Elicit and document user requirements and acceptance criteria.
- Maintain and prioritize user stories or requirements artifacts.
- Clarify requirements during refinement and development.
- Validate delivered functionality against stakeholder expectations.
- Maintain traceability between requirements, design, and tests.

Decision authority:
- Clarify requirements and approve acceptance criteria content; not a final prioritization authority.

Escalation path:
- Escalate scope conflicts to Product Owner -> Project Manager.

Primary peers/stakeholders:
- Product Owner, UX Lead, Project Manager, QA Lead.

Interactions with existing roles:
- Works closely with Product Owner to shape backlog and user stories.
- Collaborates with QA Lead to ensure test cases cover requirements.
- Coordinates with Engineering Lead to ensure feasibility and highlight constraints.

---

## Documentation Owner
Purpose: Ensure process documents, runbooks, and release notes are accurate, discoverable, and up to date.

Responsibilities:
- Maintain program process docs under docs/, runbooks, and release notes.
- Coordinate updates when processes or runbooks change.
- Ensure documentation is accessible (discoverability, linking).
- Lead documentation reviews and periodic audits.
- Capture known-bugs and post-release notes.

Decision authority:
- Accept documentation edits and decide documentation structure/organization for discoverability.

Escalation path:
- Escalate conflicting or high-impact documentation gaps to Delivery Coordinator -> Project Manager.

Primary peers/stakeholders:
- Delivery Coordinator, QA Lead, Product Owner, Release/DevOps Manager.

Interactions with existing roles:
- Works with Delivery Coordinator to surface docs needing updates after releases.
- Coordinates with QA Lead and DevOps to keep runbooks and incident steps current.

---

## Risk & Compliance Owner
Purpose: Track program risks and ensure compliance requirements are addressed and auditable.

Responsibilities:
- Maintain a program-level risk register and mitigation plans.
- Coordinate compliance checks and required audits.
- Track security, privacy, and regulatory obligations as they impact delivery.
- Score and prioritize risks; propose risk treatment plans.
- Report risk status to Program Sponsor and governance bodies.

Decision authority:
- Recommend risk acceptance or mitigation approaches; formal acceptance may require Program Sponsor sign-off.

Escalation path:
- For high or unmanaged risks, escalate to Program Sponsor -> Steering Committee.

Primary peers/stakeholders:
- Project Manager, Technical Architect, Security/Compliance teams, Program Sponsor.

Interactions with existing roles:
- Works with Project Manager to track mitigation tasks and dependencies.
- Coordinates with Technical Architect and Release/DevOps Manager on compliance-related controls.

---

## Example RACI Matrix (high-level)

Key:
- R = Responsible (does the work)
- A = Accountable (final decision)
- C = Consulted
- I = Informed

| Activity / Persona                      | Delivery Coordinator | Technical Architect | Release/DevOps | QA Lead | BA / Req Owner | Doc Owner | Risk & Compliance | Project Manager | Product Owner | Engineering Lead |
|-----------------------------------------|----------------------|---------------------|----------------|---------|----------------|-----------|-------------------|-----------------|---------------|------------------|
| Planning (scope & timeline)             | R                    | C                   | I              | I       | C              | I         | C                 | A               | C             | C                |
| Design review / architecture decisions  | I                    | A/R                 | C              | I       | C              | I         | C                 | I               | C             | R                |
| Release planning & gating               | C                    | C                   | A/R            | C       | I              | I         | C                 | R               | I             | C                |
| Incident triage / response              | I                    | C                   | R              | C       | I              | I         | C                 | I               | I             | A/R              |
| Retrospectives & continuous improvement | R                    | C                   | C              | R       | C              | C         | I                 | A               | C             | C                |

Notes:
- RACI assignments are templates; adapt as needed per release or program.
- "Project Manager" typically remains accountable for planning and delivery across activities; other personas may be accountable for specialized domains (e.g., Technical Architect for architecture).

---

## How these personas interact with existing roles
- Project Manager: Central integrator for timelines and reporting; escalates to sponsor and coordinates cross-persona action items.
- Product Owner: Owns backlog prioritization and acceptance criteria; collaborates with BA, QA, and Delivery Coordinator to align scope and releases.
- Engineering Lead: Implements technical work, partners with Technical Architect and Release/DevOps for design and deployment readiness.

---

## Adoption guidance
- Start by trialing these personas on one program increment; confirm responsibilities and adjust RACI.
- Keep persona definitions short and actionable—3–6 responsibilities.
- Record any deviations in the relevant program's decision log.

# 07. Glossary and Terminology

## Purpose of This Document

This glossary defines key terms used throughout the ISBUSHKA project.
Its purpose is to ensure a shared understanding between business stakeholders,
analysts, and future system contributors.

All terms defined in this document must be used consistently across:
- discovery documentation
- requirements
- process models
- data models
- reports

---

## Terminology Principles

- One term — one meaning
- Business-friendly wording is preferred
- Technical terms are used only when necessary
- In case of ambiguity, the definition in this document prevails

---

## Glossary

| Term | Definition | Synonyms / Related Terms | Notes |
|----|------------|--------------------------|------|
| ISBUSHKA | The name of the salon management system and the project itself | System, Application | Used as product name |
| Salon | A service business providing beauty-related services | Service business | Single-salon context |
| Client | A person receiving services from the salon | Customer, Visitor | Stores personal and contact data |
| Master | A staff member who provides services to clients | Specialist, Employee | Performs appointments |
| Administrator | A user responsible for managing daily operations | Admin | Handles scheduling and finances |
| Owner | Business owner with full visibility and control | Business owner | Strategic decisions |
| Service | A type of activity provided to a client | Procedure | Has duration and price |
| Appointment | A scheduled service for a specific client, time, and master | Booking, Visit | **Primary term** |
| Visit | A completed appointment | Completed appointment | Not used for scheduling |
| Scheduling | Process of creating and managing appointments | Booking | Part of operations |
| Appointment Slot | A specific time interval reserved for a service | Time slot | Derived from duration |
| Duration | Length of time required to perform a service | Service time | Used for scheduling |
| Calendar | A view of appointments over time | Schedule | UI representation |
| Financial Operation | A record of income or expense | Transaction | Atomic financial event |
| Income | Money received from providing services | Revenue | Positive financial operation |
| Expense | Money spent on business needs | Cost | Negative financial operation |
| Balance | Difference between total income and expenses | Net result | Calculated value |
| Daily Summary | Aggregated financial result for a day | Daily report | Key control tool |
| Monthly Summary | Aggregated financial result for a month | Monthly report | Used for analytics |
| Report | Structured representation of business data | Analytics | Read-only |
| KPI | Key performance indicator | Metric | Business-level measurement |
| Business Objective | A measurable business goal | Objective | Defined in discovery |
| Scope | Defined boundaries of system functionality | Project scope | Controls expectations |
| In Scope | Functionality included in the project | — | Must be delivered |
| Out of Scope | Functionality explicitly excluded | — | Not planned |
| Requirement | A statement describing system behavior or constraint | — | Functional or non-functional |
| Functional Requirement | A requirement describing what the system does | FR | Feature behavior |
| Non-Functional Requirement | A requirement describing how the system operates | NFR | Quality attributes |
| Business Rule | A constraint or logic governing system behavior | Rule | Enforced consistently |
| Validation Rule | A rule preventing invalid data input | Input validation | Improves data quality |
| Data Accuracy | Degree to which data correctly represents reality | Data quality | Business-critical |
| Single Source of Truth | Authoritative data source | SSOT | Avoids duplication |
| Manual Effort | Human time spent on routine operations | — | Target for reduction |
| Automation | System-assisted execution of tasks | — | Limited by no-code |
| No-Code Platform | Platform enabling system creation without coding | AppSheet | Technology constraint |
| Data Model | Logical structure of data entities and relationships | ERD | System design |
| Entity | A business object represented in data | Table | E.g. Client, Appointment |
| Attribute | A property of an entity | Column | E.g. date, amount |
| Identifier | Unique value identifying an entity | ID | Primary key |
| Calculated Field | Value derived from other data | Virtual column | Read-only |
| Audit Trail | Record of data changes | History | Improves traceability |
| Access Control | Rules defining who can see or modify data | Permissions | Security-related |
| Role | A set of permissions assigned to a user | User role | Admin, Master, Owner |
| Scalability | Ability to support growth without redesign | — | Structural concern |
| Discovery Phase | Initial analysis phase of the project | Discovery | Before design |
| As-Is | Current state of processes or system | Current state | Baseline |
| To-Be | Target future state | Desired state | After implementation |
| Epic | High-level functional area | Feature group | Backlog level |
| Feature | A specific system capability | — | Implements objectives |
| Backlog | Prioritized list of work items | — | Managed iteratively |
| Prioritization | Process of ordering work by importance | — | Value-driven |
| MVP | Minimum viable product | — | First usable version |
| Change Request | Formal request to modify scope or requirements | CR | Controlled process |

---

## Terminology Decisions

### Appointment vs Visit
- **Appointment** — used for scheduling and planning
- **Visit** — used only for completed appointments

This distinction helps separate planning and execution stages.

---

## Governance

- New terms must be added to this glossary
- Changes to existing definitions require review
- Glossary updates are versioned with the project documentation


# 05. Assumptions, Constraints, and Dependencies

## Purpose of This Document

This document captures key assumptions, constraints, and dependencies
identified during the discovery phase of the ISBUSHKA project.

Its purpose is to:
- make implicit expectations explicit
- define clear project boundaries
- identify risks related to uncertainty and external factors
- provide context for scope and solution decisions

---

## Definitions

- **Assumption** — a statement believed to be true but not yet fully validated
- **Constraint** — a fixed limitation that restricts possible solutions
- **Dependency** — reliance on an external system, tool, process, or decision

---

## Assumptions

The following assumptions are considered valid at the discovery stage.
They must be reviewed and validated as the project evolves.

### Assumptions Table

| ID | Assumption | Rationale | Validation Approach | Risk Level |
|----|------------|-----------|---------------------|------------|
| A-01 | The salon operates as a single business unit | Current operational model | Confirm with business owner | Low |
| A-02 | The number of staff (masters) is relatively small | Current team size | Review staffing plans | Low |
| A-03 | Users are non-technical | Typical salon environment | User interviews / observation | Medium |
| A-04 | Operational simplicity is more important than advanced features | Business priorities | Validate during scope approval | Medium |
| A-05 | Financial reporting requirements are basic | Early-stage analytics needs | Review reporting expectations | Medium |
| A-06 | Internet access is available during operations | Required for system usage | Operational confirmation | Low |
| A-07 | Data accuracy is more valuable than data volume | Business control focus | Align with business objectives | Low |

---

## Constraints

Constraints define non-negotiable boundaries that shape the solution design.

### Constraints Table

| ID | Constraint | Description | Impact on Solution |
|----|------------|-------------|--------------------|
| C-01 | No-code platform | The system is built using a no-code tool | Limits customization and logic complexity |
| C-02 | Data storage via Google Sheets | Data is stored in spreadsheet-based storage | Performance and scalability limits |
| C-03 | Limited IT support | No dedicated IT team | Solution must be self-maintainable |
| C-04 | Budget constraints | No significant budget for custom development | Preference for existing tools |
| C-05 | Small operational scale | Designed for small team and workload | Enterprise features out of scope |
| C-06 | Manual data entry | Data is entered by users | Requires strong validation rules |
| C-07 | Regulatory simplicity | No complex industry regulations | Focus on basic data protection only |

---

## Dependencies

Dependencies represent external factors that the system relies on.

### Dependencies Table

| ID | Dependency | Type | Description | Risk |
|----|------------|------|-------------|------|
| D-01 | AppSheet platform | Technical | Core application framework | Medium |
| D-02 | Google Sheets | Technical | Primary data storage | Medium |
| D-03 | Google account access | Operational | User authentication | Low |
| D-04 | Business owner decisions | Organizational | Scope and priority approval | Medium |
| D-05 | User availability | Operational | Feedback and validation | Medium |
| D-06 | Google Calendar | Technical | One-way event creation | Medium

---

## Assumptions vs Constraints Clarification

- Assumptions **can change** and must be validated
- Constraints **must be accepted** and worked around
- Dependencies **require monitoring** and contingency planning

Misclassifying these elements can lead to incorrect scope and design decisions.

---

## Risks Related to Assumptions and Constraints

| Risk ID | Related Item | Description | Mitigation Strategy |
|--------|--------------|-------------|---------------------|
| R-01 | A-03 | Users may require more guidance than expected | Simplify UI, provide documentation |
| R-02 | C-02 | Data volume may exceed storage performance | Limit historical data, optimize structure |
| R-03 | D-01 | Platform limitations may block features | Adjust scope, redesign logic |
| R-04 | A-05 | Reporting needs may grow | Design extensible reporting structure |

---

## Governance and Review

- Assumptions must be reviewed at each major milestone
- New constraints must be documented and approved
- Dependency changes must trigger impact analysis

This document is a living artifact and may evolve throughout the project.

---

## Traceability

This document directly influences:
- Scope definition (`06_Scope.md`)
- Domain decomposition (`05_Domain_Decomposition.md`)
- Non-functional requirements hypotheses
- Solution architecture decisions

# 08. Personas and User Goals

## Purpose of This Document

This document defines key user personas interacting with the ISBUSHKA system
and describes their goals, motivations, and success criteria.

Personas are used to:
- align requirements with real user needs
- validate scope decisions
- guide prioritization
- ensure the system supports daily operational reality

---

## Persona Modeling Principles

- Personas represent **roles**, not specific individuals
- Focus is on **goals and tasks**, not demographics
- Each persona has clear success criteria
- Personas are directly traceable to system actors

---

## Persona Overview

| Persona ID | Persona Name | Role | Primary Interaction Level |
|-----------|--------------|------|---------------------------|
| P-01 | Salon Owner | Business owner | Strategic / Analytical |
| P-02 | Administrator | Operational manager | Daily / Intensive |
| P-03 | Master | Service provider | Operational / Limited |
| P-04 | Analyst / Maintainer | System support | Occasional / Expert |

---

## P-01. Salon Owner

### Profile
Business owner responsible for profitability, sustainability, and strategic
decisions. Does not participate in daily data entry.

### Primary Goals
- Understand financial performance
- Identify trends over time
- Maintain control without micromanagement

### Key Questions
- How much did the salon earn this month?
- Which services and masters perform best?
- Are expenses under control?

### Pain Points
- Fragmented or delayed financial data
- Lack of trust in manually prepared reports
- Difficulty answering questions quickly

### Jobs To Be Done (JTBD)
> When I review salon performance,  
> I want to see clear financial summaries,  
> so that I can make informed business decisions.

### Success Criteria
- Financial summaries available without manual preparation
- Data accuracy trusted by the owner
- Minimal time spent interpreting reports

---

## P-02. Administrator

### Profile
Responsible for day-to-day salon operations, scheduling, and financial records.
Primary system user.

### Primary Goals
- Quickly create and manage appointments
- Accurately record financial operations
- Avoid operational errors

### Key Tasks
- Create appointments after agreement with masters
- Specify appointment duration
- Record payments and expenses
- Review daily summaries

### Pain Points
- Repetitive manual data entry
- High cognitive load during busy periods
- Risk of errors due to time pressure

### Jobs To Be Done (JTBD)
> When managing daily operations,  
> I want a simple and predictable system,  
> so that I can work fast without making mistakes.

### Success Criteria
- Fast data entry with minimal steps
- Clear validation preventing incorrect input
- Reduced need for corrections

---

## P-03. Master

### Profile
Professional providing services to clients. Limited interaction with the system.

### Primary Goals
- Have a clear and reliable schedule
- Avoid unexpected overlaps or changes
- Focus on service quality

### Key Tasks
- Review personal schedule
- Confirm appointment details
- Communicate changes to administrator

### Pain Points
- Last-minute schedule changes
- Ambiguous appointment details
- Administrative distractions

### Jobs To Be Done (JTBD)
> When I plan my workday,  
> I want to clearly see my appointments,  
> so that I can focus on providing quality service.

### Success Criteria
- Accurate and up-to-date schedule
- Minimal need for system interaction
- No administrative overload

---

## P-04. Analyst / Maintainer

### Profile
Person responsible for system configuration, logic updates, and documentation.
May be the same person as the analyst who designed the system.

### Primary Goals
- Maintain system consistency
- Safely introduce changes
- Preserve data integrity

### Key Tasks
- Update configuration and business rules
- Adjust reports and calculations
- Support data reconciliation

### Pain Points
- Unclear business logic
- Undocumented assumptions
- Inconsistent data usage

### Jobs To Be Done (JTBD)
> When evolving the system,  
> I want clear documentation and structure,  
> so that changes are predictable and safe.

### Success Criteria
- Clear traceability from objectives to logic
- Minimal regressions after changes
- Documentation remains up to date

---

## Persona-to-Actor Mapping

| Persona | System Actor |
|-------|--------------|
| Salon Owner | Owner |
| Administrator | Administrator |
| Master | Master |
| Analyst / Maintainer | Analyst / Maintainer |

---

## Cross-Persona Considerations

- Simplicity for Administrator must not reduce visibility for Owner
- Master interaction should remain minimal
- System changes must not disrupt daily operations

Balancing these needs is a key design challenge.

---

## Traceability

Personas and goals are directly linked to:
- Business Objectives (`01_Business_Objectives.md`)
- Scope definition (`06_Scope.md`)
- High-level requirements backlog
- Reporting and access control decisions

---

## Discovery Notes

- Personas are expected to remain stable in the near term
- New personas may be added as the business evolves
- Persona goals take precedence over feature requests

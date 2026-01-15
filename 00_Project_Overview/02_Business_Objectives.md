# 02. Business Objectives

## Purpose of This Document

This document defines the business objectives of the ISBUSHKA project.
The objectives describe *why* the system is being created, *what business
problems it addresses*, and *how success will be measured*.

Business objectives serve as a foundation for:
- scope definition
- prioritization decisions
- requirements validation
- success evaluation

---

## Business Context

ISBUSHKA operates as a small service business (beauty salon) with daily
operational activities that include appointment scheduling, service delivery,
and financial tracking.

Due to the nature of the business, operational efficiency, data accuracy,
and transparency are critical for sustainable growth and decision-making.

---

## Business Objectives Overview

The following business objectives were identified during the discovery phase.
Each objective is measurable and traceable to business value.

### Legend
- **Baseline** — estimated current state before system implementation
- **Target** — expected outcome after implementation
- **Frequency** — how often the metric should be reviewed

---

## Business Objectives Table

| Obj ID | Business Objective | Description | Success Metric | Baseline (As-Is) | Target (To-Be) | Owner | Measurement Frequency |
|------|--------------------|-------------|----------------|------------------|---------------|-------|-----------------------|
| BO-01 | Reduce scheduling errors | Minimize appointment conflicts, overlaps, and missed bookings | % of conflicting or incorrect appointments | ~5–10% of appointments | < 1% | Salon Owner | Monthly |
| BO-02 | Improve financial transparency | Ensure clear visibility of income and expenses | Availability of daily and monthly financial summary | No consolidated view | Daily summary available | Salon Owner | Daily / Monthly |
| BO-03 | Reduce manual operational effort | Decrease time spent on manual data entry and reconciliation | Avg. time to create/update records | 10–15 min per operation | < 5 min | Administrator | Monthly |
| BO-04 | Increase data accuracy | Reduce errors caused by manual tracking | Number of data correction cases | Frequent manual corrections | Rare / exceptional | Administrator | Monthly |
| BO-05 | Enable basic business analytics | Provide ability to analyze performance by period and staff | Availability of structured reports | Ad-hoc, manual | Standard reports available | Salon Owner | Monthly |
| BO-06 | Support future scalability | Prepare system structure for growth without redesign | Ability to add new entities (services, staff) | High effort | Low effort | Salon Owner | Quarterly |

---

## Business Value Mapping

The objectives above directly contribute to the following business values:

- **Operational efficiency**  
  Less time spent on routine actions, more focus on service delivery

- **Decision-making quality**  
  Access to accurate and timely data enables informed business decisions

- **Risk reduction**  
  Reduced likelihood of financial discrepancies and scheduling conflicts

- **Scalability readiness**  
  System prepared for growth without fundamental restructuring

---

## Assumptions Related to Objectives

- The salon operates with a relatively small team
- Most users are non-technical
- Simplicity and clarity are more important than advanced functionality
- Initial focus is on operational control rather than marketing growth

These assumptions are documented in detail in
`04_Assumptions_Constraints_Dependencies.md`.

---

## Traceability Notes

Each business objective will be traced to:
- high-level epics and features
- functional requirements
- reports and KPIs
- acceptance criteria

Traceability will be documented in
`18_Traceability_Matrix.md`.

---

## Approval Status

This document represents the **initial version** of business objectives
identified during discovery.

Changes to objectives must be reviewed and approved by the business owner
before being reflected in scope or requirements documentation.


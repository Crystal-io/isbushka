# 04. Stakeholders and Actors

## Purpose of This Document

This document identifies all key stakeholders and system actors involved
in the ISBUSHKA project. It describes their roles, goals, responsibilities,
and influence on the system.

Understanding stakeholders and actors is critical for:
- defining scope and priorities
- identifying risks and conflicts of interest
- shaping system behavior and access rules
- aligning business objectives with user needs

---

## Definitions

- **Stakeholder** — a person or group with interest or influence over the system
- **Actor** — a role that directly interacts with the system

A stakeholder may or may not be a system actor.

---

## Stakeholders Overview

### Primary Stakeholders

| Stakeholder | Description | Interest Level | Influence Level |
|------------|-------------|----------------|-----------------|
| Salon Owner | Business owner responsible for strategy and profitability | High | High |
| Administrator | Person managing daily operations | High | Medium |
| Masters | Staff providing services to clients | Medium | Low |

### Secondary Stakeholders

| Stakeholder | Description | Interest Level | Influence Level |
|------------|-------------|----------------|-----------------|
| Clients | End customers receiving services | Medium | Low |
| Analyst / Maintainer | Person maintaining and evolving the system | Medium | Medium |

---

## Stakeholder Goals and Pain Points

### Salon Owner

**Goals**
- Full visibility into financial performance
- Control over operations without micromanagement
- Ability to make informed decisions

**Pain Points**
- Lack of consolidated financial data
- Unclear profitability by period or staff
- Dependence on manual reports

**Risks**
- Wrong decisions due to incomplete or inaccurate data

---

### Administrator

**Goals**
- Fast and simple daily operations
- Clear overview of appointments and finances
- Minimal manual work

**Pain Points**
- Repetitive data entry
- Error-prone manual calculations
- Time pressure during peak hours

**Risks**
- Operational errors
- Increased stress and workload

---

### Masters

**Goals**
- Clear and reliable schedule
- Minimal administrative overhead
- Focus on service delivery

**Pain Points**
- Schedule changes not communicated clearly
- Overlapping or unclear appointments

**Risks**
- Missed or delayed appointments
- Reduced service quality

---

### Clients

**Goals**
- Reliable appointments
- Timely service
- Clear understanding of booked services

**Pain Points**
- Appointment changes or delays
- Lack of confirmation clarity

**Risks**
- Reduced satisfaction
- Loss of trust in the salon

---

## System Actors

The following roles directly interact with the system.

| Actor | Description | Primary Actions |
|------|-------------|-----------------|
| Owner | Strategic system user | View reports, review finances, manage configuration |
| Administrator | Operational system user | Create and manage appointments, record financial operations |
| Master | Service delivery user | View own schedule and appointments |
| Analyst / Maintainer | System support role | Adjust configuration, logic, and reports |

---

## Actor Permissions (High-Level)

| Actor | View Data | Create / Edit Data | Reports Access |
|------|-----------|--------------------|----------------|
| Owner | All | Limited | Full |
| Administrator | Operational | Full (operational scope) | Limited |
| Master | Own appointments | None / Limited | None |
| Analyst / Maintainer | All | Configuration-level | All |

> Detailed access control rules will be defined in later documentation.

---

## Stakeholder Conflicts and Considerations

- **Owner vs Administrator**  
  Owner requires transparency and control, while Administrator prioritizes speed and simplicity.

- **Administrator vs Master**  
  Administrative changes may impact service delivery schedules.

- **Client Expectations vs Operational Limitations**  
  Manual processes increase the risk of unmet expectations.

These conflicts must be considered when defining priorities and system behavior.

---

## Traceability

Stakeholder goals and pain points are directly linked to:
- Business Objectives (`01_Business_Objectives.md`)
- Problem Statement (`02_Problem_Statement_AsIs.md`)
- Scope and requirements definitions

---

## Discovery Notes

- The system is designed primarily for internal use.
- Clients do not directly interact with the system at this stage.
- The number of actors is intentionally limited to reduce complexity.
- Roles may evolve as the business grows.

---

## Next Steps

The stakeholder analysis will be used as input for:
- assumptions and constraints definition
- domain decomposition
- access control and security design


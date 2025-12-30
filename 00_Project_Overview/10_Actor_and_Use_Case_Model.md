# 10. Actor and Use Case Model

## Purpose of This Document

This document defines the system actors and high-level use cases for the
ISBUSHKA project.

The Actor & Use Case Model describes **who** interacts with the system and
**for what business purpose**, without separating technical details or UI
implementation.

The model is intentionally minimal and reflects the real operational logic
of a small service business.

---

## Definitions

- **Actor** — a role that interacts with the system
- **Use Case** — a goal-oriented interaction between an actor and the system

Create, update, and cancel actions are treated as **scenarios within a single
use case** if they serve the same business goal.

---

## System Boundary

The ISBUSHKA system includes:
- appointment management
- financial recording
- reporting
- one-way calendar synchronization

Configuration and technical setup are performed outside of system use cases
and are considered operational maintenance.

---

## Actors Overview

| Actor ID | Actor Name | Description |
|--------|------------|-------------|
| A-01 | Owner | Business owner with analytical and supervisory access |
| A-02 | Administrator | Primary operational system user |
| A-03 | Master | Service provider with read-only schedule access |
| A-04 | External Calendar | External system consuming appointment data |

---

## Actor Responsibilities

### A-01. Owner
- Review financial and operational reports
- Monitor business performance

---

### A-02. Administrator
- Manage clients and appointments
- Record payments and expenses
- Ensure operational data correctness

---

### A-03. Master
- View personal schedule
- Confirm appointment details offline

---

### A-04. External Calendar
- Display appointment schedule
- Consume derived appointment data

---

## Use Case Overview

| Use Case ID | Use Case Name | Primary Actor | Related Epic |
|-----------|---------------|---------------|--------------|
| UC-01 | Manage Clients | Administrator | E-01 |
| UC-02 | Manage Service Classification | Administrator | E-03 |
| UC-03 | Manage Appointments | Administrator | E-02 |
| UC-04 | Record Payment / Expense | Administrator | E-04 |
| UC-05 | View Reports | Owner | E-05 |
| UC-06 | View Schedule | Master | E-02 |
| UC-07 | Synchronize Calendar Event | External Calendar | E-07 |

---

## Use Case Descriptions (High-Level)

### UC-01. Manage Clients

**Primary Actor:** Administrator  
**Goal:** Maintain accurate client information

**Brief Description**  
The administrator creates, updates, and reviews client profiles that are used
for appointments and financial records.

---

### UC-02. Manage Service Classification

**Primary Actor:** Administrator  
**Goal:** Maintain service types for classification and reporting

**Brief Description**  
The administrator manages the list of service types used to classify
appointments. Services do not define fixed price or duration.

---

### UC-03. Manage Appointments

**Primary Actor:** Administrator  
**Goal:** Register and maintain agreed appointments

**Brief Description**  
The administrator creates, updates, or cancels appointments after agreement
with the master. For each appointment, the administrator specifies:
- client
- service (classification)
- master
- appointment-specific duration

**Scenarios**
- Create appointment
- Update / reschedule appointment
- Cancel appointment

**Notes**
- Appointments are created only after agreement with the master
- Appointment price is not defined at this stage

---

### UC-04. Record Payment / Expense

**Primary Actor:** Administrator  
**Goal:** Record financial outcome of operations

**Brief Description**  
The administrator records income or expense operations.
Income records include the final agreed price and may be linked
to a completed appointment.

**Postconditions**
- When a payment is recorded and linked to an appointment,
  the appointment status is automatically set to **Completed**

---

### UC-05. View Reports

**Primary Actor:** Owner  
**Goal:** Review business performance

**Brief Description**  
The owner views read-only reports and summaries generated from
operational and financial data.

---

### UC-06. View Schedule

**Primary Actor:** Master  
**Goal:** Review personal schedule

**Brief Description**  
The master views scheduled appointments without editing capabilities.
Schedule data is provided for informational purposes only.

---

### UC-07. Synchronize Calendar Event

**Primary Actor:** External Calendar  
**Goal:** Display appointment schedule externally

**Brief Description**  
The system creates, updates, or deletes calendar events based on
appointment lifecycle changes.

**Notes**
- Synchronization is one-way: system → calendar
- Calendar data is derived and not authoritative

---

## Use Case Relationships (Conceptual)

- UC-03 Manage Appointments → UC-07 Synchronize Calendar Event
- UC-04 Record Payment → automatic appointment completion
- UC-03 and UC-04 provide data for UC-05 View Reports

---

## Traceability

This use case model is traceable to:
- High-Level Requirements Backlog (`09_Requirements_Backlog_HL.md`)
- Personas and User Goals (`08_Personas_and_User_Goals.md`)
- Scope definition (`06_Scope.md`)
- Domain Decomposition (`05_Domain_Decomposition.md`)

---

## Design Notes

- The model intentionally avoids technical configuration use cases
- Business flows are preferred over CRUD-level granularity
- Automation is represented as system behavior, not user actions

---

## Next Steps

This model serves as a foundation for:
- detailed use case specifications
- BPMN process modeling
- functional requirements definition

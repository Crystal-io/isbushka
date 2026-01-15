# 11. Actor and Use Case Model

## Purpose of This Document

This document defines system actors and high-level use cases for the ISBUSHKA project.
It formalizes **who** interacts with the system and **for what business purpose**,
without describing UI or implementation.

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
- client data management
- appointment management
- financial operations recording
- reporting
- one-way calendar synchronization

External systems (e.g., Google Calendar) are outside the system boundary
and consume derived data only.

---

## Actors Overview

| Actor ID | Actor Name | Description |
|--------|------------|-------------|
| A-01 | Owner | Business owner with read-only analytical access and supervisory visibility |
| A-02 | Administrator | Primary operational user (appointments, finance, reference data) |
| A-03 | Master | Service provider with read-only schedule access |
| A-04 | External Calendar | External consumer of appointment schedule data (derived) |

---

## Actor Responsibilities

### A-01. Owner
- Review financial and operational reports
- Monitor performance indicators

### A-02. Administrator
- Maintain clients
- Create and manage appointments (after agreement with master)
- Record income/expense operations
- Ensure correctness of operational and financial data

### A-03. Master
- View personal schedule
- Confirm appointment details offline (outside the system)

### A-04. External Calendar
- Display derived appointment schedule data (read-only consumer)

---

## Use Case Overview

| Use Case ID | Use Case Name | Primary Actor | Notes |
|-----------|---------------|---------------|------|
| UC-01 | Manage Clients | Administrator | Create/update client profiles used across operations |
| UC-02 | Manage Service Classification | Administrator | Maintain list of service types (no fixed price/duration) |
| UC-03 | Manage Appointments | Administrator | Create/update/cancel appointments; duration specified per appointment |
| UC-04 | Record Payment / Expense | Administrator | Multiple entry points; optional linking; appointment completion automation |
| UC-05 | View Reports | Owner | Read-only analytics and summaries |
| UC-06 | View Schedule | Master | Read-only personal schedule |
| UC-07 | Synchronize Calendar Event (One-Way) | External Calendar | System pushes schedule changes to calendar |

---

## Use Case Descriptions (High-Level)

### UC-01. Manage Clients

**Primary Actor:** Administrator  
**Goal:** Maintain accurate client information

**Brief Description**  
The administrator creates, updates, and reviews client profiles that are used
for appointments and (optional) financial linking.

---

### UC-02. Manage Service Classification

**Primary Actor:** Administrator  
**Goal:** Maintain service types for classification and reporting

**Brief Description**  
The administrator manages the list of service types used to classify appointments.
Services do not define fixed price or duration.

---

### UC-03. Manage Appointments

**Primary Actor:** Administrator  
**Goal:** Register and maintain agreed appointments

**Brief Description**  
The administrator creates, updates, or cancels appointments after agreement with the master.
For each appointment the administrator specifies:
- client
- service (classification)
- master
- appointment-specific duration

**Scenarios**
- Create appointment
- Update / reschedule appointment
- Cancel appointment

**Notes**
- Appointment is created only after agreement with the master
- Appointment price is not defined at this stage

---

### UC-04. Record Payment / Expense

**Primary Actor:** Administrator  
**Goal:** Record financial operations (income and expenses) with correct linking and automation

**Brief Description**  
The administrator records financial operations. The system supports multiple creation
scenarios and entry points:
- **context-driven income** created from an appointment (prefilled context)
- **standalone financial operation** (income or expense) created from a dedicated form
- optional manual linking to client and/or appointment

**Scenarios**

**Scenario 1 — Income created from Appointment (Context-Driven)**  
- Administrator initiates payment creation from an appointment
- System pre-fills client and appointment context
- Administrator enters the final agreed amount and confirms payment

**Scenario 2 — Standalone Financial Operation Form**

2A) **Expense without appointment / client**  
- Administrator records an expense not linked to any client or appointment  
  (e.g., materials, supplies, equipment)

2B) **Income without appointment**  
- Administrator records income that is not related to an appointment  
  (e.g., product sale, other income)

2C) **Manual linking (optional)**  
- Administrator may optionally select client and/or appointment for the operation  
- If appointment is selected, the operation is linked to that appointment

**Rules and Notes**
- Financial operations may exist without client and appointment
- Linking to appointment is optional and used when operationally meaningful
- Appointment price is represented by the final agreed amount recorded in the linked income operation

**Postconditions**
- If an **income** operation is created and linked to an appointment,
  the appointment status is automatically set to **Completed**

---

### UC-05. View Reports

**Primary Actor:** Owner  
**Goal:** Review business performance

**Brief Description**  
The owner views read-only reports and summaries based on operational and financial data.

---

### UC-06. View Schedule

**Primary Actor:** Master  
**Goal:** Review personal schedule

**Brief Description**  
The master views scheduled appointments without editing capabilities.

---

### UC-07. Synchronize Calendar Event (One-Way)

**Primary Actor:** External Calendar  
**Goal:** Display appointment schedule externally

**Brief Description**  
The system creates, updates, or deletes calendar events based on appointment lifecycle changes.

**Notes**
- Synchronization is one-way: system → calendar
- Calendar data is derived and not authoritative (SSOT remains in system data)

---

## Use Case Relationships (Conceptual)

- UC-03 Manage Appointments → UC-07 Synchronize Calendar Event
- UC-04 Record Payment / Expense → (conditional) automatic appointment completion
- UC-03 and UC-04 provide data for UC-05 View Reports

---

## Traceability

This use case model is traceable to:
- High-Level Requirements Backlog (`09_Requirements_Backlog_HL.md`)
- Personas and User Goals (`08_Personas_and_User_Goals.md`)
- Scope definition (`06_Scope.md`)
- Domain Decomposition (`05_Domain_Decomposition.md`)
- Data sources and ownership (`14_Data_Sources_and_Ownership.md`)

---

## Design Notes

- The model avoids CRUD-level granularity and focuses on business goals
- Automation is represented as system behavior (postconditions), not as separate use cases
- Technical configuration is treated as operational maintenance outside of use case scope

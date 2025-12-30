# 10. Actor and Use Case Model

## Purpose of This Document

This document defines the system actors and high-level use cases for the
ISBUSHKA project.

The Actor & Use Case Model:
- formalizes system interactions
- bridges requirements backlog and detailed specifications
- serves as a foundation for BPMN and functional requirements
- clarifies system boundaries and responsibilities

This document intentionally avoids UI and implementation details.

---

## Definitions

- **Actor** — a role that interacts with the system
- **Use Case** — a goal-oriented interaction between an actor and the system

Actors are derived from personas and stakeholders defined during discovery.

---

## System Boundary

The ISBUSHKA system includes:
- appointment management
- financial recording
- reporting
- one-way calendar synchronization

External systems (e.g. Google Calendar) are outside the system boundary
and consume derived data only.

---

## Actors Overview

| Actor ID | Actor Name | Description |
|--------|------------|-------------|
| A-01 | Owner | Strategic system user with full visibility |
| A-02 | Administrator | Primary operational system user |
| A-03 | Master | Service provider with limited access |
| A-04 | Analyst / Maintainer | System configuration and support role |
| A-05 | External Calendar | External system consuming schedule data |

---

## Actor Responsibilities

### A-01. Owner

**Responsibilities**
- Review financial performance
- Monitor operational indicators
- Manage high-level configuration
- Access reports

---

### A-02. Administrator

**Responsibilities**
- Create and manage appointments
- Record financial operations
- Maintain reference data
- Ensure data correctness

---

### A-03. Master

**Responsibilities**
- View personal schedule
- Confirm appointment details
- Communicate changes to administrator

---

### A-04. Analyst / Maintainer

**Responsibilities**
- Maintain system configuration
- Update business rules
- Ensure data consistency
- Support system evolution

---

### A-05. External Calendar

**Responsibilities**
- Receive appointment data
- Display schedule information
- Act as a read-only consumer

---

## Use Case Overview

| Use Case ID | Use Case Name | Primary Actor | Related Epic |
|-----------|---------------|---------------|--------------|
| UC-01 | Manage Clients | Administrator | E-01 |
| UC-02 | Manage Service Classification | Administrator | E-03 |
| UC-03 | Create Appointment | Administrator | E-02 |
| UC-04 | Update Appointment | Administrator | E-02 |
| UC-05 | Complete Appointment | Administrator | E-02 |
| UC-06 | Record Financial Operation | Administrator | E-04 |
| UC-07 | View Reports | Owner | E-05 |
| UC-08 | View Schedule | Master | E-02 |
| UC-09 | Synchronize Calendar Event | External Calendar | E-07 |
| UC-10 | Manage Access and Roles | Owner | E-06 |
| UC-11 | Maintain System Configuration | Analyst / Maintainer | Cross-cutting |

---

## Use Case Descriptions (High-Level)

### UC-01. Manage Clients

**Primary Actor**: Administrator  
**Goal**: Maintain accurate client information

**Brief Description**  
The administrator creates, updates, and reviews client profiles
used across appointments and financial operations.

---

### UC-02. Manage Service Classification

**Primary Actor**: Administrator  
**Goal**: Maintain service types for classification and reporting

**Brief Description**  
The administrator manages the list of service types without defining
price or duration.

---

### UC-03. Create Appointment

**Primary Actor**: Administrator  
**Goal**: Register an agreed appointment in the system

**Brief Description**  
An appointment is created only after agreement with the master.
The administrator specifies client, service, master, and duration.

---

### UC-04. Update Appointment

**Primary Actor**: Administrator  
**Goal**: Modify appointment details

**Brief Description**  
The administrator updates appointment date, time, master, or duration
based on changes agreed with the master.

---

### UC-05. Complete Appointment

**Primary Actor**: Administrator  
**Goal**: Mark appointment as completed

**Brief Description**  
The appointment is marked as completed and becomes eligible for
financial recording.

---

### UC-06. Record Financial Operation

**Primary Actor**: Administrator  
**Goal**: Record income or expense

**Brief Description**  
The administrator records a financial operation with the final agreed
price and links it to a completed appointment where applicable.

---

### UC-07. View Reports

**Primary Actor**: Owner  
**Goal**: Review business performance

**Brief Description**  
The owner views read-only reports and summaries generated from
operational and financial data.

---

### UC-08. View Schedule

**Primary Actor**: Master  
**Goal**: Review personal schedule

**Brief Description**  
The master views scheduled appointments without editing capabilities.

---

### UC-09. Synchronize Calendar Event

**Primary Actor**: External Calendar  
**Goal**: Display appointment data externally

**Brief Description**  
The system creates, updates, or removes calendar events based on
appointment lifecycle changes.

---

### UC-10. Manage Access and Roles

**Primary Actor**: Owner  
**Goal**: Control system access

**Brief Description**  
The owner manages role-based access rules and data visibility.

---

### UC-11. Maintain System Configuration

**Primary Actor**: Analyst / Maintainer  
**Goal**: Safely evolve system configuration

**Brief Description**  
The analyst maintains business rules, validation logic, and configuration
without affecting operational stability.

---

## Use Case Relationships (Conceptual)

- UC-03 Create Appointment → UC-09 Synchronize Calendar Event
- UC-05 Complete Appointment → UC-06 Record Financial Operation
- UC-06 Record Financial Operation → UC-07 View Reports

These relationships will be elaborated in BPMN and sequence diagrams.

---

## Traceability

This use case model is traceable to:
- High-Level Requirements Backlog (`09_Requirements_Backlog_HL.md`)
- Personas and User Goals (`08_Personas_and_User_Goals.md`)
- Scope definition (`06_Scope.md`)

---

## Next Steps

This document will serve as a basis for:
- detailed use case specifications
- BPMN process modeling
- functional requirements definition
- data model refinement

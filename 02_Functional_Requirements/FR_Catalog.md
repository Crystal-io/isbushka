
# Functional Requirements Catalog (FR)
## MVP vs Future Versions

## Purpose
This document defines functional requirements for the ISBUSHKA system and explicitly separates
**MVP (Release 1)** scope from **Post-MVP (Future Releases)** scope.

Legend:
- **MVP** – mandatory for first production release
- **R2** – next iteration after MVP
- **Future** – backlog / nice-to-have

---

## FR-01 Client Management

| ID | Requirement | Release |
|----|------------|---------|
| FR-01.1 | Create client profile | MVP |
| FR-01.2 | Update client profile | MVP |
| FR-01.3 | Unique client identity | MVP |
| FR-01.4 | Archive (soft-delete) client | R2 |
| FR-01.5 | Prevent new appointments for archived clients | MVP |

---

## FR-02 Service Classification

| ID | Requirement | Release |
|----|------------|---------|
| FR-02.1 | Maintain service classification list | MVP |
| FR-02.2 | Assign service classification to appointment | MVP |
| FR-02.3 | Service classification has no price or duration | MVP |

---

## FR-03 Appointment Management

| ID | Requirement | Release |
|----|------------|---------|
| FR-03.1 | Create appointment from client context | MVP |
| FR-03.2 | Auto-link appointment to client | MVP |
| FR-03.3 | Assign service classification | MVP |
| FR-03.4 | Assign master | MVP |
| FR-03.5 | Set appointment date and time | MVP |
| FR-03.6 | Set appointment-specific duration | MVP |
| FR-03.7 | Update appointment (Planned only) | MVP |
| FR-03.8 | Cancel appointment (Planned only) | MVP |
| FR-03.9 | Prevent payment/completion for cancelled appointment | MVP |
| FR-03.10 | Prevent modification of completed appointment | MVP |
| FR-03.11 | Appointment statuses (Planned/Completed/Cancelled) | MVP |

---

## FR-04 Financial Operations

| ID | Requirement | Release |
|----|------------|---------|
| FR-04.1 | Record income operation | MVP |
| FR-04.2 | Record expense operation | MVP |
| FR-04.3 | Standalone payments without client/appointment | MVP |
| FR-04.4 | Optional payment–client link | MVP |
| FR-04.5 | Optional payment–appointment link | MVP |
| FR-04.6 | Update payment | R2 |
| FR-04.7 | Soft-delete payment | R2 |
| FR-04.8 | Auto-complete appointment on linked income | MVP |
| FR-04.9 | Income as pricing source of truth | MVP |
| FR-04.10 | Expense does not affect appointment status | MVP |
| FR-04.11 | Recalculate appointment financial state | R2 |

---

## FR-05 Reporting

| ID | Requirement | Release |
|----|------------|---------|
| FR-05.1 | Financial summary reports | R2 |
| FR-05.2 | Reports based on financial operations | MVP |
| FR-05.3 | Filter reports by time period | R2 |

---

## FR-06 Calendar Synchronization

| ID | Requirement | Release |
|----|------------|---------|
| FR-06.1 | Create calendar event on appointment creation | MVP |
| FR-06.2 | Update calendar event on appointment update | MVP |
| FR-06.3 | Update/remove calendar event on cancellation | MVP |
| FR-06.4 | One-way calendar sync | MVP |
| FR-06.5 | Store sync status | R2 |
| FR-06.6 | Retry calendar sync on failure | R2 |

---


# Functional Requirements Catalog (FR)

## Purpose
This document contains **atomic, testable** functional requirements describing **what** the ISBUSHKA system shall do.
Requirements are implementation-independent and derived from Discovery artifacts, Use Cases, and BPMN To-Be processes.

## Notation
- FR — Functional Requirement
- UC — Use Case
- BPMN — Business Process Model (To-Be)

## Requirement format (recommended)
Each FR is written to be:
- **Atomic** (one behavior per requirement)
- **Testable** (clear pass/fail)
- **Implementation-independent**

---

## FR-01 Client Management

### FR-01.1 Create client
System shall allow the administrator to create a client profile.  
Source: UC-01, BPMN Client L1 | Priority: Must

### FR-01.2 Update client
System shall allow the administrator to update client profile information.  
Source: UC-01, BPMN Client L1 | Priority: Must

### FR-01.3 Unique client identity
System shall uniquely identify each client within the system.  
Source: UC-01 | Priority: Must

### FR-01.4 Archive client
System shall allow the administrator to archive (deactivate) a client.  
Source: UC-01, BPMN Client L1 | Priority: Should

### FR-01.5 Restrict new appointments for archived clients
System shall prevent creating new appointments for archived clients.  
Source: UC-03 | Priority: Must

---

## FR-02 Service Classification

### FR-02.1 Maintain service classification list
System shall allow the administrator to maintain a list of service classifications.  
Source: UC-02 | Priority: Must

### FR-02.2 Use service classification for appointment categorization
System shall allow service classifications to be used for appointment categorization.  
Source: UC-03 | Priority: Must

### FR-02.3 Service classification has no price/duration
Service classifications shall not define price or duration.  
Source: Discovery rules | Priority: Must

---

## FR-03 Appointment Management

### FR-03.1 Create appointment from client context
System shall allow the administrator to create an appointment **from a client context** (client is preselected).  
Source: UC-03, BPMN Appointment L1/L2 | Priority: Must

### FR-03.2 Auto-associate appointment with client
System shall automatically associate a newly created appointment with the selected client.  
Source: UC-03 | Priority: Must

### FR-03.3 Assign service classification
System shall allow the administrator to assign a service classification to an appointment.  
Source: UC-03 | Priority: Must

### FR-03.4 Assign master
System shall allow the administrator to assign a master to an appointment.  
Source: UC-03 | Priority: Must

### FR-03.5 Set date/time
System shall allow the administrator to specify appointment date and time.  
Source: UC-03 | Priority: Must

### FR-03.6 Set appointment-specific duration
System shall allow the administrator to specify appointment-specific duration.  
Source: UC-03 | Priority: Must

### FR-03.7 Update appointment details (only Planned)
System shall allow the administrator to update appointment details only when appointment status is **Planned**.  
Source: BPMN Appointment L2 | Priority: Must

### FR-03.8 Cancel appointment (only Planned)
System shall allow the administrator to cancel an appointment only when appointment status is **Planned**.  
Source: BPMN Appointment L2 | Priority: Must

### FR-03.9 Prevent paying/completing cancelled appointments
System shall prevent cancelled appointments from being completed or paid.  
Source: BPMN Appointment L2 | Priority: Must

### FR-03.10 Prevent modification/cancellation of completed appointments
System shall prevent completed appointments from being modified or cancelled.  
Source: BPMN Appointment L2 | Priority: Must

### FR-03.11 Appointment status model
System shall support appointment statuses: **Planned, Completed, Cancelled**.  
Source: BPMN Appointment L2 | Priority: Must

---

## FR-04 Financial Operations (Payments)

### FR-04.1 Record income
System shall allow the administrator to record income operations.  
Source: UC-04, BPMN Payment L1 | Priority: Must

### FR-04.2 Record expense
System shall allow the administrator to record expense operations.  
Source: UC-04, BPMN Payment L1 | Priority: Must

### FR-04.3 Allow standalone payments
System shall allow financial operations to exist without association to a client or appointment.  
Source: UC-04 | Priority: Must

### FR-04.4 Optionally link payment to client
System shall allow the administrator to optionally associate a financial operation with a client.  
Source: UC-04 | Priority: Must

### FR-04.5 Optionally link payment to appointment
System shall allow the administrator to optionally associate a financial operation with an appointment.  
Source: UC-04 | Priority: Must

### FR-04.6 Update payment
System shall allow the administrator to update an existing financial operation.  
Source: UC-04, BPMN Payment L1 | Priority: Should

### FR-04.7 Remove payment (soft delete)
System shall allow the administrator to remove a financial operation (mark as deleted) without physical deletion from storage.  
Source: UC-04 | Priority: Should

### FR-04.8 Auto-complete appointment on linked income
System shall automatically set appointment status to **Completed** when an **income** operation associated with that appointment is recorded.  
Source: BPMN Appointment L2, BPMN Payment L1 | Priority: Must

### FR-04.9 Pricing source of truth
System shall treat recorded income operations as the source of truth for appointment pricing.  
Source: Discovery rules | Priority: Must

### FR-04.10 Expense does not change appointment status
System shall not change appointment status based on expense operations.  
Source: BPMN Payment L1 | Priority: Must

### FR-04.11 Recalculate appointment financial state on payment changes
System shall recalculate appointment financial state when a linked income operation is updated or removed.  
Source: BPMN Payment L1 (delete path) | Priority: Should

---

## FR-05 Reporting

### FR-05.1 Provide financial summary reports
System shall provide read-only financial summary reports.  
Source: Discovery | Priority: Should

### FR-05.2 Calculate reports from financial operations
System shall calculate financial reports based on recorded financial operations.  
Source: Discovery | Priority: Must

### FR-05.3 Filter reports by time period
System shall allow reports to be filtered by time period.  
Source: Discovery | Priority: Should

---

## FR-06 Calendar Synchronization

### FR-06.1 Create calendar event on appointment creation
System shall create a calendar event when a planned appointment is created.  
Source: BPMN Calendar Sync L1 | Priority: Must

### FR-06.2 Update calendar event on appointment update
System shall update the calendar event when appointment details change.  
Source: BPMN Calendar Sync L1 | Priority: Must

### FR-06.3 Update/remove calendar event on cancellation
System shall update or remove the calendar event when an appointment is cancelled.  
Source: BPMN Calendar Sync L1 | Priority: Must

### FR-06.4 One-way sync
Calendar synchronization shall be one-way from the system to the external calendar.  
Source: BPMN Calendar Sync L1 | Priority: Must

### FR-06.5 Store sync status
System shall store the calendar synchronization status for each appointment (e.g., success/failed).  
Source: BPMN Calendar Sync L1 | Priority: Should

### FR-06.6 Retry on failure (high-level)
System shall support retrying calendar synchronization when a sync attempt fails.  
Source: BPMN Calendar Sync L1 | Priority: Should

---

## Notes
- User interaction flows and validations are detailed in Use Case specifications.
- Process sequencing is defined in BPMN diagrams.
- User Stories and Acceptance Criteria will be derived from FR and BPMN (L1/L2).


## Summary

- **MVP focus:** core operations (clients, appointments, payments, calendar sync)
- **R2 focus:** edit/delete flows, reporting enhancements, resiliency
- **Future:** advanced analytics, role expansion, configuration UI

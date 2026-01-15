
# Functional Requirements Catalog (FR)

## Purpose
This document defines functional requirements for the ISBUSHKA system and explicitly separates
**MVP (Release 1)** scope from **Post-MVP (R2)** scope.

Legend:
- **MVP** – mandatory for first production release
- **R2** – next iteration after MVP

---

## FR-01 Client Management

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-01.1 | Create client | System shall allow the administrator to create a client profile. | UC-01, Discovery | MVP |
| FR-01.2 | Update client | System shall allow the administrator to update client profile information. | UC-01, Discovery | MVP |
| FR-01.3 | Client status model | System shall support client statuses: Active, Archived. | Discovery | MVP |
| FR-01.4 | Archive client | System shall allow the administrator to archive (soft-delete) a client. | UC-01 | MVP |
| FR-01.5 | Restrict archived clients | System shall prevent creating new appointments for archived clients. | UC-03, BPMN Appointment L2 | MVP |

---

## FR-02 Service Classification

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-02.1 | Manage service classifications | System shall allow the administrator to maintain a list of service classifications. | UC-02, Discovery | MVP |
| FR-02.2 | Assign service classification | System shall allow service classifications to be used for appointment categorization. | UC-03 | MVP |
| FR-02.3 | No price/duration in classification | Service classifications shall not define price or duration. | Discovery (Business Rule) | MVP |

---

## FR-03 Appointment Management

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-03.1 | Create appointment | System shall allow the administrator to create an appointment from a client context. | UC-03, BPMN Appointment L1 | MVP |
| FR-03.2 | Auto-link client | System shall automatically associate a newly created appointment with the selected client. | UC-03 | MVP |
| FR-03.3 | Assign service | System shall allow the administrator to assign a service classification to an appointment. | UC-03 | MVP |
| FR-03.4 | Assign master | System shall allow the administrator to assign a master to an appointment. | UC-03 | MVP |
| FR-03.5 | Set date and time | System shall allow the administrator to specify appointment date and time. | UC-03 | MVP |
| FR-03.6 | Set duration | System shall allow the administrator to specify appointment-specific duration. | UC-03 | MVP |
| FR-03.7 | Update planned appointment | System shall allow appointment updates only when status is Planned. | BPMN Appointment L2 | MVP |
| FR-03.8 | Cancel planned appointment | System shall allow appointment cancellation only when status is Planned. | BPMN Appointment L2 | MVP |
| FR-03.9 | Block cancelled appointment actions | System shall prevent payment or completion of cancelled appointments. | BPMN Appointment L2 | MVP |
| FR-03.10 | Lock completed appointment | System shall prevent modification or cancellation of completed appointments. | BPMN Appointment L2 | MVP |
| FR-03.11 | Appointment status model | System shall support appointment statuses: Planned, Completed, Cancelled. | BPMN Appointment L2 | MVP |

---

## FR-04 Financial Operations (Payments)

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-04.1 | Record income | System shall allow the administrator to record income operations. | UC-04, BPMN Payment L1 | MVP |
| FR-04.2 | Record expense | System shall allow the administrator to record expense operations. | UC-04, BPMN Payment L1 | MVP |
| FR-04.3 | Standalone payment | System shall allow financial operations without client or appointment association. | UC-04 | MVP |
| FR-04.4 | Link payment to client | System shall allow optional association of a payment with a client. | UC-04 | MVP |
| FR-04.5 | Link payment to appointment | System shall allow optional association of a payment with an appointment. | UC-04 | MVP |
| FR-04.6 | Update payment | System shall allow updating an existing financial operation. | UC-04 | R2 |
| FR-04.7 | Delete payment (soft) | System shall allow soft deletion of a financial operation. | UC-04 | R2 |
| FR-04.8 | Auto-complete appointment | System shall automatically complete an appointment when linked income is recorded. | BPMN Appointment L2 | MVP |
| FR-04.9 | Income as price source | System shall treat income payments as source of truth for appointment pricing. | Discovery | MVP |
| FR-04.10 | Expense no status impact | System shall not change appointment status based on expense operations. | BPMN Payment L1 | MVP |
| FR-04.11 | Recalculate financial state | System shall recalculate appointment financial state when linked income is updated or removed. | BPMN Payment L1 | R2 |

---

## FR-05 Reporting

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-05.1 | Financial summary reports | System shall provide financial summary reports. | Discovery | R2 |
| FR-05.2 | Calculate reports | System shall calculate reports based on recorded financial operations. | Discovery | MVP |
| FR-05.3 | Filter reports | System shall allow filtering reports by time period. | Discovery | R2 |

---

## FR-06 Calendar Synchronization

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-06.1 | Create calendar event | System shall create a calendar event when a planned appointment is created. | BPMN Calendar Sync L1 | MVP |
| FR-06.2 | Update calendar event | System shall update calendar events when appointment details change. | BPMN Calendar Sync L1 | MVP |
| FR-06.3 | Cancel calendar event | System shall update or remove calendar events when an appointment is cancelled. | BPMN Calendar Sync L1 | MVP |
| FR-06.4 | One-way sync | Calendar synchronization shall be one-way from system to calendar. | BPMN Calendar Sync L1 | MVP |
| FR-06.5 | Store sync status | System shall store the result of calendar synchronization attempts. | BPMN Calendar Sync L1 | R2 |
| FR-06.6 | Retry calendar sync | System shall retry calendar synchronization after failure. | BPMN Calendar Sync L1 | R2 |

---

## Notes
This FR catalog is logically consistent with Discovery artifacts, BPMN To-Be diagrams, and Use Case definitions.

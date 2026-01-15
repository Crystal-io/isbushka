
# Functional Requirements Catalog
## MVP vs Post-MVP Scope

## Purpose
This document defines functional requirements for the ISBUSHKA system and explicitly separates
a **Strict MVP (Release 1)** scope from **R2 (Next iteration)** scope.
This version intentionally keeps MVP minimal and pushes non-critical capabilities to R2.

Legend:
- **MVP** – minimal set required to operate the salon workflow end-to-end
- **R2** – post-MVP enhancements, automation, resiliency, and convenience features

---

## FR-01 Client Management

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-01.1 | Create client | System shall allow the administrator to create a client profile. | UC-01, Discovery | MVP |
| FR-01.2 | Update client | System shall allow the administrator to update client profile information. | UC-01, Discovery | MVP |
| FR-01.3 | Unique client identity | System shall uniquely identify each client within the system. | Discovery | MVP |
| FR-01.4 | Client status model | System shall support client statuses: Active, Archived. | Discovery | R2 |
| FR-01.5 | Archive client | System shall allow the administrator to archive (soft-delete) a client. | UC-01 | R2 |
| FR-01.6 | Restrict archived clients | System shall prevent creating new appointments for archived clients. | UC-03 | R2 |

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
| FR-03.7 | Appointment status model | System shall support appointment statuses: Planned, Cancelled, Completed. | BPMN Appointment L2 | MVP |
| FR-03.8 | Cancel appointment | System shall allow the administrator to cancel an appointment. | BPMN Appointment L2 | MVP |
| FR-03.9 | Update appointment | System shall allow the administrator to update appointment details (reschedule/edit). | BPMN Appointment L2 | R2 |
| FR-03.10 | Enforce state rules | System shall enforce state-based restrictions for modify/cancel/complete actions. | BPMN Appointment L2 | R2 |

---

## FR-04 Financial Operations (Payments)

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-04.1 | Record income | System shall allow the administrator to record income operations. | UC-04, BPMN Payment L1 | MVP |
| FR-04.2 | Record expense | System shall allow the administrator to record expense operations. | UC-04, BPMN Payment L1 | MVP |
| FR-04.3 | Standalone payment | System shall allow financial operations without client or appointment association. | UC-04 | MVP |
| FR-04.4 | Link payment to appointment | System shall allow optional association of a payment with an appointment. | UC-04 | MVP |
| FR-04.5 | Link payment to client | System shall allow optional association of a payment with a client. | UC-04 | R2 |
| FR-04.6 | Update payment | System shall allow updating an existing financial operation. | UC-04 | R2 |
| FR-04.7 | Delete payment (soft) | System shall allow soft deletion of a financial operation. | UC-04 | R2 |
| FR-04.8 | Income as price source | System shall treat recorded income payments as the source of truth for appointment pricing. | Discovery | MVP |
| FR-04.9 | Auto-complete appointment | System shall automatically complete an appointment when linked income is recorded. | BPMN Appointment L2 | R2 |
| FR-04.10 | Recalculate financial state | System shall recalculate appointment financial state when linked income is updated or removed. | BPMN Payment L1 | R2 |

---

## FR-05 Reporting

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-05.1 | Financial summary reports | System shall provide financial summary reports. | Discovery | R2 |
| FR-05.2 | Filter reports | System shall allow filtering reports by time period. | Discovery | R2 |

---

## FR-06 Calendar Synchronization

| ID | Requirement | Description | Source | Release |
|----|------------|-------------|--------|---------|
| FR-06.1 | Calendar sync (one-way) | System shall synchronize appointment events to an external calendar (one-way). | BPMN Calendar Sync L1 | R2 |
| FR-06.2 | Store sync status | System shall store the result of calendar synchronization attempts. | BPMN Calendar Sync L1 | R2 |
| FR-06.3 | Retry calendar sync | System shall retry calendar synchronization after failure. | BPMN Calendar Sync L1 | R2 |

---

## MVP Definition (Strict)
MVP provides the minimum operational loop:
- maintain clients (create/update)
- create appointments (client context, service, master, date/time, duration) and allow cancellation
- record income/expense, link income to appointment for pricing tracking
- no automation-heavy features (calendar sync, auto-complete, payment edits/deletes) in MVP

R2 adds convenience, automation, resiliency, and reporting.

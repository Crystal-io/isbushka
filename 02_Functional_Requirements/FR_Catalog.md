# Functional Requirements Catalog (FR)
## MVP vs Post-MVP Scope

## Purpose
This document defines functional requirements for the ISBUSHKA system and explicitly separates
**MVP (Release 1)** scope from **Post-MVP (Future Releases)** scope.

Legend:
- **MVP** – mandatory for first production release
- **R2** – next iteration after MVP
- **Future** – backlog / nice-to-have

---

## FR-01 Client Management

| ID | Description | Source | Release |
|----|------------|--------|---------|
| FR-01.1 | System shall allow the administrator to create a client profile. | UC-01, Discovery | MVP |
| FR-01.2 | System shall allow the administrator to update client profile information. | UC-01, Discovery | MVP |
| FR-01.3 | System shall uniquely identify each client within the system. | Discovery | MVP |
| FR-01.4 | System shall allow the administrator to archive (soft-delete) a client. | UC-01 | R2 |
| FR-01.5 | System shall prevent creating new appointments for archived clients. | UC-03, BPMN Appointment L2 | MVP |

---

## FR-02 Service Classification

| ID | Description | Source | Release |
|----|------------|--------|---------|
| FR-02.1 | System shall allow the administrator to maintain a list of service classifications. | UC-02, Discovery | MVP |
| FR-02.2 | System shall allow service classifications to be used for appointment categorization. | UC-03 | MVP |
| FR-02.3 | Service classifications shall not define price or duration. | Discovery (Business Rule) | MVP |

---

## FR-03 Appointment Management

| ID | Description | Source | Release |
|----|------------|--------|---------|
| FR-03.1 | System shall allow the administrator to create an appointment from a client context. | UC-03, BPMN Appointment L1 | MVP |
| FR-03.2 | System shall automatically associate a newly created appointment with the selected client. | UC-03 | MVP |
| FR-03.3 | System shall allow the administrator to assign a service classification to an appointment. | UC-03 | MVP |
| FR-03.4 | System shall allow the administrator to assign a master to an appointment. | UC-03 | MVP |
| FR-03.5 | System shall allow the administrator to specify appointment date and time. | UC-03 | MVP |
| FR-03.6 | System shall allow the administrator to specify appointment-specific duration. | UC-03 | MVP |
| FR-03.7 | System shall allow appointment updates only when status is Planned. | BPMN Appointment L2 | MVP |
| FR-03.8 | System shall allow appointment cancellation only when status is Planned. | BPMN Appointment L2 | MVP |
| FR-03.9 | System shall prevent payment or completion of cancelled appointments. | BPMN Appointment L2 | MVP |
| FR-03.10 | System shall prevent modification or cancellation of completed appointments. | BPMN Appointment L2 | MVP |
| FR-03.11 | System shall support appointment statuses: Planned, Completed, Cancelled. | BPMN Appointment L2 | MVP |

---

## FR-04 Financial Operations (Payments)

| ID | Description | Source | Release |
|----|------------|--------|---------|
| FR-04.1 | System shall allow the administrator to record income operations. | UC-04, BPMN Payment L1 | MVP |
| FR-04.2 | System shall allow the administrator to record expense operations. | UC-04, BPMN Payment L1 | MVP |
| FR-04.3 | System shall allow financial operations to exist without client or appointment association. | UC-04 | MVP |
| FR-04.4 | System shall allow optional association of a payment with a client. | UC-04 | MVP |
| FR-04.5 | System shall allow optional association of a payment with an appointment. | UC-04 | MVP |
| FR-04.6 | System shall allow updating an existing financial operation. | UC-04 | R2 |
| FR-04.7 | System shall allow removal (soft deletion) of a financial operation. | UC-04 | R2 |
| FR-04.8 | System shall automatically complete an appointment when a linked income payment is recorded. | BPMN Appointment L2 | MVP |
| FR-04.9 | System shall treat income payments as the source of truth for appointment pricing. | Discovery (Business Rule) | MVP |
| FR-04.10 | System shall not change appointment status based on expense operations. | BPMN Payment L1 | MVP |
| FR-04.11 | System shall recalculate appointment financial state when a linked income payment is updated or removed. | BPMN Payment L1 | R2 |

---

## FR-05 Reporting

| ID | Description | Source | Release |
|----|------------|--------|---------|
| FR-05.1 | System shall provide financial summary reports. | Discovery | R2 |
| FR-05.2 | System shall calculate reports based on recorded financial operations. | Discovery | MVP |
| FR-05.3 | System shall allow filtering reports by time period. | Discovery | R2 |

---

## FR-06 Calendar Synchronization

| ID | Description | Source | Release |
|----|------------|--------|---------|
| FR-06.1 | System shall create a calendar event when a planned appointment is created. | BPMN Calendar Sync L1 | MVP |
| FR-06.2 | System shall update calendar events when appointment details change. | BPMN Calendar Sync L1 | MVP |
| FR-06.3 | System shall update or remove calendar events when an appointment is cancelled. | BPMN Calendar Sync L1 | MVP |
| FR-06.4 | Calendar synchronization shall be one-way from the system to the external calendar. | BPMN Calendar Sync L1 | MVP |
| FR-06.5 | System shall store the result of calendar synchronization attempts. | BPMN Calendar Sync L1 | R2 |
| FR-06.6 | System shall retry calendar synchronization after failure. | BPMN Calendar Sync L1 | R2 |

---

## Summary

- **MVP** focuses on core salon operations: clients, appointments, payments, and basic calendar synchronization.
- **R2** adds resiliency, edit/delete flows, and reporting enhancements.
- This separation allows controlled delivery while preserving future scalability.

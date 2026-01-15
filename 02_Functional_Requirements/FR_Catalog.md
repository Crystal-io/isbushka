
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

## Summary

- **MVP focus:** core operations (clients, appointments, payments, calendar sync)
- **R2 focus:** edit/delete flows, reporting enhancements, resiliency
- **Future:** advanced analytics, role expansion, configuration UI

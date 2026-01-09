# Functional Requirements Catalog

## Purpose
This document contains atomic functional requirements derived from
use cases and high-level business requirements.

Functional requirements describe **what** the system shall do,
independent of implementation details.

---

## Legend
- FR — Functional Requirement
- UC — Use Case
- HL — High-Level Requirement

---

## FR-01 Client Management

### FR-01.1
System shall allow the administrator to create a client profile.

### FR-01.2
System shall allow the administrator to update client profile information.

---

## FR-02 Service Classification

### FR-02.1
System shall allow the administrator to maintain a list of service classifications.

### FR-02.2
Service classifications shall not define price or duration.

---

## FR-03 Appointment Management

### FR-03.1
System shall allow the administrator to create an appointment from a client context.

### FR-03.2
System shall automatically associate the appointment with the selected client.

### FR-03.3
System shall allow the administrator to select a service classification for an appointment.

### FR-03.4
System shall allow the administrator to specify appointment-specific duration.

### FR-03.5
System shall allow the administrator to reschedule an existing appointment.

### FR-03.6
System shall allow the administrator to cancel an appointment.

---

## FR-04 Financial Operations

### FR-04.1
System shall allow the administrator to record an income operation linked to an appointment.

### FR-04.2
System shall automatically set appointment status to **Completed**
when a linked income operation is recorded.

### FR-04.3
System shall allow the administrator to record income not linked to any appointment.

### FR-04.4
System shall allow the administrator to record expense operations
without client or appointment linkage.

### FR-04.5
System shall allow optional manual linking of a financial operation
to a client and/or appointment.

---

## FR-05 Reporting

### FR-05.1
System shall provide read-only financial summary reports for the owner.

### FR-05.2
System shall calculate reports based on recorded financial operations.

---

## FR-06 Calendar Synchronization

### FR-06.1
System shall create calendar events for planned appointments.

### FR-06.2
System shall update calendar events when appointment data changes.

### FR-06.3
System shall remove or update calendar events when appointments are cancelled.


# Functional Requirements Catalog

## Purpose

This document contains atomic functional requirements describing
**what** the ISBUSHKA system shall do.

Functional requirements are:
- implementation-independent
- testable
- derived from use cases and business rules

---

## Notation

- FR — Functional Requirement
- UC — Use Case

---

## FR-01 Client Management

### FR-01.1
System shall allow the administrator to create a client profile.

### FR-01.2
System shall allow the administrator to update client profile information.

### FR-01.3
System shall uniquely identify each client within the system.

---

## FR-02 Service Classification

### FR-02.1
System shall allow the administrator to maintain a list of service classifications.

### FR-02.2
System shall allow service classifications to be used for appointment categorization.

### FR-02.3
Service classifications shall not define price or duration.

---

## FR-03 Appointment Management

### FR-03.1
System shall allow the administrator to create an appointment **from a client context**.

### FR-03.2
System shall automatically associate a newly created appointment
with the selected client.

### FR-03.3
System shall allow the administrator to assign a service classification to an appointment.

### FR-03.4
System shall allow the administrator to assign a master to an appointment.

### FR-03.5
System shall allow the administrator to specify appointment date and time.

### FR-03.6
System shall allow the administrator to specify appointment-specific duration.

### FR-03.7
System shall allow the administrator to update appointment details.

### FR-03.8
System shall allow the administrator to cancel an appointment.

### FR-03.9
System shall prevent cancelled appointments from being completed or paid.

---

## FR-04 Financial Operations

### FR-04.1
System shall allow the administrator to record income operations.

### FR-04.2
System shall allow the administrator to record expense operations.

### FR-04.3
System shall allow financial operations to exist without association
to a client or appointment.

### FR-04.4
System shall allow the administrator to optionally associate
a financial operation with a client.

### FR-04.5
System shall allow the administrator to optionally associate
a financial operation with an appointment.

### FR-04.6
System shall automatically set appointment status to **Completed**
when an income operation associated with that appointment is recorded.

### FR-04.7
System shall treat recorded income operations as the source of truth
for appointment pricing.

---

## FR-05 Reporting

### FR-05.1
System shall provide read-only financial summary reports.

### FR-05.2
System shall calculate financial reports based on recorded financial operations.

### FR-05.3
System shall allow reports to be filtered by time period.

---

## FR-06 Calendar Synchronization

### FR-06.1
System shall create calendar events for planned appointments.

### FR-06.2
System shall update calendar events when appointment details change.

### FR-06.3
System shall update or remove calendar events when appointments are cancelled.

### FR-06.4
Calendar synchronization shall be one-way from the system to the external calendar.

---

## Notes

- Validation rules and user interaction flows are defined in detailed use case specifications.
- Process sequencing is defined in BPMN diagrams.

# UC-03 — Manage Appointments

## Use Case ID
UC-03

## Primary Actor
Administrator

## Goal
Create, update, or cancel appointments for a selected client
based on prior agreement with the master.

---

## Description
This use case allows the administrator to manage salon appointments
**from within a client context**.

An appointment is always associated with a specific client and is created
from the client card after agreement with the master.
Appointment pricing is **not** defined at this stage.

---

## Preconditions
- Administrator is authenticated
- Client exists in the system
- Service classification exists
- Master availability is confirmed offline

---

## Postconditions
- Appointment is saved or updated
- Appointment is visible in schedules
- Appointment is linked to the client
- Calendar event may be created or updated (derived data)

---

## Main Scenarios

### Scenario 1 — Create Appointment (from Client Card)

1. Administrator opens an existing client card
2. Administrator initiates appointment creation from the client card
3. System automatically assigns the client to the appointment
4. Administrator selects service (classification only)
5. Administrator selects master
6. Administrator specifies appointment date and time
7. Administrator specifies appointment-specific duration
8. Administrator saves appointment
9. System creates appointment with status **Planned**
10. System triggers one-way calendar synchronization

---

### Scenario 2 — Update / Reschedule Appointment

1. Administrator opens an existing appointment
2. Administrator modifies date, time, master, service, or duration
3. Administrator saves changes
4. System updates appointment data
5. System updates related calendar event

---

### Scenario 3 — Cancel Appointment

1. Administrator opens an existing appointment
2. Administrator selects cancel action
3. System marks appointment as **Cancelled**
4. System removes or updates calendar event

---

## Business Rules

- BR-01: Appointment can be created **only from a client card**
- BR-02: Appointment is always linked to exactly one client
- BR-03: Appointment duration is specified per appointment
- BR-04: Service classification does not define price or duration
- BR-05: Appointment price is not stored in appointment data
- BR-06: Cancelled appointments cannot be completed or paid

---

## Notes
- Appointment completion is handled automatically during payment recording
- Appointment data serves as operational context for financial operations

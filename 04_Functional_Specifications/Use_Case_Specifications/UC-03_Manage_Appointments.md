# UC-03 — Manage Appointments

## Use Case ID
UC-03

## Primary Actor
Administrator

## Goal
Create, update, or cancel appointments based on prior agreement with the master.

---

## Description
This use case allows the administrator to manage salon appointments.
An appointment is created only after agreement with the master and represents
a planned service session with explicitly defined parameters.

Appointment pricing is **not** defined at this stage.

---

## Preconditions
- Administrator is authenticated
- Client exists in the system
- Service classification exists
- Master is available based on offline agreement

---

## Postconditions
- Appointment is saved or updated
- Appointment is visible in schedules
- Calendar event may be created or updated (derived data)

---

## Main Scenarios

### Scenario 1 — Create Appointment

1. Administrator initiates appointment creation
2. Administrator selects client
3. Administrator selects service (classification only)
4. Administrator selects master
5. Administrator specifies appointment date and time
6. Administrator specifies appointment-specific duration
7. Administrator saves appointment
8. System creates appointment with status **Planned**
9. System triggers calendar synchronization (one-way)

---

### Scenario 2 — Update / Reschedule Appointment

1. Administrator opens existing appointment
2. Administrator modifies date, time, master, service, or duration
3. Administrator saves changes
4. System updates appointment data
5. System updates related calendar event

---

### Scenario 3 — Cancel Appointment

1. Administrator opens existing appointment
2. Administrator selects cancel action
3. System marks appointment as **Cancelled**
4. System removes or updates calendar event

---

## Business Rules

- BR-01: Appointment can be created only after agreement with the master
- BR-02: Appointment duration is specified per appointment
- BR-03: Service does not define price or duration
- BR-04: Appointment price is not stored in appointment data
- BR-05: Cancelled appointments cannot be completed or paid

---

## Notes
- Appointment completion is handled automatically during payment recording
- Appointment data serves as operational context for financial operations

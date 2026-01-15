# User Story: Cancel Appointment

## Story ID
US-03-02

---

## Description
As an administrator  
I want to cancel an existing appointment  
So that the appointment is no longer considered valid

---

## Related Use Case
- UC-03 — Manage Appointments (MVP)

---

## Related Requirements
- FR-03.8
- FR-03.9
- FR-03.10

---

## Acceptance Criteria

### AC-1: Successful cancellation
**Given** an appointment with status **Planned**  
**When** the administrator cancels the appointment  
**Then** the system updates the appointment status to **Cancelled**

---

### AC-2: Cancellation not allowed for completed appointments
**Given** an appointment with status **Completed**  
**When** the administrator attempts to cancel the appointment  
**Then** the system prevents cancellation  
**And** displays an appropriate message

---

### AC-3: No further actions after cancellation
**Given** an appointment with status **Cancelled**  
**When** the administrator attempts to create a payment for the appointment  
**Then** the system prevents the action

---

## Notes
- Cancelled appointments cannot be completed or paid.


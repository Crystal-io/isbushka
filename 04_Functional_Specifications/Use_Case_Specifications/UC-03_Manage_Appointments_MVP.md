# Use Case: Manage Appointments (MVP)

## Name
Manage Appointments (Create and Cancel)

---

## Actors
- Administrator
- ISBUSHKA System

---

## Preconditions
- Administrator is authenticated in the system.
- Client exists in the system and has status **Active**.
- Service classifications are available.
- Masters are available in the system.

---

## Main Scenario (Create Appointment)

1. Administrator opens a client profile.
2. Administrator initiates creation of a new appointment.
3. System opens the appointment creation form with the client preselected.
4. Administrator selects a service classification.
5. Administrator selects a master.
6. Administrator specifies appointment date and time.
7. Administrator specifies appointment duration.
8. System validates the provided data.
9. System creates a new appointment with status **Planned** and links it to the client.
10. System saves the appointment.
11. The use case is successfully completed.

---

## Alternative Scenarios

### Alternative Scenario 1: Validation Error
- If required data is missing or invalid,
- the system displays a validation error message,
- and requests the administrator to correct the data.

---

### Alternative Scenario 2: Client Is Archived
- If the client has status **Archived**,
- the system prevents appointment creation,
- and displays an appropriate message.

---

## Cancel Appointment

### Main Scenario (Cancel Appointment)

1. Administrator opens an existing appointment with status **Planned**.
2. Administrator initiates appointment cancellation.
3. System verifies the current appointment status.
4. System changes the appointment status to **Cancelled**.
5. System saves the updated appointment.
6. The use case is successfully completed.

---

### Alternative Scenario: Cancellation Not Allowed
- If the appointment has status **Completed**,
- the system prevents cancellation,
- and informs the administrator that the action is not allowed.

---

## Postconditions
- After successful creation:
  - The appointment is created with status **Planned**.
  - The appointment is linked to the client.
  - Appointment data is persisted in the system.
- After successful cancellation:
  - The appointment status is **Cancelled**.
  - Further payment or completion actions are not allowed.

---

## Business Rules
- Appointments can be created only from a client context (FR-03.1).
- Appointments can be cancelled only in status **Planned** (FR-03.8).
- Service price is not defined during appointment creation and is fixed only at payment creation (FR-04.8).
- Archived clients cannot have new appointments (FR-01.6 – R2).

---

## Related Requirements
- Functional Requirements:
  - FR-03.1 – FR-03.8
  - FR-02.2
  - FR-01.1 – FR-01.3
- BPMN:
  - Appointment Lifecycle — L1
  - Appointment Lifecycle — L2
- Scope:
  - MVP

---

## Notes
- Appointment update (reschedule / edit) is part of **R2** and is not included in this use case.
- Automatic appointment completion is handled through payment flows and is not part of UC-03 MVP.

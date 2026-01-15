# Use Case: Manage Clients (MVP)

## Name
Manage Clients (Create and Update)

---

## Actors
- Administrator
- ISBUSHKA System

---

## Preconditions
- Administrator is authenticated in the system.
- The system is available.
- Client data storage is accessible.

---

## Main Scenario (Create Client)

1. Administrator initiates client creation.
2. System opens the client creation form.
3. Administrator enters client details (e.g. name, contact information).
4. System validates the provided data.
5. System creates a new client profile with status **Active**.
6. System saves the client profile.
7. The use case is successfully completed.

---

## Alternative Scenarios

### Alternative Scenario 1: Validation Error
- If required client data is missing or invalid,
- the system displays a validation error message,
- and requests the administrator to correct the data.

---

## Update Client

### Main Scenario (Update Client)

1. Administrator opens an existing client profile.
2. Administrator initiates client editing.
3. Administrator updates client details.
4. System validates the updated data.
5. System saves the updated client profile.
6. The use case is successfully completed.

---

### Alternative Scenario: Update Not Allowed
- If the client profile cannot be updated due to a system or validation error,
- the system prevents saving changes,
- and displays an appropriate error message.

---

## Postconditions
- After successful creation:
  - A client profile exists in the system.
  - Client status is **Active**.
- After successful update:
  - Client data is updated and persisted.

---

## Business Rules
- Each client must be uniquely identifiable within the system (FR-01.3).
- Client creation and update do not affect existing appointments.
- Client archiving is not part of MVP and is handled in R2.

---

## Related Requirements
- Functional Requirements:
  - FR-01.1
  - FR-01.2
  - FR-01.3
- BPMN:
  - Client Lifecycle — L1
- Scope:
  - MVP

---

## Notes
- Client archiving and restrictions for archived clients are part of **R2**.
- No appointment or payment actions are triggered by this use case.

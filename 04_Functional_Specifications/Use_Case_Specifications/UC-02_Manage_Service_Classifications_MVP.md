# Use Case: Manage Service Classifications (MVP)

## Name
Manage Service Classifications

---

## Actors
- Administrator
- ISBUSHKA System

---

## Preconditions
- Administrator is authenticated in the system.
- The system is available.

---

## Main Scenario (Create Service Classification)

1. Administrator initiates creation of a new service classification.
2. System opens the service classification creation form.
3. Administrator enters service classification name and description.
4. System validates the provided data.
5. System creates a new service classification.
6. System saves the service classification.
7. The use case is successfully completed.

---

## Alternative Scenarios

### Alternative Scenario 1: Validation Error
- If required service classification data is missing or invalid,
- the system displays a validation error message,
- and requests the administrator to correct the data.

---

## Update Service Classification

### Main Scenario (Update Service Classification)

1. Administrator opens an existing service classification.
2. Administrator initiates editing of the service classification.
3. Administrator updates the service classification details.
4. System validates the updated data.
5. System saves the updated service classification.
6. The use case is successfully completed.

---

### Alternative Scenario: Update Not Allowed
- If the service classification cannot be updated due to a system or validation error,
- the system prevents saving changes,
- and displays an appropriate error message.

---

## Postconditions
- After successful creation:
  - A service classification exists in the system.
- After successful update:
  - Service classification data is updated and persisted.

---

## Business Rules
- Service classifications define **type of service only** and do not contain price or duration (FR-02.3).
- Service classifications are used only for appointment categorization.
- Removing service classifications is not part of MVP.

---

## Related Requirements
- Functional Requirements:
  - FR-02.1
  - FR-02.2
  - FR-02.3
- BPMN:
  - Appointment Lifecycle — L1
- Scope:
  - MVP

---

## Notes
- Deletion of service classifications is out of scope for MVP.
- Price and duration are defined per appointment and payment, not per service classification.

# Use Case: Manage Payments (MVP)

## Name
Manage Payments (Record Income and Expense)

---

## Actors
- Administrator
- ISBUSHKA System

---

## Preconditions
- Administrator is authenticated in the system.
- The system is available.
- (Optional) Client exists in the system.
- (Optional) Appointment exists in the system.

---

## Main Scenario (Record Income Payment)

1. Administrator initiates creation of a new payment.
2. System opens the payment creation form.
3. Administrator selects payment type **Income**.
4. Administrator enters payment amount.
5. Administrator optionally selects a client.
6. Administrator optionally selects an appointment.
7. System validates the provided data.
8. System creates an income payment record.
9. System links the payment to the selected client and/or appointment, if provided.
10. System saves the payment.
11. The use case is successfully completed.

---

## Alternative Scenarios

### Alternative Scenario 1: Validation Error
- If required payment data is missing or invalid,
- the system displays a validation error message,
- and requests the administrator to correct the data.

---

### Alternative Scenario 2: Appointment Not Selected
- If no appointment is selected,
- the system records the income payment as standalone,
- without linking it to an appointment.

---

## Record Expense Payment

### Main Scenario (Record Expense)

1. Administrator initiates creation of a new payment.
2. System opens the payment creation form.
3. Administrator selects payment type **Expense**.
4. Administrator enters payment amount and description.
5. Administrator optionally selects a client.
6. System validates the provided data.
7. System creates an expense payment record.
8. System saves the payment.
9. The use case is successfully completed.

---

## Postconditions
- After successful income creation:
  - An income payment record exists in the system.
  - The payment may be linked to a client and/or appointment.
- After successful expense creation:
  - An expense payment record exists in the system.
- Payment data is persisted in the system.

---

## Business Rules
- Payments can be of type **Income** or **Expense** (FR-04.1, FR-04.2).
- Payments may exist without a linked client or appointment (FR-04.3).
- Income payments represent the actual price of a service (FR-04.8).
- Expense payments do not affect appointment status.
- Updating or deleting payments is out of scope for MVP and handled in R2.

---

## Related Requirements
- Functional Requirements:
  - FR-04.1
  - FR-04.2
  - FR-04.3
  - FR-04.4
  - FR-04.8
- BPMN:
  - Payment Lifecycle — L1
- Scope:
  - MVP

---

## Notes
- Automatic appointment completion based on income payments is part of **R2**.
- Payment update and deletion are part of **R2**.
- Financial reporting is handled separately and is not part of this use case.

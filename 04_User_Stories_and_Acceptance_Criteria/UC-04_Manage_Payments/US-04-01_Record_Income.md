# User Story: Record Income Payment

## Story ID
US-04-01

---

## Description
As an administrator  
I want to record an income payment  
So that the salon can track received revenue

---

## Related Use Case
- UC-04 — Manage Payments (MVP)

---

## Related Requirements
- FR-04.1
- FR-04.3
- FR-04.4
- FR-04.8

---

## Acceptance Criteria

### AC-1: Record income payment successfully
**Given** the administrator is authenticated  
**When** the administrator creates an income payment with a valid amount  
**Then** the system creates an income payment record  
**And** saves it in the system

---

### AC-2: Link income to appointment (optional)
**Given** an existing appointment  
**When** the administrator links the income payment to the appointment  
**Then** the system associates the payment with the appointment

---

### AC-3: Standalone income payment
**Given** no appointment is selected  
**When** the administrator creates an income payment  
**Then** the system records the payment without appointment association

---

### AC-4: Validation error
**Given** invalid or missing payment amount  
**When** the administrator attempts to save the payment  
**Then** the system displays a validation error  
**And** does not create the payment

---

## Notes
- Income payment defines the actual service price.
- Appointment auto-completion is not part of MVP.

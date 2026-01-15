# User Story: Record Expense Payment

## Story ID
US-04-02

---

## Description
As an administrator  
I want to record an expense payment  
So that the salon can track operational costs

---

## Related Use Case
- UC-04 — Manage Payments (MVP)

---

## Related Requirements
- FR-04.2
- FR-04.3

---

## Acceptance Criteria

### AC-1: Record expense payment successfully
**Given** the administrator is authenticated  
**When** the administrator creates an expense payment with a valid amount  
**Then** the system creates an expense payment record  
**And** saves it in the system

---

### AC-2: Expense without client or appointment
**Given** no client or appointment is selected  
**When** the administrator records an expense payment  
**Then** the system records the payment as standalone

---

### AC-3: Validation error
**Given** invalid or missing expense amount  
**When** the administrator attempts to save the payment  
**Then** the system displays a validation error  
**And** does not create the payment

---

## Notes
- Expense payments do not affect appointment status.
- Expense categorization is out of scope for MVP.

# User Story: Create Client

## Story ID
US-01-01

---

## Description
As an administrator  
I want to create a client profile  
So that the client can be used for appointments and payments

---

## Related Use Case
- UC-01 — Manage Clients (MVP)

---

## Related Requirements
- FR-01.1
- FR-01.2

---

## Acceptance Criteria

### AC-1: Create client successfully
**Given** the administrator is authenticated  
**When** the administrator enters mandatory client data (name)  
**And** saves the client  
**Then** the system creates a client record  
**And** the client becomes available for appointments

---

### AC-2: Minimal required data
**Given** only client name is provided  
**When** the administrator saves the client  
**Then** the system creates the client successfully

---

### AC-3: Validation error
**Given** mandatory client data is missing  
**When** the administrator attempts to save the client  
**Then** the system displays a validation error  
**And** does not create the client

---

## Notes
- Client contact details are optional in MVP.
- Duplicate client names are allowed.

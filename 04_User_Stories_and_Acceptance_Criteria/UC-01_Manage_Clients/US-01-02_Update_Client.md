# User Story: Update Client

## Story ID
US-01-02

---

## Description
As an administrator  
I want to update client information  
So that client data remains accurate

---

## Related Use Case
- UC-01 — Manage Clients (MVP)

---

## Related Requirements
- FR-01.3

---

## Acceptance Criteria

### AC-1: Update client successfully
**Given** an existing client  
**When** the administrator edits client information  
**And** saves changes  
**Then** the system updates the client record

---

### AC-2: Partial update
**Given** only some fields are changed  
**When** the administrator saves the client  
**Then** the system updates only modified fields

---

### AC-3: Validation error
**Given** invalid client data  
**When** the administrator attempts to save changes  
**Then** the system displays a validation error  
**And** does not update the client

---

## Notes
- Client deletion or archiving is out of scope for MVP.

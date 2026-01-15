# User Story: Update Service Classification

## Story ID
US-02-02

---

## Description
As an administrator  
I want to update a service classification  
So that the list of services stays актуальной

---

## Related Use Case
- UC-02 — Manage Service Classification (MVP)

---

## Related Requirements
- FR-02.3

---

## Acceptance Criteria

### AC-1: Update service classification successfully
**Given** an existing service classification  
**When** the administrator edits the service name  
**And** saves changes  
**Then** the system updates the service classification

---

### AC-2: Impact on existing appointments
**Given** the service classification is already used in appointments  
**When** the service name is updated  
**Then** existing appointments remain linked to the updated service

---

### AC-3: Validation error
**Given** invalid service data  
**When** the administrator attempts to save changes  
**Then** the system displays a validation error  
**And** does not update the service

---

## Notes
- Service deletion is out of scope for MVP.

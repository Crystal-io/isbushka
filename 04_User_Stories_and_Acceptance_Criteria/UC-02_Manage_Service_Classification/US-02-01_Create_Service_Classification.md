# User Story: Create Service Classification

## Story ID
US-02-01

---

## Description
As an administrator  
I want to create a service classification  
So that it can be selected when creating an appointment

---

## Related Use Case
- UC-02 — Manage Service Classification (MVP)

---

## Related Requirements
- FR-02.1
- FR-02.2

---

## Acceptance Criteria

### AC-1: Create service classification successfully
**Given** the administrator is authenticated  
**When** the administrator enters a service name  
**And** saves the service  
**Then** the system creates a service classification  
**And** makes it available for appointment creation

---

### AC-2: Minimal required data
**Given** only service name is provided  
**When** the administrator saves the service  
**Then** the system creates the service successfully

---

### AC-3: Validation error
**Given** service name is missing  
**When** the administrator attempts to save the service  
**Then** the system displays a validation error  
**And** does not create the service

---

## Notes
- Service classification does not include price or duration.
- Duplicate service names are allowed.

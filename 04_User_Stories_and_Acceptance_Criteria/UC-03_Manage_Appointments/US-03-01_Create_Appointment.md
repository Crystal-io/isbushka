# User Story: Create Appointment

## Story ID
US-03-01

---

## Description
As an administrator  
I want to create an appointment for a client  
So that the client can receive a scheduled service at a specific time

---

## Related Use Case
- UC-03 — Manage Appointments (MVP)

---

## Related Requirements
- FR-03.1
- FR-03.2
- FR-03.3
- FR-03.4
- FR-03.5
- FR-03.6
- FR-03.7
- FR-02.2

---

## Acceptance Criteria

### AC-1: Successful appointment creation
**Given** an active client exists  
**And** service classifications are available  
**And** a master is available  
**When** the administrator creates an appointment with valid date, time, and duration  
**Then** the system creates the appointment  
**And** assigns status **Planned**  
**And** links the appointment to the client

---

### AC-2: Client context is mandatory
**Given** the administrator is not in a client profile  
**When** the administrator attempts to create an appointment  
**Then** the system prevents appointment creation

---

### AC-3: Validation error
**Given** an active client  
**When** the administrator submits the appointment form with missing or invalid data  
**Then** the system displays a validation error  
**And** does not create the appointment

---

### AC-4: Archived client restriction (R2 awareness)
**Given** a client with status **Archived**  
**When** the administrator attempts to create an appointment  
**Then** the system prevents appointment creation  
**And** displays an informative message

---

## Notes
- Appointment price is not defined at this stage.
- Appointment update is out of scope for MVP.


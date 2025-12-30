# 09. High-Level Requirements Backlog

## Purpose of This Document

This document defines the high-level requirements backlog for the ISBUSHKA project.
It translates discovery outcomes into structured Epics and Features that
describe *what* the system must support, without detailing implementation.

The backlog is used to:
- align requirements with business objectives
- support scope control and prioritization
- serve as a foundation for detailed requirements and use cases

---

## Backlog Structure

- **Epic** — a high-level business capability
- **Feature** — a specific system capability within an epic

Each epic and feature is traceable to:
- Business Objectives
- Personas
- Scope definition

---

## Backlog Overview

| Epic ID | Epic Name | Primary Persona | Business Objectives |
|-------|-----------|-----------------|---------------------|
| E-01 | Client Management | Administrator | BO-03, BO-04 |
| E-02 | Appointment Management | Administrator | BO-01, BO-03 |
| E-03 | Service Classification | Administrator | BO-05 |
| E-04 | Financial Operations | Administrator / Owner | BO-02, BO-04 |
| E-05 | Reporting and Analytics | Owner | BO-02, BO-05 |
| E-06 | Access Control and Roles | Owner | BO-04 |
| E-07 | External Calendar Sync (One-Way) | Administrator / Master | BO-01, BO-03 |

---

## E-01. Client Management

**Description**  
Support creation and maintenance of client information used across the system.

### Features

| Feature ID | Feature Name | Description | Personas |
|-----------|--------------|-------------|----------|
| F-01.1 | Create client | Create a new client profile | Administrator |
| F-01.2 | Edit client | Update client contact information | Administrator |
| F-01.3 | View client history | View client-related appointments and payments | Administrator |
| F-01.4 | Client identification | Uniquely identify clients in the system | Administrator |

---

## E-02. Appointment Management

**Description**  
Support scheduling and tracking of appointments agreed with masters.

### Features

| Feature ID | Feature Name | Description | Personas |
|-----------|--------------|-------------|----------|
| F-02.1 | Create appointment | Create appointment after agreement with master | Administrator |
| F-02.2 | Assign service | Assign service as procedure type | Administrator |
| F-02.3 | Specify duration | Define appointment-specific duration | Administrator |
| F-02.4 | Assign master | Associate appointment with a master | Administrator |
| F-02.5 | Update appointment | Modify date, time, or master | Administrator |
| F-02.6 | Complete appointment | Mark appointment as completed | Administrator |

---

## E-03. Service Classification

**Description**  
Maintain a controlled list of service types used for classification and reporting.

### Features

| Feature ID | Feature Name | Description | Personas |
|-----------|--------------|-------------|----------|
| F-03.1 | Manage services | Create and maintain service types | Owner / Administrator |
| F-03.2 | Use services in appointments | Reference services during appointment creation | Administrator |

> Services do not include price or duration.

---

## E-04. Financial Operations

**Description**  
Support recording and tracking of financial transactions.

### Features

| Feature ID | Feature Name | Description | Personas |
|-----------|--------------|-------------|----------|
| F-04.1 | Record income | Create income records with final agreed price | Administrator |
| F-04.2 | Record expense | Record operational expenses | Administrator |
| F-04.3 | Link payment to appointment | Associate income with completed appointment | Administrator |
| F-04.4 | Calculate balances | Calculate daily and monthly balances | Owner |

---

## E-05. Reporting and Analytics

**Description**  
Provide read-only visibility into salon performance.

### Features

| Feature ID | Feature Name | Description | Personas |
|-----------|--------------|-------------|----------|
| F-05.1 | Daily summary | View daily financial summary | Owner / Administrator |
| F-05.2 | Monthly summary | View monthly financial summary | Owner |
| F-05.3 | Performance by master | Analyze performance by staff | Owner |
| F-05.4 | Performance by service | Analyze results by service type | Owner |

---

## E-06. Access Control and Roles

**Description**  
Ensure data access is restricted based on user role.

### Features

| Feature ID | Feature Name | Description | Personas |
|-----------|--------------|-------------|----------|
| F-06.1 | Role-based access | Restrict access based on role | Owner |
| F-06.2 | Data visibility rules | Control data visibility per role | Owner |
| F-06.3 | Read-only reports | Enforce read-only access to reports | Owner |

---

## E-07. External Calendar Sync (One-Way)

**Description**  
Provide one-way synchronization from system appointments to Google Calendar.

### Features

| Feature ID | Feature Name | Description | Personas |
|-----------|--------------|-------------|----------|
| F-07.1 | Create calendar event | Create calendar event on appointment creation | Administrator |
| F-07.2 | Update calendar event | Update event on appointment change | Administrator |
| F-07.3 | Delete calendar event | Remove event on appointment cancellation | Administrator |
| F-07.4 | View-only calendar | Treat calendar as derived, read-only data | Master |

---

## Prioritization Notes

- Appointment management and financial operations are highest priority
- Reporting is dependent on data quality and structure
- Calendar sync is supportive, not core

Detailed prioritization is defined in `10_Prioritization_Model.md`.

---

## Traceability

This backlog is traceable to:
- Business Objectives (`01_Business_Objectives.md`)
- Personas and User Goals (`08_Personas_and_User_Goals.md`)
- Scope definition (`06_Scope.md`)
- Domain Decomposition (`05_Domain_Decomposition.md`)

---

## Next Steps

This high-level backlog will be used as a basis for:
- detailed requirements
- use case specifications
- process modeling (BPMN)
- data model refinement

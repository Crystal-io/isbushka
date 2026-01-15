# 06. Domain Decomposition

## Purpose of This Document

This document provides a high-level logical decomposition of the ISBUSHKA
business domain. It identifies core domain areas, key business concepts,
and their relationships without going into process flows or technical
implementation details.

Domain decomposition serves as a foundation for:
- scope definition
- data modeling (ERD)
- functional requirements
- business rules
- reporting structure

---

## Domain Decomposition Principles

- Focus on **business concepts**, not UI or implementation
- Avoid premature technical design
- Use stable, business-oriented terminology
- Separate concerns between different functional areas

---

## High-Level Domain Overview

The ISBUSHKA domain can be logically divided into the following areas:

1. Client Management
2. Service Catalog
3. Appointment Management
4. Staff (Masters) Management
5. Financial Management
6. Reporting and Analytics
7. System Configuration and Control

Each domain area represents a cohesive set of responsibilities and data.

---

## Domain Areas Description

### 1. Client Management

**Description**  
Manages information related to salon clients.

**Key Concepts**
- Client profile
- Contact information
- Client history

**Responsibilities**
- Store and maintain client data
- Identify clients uniquely
- Link clients to appointments and financial operations

**Notes**
- Clients do not directly interact with the system
- Client data includes personally identifiable information (PII)

---

### 2. Service Catalog

**Description**  
Represents the list of service types offered by the salon. Services define
*what kind of procedure is performed*, but do not contain fixed duration
or pricing.

**Key Concepts**
- Service (type of procedure)
- Service category (optional)

**Responsibilities**
- Maintain the list of available service types
- Serve as a semantic reference for appointments
- Support reporting and analytics by service type

**Notes**
- Services do NOT define fixed duration or price
- Duration and price are determined individually by the master
- Services act as classification rather than pricing entities

---

### 3. Appointment Management

**Description**  
Handles planning and tracking of client visits.

**Key Concepts**
- Appointment
- Appointment status
- Time slot

**Responsibilities**
- Schedule appointments
- Associate clients, services, and masters
- Track appointment lifecycle (planned → completed)

**Notes**
- Appointment is the central operational entity
- Scheduling rules are critical for data consistency

---

### 4. Staff (Masters) Management

**Description**  
Manages salon staff who provide services.

**Key Concepts**
- Master
- Role
- Availability (implicit)

**Responsibilities**
- Maintain list of masters
- Associate masters with appointments
- Support reporting by staff member

**Notes**
- Availability management is simplified at this stage
- Advanced scheduling constraints are out of scope

---

### 5. Financial Management

**Description**  
Tracks financial operations related to salon activity.

**Key Concepts**
- Financial operation
- Income
- Expense
- Balance

**Responsibilities**
- Record income from completed appointments
- Record operational expenses
- Calculate daily and monthly balances

**Notes**
- Financial operations are atomic records
- Calculated values are derived, not stored

---

### 6. Reporting and Analytics

**Description**  
Provides visibility into salon performance through aggregated data.

**Key Concepts**
- Report
- KPI
- Aggregation period

**Responsibilities**
- Aggregate operational and financial data
- Present summaries by period and staff
- Support basic business analytics

**Notes**
- Reports are read-only
- Focus is on operational and financial insights

---

### 7. System Configuration and Control

**Description**  
Defines system-level settings and governance.

**Key Concepts**
- User role
- Access control
- Configuration parameters

**Responsibilities**
- Manage user access and permissions
- Maintain system configuration
- Support auditability and control

**Notes**
- Configuration changes are limited
- Role-based access is essential

---

## Domain Relationships (Conceptual)

- A **Client** can have multiple **Appointments**
- An **Appointment** is associated with one **Client**, one **Service**, and one **Master**
- A completed **Appointment** may generate one or more **Financial Operations**
- **Services** define default parameters used by **Appointments**
- **Masters** are linked to **Appointments** and **Reports**
- **Reports** aggregate data from Appointments and Financial Operations

These relationships will be formalized in the data model (ERD).

---

## Domain Events (High-Level)

The following domain events occur within the system:

- Client created or updated
- Appointment scheduled
- Appointment completed
- Financial operation recorded
- Report generated
- “Appointment scheduled” may trigger “Calendar event created”

These events are used to reason about system behavior and data changes.

---

## Out of Scope Domain Areas

The following areas are explicitly excluded from the current domain model:

- Marketing and promotions
- Loyalty programs
- External payment processing
- Client self-service portals

---

## Traceability

This domain decomposition directly informs:
- Scope definition (`06_Scope.md`)
- Data model (ERD)
- Functional requirements
- Business rules catalog
- Reporting structure

---

## Discovery Notes

- The domain model is intentionally simple and modular
- Each domain area can evolve independently
- The decomposition supports future scaling without redesign



---

## Domain Clarification v2: Service, Duration, and Pricing Model

### Context

During further discovery and domain analysis, it was clarified that
ISBUSHKA operates with a highly individualized service delivery model.

Service duration and pricing are not fixed attributes and depend on
the master’s professional assessment and agreement with the client.

This clarification refines the initial domain assumptions and updates
the conceptual model accordingly.

---

### Updated Domain Principles

- Service represents a **type of procedure**, not a pricing unit
- Duration is defined **per appointment**, not per service
- Price is agreed individually and recorded **only at payment creation**
- The master is the primary source of truth for duration and price

---

### Clarified Domain Responsibilities

#### Service (Revised)

- Defines the type of procedure
- Used for classification and reporting
- Does **not** store price or duration

#### Appointment (Revised)

- Created only after agreement with the master
- Stores appointment-specific duration
- May exist without a finalized price

#### Financial Operation (Revised)

- Records the final agreed price
- Represents the monetary outcome of a completed appointment
- Is the only source of truth for service price

---

### Impact on System Design

This clarification impacts:
- data model (ERD)
- business rules
- UI behavior during appointment creation
- financial calculations and reporting

These impacts will be addressed in subsequent documentation.


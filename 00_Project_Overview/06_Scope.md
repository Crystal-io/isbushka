# 06. Project Scope

## Purpose of This Document

This document defines the scope of the ISBUSHKA project.
It clearly outlines what is included in the system (**In Scope**),
what is explicitly excluded (**Out of Scope**), and the boundaries
within which the system operates.

The scope is based on:
- Business Objectives
- Problem Statement (As-Is)
- Domain Decomposition (including domain clarifications)
- Assumptions and Constraints

---

## Scope Principles

- The system supports **business operations**, not business decisions
- The system records **agreed facts**, not assumptions
- Simplicity and transparency are prioritized over feature richness
- Individual service delivery is respected as a core business value

---

## In Scope

The following capabilities are included in the ISBUSHKA system.

### Client Management
- Creation and maintenance of client profiles
- Storage of basic contact information
- Linking clients to appointments and financial operations

---

### Appointment Management
- Creation of appointments **only after agreement with the master**
- Association of appointments with:
  - client
  - service (as procedure type)
  - master
- Explicit specification of appointment-specific duration
- Tracking appointment lifecycle (planned, completed)

---

### Service Classification
- Maintenance of a list of service types
- Use of services as **semantic classification**, not pricing entities
- Support for reporting and analytics by service type

> Services do not define fixed price or duration.

---

### Financial Operations
- Recording of financial operations (income and expenses)
- Creation of payment records with **final agreed price**
- Linking financial operations to completed appointments
- Calculation of daily and monthly financial summaries

---

### Reporting and Analytics
- Generation of basic operational reports
- Generation of financial summaries by:
  - time period
  - master
  - service type
- Read-only access to reports

---

### Access Control
- Role-based access to system data
- Separation of permissions between:
  - Owner
  - Administrator
  - Master
- Restricted visibility based on user role

---

## Out of Scope

The following capabilities are explicitly excluded from the current project scope.

### Pricing Management
- No fixed price lists
- No automated price calculation
- No price suggestion logic

Price is agreed manually and recorded only at payment creation.

---

### Advanced Scheduling
- No automated availability calculation
- No conflict resolution algorithms
- No optimization or load balancing logic

---

### Client Self-Service
- No client-facing interfaces
- No online booking
- No automated notifications to clients

---

### Marketing and CRM
- No promotions or discounts management
- No loyalty programs
- No marketing analytics

---

### External Integrations
- No payment gateway integrations
- No accounting system integrations
- No external calendar synchronization

---

## Scope Boundaries

- The system is designed for a **single salon**
- The system supports a **small operational team**
- Data is

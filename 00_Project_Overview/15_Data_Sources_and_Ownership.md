# 15. Data Sources and Ownership

## Purpose of This Document

This document defines data sources, ownership, and data responsibility
within the ISBUSHKA system.

Its purpose is to:
- clearly identify the **Source of Truth (SSOT)** for each data domain
- distinguish between primary and derived data
- prevent ambiguity in data updates and corrections
- support consistent reporting and integrations

---

## Core Data Principles

- Each data element has **one authoritative source**
- Derived data must not override source data
- External systems may consume data but do not control it
- Data ownership is explicitly assigned

---

## High-Level Data Architecture

The ISBUSHKA system uses the following components:

- **Google Sheets** — primary data storage and source of truth
- **AppSheet** — application layer for data input, validation, and presentation
- **Google Calendar** — derived, read-only representation of scheduled data

---

## Data Domains and Sources

### Data Source Matrix

| Data Domain | Data Entity | Source of Truth | Data Owner | Notes |
|------------|------------|-----------------|------------|------|
| Client Data | Client | Google Sheets | Salon Owner | Contains PII |
| Appointments | Appointment | Google Sheets | Administrator | Core operational data |
| Services | Service | Google Sheets | Salon Owner | Classification only |
| Staff | Master | Google Sheets | Salon Owner | Active staff list |
| Financials | Financial Operation | Google Sheets | Salon Owner | Legal relevance |
| Reports | Aggregated Data | Google Sheets (calculated) | Salon Owner | Read-only |
| Calendar View | Calendar Event | Google Calendar (derived) | System | Not a source of truth |

---

## Google Calendar Integration Clarification

### Integration Type

- **One-way synchronization**
- Direction: **System → Google Calendar**

### Purpose

Google Calendar is used as a **convenience visualization tool** for:
- viewing schedules
- sharing availability
- daily planning

It does **not** serve as a system of record.

---

### Calendar Data Characteristics

| Aspect | Description |
|-----|-------------|
| Creation | Triggered by appointment creation |
| Updates | Optional, system-driven |
| Deletion | Optional, system-driven |
| Manual edits | Not supported / ignored |
| Authority | Derived only |

---

### Source of Truth Rule

- Appointment data in Google Sheets is the **only authoritative source**
- Calendar events reflect appointment data at the time of creation/update
- Changes made directly in Google Calendar do **not** propagate back

This rule prevents:
- data conflicts
- accidental overwrites
- unclear ownership

---

## Data Ownership and Responsibility

### Ownership Model

| Role | Responsibility |
|----|----------------|
| Salon Owner | Data governance and correctness |
| Administrator | Accurate operational data entry |
| Master | Confirmation of service details |
| System | Data synchronization and derivation |

---

### Data Modification Rules

- Clients, appointments, and financial data are modified **only** via the system
- Calculated fields are not editable
- Derived data must be regenerated from source data if inconsistencies occur

---

## Error Handling and Reconciliation

In case of data inconsistency:

1. Google Sheets data is considered correct
2. Derived data (reports, calendar events) is regenerated
3. Manual correction of derived data is avoided

---

## Data Retention and History (High-Level)

- Operational data is retained for historical reporting
- No automated archival strategy is defined at this stage
- Auditability is supported via timestamps and system logs

---

## Security and Privacy Notes

- Client data contains personally identifiable information (PII)
- Access to PII is restricted based on role
- Calendar events may expose limited client data and must be reviewed
  for privacy compliance

---

## Traceability

This document is directly linked to:
- Scope definition (`06_Scope.md`)
- Domain decomposition (`05_Domain_Decomposition.md`)
- Assumptions and constraints (`04_Assumptions_Constraints_Dependencies.md`)
- Reporting and KPI definitions

---

## Governance

- Any new data source must be documented here
- Changes in data ownership require approval
- Integration changes must respect SSOT principles

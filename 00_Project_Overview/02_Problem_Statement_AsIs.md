# 02. Problem Statement (As-Is)

## Purpose of This Document

This document describes the current state of salon operations (**As-Is**),
key problems observed in day-to-day activities, their root causes, and
business impact.

The identified problems are directly linked to the Business Objectives
defined in `01_Business_Objectives.md` and serve as an input for:
- scope definition
- requirements prioritization
- solution design decisions

---

## Current State Overview (As-Is)

Salon operations are currently managed using a combination of manual
processes and basic tools that are not fully integrated.

Key operational areas such as appointment scheduling, financial tracking,
and reporting are handled separately, which leads to inconsistencies,
errors, and lack of transparency.

There is no single source of truth for operational and financial data.

---

## Key Problems Summary

| Problem ID | Problem Title | Affected Areas | Related Business Objectives |
|----------|---------------|----------------|-----------------------------|
| P-01 | Scheduling conflicts and inconsistencies | Appointments | BO-01, BO-03 |
| P-02 | Fragmented financial data | Finance | BO-02, BO-05 |
| P-03 | High manual effort in daily operations | Operations | BO-03, BO-04 |
| P-04 | Low data accuracy and error correction overhead | Data quality | BO-04 |
| P-05 | Limited visibility into business performance | Reporting | BO-02, BO-05 |
| P-06 | Lack of structural readiness for growth | Scalability | BO-06 |

---

## Detailed Problem Analysis

### P-01. Scheduling Conflicts and Inconsistencies

**Description**  
Appointments are created and managed manually or semi-manually, which can
result in overlapping bookings, incorrect time allocation, or mismatches
between clients, services, and staff.

**Root Causes**
- No centralized scheduling logic
- Manual time calculations
- Lack of validation rules

**Business Impact**
- Missed or delayed appointments
- Client dissatisfaction
- Revenue loss due to errors

**Related Business Objectives**
- BO-01 Reduce scheduling errors  
- BO-03 Reduce manual operational effort

---

### P-02. Fragmented Financial Data

**Description**  
Financial information (income, expenses, payments) is recorded in multiple
places or formats without a consolidated view.

**Root Causes**
- No unified financial tracking mechanism
- Manual reconciliation of records
- Absence of standard financial structure

**Business Impact**
- No real-time understanding of financial status
- Delayed or incorrect financial decisions
- Increased risk of discrepancies

**Related Business Objectives**
- BO-02 Improve financial transparency  
- BO-05 Enable basic business analytics

---

### P-03. High Manual Effort in Daily Operations

**Description**  
Daily operational tasks require significant manual input, including data
entry, updates, and cross-checking information between different records.

**Root Causes**
- Lack of automation or system-assisted workflows
- Redundant data entry
- No clear separation between calculated and input data

**Business Impact**
- Time loss for administrative staff
- Higher probability of errors
- Reduced focus on customer service

**Related Business Objectives**
- BO-03 Reduce manual operational effort  
- BO-04 Increase data accuracy

---

### P-04. Low Data Accuracy and Error Correction Overhead

**Description**  
Manual handling of operational and financial data leads to frequent errors
that require additional effort to identify and correct.

**Root Causes**
- Absence of validation rules
- Manual calculations
- No audit trail for changes

**Business Impact**
- Unreliable reports
- Additional operational overhead
- Reduced trust in data

**Related Business Objectives**
- BO-04 Increase data accuracy

---

### P-05. Limited Visibility into Business Performance

**Description**  
The business lacks structured reports and indicators that provide insight
into performance over time, by staff, or by service.

**Root Causes**
- Unstructured data storage
- No predefined KPIs
- Reporting relies on manual calculations

**Business Impact**
- Inability to assess profitability
- Reactive rather than proactive management
- Missed optimization opportunities

**Related Business Objectives**
- BO-02 Improve financial transparency  
- BO-05 Enable basic business analytics

---

### P-06. Lack of Structural Readiness for Growth

**Description**  
Current operational practices are tightly coupled to existing scale and
do not support easy extension (new services, staff, reporting needs).

**Root Causes**
- Ad-hoc data structures
- No documented system model
- No separation between core logic and presentation

**Business Impact**
- High cost of future changes
- Risk of system rework
- Limited scalability

**Related Business Objectives**
- BO-06 Support future scalability

---

## Problem Interdependencies

Several problems reinforce each other:

- High manual effort (**P-03**) increases error rate (**P-04**)
- Low data accuracy (**P-04**) limits reporting capabilities (**P-05**)
- Fragmented data (**P-02**) reduces financial transparency (**P-02**, **P-05**)

Understanding these dependencies is critical for correct prioritization.

---

## Discovery Notes

- Problems described above are typical for small service businesses
  transitioning from manual to system-based operations.
- Not all problems require immediate resolution; prioritization will be
  addressed in subsequent discovery documents.
- The focus of the solution is operational control and transparency,
  not feature richness.

---

## Next Steps

The identified problems will be used as inputs for:
- domain decomposition
- scope definition
- high-level requirements backlog

Detailed prioritization and solution design will follow in subsequent
documentation stages.


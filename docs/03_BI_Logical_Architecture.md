# BI Logical Architecture & Data Flow Design  
**Project:** Enterprise BI Reporting Lifecycle – Insurance Case Study  
**Document ID:** DOC-03  
**Version:** v1.0  
**Author:** <Your Name>  
**Role:** BI / Reporting Business Analyst  
**Date:** Week 2–3  

---

## 1. Purpose of the Document

The purpose of this document is to define the **logical BI architecture and high-level data flows** required to support the business requirements outlined in the Business Requirements Document (DOC-02).

This document:
- translates business needs into a **logical data processing view**
- provides a shared understanding between Business, BI, and IT stakeholders
- serves as input for detailed data modeling and technical design

This document is **technology-agnostic** and does not prescribe specific physical implementations.

---

## 2. Design Principles

The following principles guide the logical BI architecture:

- **Single source of truth:** KPIs should be calculated once and reused
- **Transparency:** Data origins and transformations must be explainable
- **Separation of concerns:** Source systems, data processing, and reporting are logically separated
- **Scalability:** The architecture should support future extensions
- **Governance readiness:** Definitions and ownership must be enforceable

---

## 3. High-Level BI Architecture Overview

The BI architecture is structured into the following logical layers:

1. Source Systems  
2. Data Integration & Staging  
3. BI Data Model  
4. Semantic / Reporting Layer  
5. Consumption Layer (Reports)

Each layer has a clear responsibility and ownership.

---

## 4. Source Systems (Logical View)

The following source systems are considered in scope for the initial phase:

### 4.1 Policy Administration System
- Policy creation and lifecycle events
- Product and policy attributes
- Customer-policy relationships

### 4.2 Claims Management System
- Claim registration and status
- Claim amounts and settlements
- Claim-related dates and classifications

### 4.3 Finance / Accounting System
- Aggregated financial figures
- Reconciliation reference values
- Financial calendar and periods

> Note: Specific system names are intentionally abstracted at this stage.

---

## 5. Data Integration & Staging Layer

### 5.1 Purpose

The staging layer provides:
- controlled ingestion of source data
- basic validation and harmonization
- isolation between source systems and BI logic

### 5.2 Logical Responsibilities

- Extract relevant datasets from source systems
- Apply basic data quality checks (completeness, format)
- Align common reference data (e.g. dates, product codes)
- Preserve raw historical data for traceability

No business aggregations or KPI calculations occur in this layer.

---

## 6. BI Data Model Layer (Logical)

### 6.1 Purpose

The BI data model layer:
- integrates data from multiple sources
- structures data for analytical use
- serves as the basis for consistent KPI calculation

### 6.2 Logical Modeling Approach

A **dimensional modeling approach** is assumed, separating:
- **Fact tables** (measurable events)
- **Dimension tables** (descriptive context)

At this stage, only logical entities are defined.

---

### 6.3 Core Logical Fact Entities

- **Claims Fact**
  - claim count
  - claim amount
  - settlement indicators

- **Policy Fact**
  - active policy count
  - policy lifecycle events

These facts will be analyzed across shared dimensions.

---

### 6.4 Core Logical Dimension Entities

- Time
- Product
- Customer / Segment
- Organizational Unit

Dimension definitions and attributes will be detailed in a separate document.

---

## 7. KPI Calculation Layer (Logical)

### 7.1 Responsibility

KPI calculations are logically centralized to:
- ensure consistency
- avoid duplication across reports
- support governance and documentation

KPIs are derived from:
- BI fact tables
- standardized dimension joins
- approved business logic

---

### 7.2 KPI Ownership

- Business owns **definitions and intent**
- BI owns **implementation and consistency**
- Finance validates **financial correctness**

This ownership model supports trust and accountability.

---

## 8. Semantic / Reporting Layer

### 8.1 Purpose

The semantic layer:
- translates data models into business-friendly structures
- hides technical complexity from end users
- enforces consistent metric usage

Examples include:
- predefined measures
- standardized naming conventions
- curated fields for reporting tools

---

### 8.2 Alignment with BI Tools

The semantic layer is designed to be consumed by:
- Power BI
- other reporting or visualization tools if required

Tool-specific implementation details are intentionally excluded.

---

## 9. Consumption Layer (Reports & Dashboards)

### 9.1 Report Types

The architecture supports:
- Executive management dashboards
- Operational performance reports
- Exploratory analytical views (within defined boundaries)

---

### 9.2 User Interaction Principles

- Reports are primarily **read-only**
- Filtering and slicing are controlled
- Free-form calculations by end users are minimized

This reduces misinterpretation and KPI misuse.

---

## 10. Data Flow Overview (End-to-End)

High-level logical flow:

1. Data extracted from source systems  
2. Data staged and validated  
3. Data integrated into BI fact and dimension structures  
4. KPIs calculated centrally  
5. Semantic layer exposes curated data  
6. Reports consume standardized metrics  

Each step is documented and traceable.

---

## 11. Data Quality & Control Considerations

Initial controls include:
- row count reconciliation
- key field completeness checks
- comparison against Finance reference figures

Detailed data quality rules will be defined in the testing phase.

---

## 12. Assumptions and Constraints

### Assumptions
- Source systems provide stable identifiers
- Historical data is available for agreed time ranges

### Constraints
- No real-time processing in the initial phase
- Architecture must align with corporate BI standards

---

## 13. Risks and Mitigation

| Risk | Mitigation |
|-----|-----------|
| Over-complex data model | Keep logical scope minimal |
| KPI logic spread across layers | Centralize calculations |
| Misalignment between business and BI | Early validation sessions |

---

## 14. Next Steps

The next phase focuses on:
- detailed logical data model definition
- KPI and metric specification
- business glossary alignment

These will be captured in:

> **Document 04 – Data Model & KPI Definitions**

---

*End of document*

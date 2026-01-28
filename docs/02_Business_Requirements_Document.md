# Business Requirements Document (BRD)  
**Project:** Enterprise BI Reporting Lifecycle – Insurance Case Study  
**Document ID:** DOC-02  
**Version:** v1.0  
**Author:** Agnes Offenbek
**Role:** BI / Reporting Business Analyst  
**Date:** Week 2  

---

## 1. Purpose of the Document

The purpose of this document is to capture, structure, and prioritize the **business requirements** for the insurance reporting and BI initiative.

This document translates high-level business needs into **clear, actionable, and testable requirements**, which will serve as the basis for:
- BI solution design
- data modeling
- report development
- testing and validation

This BRD is **business-focused** and avoids technical implementation details.

---

## 2. Scope of the Requirements

### 2.1 In Scope

- Management and operational reporting related to:
  - insurance policies
  - claims
  - aggregated financial performance
- Standardized KPI definitions
- Historical trend analysis
- Cross-departmental comparability of metrics

---

### 2.2 Out of Scope

- Predictive analytics or forecasting
- Machine learning–based insights
- Real-time or near-real-time reporting
- External regulatory reporting

---

## 3. Stakeholders and Roles

| Stakeholder Group | Responsibility |
|------------------|----------------|
| Executive Management | Defines strategic information needs |
| Finance / Controlling | Validates financial KPIs |
| Claims Operations | Provides operational requirements |
| Policy Management | Defines policy-related metrics |
| BI / Analytics Team | Designs and builds reports |
| Data Governance | Ensures standardization and data quality |

---

## 4. Business Objectives (Reconfirmed)

The BI solution must support the following objectives:

- Provide a **single, trusted source** for insurance performance reporting
- Enable consistent interpretation of KPIs across departments
- Reduce manual reconciliation and Excel-based reporting
- Improve transparency of metric definitions and data sources

---

## 5. Requirement Structure and Methodology

Requirements are structured using the following hierarchy:

- **Epic** – High-level business capability
- **Feature** – Logical grouping of related requirements
- **Business Requirement** – Specific, testable business need

Each requirement includes:
- unique ID
- description
- priority
- acceptance criteria

---

## 6. Business Requirements

---

### Epic 1: Executive-Level Performance Visibility

#### Feature 1.1: Standardized Management KPIs

**BR-01**  
**Description:**  
The system shall provide a standardized set of executive-level KPIs covering insurance performance.

**Priority:** High  

**Acceptance Criteria:**
- KPIs are consistently defined across all management reports
- Definitions are approved by Finance and Business stakeholders
- KPIs are documented and accessible to users

---

**BR-02**  
**Description:**  
The system shall enable trend analysis of executive KPIs over time.

**Priority:** High  

**Acceptance Criteria:**
- Historical data is available for agreed time periods
- Users can analyze KPI changes by month and year
- Trend views are consistent across reports

---

### Epic 2: Claims Performance Analysis

#### Feature 2.1: Claims Volume and Cost Monitoring

**BR-03**  
**Description:**  
The system shall allow business users to analyze claims volume and cost by key dimensions (e.g. product, time, customer segment).

**Priority:** High  

**Acceptance Criteria:**
- Claims metrics are available by agreed dimensions
- Aggregations match Finance-validated figures
- Users can identify high-level patterns and anomalies

---

**BR-04**  
**Description:**  
The system shall provide visibility into claims ratios and loss indicators.

**Priority:** Medium  

**Acceptance Criteria:**
- Ratio calculations are documented and approved
- Users can compare ratios across business units
- Results are reproducible and traceable

---

### Epic 3: Policy Portfolio Overview

#### Feature 3.1: Policy Lifecycle Reporting

**BR-05**  
**Description:**  
The system shall provide reporting on policy portfolio size and composition.

**Priority:** Medium  

**Acceptance Criteria:**
- Policy counts are consistent across reports
- Users can filter by product and time period
- Metrics align with Policy Management expectations

---

**BR-06**  
**Description:**  
The system shall enable high-level monitoring of policy changes over time.

**Priority:** Low  

**Acceptance Criteria:**
- Trends are visible at an aggregated level
- Definitions are clearly documented
- Data limitations are transparently communicated

---

### Epic 4: Data Transparency and Trust

#### Feature 4.1: Metric Documentation and Traceability

**BR-07**  
**Description:**  
The system shall provide business-accessible documentation for KPIs and metrics.

**Priority:** High  

**Acceptance Criteria:**
- Each KPI has a clear business definition
- Source systems are documented
- Calculation logic is described in business terms

---

**BR-08**  
**Description:**  
The system shall support traceability between reported figures and source data.

**Priority:** Medium  

**Acceptance Criteria:**
- Users can identify the origin of key figures
- Reconciliation logic is documented
- Known limitations are clearly stated

---

## 7. Non-Functional Requirements

### NFR-01: Data Refresh

- Reports shall be refreshed according to an agreed schedule
- Refresh frequency must be clearly communicated to users

---

### NFR-02: Performance and Usability

- Reports must load within acceptable timeframes
- Visuals must be clear and interpretable for non-technical users

---

### NFR-03: Security and Access Control

- Access to reports must align with user roles
- Sensitive information must be appropriately restricted

---

## 8. Dependencies and Assumptions

### Dependencies
- Availability of required data from source systems
- Timely stakeholder feedback during validation phases

### Assumptions
- Existing BI tooling (e.g. Power BI) remains in use
- Historical data quality is sufficient for trend analysis

---

## 9. Risks and Mitigation

| Risk | Mitigation |
|-----|-----------|
| KPI definition conflicts | Early stakeholder validation |
| Scope creep | Formal prioritization and change control |
| Data quality issues | Transparent documentation and testing |

---

## 10. Approval and Next Steps

This BRD represents the **initial baseline** of business requirements and will be refined iteratively.

### Next Steps:
- Translate business requirements into logical BI design
- Define data model and data flows
- Prepare test strategy and test cases

These activities will be documented in:

> **Document 03 – BI Logical Architecture & Data Flow Design**

---

*End of document*

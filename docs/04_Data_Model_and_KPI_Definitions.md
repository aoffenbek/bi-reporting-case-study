# Logical Data Model & KPI Definitions  
**Project:** Enterprise BI Reporting Lifecycle – Insurance Case Study  
**Document ID:** DOC-04  
**Version:** v1.0  
**Author:** Agnes Offenbek  
**Role:** BI / Reporting Business Analyst  
**Date:** Week 3–4  

---

## 1. Purpose of the Document

The purpose of this document is to define the **logical data model** and **business-approved KPI definitions** required to support enterprise BI reporting.

This document:
- translates business requirements into analytical structures
- defines facts, dimensions, and their relationships
- establishes a single, governed set of KPIs
- serves as the foundation for semantic models and reporting

This is a **logical design document** and does not describe physical tables or tool-specific implementations.

---

## 2. Scope

In scope:
- Core analytical subject areas (Policies and Claims)
- Logical fact and dimension entities
- KPI definitions aligned with business terminology
- Calculation logic at a conceptual level

Out of scope:
- Physical database schema
- Performance optimization
- Tool-specific expressions (e.g. DAX, SQL)

---

## 3. Modeling Approach

### 3.1 Chosen Modeling Paradigm

A **dimensional modeling approach** is used, consisting of:
- **Fact entities** representing measurable business events
- **Dimension entities** providing descriptive context

This approach is chosen to:
- simplify analytical queries
- support intuitive reporting
- ensure KPI consistency

---

### 3.2 Grain Definition

Each fact entity has a clearly defined grain:

- **Claims Fact:** one record per claim event
- **Policy Fact:** one record per policy per lifecycle state

Grain clarity is critical to prevent incorrect aggregations.

---

## 4. Logical Fact Entities

### 4.1 Claims Fact

**Business Description:**  
Represents insurance claim events raised by customers.

**Grain:**  
One record per claim.

**Key Measures (Logical):**
- Claim Count
- Claim Amount (Gross)
- Settled Claim Amount
- Outstanding Claim Amount

**Key Identifiers:**
- Claim ID
- Policy ID
- Claim Date Key

---

### 4.2 Policy Fact

**Business Description:**  
Represents insurance policies and their lifecycle status.

**Grain:**  
One record per policy per status period.

**Key Measures (Logical):**
- Active Policy Indicator
- Policy Count
- Premium Amount (if applicable)

**Key Identifiers:**
- Policy ID
- Policy Start Date Key
- Policy End Date Key

---

## 5. Logical Dimension Entities

### 5.1 Time Dimension

**Purpose:**  
Provides consistent time-based analysis across all facts.

**Key Attributes:**
- Date
- Day / Month / Quarter / Year
- Fiscal Period
- Reporting Period Flag

---

### 5.2 Product Dimension

**Purpose:**  
Enables analysis by insurance product and coverage type.

**Key Attributes:**
- Product Code
- Product Name
- Product Category
- Coverage Type

---

### 5.3 Customer / Segment Dimension

**Purpose:**  
Supports customer and portfolio segmentation analysis.

**Key Attributes:**
- Customer ID
- Customer Type
- Segment
- Risk Category

---

### 5.4 Organizational Unit Dimension

**Purpose:**  
Allows performance analysis by internal structure.

**Key Attributes:**
- Business Unit
- Region
- Sales Channel
- Organizational Hierarchy Level

---

## 6. Fact-to-Dimension Relationships

### 6.1 Claims Fact Relationships

- Claims Fact → Time Dimension (Claim Date)
- Claims Fact → Product Dimension
- Claims Fact → Customer Dimension
- Claims Fact → Organizational Unit Dimension

---

### 6.2 Policy Fact Relationships

- Policy Fact → Time Dimension
- Policy Fact → Product Dimension
- Policy Fact → Customer Dimension
- Policy Fact → Organizational Unit Dimension

Conformed dimensions ensure cross-subject analysis.

---

## 7. KPI Definitions

### 7.1 KPI Governance Principles

All KPIs:
- have a single business definition
- are calculated centrally
- are reusable across reports
- are documented and versioned

---

### 7.2 Core KPIs

#### 7.2.1 Total Claims Count

**Business Definition:**  
Number of insurance claims registered in the selected period.

**Calculation Logic:**  
Count of Claim ID.

**Granularity:**  
Time, Product, Customer, Organization.

---

#### 7.2.2 Total Claim Amount

**Business Definition:**  
Total gross monetary value of registered claims.

**Calculation Logic:**  
Sum of Claim Amount.

**Notes:**  
Excludes recoveries unless explicitly stated.

---

#### 7.2.3 Settled Claims Ratio

**Business Definition:**  
Proportion of claims that have been settled.

**Calculation Logic:**  
Settled Claims Count ÷ Total Claims Count.

---

#### 7.2.4 Active Policy Count

**Business Definition:**  
Number of policies active during the selected period.

**Calculation Logic:**  
Count of Policy ID where Active Indicator = true.

---

#### 7.2.5 Claims per Policy

**Business Definition:**  
Average number of claims per active policy.

**Calculation Logic:**  
Total Claims Count ÷ Active Policy Count.

---

## 8. Business Glossary (Initial)

| Term | Definition |
|----|-----------|
| Claim | A request for compensation under an insurance policy |
| Policy | A contract between insurer and customer |
| Active Policy | A policy valid within a given time period |
| Settled Claim | A claim with finalized payment |

This glossary will be expanded and governed.

---

## 9. Data Validation Considerations

Initial validation rules:
- Claim counts must reconcile with source systems
- Financial KPIs must align with Finance reference figures
- Policy counts must match operational dashboards

Validation ownership:
- Business validates meaning
- BI validates consistency
- Finance validates amounts

---

## 10. Assumptions & Open Questions

### Assumptions
- One claim is linked to one policy
- Policy status history is available

### Open Questions
- Treatment of reopened claims
- Handling of mid-period policy cancellations
- Inclusion/exclusion of reinsurance

These will be clarified in stakeholder workshops.

---

## 11. Change Management

All changes to:
- KPI logic
- dimension attributes
- grain definitions  

must follow formal change approval and versioning.

---

## 12. Next Steps

The next phase focuses on:
- semantic layer design
- report mapping to KPIs
- security and access considerations

These will be documented in:

> **Document 05 – Semantic Layer & Reporting Mapping**

---

*End of document*

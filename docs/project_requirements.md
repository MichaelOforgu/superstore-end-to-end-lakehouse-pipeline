# Project Requirements (PRD)  
## Superstore Sales Lakehouse – Azure Data Platform

---

# 1. Purpose

This document defines the functional and non-functional requirements for implementing a cloud-based data platform to ingest, transform, store, and serve Superstore sales data from an on-premises SQL Server environment.

The objective is to establish a reliable, scalable, and governed analytics foundation.

---

# 2. Business Objectives

- Centralize sales and master data into a unified cloud platform  
- Enable reliable daily reporting and analytics  
- Improve data quality and governance  
- Reduce manual data preparation efforts  
- Support future scalability and analytics expansion  

---

# 3. Scope

## In Scope
- Extraction of defined datasets from on-prem SQL Server  
- Automated daily data ingestion  
- Implementation of layered data processing (Raw, Standardized, Analytics-ready)  
- Structured analytical data modeling  
- Secure role-based access control  
- Monitoring and operational readiness  

## Out of Scope
- Real-time streaming ingestion  
- Machine learning model deployment  
- External third-party integrations  
- Advanced predictive analytics workloads  

---

# 4. Functional Requirements

## 4.1 Data Ingestion
- The system shall extract required tables from SQL Server.
- The system shall support an initial full data load.
- The system shall support incremental daily data loads.
- The system shall log execution status and failures.

## 4.2 Data Processing
- The system shall cleanse and standardize data.
- The system shall handle nulls, duplicates, and invalid records.
- The system shall apply defined business transformation rules.

## 4.3 Data Modeling
- The system shall implement an analytics-ready data model.
- The system shall provide fact and dimension structures for reporting.

## 4.4 Data Availability
- The system shall make processed data available for reporting daily.
- Data availability SLA: 08:00 AM UTC.

---

# 5. Non-Functional Requirements

## 5.1 Performance
- Daily data processing must complete within a 2-hour window.
- The platform must support 10× projected data growth without architectural redesign.

## 5.2 Reliability
- ≥ 99% scheduled pipeline execution success rate.
- Automatic retry for transient failures.

## 5.3 Security
- Data must be encrypted at rest and in transit.
- Access must be governed through role-based access control.
- Credentials must not be hardcoded.

## 5.4 Governance
- Data lineage must be traceable.
- Data ownership must be defined.
- Metadata must be documented.

## 5.5 Scalability
- The platform must support independent scaling of storage and compute resources.

---

# 6. Compliance & Risk Considerations

- Secure handling of potentially sensitive data.
- Controlled access to production datasets.
- Monitoring for operational failures and performance degradation.

---

# 7. Acceptance Criteria

- All defined source tables successfully ingested.
- Incremental loading validated and operational.
- Data reconciliation variance < 0.1%.
- Daily data availability meets SLA.
- Monitoring and alerting operational.
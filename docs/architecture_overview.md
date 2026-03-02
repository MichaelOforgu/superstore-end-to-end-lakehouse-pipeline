# Architecture Overview (HLD)  
## Superstore Sales Lakehouse – Azure Data Platform

---

# 1. Architecture Objective

Provide a scalable and secure Lakehouse architecture that fulfills the approved project requirements for ingestion, transformation, storage, and analytics enablement.

---

# 2. Architectural Design Approach

The solution follows a modern cloud-native Lakehouse architecture built on separation of storage and compute, modular services, and Infrastructure-as-Code deployment.

Key design principles:
- Layered data processing
- Decoupled ingestion and transformation
- Secure-by-design
- Environment isolation
- Automated deployment

---

# 3. Component Architecture

## Source Layer
- On-premises SQL Server hosting transactional datasets.

## Ingestion & Orchestration Layer
- Azure Data Factory orchestrates extraction workflows.
- Self-Hosted Integration Runtime enables secure on-prem connectivity.

## Storage Layer
- Azure Data Lake Storage Gen2 serves as the centralized storage platform.
- Data is organized into logical zones aligned with processing stages.

## Processing Layer
- Azure Databricks performs distributed transformations.
- Business logic and data standardization implemented via Spark workloads.

## Serving Layer
- Gold datasets exposed for analytical consumption.
- Power BI connects to curated data models.

## Supporting Services
- Azure Key Vault for secret management.
- Role-Based Access Control for access governance.
- Bicep templates for infrastructure provisioning.

---

# 4. Data Layering Strategy

The architecture implements a structured Lakehouse layering model:

### Bronze
Raw ingestion zone maintaining source-aligned datasets.

### Silver
Standardized and validated datasets prepared for analytical modeling.

### Gold
Curated star schema optimized for BI consumption.

---

# 5. Security Architecture

- Secure network communication via Self-Hosted Integration Runtime.
- Encryption at rest and in transit.
- RBAC enforcement at storage and workspace levels.
- Secret isolation through Azure Key Vault.

---

# 6. Deployment Architecture

- Infrastructure provisioned using Bicep templates.
- Parameterized configurations across Dev, Test, and Prod environments.
- CI/CD pipeline enables controlled promotion.

---

# 7. Scalability & Performance Design

- Columnar Parquet storage for optimized reads.
- Partitioned fact datasets.
- Elastic compute clusters in Databricks.
- Independent scaling of storage and compute.

---

# 8. Observability & Reliability

- Centralized pipeline monitoring.
- Job-level execution tracking.
- Alerting for failures and SLA breaches.
- Cost monitoring for usage optimization.

---

# 9. Architectural Outcome

The architecture delivers a modular, secure, and scalable data platform capable of supporting reliable ingestion, governed transformation, and analytics-ready consumption.
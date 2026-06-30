---
title: "Enmark Cloud ETL — Multi-Tenant Near Real-Time Data Synchronization"
type: use-case
status: draft
date: "2024-Q2"
domain: "ERP Business Software"
client: "Enmark Systems, Inc."
technologies: [".NET 8", "Azure Kubernetes Service", "MySQL", "Azure SQL", "CDC", "Helm", "Azure DevOps"]
experts: ["@IuriiS", "@AnastasiiaV", "@AndreeaM", "@AnhelinaL"]
tags: ["ETL", "DataSynchronization", "CloudMigration", "MultiTenant", "CDC"]
---

# Enmark Cloud ETL — Multi-Tenant Near Real-Time Data Synchronization

> **One-liner summary** — Designed and built a multi-tenant Cloud ETL application to synchronize legacy on-premises databases with a web-based reporting system in near real-time. This solution allowed seamless client onboarding and ensured accurate, data-driven reporting for end-users.

---

## Problem Overview

Enmark needed to integrate their new multi-tenant web-based reporting system (EnVision) with existing legacy, on-premises MS SQL Server databases. The primary goal was to replicate an old set of Crystal Reports while ensuring near real-time data accuracy across over 300 companies and 3,000 users throughout North America. The core legacy codebase presented significant engineering challenges due to its age and original structure, requiring a robust mid-tier solution to handle data synchronization without degrading on-premises performance.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Legacy Code Obstacles** | The core system relied on complex legacy code built over 15 years prior, making straight-to-cloud integration difficult. |
| 2 | **Near Real-Time Accuracy** | Data had to be synchronized in near real-time from distributed, on-premises client nodes into a centralized cloud platform. |
| 3 | **Multi-Tenancy Isolation** | The architecture needed to securely isolate and orchestrate data flows for multiple distinct customer databases simultaneously. |
| 4 | **Cost & Effort Optimization** | The initial phase required minimizing cloud resource costs and deployment efforts while remaining highly scalable for future growth. |

---

## Proposed Solution

INSART designed and developed a specialized multi-tenant Cloud ETL application using a containerized architecture on Azure. To track modifications efficiently without placing an undue load on production environments, Change Data Capture (CDC) was selected as the core tracking mechanism. 

Since the load was determined to be permanent and predictable, the system utilized .NET 8 Worker Services deployed via Azure Kubernetes Service (AKS) and Helm. To keep initial infrastructure costs low, a dedicated database table was strategically chosen to act as the primary message queue for the first stage of development.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **ETL Administrator User** | Responsible for managing global configurations and overseeing customer database onboarding. |
| **EnVision Platform / Tenants** | End customers whose on-premises databases supply the raw data for real-time reporting. |

---

## Process / Solution Flow

The data synchronization functions end-to-end through both initial synchronization (onboarding) and subsequent delta updates at pre-defined intervals:

1. **Data Extraction** — Data is safely extracted from the source on-premises databases directly into a cloud Snapshot table using Bulk Copy protocols.
2. **Data Merge** — The system executes a high-performance merge of the Snapshot and Staging tables to properly isolate and generate Change Data Capture (CDC) records.
3. **Batches Creation** — Organized data batches are automatically created based on the isolated CDC data.
4. **API Execution** — The application converts these compiled batches into clean API requests and transmits them to the Data Push endpoints of the EnVision reporting system.

<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/b2b-infrastructure/enmark_data_flow.png" width="600">

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Backend / Workers** | .NET 8 Worker Services  | Permanent and predictable processing load. |
| **Orchestration** | Azure Kubernetes Service (AKS), Helm  | Handles container management and deployment structures. |
| **Database (Staging/Config)** | Azure Database for MySQL, Azure SQL VM  | MySQL manages configuration; SQL VM handles staging with CDC enabled. |
| **Infrastructure / DevOps** | Azure DevOps Pipelines, Container Registry  | Automates build, deployment, and cloud security containment. |
| **Monitoring & Security** | Azure Application Insights, Azure Key Vault  | Provides full application performance monitoring and secret management. |

<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/b2b-infrastructure/enmark_architecture.png" width="600">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/b2b-infrastructure/enmark_deployment.png" width="600">

---

## Business Outcome

- **Accelerated Onboarding** — Successfully automated the onboarding flow, connecting 3 active clients to the system immediately following launch at a steady pace of approximately one client per week.
- **High Client Satisfaction** — Delivered a recognized achievement that made the client highly satisfied, proving that high-performing cloud reporting can be built on top of challenging legacy foundations.
- **Subsequent Phase Enablement** — The architecture was designed to seamlessly scale; it is fully ready to integrate advanced auto-scaling (HPA/KEDA) and read-only asynchronous replicas for premium subscribers in later iterations.

---

## Lessons Learned

- **Database Tables as Temporary Queues** — For the early stages of a project, utilizing a structured database table as a message queue is an exceptionally effective pattern to minimize initial infrastructure efforts and cloud costs.
- **Predictable Load Optimization** — Choosing Kubernetes-bound Worker Services over serverless functions (like Azure Functions) is highly optimal when processing loads are permanent and well-predicted.

---

## Reusable Components / Patterns

- [x] Architecture schema for Multi-Tenant Cloud ETL processing.
- [x] Standardized CDC-to-API batching and mapping data flow.

---

## Resources

| Resource | Link |
|---|---|
| Code Repository | *[to be added]* |
| Slide Deck | [`[EB] Service Delivery Meeting (29.05.2024)`](https://docs.google.com/presentation/d/1SfdlgZJLSUgA-IjnWMZM732WYYUe0GJH6eGhZWA7eCQ/edit?usp=sharing) |
| System Architecture | Documented in Cloud ETL Architecture Slide  |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Iurii S.** | Technical Lead  |
| **Anastasiia V.** | .NET Developer  |
| **Andreea M.** | Reporting Specialist  |
| **Anhelina L.** | Business Analyst  |

<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/b2b-infrastructure/enmark_insart_team.png" width="600">


---
_Last updated: 2024-Q2 · Status: draft_ 

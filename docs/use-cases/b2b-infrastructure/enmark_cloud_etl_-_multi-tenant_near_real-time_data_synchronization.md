---
title: "Enmark Cloud ETL — Multi-Tenant Near Real-Time Data Synchronization"
type: use-case
status: draft
date: "2024-Q2"
domain: "FinTech"
client: "Enmark Systems, Inc."
technologies: [".NET 8", "Azure Kubernetes Service", "MySQL", "Azure SQL", "CDC", "Helm", "Azure DevOps"]
experts: ["@IuriiS", "@AnastasiiaV", "@AndreeaM", "@AnhelinaL"]
tags: ["ETL", "DataSynchronization", "CloudMigration", "MultiTenant", "CDC"]
---

# Enmark Cloud ETL — Multi-Tenant Near Real-Time Data Synchronization

> [cite_start]**One-liner summary** — Designed and built a multi-tenant Cloud ETL application to synchronize legacy on-premises databases with a web-based reporting system in near real-time[cite: 56, 93]. [cite_start]This solution allowed seamless client onboarding and ensured accurate, data-driven reporting for end-users[cite: 33, 93].

---

## Problem Overview

[cite_start]Enmark needed to integrate their new multi-tenant web-based reporting system (EnVision) with existing legacy, on-premises MS SQL Server databases[cite: 93]. [cite_start]The primary goal was to replicate an old set of Crystal Reports while ensuring near real-time data accuracy across over 300 companies and 3,000 users throughout North America[cite: 10, 93]. [cite_start]The core legacy codebase presented significant engineering challenges due to its age and original structure, requiring a robust mid-tier solution to handle data synchronization without degrading on-premises performance[cite: 129, 157].

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Legacy Code Obstacles** | [cite_start]The core system relied on complex legacy code built over 15 years prior, making straight-to-cloud integration difficult[cite: 157]. |
| 2 | **Near Real-Time Accuracy** | [cite_start]Data had to be synchronized in near real-time from distributed, on-premises client nodes into a centralized cloud platform[cite: 93]. |
| 3 | **Multi-Tenancy Isolation** | [cite_start]The architecture needed to securely isolate and orchestrate data flows for multiple distinct customer databases simultaneously[cite: 56, 93]. |
| 4 | **Cost & Effort Optimization** | [cite_start]The initial phase required minimizing cloud resource costs and deployment efforts while remaining highly scalable for future growth[cite: 101, 105]. |

---

## Proposed Solution

[cite_start]INSART designed and developed a specialized multi-tenant Cloud ETL application using a containerized architecture on Azure[cite: 56, 72]. [cite_start]To track modifications efficiently without placing an undue load on production environments, Change Data Capture (CDC) was selected as the core tracking mechanism[cite: 103]. 

[cite_start]Since the load was determined to be permanent and predictable, the system utilized .NET 8 Worker Services deployed via Azure Kubernetes Service (AKS) and Helm[cite: 71, 72, 79, 99]. [cite_start]To keep initial infrastructure costs low, a dedicated database table was strategically chosen to act as the primary message queue for the first stage of development[cite: 105].

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **ETL Administrator User** | [cite_start]Responsible for managing global configurations and overseeing customer database onboarding[cite: 108]. |
| **EnVision Platform / Tenants** | [cite_start]End customers whose on-premises databases supply the raw data for real-time reporting[cite: 93, 108]. |

---

## Process / Solution Flow

[cite_start]The data synchronization functions end-to-end through both initial synchronization (onboarding) and subsequent delta updates at pre-defined intervals[cite: 95, 96]:

1. [cite_start]**Data Extraction** — Data is safely extracted from the source on-premises databases directly into a cloud Snapshot table using Bulk Copy protocols[cite: 110].
2. [cite_start]**Data Merge** — The system executes a high-performance merge of the Snapshot and Staging tables to properly isolate and generate Change Data Capture (CDC) records[cite: 111].
3. [cite_start]**Batches Creation** — Organized data batches are automatically created based on the isolated CDC data[cite: 112].
4. [cite_start]**API Execution** — The application converts these compiled batches into clean API requests and transmits them to the Data Push endpoints of the EnVision reporting system[cite: 113].

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Backend / Workers** | [cite_start].NET 8 Worker Services [cite: 71] | [cite_start]Permanent and predictable processing load[cite: 99]. |
| **Orchestration** | [cite_start]Azure Kubernetes Service (AKS), Helm [cite: 72, 79] | [cite_start]Handles container management and deployment structures[cite: 99]. |
| **Database (Staging/Config)** | [cite_start]Azure Database for MySQL, Azure SQL VM [cite: 73, 74] | MySQL manages configuration; [cite_start]SQL VM handles staging with CDC enabled[cite: 74, 107]. |
| **Infrastructure / DevOps** | [cite_start]Azure DevOps Pipelines, Container Registry [cite: 77, 78] | [cite_start]Automates build, deployment, and cloud security containment[cite: 55]. |
| **Monitoring & Security** | [cite_start]Azure Application Insights, Azure Key Vault [cite: 75, 76] | [cite_start]Provides full application performance monitoring and secret management[cite: 75, 76]. |

---

## Business Outcome

- [cite_start]**Accelerated Onboarding** — Successfully automated the onboarding flow, connecting 3 active clients to the system immediately following launch at a steady pace of approximately one client per week[cite: 33].
- [cite_start]**High Client Satisfaction** — Delivered a recognized achievement that made the client highly satisfied, proving that high-performing cloud reporting can be built on top of challenging legacy foundations[cite: 32, 158].
- [cite_start]**Subsequent Phase Enablement** — The architecture was designed to seamlessly scale; it is fully ready to integrate advanced auto-scaling (HPA/KEDA) and read-only asynchronous replicas for premium subscribers in later iterations[cite: 100, 101].

---

## Lessons Learned

- [cite_start]**Database Tables as Temporary Queues** — For the early stages of a project, utilizing a structured database table as a message queue is an exceptionally effective pattern to minimize initial infrastructure efforts and cloud costs[cite: 105].
- [cite_start]**Predictable Load Optimization** — Choosing Kubernetes-bound Worker Services over serverless functions (like Azure Functions) is highly optimal when processing loads are permanent and well-predicted[cite: 98, 99].

---

## Reusable Components / Patterns

- [x] [cite_start]Architecture schema for Multi-Tenant Cloud ETL processing[cite: 108].
- [x] [cite_start]Standardized CDC-to-API batching and mapping data flow[cite: 109].

---

## Resources

| Resource | Link |
|---|---|
| Code Repository | *[Internal GitLab Link TBD]* |
| Slide Deck | `[EB] Service Delivery Meeting (29.05.2024)` |
| System Architecture | [cite_start]Documented in Cloud ETL Architecture Slide [cite: 108] |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Iurii S.** | [cite_start]Technical Lead [cite: 36] |
| **Anastasiia V.** | [cite_start].NET Developer [cite: 41] |
| **Andreea M.** | [cite_start]Reporting Specialist [cite: 44] |
| **Anhelina L.** | [cite_start]Business Analyst [cite: 45] |

---
[cite_start]_Last updated: 2024-Q2 · Status: draft_ [cite: 3]
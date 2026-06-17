---
title: "Enmark Eniteo — Legacy ERP Modernization & Advanced Reporting Infrastructure"
type: use-case
status: draft
date: "2024-Q1"
domain: "FinTech"
client: "Enmark Systems, Inc."
technologies: [".NET 6", ".NET Framework 4.8.1", "Kotlin", "Android", "Vue.js", "Azure AKS", "PostgreSQL", "MSSQL", "Redis", "Docker", "Helm"]
experts: ["@AlexSukhenko", "@DavidRiley"]
tags: ["ERPModernization", "BarcodeScanning", "BusinessIntelligence", "CloudMigration", "TechAudit", "MultiTenant"]
---

# Enmark Eniteo — Legacy ERP Modernization & Advanced Reporting Infrastructure

> **One-liner summary** — Modernized Enmark's flagship Eniteo ERP ecosystem by replacing obsolete Windows CE scanning devices with a multi-tenant Android Barcode Scanner application and executing a comprehensive technical due diligence audit and intake of the EnVision reporting platform[cite: 10].

---

## Problem Overview

Enmark Systems, Inc. is the leading provider of enterprise solutions tailored for the Metal Service Center Industry[cite: 10]. Their signature product, Eniteo, is a robust ERP system designed to manage complex warehouse inventory, shipping, purchasing, accounting, and production processes across distributed environments[cite: 10]. 

To retain its extensive existing client network, attract new enterprise accounts, and expand licensing models, Enmark secured strategic growth investments from Accel-KKR[cite: 10]. However, the core platform was restricted by aging on-premises components, an obsolete Windows CE mobile scanning application, and complex business logic written decades prior[cite: 10]. Enmark partnered with INSART to execute a complete technical transformation, migrate legacy infrastructures to Microsoft Azure, and perform an end-to-end code intake of a newly acquired third-party reporting platform[cite: 10].

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Fragmented Legacy Logic** | Highly critical, multi-layered business logic was heavily scattered across old Visual Basic code, unmapped database stored procedures, and complex CLR functions[cite: 10]. |
| 2 | **Obsolete Hardware Dead Ends** | Warehouse teams depended on outdated Windows CE devices, requiring a total ground-up rebuild of the scanning subsystem to transition to modern Android hardware[cite: 10]. |
| 3 | **Severe Documentation Deficits** | The acquired EnVision web reporting code arrived with a massive legacy footprint, zero technical documentation, and highly restricted developer support from the previous engineering group[cite: 10]. |
| 4 | **Deep Database Proximity** | Core platform operations were rigidly bound to tight legacy database schemas, making the decoupling process for cloud multi-tenancy exceptionally delicate[cite: 10]. |
| 5 | **Critical Security Vulnerabilities** | Early evaluation uncovered significant security compliance gaps, including outdated TLS versions, weak password hashing algorithms, and explicit Role-Based Access Control (RBAC) API vulnerabilities[cite: 10]. |

---

## Proposed Solution

INSART deployed an expert cross-functional agile team to concurrently address the mobile scanning ecosystem and the web reporting platform[cite: 10]:

* **Barcode Scanner App:** Built a modern, native Android application (Kotlin, Android 6+) that officially supports premium Honeywell enterprise hardware (CK75, CK65, CT60)[cite: 10]. The solution architecture leverages a multi-tenant cloud framework on Azure to safely interact with Eniteo multi-tenant databases[cite: 10].
* **EnVision Reporting Web App:** Conducted a rigorous technical due diligence code audit to validate the asset's structural design before assisting Enmark through direct code intake, comprehensive rebranding, and immediate vulnerability resolution[cite: 10].

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Warehouse Operators** | Execute standard industrial operations (Physical Inventory, Picking, Moving, Cutting, Loading, and Label Printing) directly via mobile scanning touchscreens[cite: 10]. |
| **Advisors / Firm Managers** | Access the EnVision portal to build dynamic data views, configure corporate datasets, and assess advanced sales, purchasing, and account metrics[cite: 10]. |
| **System Administrators** | Configure client spaces, provision automated customers, and manage subscription limits across Free and Paid licensing plans[cite: 10]. |

---

## Process / Solution Flow

### The Barcode Scanner App Cycle:
1. **Device Execution** — Operators trigger action flows (e.g., Moving, Cutting, Loading) directly from physical keyboards or virtual screen input configurations on Honeywell devices[cite: 10].
2. **Cloud API Handshake** — The Android client securely communicates transactional data payloads directly up to Azure Kubernetes Services[cite: 10].
3. **Database Integration** — The cloud routing core instantly connects with multi-tenant Eniteo database instances to pull, validate, and write back live inventory changes[cite: 10].

### EnVision Advanced ETL & Reporting Pipelines:
1. **Core Data Extraction** — Raw metrics are continually pulled directly from distributed Eniteo client databases via an automated ETL engine[cite: 10].
2. **Queue Management** — Extracted streams are parsed into standard formats and queued asynchronously inside high-performance Redis Queue structures[cite: 10].
3. **Service Validation** — The underlying EnVision Service consumes the raw queues, processes CSV records, and maps variables cleanly into the EnVision cloud data warehouse[cite: 10].
4. **Dashboard Presentation** — Refreshed datasets populate the Vue.js micro-frontend views, serving rich visual charts to system users[cite: 10].

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Mobile App Core** | Kotlin, Android 6+, Firebase[cite: 10] | Native mobile execution platform with Firebase-driven application distribution pipelines[cite: 10]. |
| **Reporting Frontend** | Vue.js, ASP.NET MVC[cite: 10] | Employs scalable Micro Frontend Applications for flexible client dashboards[cite: 10]. |
| **Backend Services** | .NET 6, .NET Framework 4.8.1[cite: 10] | Supports both the updated scanner cloud backend and the legacy EnVision service engine[cite: 10]. |
| **Data & Queues** | PostgreSQL, MSSQL, Redis, Liquibase[cite: 10] | Out-of-the-box integration with historical MSSQL; PostgreSQL handles scalable modern data[cite: 10]. |
| **Cloud Infrastructure** | Azure Kubernetes Service (AKS), KeyVault, App Insights[cite: 10] | Encapsulates container runtimes, manages encrypted environment secrets, and tracks telemetry[cite: 10]. |
| **CI/CD & Testing** | Azure DevOps Pipelines, Java Automation QA Framework[cite: 10] | Drives fully automated compilation pipelines alongside custom mobile regression testing suites[cite: 10]. |

---

## Business Outcome

* **Successful Cloud Deployment** — Replaced aging legacy setups with standard public APIs and an enterprise cloud layout on Azure Kubernetes Service, making the software accessible to global users instantly[cite: 10].
* **Enterprise-Grade Security Compliance** — Passed exhaustive black-box penetration testing by integrating server certificate validation, code-level certificate pinning, strict TLS updates, secure encryption upgrades, and closing severe RBAC API gaps[cite: 10].
* **Acquisition Risk Mitigation** — Performed a thorough third-party technical due diligence audit using deep static code analysis and inspection tools, giving Enmark the clarity needed to proceed with purchasing the software asset[cite: 10].
* **Tiered Subscription Ingestion** — Delivered stable MVP milestones (Milestones 1 through 3), giving sales teams a presentable platform to upsell users from Free plans into Advanced Paid tiers[cite: 10].
* **Future-Proof Payment Foundations** — Laid out complete system roadmaps to integrate point-of-sale payment processor hardware connections and financial card tokenization engines into upcoming releases[cite: 10].

---

## Lessons Learned

* **Evaluating External Source Code** — When executing code intake on third-party software with limited developer support, running static code tools early prevents architectural regression and pinpoints systemic RBAC access issues before launch[cite: 10].
* **Managing Device Migration Trajectories** — Moving old industrial installations to newer operating systems depends heavily on client readiness to upgrade hardware and set up corporate Google accounts, requiring engineers to maintain active staging environments longer than anticipated[cite: 10].

---

## Reusable Components / Patterns

* [x] Multi-tenant database connection profiles for Microsoft Azure[cite: 10].
* [x] Mobile security blueprint templates for Honeywell scanning devices (certificate pinning and validation)[cite: 10].
* [x] Redis-backed asynchronous ETL parsing workflow configurations for bulk CSV uploads[cite: 10].

---

## Resources

| Resource | Link |
|---|---|
| Comprehensive Presentation | `4.12.2023 INSART SD Meeting. Enmark Project.pptx`[cite: 10] |
| Mobile Security Spec | Penetration Testing Remediation Blueprint[cite: 10] |
| Database Engine Map | Liquibase PostgreSQL Schema Manifest[cite: 10] |

---

## Experts

| Expert | Role on Project |
|---|---|
| **INSART Core Lead** | 1 Senior .NET Tech Lead[cite: 10] |
| **Development Team** | 2 Middle .NET Developers / 1 Senior Android Developer / 1 Vue.js Specialist[cite: 10] |
| **Product & Logic Leads** | 1 Project Manager / 1 Business Analyst / 1 UI/UX Designer[cite: 10] |
| **Quality & Integration Specialists** | 1 Manual QA / 1 Automation QA / 1 Senior Reporting Specialist[cite: 10] |

---
_Last updated: 2024-Q1 · Status: draft_
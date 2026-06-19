---
title: "Jazva — E-Commerce Platform Modernization & Multi-Marketplace Integration Ecosystem"
type: use-case
status: draft
date: "2023-Q2"
domain: "FinTech"
client: "Jazva, Inc."
technologies: ["Java 11", "Spring Boot 2", "Hibernate 5.6", "Apache Struts 1", "MySQL", "Mirakl API", "Wish API"]
experts: ["@MariaKyryliuk"]
tags: ["ECommerce", "InventoryManagement", "FrameworkMigration", "MultiMarketplace", "AppModernization", "DependencyUpgrade"]
---

# Jazva — E-Commerce Platform Modernization & Multi-Marketplace Integration Ecosystem

> **One-liner summary** — We executed a comprehensive core backend modernization for a multi-channel reseller platform, updating legacy Java 8 and Spring 4 layers to Java 11 and Spring Boot 2 while establishing real-time synchronization pipelines for global marketplaces[cite: 16].

---

## Problem Overview

Jazva provides a specialized multi-channel inventory, supply chain, and order management application designed for small and medium-sized online retail resellers[cite: 16]. The platform consolidates complex operational data loops, helping merchants track inbounds, outbounds, distributed warehouse stock levels, and multi-platform customer orders[cite: 16]. 

To sustain fast-moving data streams across external digital channels, Jazva required an intensive modernization of its core engineering footprint[cite: 16]. The application was constrained by aging framework models (Java 8, Spring 4, and Hibernate 5.2), which introduced security vulnerabilities and restricted performance scalability[cite: 16]. Jazva partnered with INSART to eliminate this technical debt, decouple their monolithic architecture for cloud readiness, and build real-time synchronization adapters for prominent third-party enterprise marketplace networks[cite: 16].

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Deep Technical & Dependency Debt** | Core business logic was locked within outdated infrastructure dependencies (Java 8, Spring 4, Hibernate 5.2), creating software vulnerability exposure[cite: 16]. |
| 2 | **Monolithic Structural Bottlenecks** | Core computational features and frontend web display components were tightly bundled, preventing parallelized database calls and delaying cloud service scaling[cite: 16]. |
| 3 | **Complex Multi-Platform Data Sync** | Ingesting and reflecting real-time updates across distinct, multi-tenant external endpoints required processing bidirectional data entities simultaneously[cite: 16]. |
| 4 | **Test Suite Regression Fixing** | Upgrading highly historical underlying frameworks triggered massive compilation disruptions and failures across legacy system test suites[cite: 16]. |

---

## Proposed Solution

INSART embedded a senior Java engineering squad to systematically re-architect the backend environment without interrupting live customer channels[cite: 16]. The solution addressed modernization across three distinct paths:

* **Iterative Core Migration:** Designed an upgrade path to transition the codebase from Java 8 directly to Java 11, moving Spring 4 through to Spring 5 and Spring Boot 2, while shifting Hibernate to version 5.6[cite: 16].
* **Application Modularization:** Decoupled the monolith into independent **Web** and **Core** modules[cite: 16]. This architectural split isolates the core computational engines, allowing them to be deployed independently as cloud services to parallelize database interactions and maximize processing speeds[cite: 16].
* **Marketplace Sync Integration:** Developed standardized multi-entity mapping connectors to facilitate live data sharing with enterprise SaaS platforms and retail consumer networks[cite: 16].

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Small & Medium Resellers** | Leverage the core application to maintain active control over inbound supply routes, outbound fulfillment, and multi-warehouse stock levels[cite: 16]. |
| **Retail Merchants (e.g., PyramidAir)** | Utilize third-party enterprise sync setups to manage independent dropship architectures and external consumer stores[cite: 16]. |
| **Advisory & Business Admins** | Evaluate operational data requirements, handle client onboarding settings, and check data mapping rules[cite: 16]. |

---

## Process / Solution Flow

The modernized Jazva core processes inventory modifications and marketplace transactions through an optimized synchronization cycle:

1. **Incremental Compilation Upgrade** — Code environments undergo systematic framework upgrades (Java 11, Spring Boot 2, Hibernate 5.6) with dependency vulnerabilities resolved[cite: 16].
2. **Modular Inversion** — Web layout presentation logic (Apache Struts 1/JSP) is isolated from fundamental business rules, establishing an independent Core processing tier[cite: 16].
3. **Multi-Marketplace Ingestion Loop** — Real-time event streams from external channels (such as Mirakl SaaS or the Wish Marketplace) connect via custom-built endpoints[cite: 16].
4. **Bidirectional Entity Mapping** — The integration core handles simultaneous data transformations[cite: 16]:
    * **Inbound Streams:** Imports external product files and fetches customer orders into Jazva[cite: 16].
    * **Outbound Pushes:** Transmits live inventory volumes and updates pricing structures directly back to the target marketplaces[cite: 16].
5. **UI Layer Validation** — Custom configuration windows inside the Jazva UI allow merchants to monitor connection statuses and manage active sync feeds[cite: 16].

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Backend Architecture** | Java 11, Spring Boot 2, Spring 5[cite: 16] | Migrated up from Java 8 and Spring 4 to establish a stable, cloud-ready foundation[cite: 16]. |
| **Legacy Web Layer** | Apache Struts 1, JSP[cite: 16] | Retained and isolated inside a dedicated Web module during the initial decoupling phase[cite: 16]. |
| **ORM / Data Access** | Hibernate 5.6[cite: 16] | Upgraded from version 5.2 to eliminate data transaction delays and mapping gaps[cite: 16]. |
| **Frontend Store** | HTML, CSS, JavaScript[cite: 16] | Drives the primary user configuration dashboards and integration setup screens[cite: 16]. |
| **Database Engine** | MySQL[cite: 16] | Central repository for multi-channel merchant metrics, inventory data, and orders[cite: 16]. |
| **E-Commerce Integrations** | Mirakl SaaS API, Wish Marketplace API[cite: 16] | Facilitates live product imports, order ingestion, price pushes, and inventory sync[cite: 16]. |

---

## Business Outcome

* **Complete Framework Rejuvenation** — Eradicated systemic technical debt by successfully moving the entire core backend ecosystem up to Java 11, Spring Boot 2, and Hibernate 5.6[cite: 16].
* **Enabled High-Performance Cloud Scaling** — Successfully split the platform into independent Web and Core modules, preparing Jazva to deploy independent cloud services that parallelize database calls and reduce latency[cite: 16].
* **Enterprise Marketplace Ingestion (Mirakl)** — Delivered a bidirectional synchronization connector for the Mirakl SaaS platform, enabling enterprise dropship management and live catalog tracking for retail clients like PyramidAir[cite: 16].
* **Global Consumer Reach Expansion (Wish)** — Engineered a multi-entity integration adapter for the Wish marketplace, synchronizing volatile product parameters, consumer orders, pricing variations, and stock levels[cite: 16].
* **Stabilized Code Integrity** — Resolved extensive test suite failures caused by major framework updates, ensuring stable, regression-free software delivery[cite: 16].

---

## Lessons Learned

* **Phased Framework Modernization** — When migrating deeply coupled systems, breaking framework updates into distinct sub-phases (e.g., migrating Spring versions before enforcing Spring Boot patterns) prevents configuration conflicts and makes debugging test failures manageable[cite: 16].
* **Isolating Before Cloud Deployments** — Separating core calculation layers from user interface modules (such as Struts/JSP components) must be completed *before* moving infrastructure to the cloud to ensure services can scale independently[cite: 16].

---

## Reusable Components / Patterns

* [x] Step-by-step upgrade configuration files for legacy Spring-to-Spring Boot migrations[cite: 16].
* [x] Multi-tenant inventory and pricing push mapping schemas for Mirakl SaaS environments[cite: 16].
* [x] Standardized API connection templates for Wish marketplace order ingestion[cite: 16].

---

## Resources

| Resource | Link |
|---|---|
| Master Review Deck | `Jazva Service Delivery.pptx`[cite: 16] |
| Client Digital Domain | [Jazva Corporate Portal](https://www.jazva.com/)[cite: 16] |
| External Enterprise Partner | [Mirakl Marketplace Platform](https://www.mirakl.com/)[cite: 16] |

---

## Experts

| Expert | Role on Project |
|---|---|
| **INSART Java Specialists** | 1 Senior Java Developer / 1 Middle Java Developer[cite: 16] |
| **Levon (Client-Side)** | CTO / Primary Technical Decision Maker[cite: 16] |
| **Sasha (Client-Side)** | Business Developer / Integration Requirements Lead[cite: 16] |
| **Jose, Tigran, Itso** | Senior Backend Developers[cite: 16] |

---
_Last updated: 2023-Q2 · Status: draft_
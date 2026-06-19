---
title: "Midway Dental — B2B E-Commerce Platform Modernization & ERP Cloud Migration"
type: use-case
status: draft
date: "2022-Q4"
domain: "HealthTech"
client: "Midway Dental"
technologies: ["PHP", "Symfony", "MySQL", "Backbone.js", "RabbitMQ", "ElasticSearch", "Redis", "Azure"]
experts: ["@MariaKyryliuk"]
tags: ["Ecommerce", "ERPMigration", "B2B", "APIIntegration", "ProductCatalog"]
---

# Midway Dental — B2B E-Commerce Platform Modernization & ERP Cloud Migration

> **One-liner summary** — We modernized an ORO-based B2B dental e-commerce platform by executing an undocumented ERP API cloud migration to Azure, eliminating legacy middleware, and launching multi-brand supplier integrations. This significantly improved development velocity and positioning, culminating in the company's acquisition by its largest competitor.

---

## Problem Overview

Midway Dental was an established distributor exclusively sourcing 100% certified dental equipment and medical supplies via regional web subdomains. The digital store and its administrative panels were built on top of the ORO e-commerce platform. 

Before INSART's engagement, all core engineering was handled directly by the ORO platform team. Because Midway Dental was considered a relatively small client, their customization requests faced extensive delays and high development premiums. To achieve true operational autonomy, scale their catalog, and prepare their internal Prophet 21 (P21) ERP for a critical migration to Microsoft Azure, Midway Dental partnered with INSART to take over technical ownership.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Vendor Neglect & Cost Inflation** | The original platform development team offered limited support and slow turnaround cycles due to the small relative account size. |
| 2 | **Undocumented Legacy Ecosystem** | The complex architecture surrounding the core ERP (P21) and its data migration paths to Azure entirely lacked updated technical documentation. |
| 3 | **Fragmented Multi-Brand Data** | Ingesting and synchronizing catalogs, pricing tiers, and automated order loops across diverse third-party marketplaces required custom integrations. |
| 4 | **Absence of Dedicated QA** | The project operated with zero dedicated QA engineers, putting the burden of deployment validation entirely on the PM and software developers. |
| 5 | **Outdated Frontend Core** | The consumer-facing storefront relied on an obsolete Backbone.js configuration, restricting rapid interactive features. |

---

## Proposed Solution

INSART deployed a dedicated agile engineering pod consisting of a Project Manager and Senior PHP/Symfony Developers to replace the legacy vendor. The team bypassed intermediate middleware layers by establishing direct API pathways between the storefront and the Azure-hosted ERP. 

To optimize the B2B purchasing journey, INSART built an array of custom e-commerce modules—such as fallback product recommendations and advanced inventory limits—while handling rigorous local white-box testing directly inside the development cycle to counter the lack of specialized QA.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Certified Dentists & Clinics** | Authenticate verified medical licenses, manage region-specific subdomains, evaluate out-of-stock substitutions, and buy historical packages. |
| **Customer Service Team** | Manage backend order processes, track invoicing terms, and review customer records via the central administrative panel. |
| **Order Reviewers & Confirmers** | Custom administrative roles created to handle compliance checks, evaluate financial credit paths, and authorize high-value medical hardware purchases. |

---

## Process / Solution Flow

The modernized e-commerce engine routes multi-brand inventory updates and client order records through a unified lifecycle:

1. **Catalog Aggregation** — The backend processes incoming multi-brand product feeds from wholesale dental platforms (Clixon, Dentira, Supply Clinic) to build a unified certified inventory cache.
2. **Dynamic Search Grouping** — Products are dynamically organized via the "Product Family" feature, allowing users to find alternative matches via ElasticSearch autosuggestions.
3. **Purchasing & Tax Evaluation** — The customer places items into the shopping cart, triggering automatic tax calculations via an integrated Avalara API micro-call.
4. **Payment Gateway Authorization** — Payment transactions are safely securely authorized through PayTrace or Authorize.NET payment modules.
5. **Direct Azure ERP Sync** — Validated orders pass through RabbitMQ and flow directly into the Azure-hosted ERP (P21), eliminating external middleware.
6. **Substitution Handling** — If an item goes out of stock, substitution rules dynamically present equivalent alternatives on-screen to prevent cart abandonment.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Backend Core** | PHP 7.4, Symfony 4.4, ORO Platform | The foundational e-commerce framework optimized for custom business rules. |
| **Frontend Interface** | JavaScript, HTML/CSS, Backbone.js | Legacy storefront rendering layer; future roadmap intended a full React rewrite. |
| **Asynchronous Queues** | RabbitMQ | Brokers messages and transactional order loops across decoupled services. |
| **Data & Search** | MySQL, ElasticSearch, Redis | MySQL manages structured data; ElasticSearch powers autosuggestions; Redis caches sessions. |
| **Cloud Infrastructure** | Microsoft Azure | Hosts the target migrated environment for the enterprise ERP system. |
| **Financial Gateways** | Avalara, PayTrace, Authorize.NET | Automates tax calculation rules and secure credit clearing. |
| **B2B Integrations** | Clixon, Dentira, Supply Clinic | Syncs dynamic product catalogs and automates supply orders. |

---

## Business Outcome

* **Middleware Elimination & Cloud Migration** — Completed an extensive API redesign that successfully migrated the core ERP database to Microsoft Azure while completely stripping away expensive middleware layers.
* **Successful Corporate Acquisition** — The technical modernization and robust operational updates positioned Midway Dental for a successful acquisition by Henry Schein, their largest market competitor.
* **Enhanced B2B Buying Mechanics** — Shipped high-value custom modules, including a "Buy It Again" dashboard, an automated out-of-stock product substitution engine, and an invoicing analytic report that makes payment terms and debts transparent.
* **Advanced Access Control Governance** | Implemented granular security access layers across the admin workspace by establishing unique permissions for Agents, Order Reviewers, and Order Confirmers.
* **Optimized Search Experience** — Tailored default ElasticSearch components to run automated autosuggestions and prioritize high-margin, certified product arrays.

---

## Lessons Learned

* **Developer-Led Quality Controls** — In projects where separate QA budgets are unavailable, having the PM partner with Senior Developers to design explicit testing plans ensures high-quality code releases without separate QA staff.
* **Documenting Undocumented Migrations** — When undertaking large-scale cloud migrations on legacy ERP systems without existing document trails, capturing technical structures inside Confluence during discovery helps insulate development sprints against unexpected regression.

---

## Reusable Components / Patterns

* [ ] Reusable ORO platform API configuration maps for Azure cloud migrations.
* [ ] Standard multi-brand supplier catalog transformation rules (Clixon/Dentira/Supply Clinic).
* [ ] Automated product family data relationship schemas for complex catalog grouping.

---

## Resources

| Resource | Link |
|---|---|
| Master Slide Deck | [Midway Dental 31.07.2023.pptx](https://docs.google.com/presentation/d/1XufO_H0ugPDdU4_dsQZV7XjJa_mE5IK6wT28OLGbqJw/edit?usp=sharing) |
| Corporate Space | [Midway Dental Archival Portal](http://www.midwaydental.com) |
| Code Repository | _[To be added]_ |
| Design Files | _[To be added]_ |
| Demo Video | _[To be added]_ |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Maria Kyryliuk** | Project Manager / Developer-Led Testing Coordinator |
| **Alex** | Senior PHP & Symfony Developer |
| **Boris** | Senior PHP & Symfony Developer |
| **Vyacheslav** | Mid Frontend Developer |

---
_Last updated: 2023-Q3 · Status: draft_

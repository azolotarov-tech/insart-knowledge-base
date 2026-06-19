---
title: "Salsa CRM & Engage — Scalable Marketing Automation and Fundraising Platform"
type: use-case
status: draft
date: "2023-Q1"
domain: "FinTech"
client: "Salsa Labs (Bonterra Tech)"
technologies: ["Java", "Spring", "Apache Struts 2", "Hibernate", "Angular", "jQuery", "PostgreSQL", "MySQL", "ElasticSearch", "AWS", "PowerMTA", "Highcharts"]
experts: ["@VitaliiAvramchuk", "@ArtemSvetlovsky", "@AntonGoncharov", "@EduardFastovskyi", "@YevhenKostiuk", "@NatalieStruk", "@OlegLauta", "@KirillGolovin", "@VitaliiListratenko", "@ValeriePavliuk"]
tags: ["Fundraising", "CRM", "NonProfit", "MachineLearning", "PlatformRenovation", "Microservices", "HighLoad"]
---

# Salsa CRM & Engage — Scalable Marketing Automation and Fundraising Platform

> **One-liner summary** — We scaled and modernized an enterprise nonprofit fundraising and marketing platform over a 9-year partnership, building an autonomous cloud engagement engine from scratch, renovating a monolithic legacy CRM, and launching machine learning-driven donor analytics.

---

## Problem Overview

Salsa Labs (now a part of Bonterra Tech) is an innovative software provider fueling more than 3,000 nonprofit organizations and 10,000 fundraising professionals. The company’s flagship platform offers an extensive suite of online fundraising, advocacy campaigning, multi-channel communication, and donor management functionalities. 

While their digital engagement system ("Engage") was developed from scratch, the core Salsa CRM product was an acquired legacy application bound to an obsolete framework (Apache Struts 2) and an on-premises multi-VM database cluster. As Salsa's client base expanded rapidly—doubling almost twice a year—the legacy infrastructure degraded severely. This resulted in critical UI performance crashes during major data queries, manual bottlenecks in address verification, and vulnerable security protocols. The platform required a major, multi-year reengineering effort to maintain peak load availability during massive seasonal fundraising events.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Rigid Legacy Architecture** | Core CRM modules were locked in outdated Apache Struts 2 and JavaScript configurations, making the codebase unmaintainable and unextendable. |
| 2 | **Browser Rendering Crashes** | The original Advanced Query Wizard (AQW) choked and crashed client web browsers whenever an advisor attempted to load more than 10,000 records. |
| 3 | **Extreme High-Load Spikes** | "End of Year" giving campaigns (stretching from Giving Tuesday through New Year's Eve) triggered extreme peak loads that threatened system availability. |
| 4 | **Manual Operations Bottlenecks** | Crucial National Change of Address (NCOA) cleansing required staff to manually export text files, transmit them to third parties, and import them back into the database[cite: 10, 18]. |
| 5 | **Volatile Project Parameters** | The engineering team faced constantly shifting priorities, compressed timelines, and unestimated product backlogs from client-side product managers. |

---

## Proposed Solution

INSART built a full-fledged, autonomous engineering division that scaled up to 23 personnel over a 9-year lifecycle. Moving past basic defect-fixing roles, INSART assumed complete technical ownership of feature analysis, automated QA monitoring, and international developer recruitment.

We engineered a **hybrid legacy-modern system bridge** that seamlessly embedded modern Spring framework nodes and Angular interfaces directly inside the active Struts 2 monoblock, enabling gradual software renovation without live user downtime. The team rolled out machine learning capabilities for donor optimization, automated the entire address validation pipeline, built a high-performance pagination query builder, and managed seasonal infrastructure load spikes.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Nonprofit Professionals** | Construct multi-channel marketing workflows, deploy peer-to-peer event tracking forms, and review performance dashboards. |
| **Donors & Supporters** | Submit secure online donations, interact with automated text triggers, and coordinate local third-party fundraising groups. |
| **Salsa Operations Admins** | Manage application configurations, execute large-scale user data migrations via automated validation grids, and evaluate operational metrics. |
| **Internal Treasury Teams** | Review graphic financial metrics, track giving histories across annual milestones, and execute rapid gift entries. |

---

## Process / Solution Flow

The modernized fundraising platform coordinates live donor communications and transaction records through five core steps:

1. **Bi-Directional Synchronization** — The legacy CRM and the modern Engage platform share active constituent entities and tracking metrics in near real-time via secure token-based REST APIs.
2. **Predictive Ask Modeling** — Integrated machine learning algorithms parse large pools of historical donor activity, giving histories, and demographic attributes to compute the optimal "Smart Ask" donation amount for individual supporters.
3. **Automated Address Verification** — The automated NCOA module systematically sweeps data records, flags permanent resident or business relocation changes, and rewrites the database records without manual text export processes.
4. **High-Volume Request Pagination** — The overhauled Advanced Query Wizard executes structural pagination on the backend, bypassing browser rendering restrictions to seamlessly display an unlimited number of records.
5. **Dynamic Document Merging** — The system links directly with Google Drive and Google Docs APIs, completely replacing old embedded editors to allow users to build complex mail-merge layout structures.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Backend Core** | Java, Spring Framework, Apache Struts 2, Hibernate, Hazelcast, WildFly | Tightly integrates legacy structures with modern microservice logic in an event-based architecture. |
| **Frontend Platform** | Angular, jQuery, Highcharts | Powers interactive layout dashboards, complex query builders, and extensive analytical graphs. |
| **Data Layers** | PostgreSQL, MySQL, ElasticSearch | Manages millions of heavy donor profiles, global search query nodes, and transaction indices. |
| **Infrastructure** | AWS (S3, SQS), Jenkins, Linux, Docker | Utilizes asynchronous message brokers and containerized code compilation pipelines. |
| **Email Processing** | Localized PowerMTA (by Messagebird) | Hosted inside an independent data center and optimized via direct API file system integrations. |

---

## Business Outcome

* **Sustained Continuous Hyper-Growth** — Scaled and optimized the platform's core infrastructure to comfortably accommodate a client base that doubled almost twice a year.
* **Machine Learning Monetization** — Successfully deployed predictive data analytics models that calculate hyper-personalized donor ask structures, driving donation conversion rates across the nonprofit ecosystem.
* **Massive Query Breakthroughs** — Eliminated browser hanging issues by upgrading the Advanced Query Wizard, allowing users to process and view unlimited transaction and profile records.
* **Enabled High-Value Corporate Mergers** — The significant technical modernization and enterprise viability enabled Salsa Labs to be successfully acquired by EveryAction, eventually joining Bonterra Tech.
* **Complete Process Autonomy** — Built an absolute relationship of trust, allowing INSART to assume full liability for the engineering hiring pipeline and out-of-hours high-load performance stabilization.
* **Completed Crucial Security Overhauls** — Engineered custom 2FA security pathways from initial Proof of Concept through full production deployment across CRM platforms.

---

## Lessons Learned

* **The Power of Hybrid Architectural Coexistence** — When a complete platform rewrite is blocked by business timelines, creating a hybrid framework where legacy configurations (Struts 2) and modern environments (Spring + Angular) are tightly integrated provides a stable user transition path.
* **The Vulnerability of Cloud Mass-Mailing Migration** — Transitioning high-volume transactional email operations to commercial cloud mailing endpoints can lead to catastrophic scalability bottlenecks during peak load spikes; maintaining dedicated on-premises infrastructure (PowerMTA) and driving it via optimized APIs ensures optimal deliverability.
* **Managing Unestimated Deadlines** — In fast-moving environments where product backlogs lack formal estimation structures, engineering leads can counteract unrealistic deadlines by continually tracking sprint velocity against delivery dates, proactively cutting or adapting scope elements early.

---

## Reusable Components / Patterns

* [ ] Reusable architectural blueprints for hybrid Struts 2 to Spring Boot / Angular bridges.
* [ ] High-volume database query pagination plugin patterns for frontend UI data grids.
* [ ] Machine learning data ingestion profiling templates for predictive behavior calculation.
* [ ] Automated background NCOA address cleaning integration workflows.
* [ ] Google Apps Script validation logic configurations for bulk data entry spreadsheets.

---

## Resources

| Resource | Link |
|---|---|
| Comprehensive Presentation | [Salsa/Bonterra Service Delivery Overview.pptx](https://docs.google.com/presentation/d/1UJAhDaWVeM2Xr57rNrM99_ooIOJu2BuINaULREIjoO4/edit?usp=sharing) |
| Public Parent Domain | [Bonterra Tech Platform Home](https://www.bonterratech.com/) |
| Code Repository | _[To be added]_ |
| Design Files | _[To be added]_ |
| Demo Video | _[To be added]_ |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Vitalii Avramchuk** | QA Manager / Project Manager |
| **Artem Svetlovsky** | Java Tech Lead / Senior Java Developer |
| **Anton Goncharov** | Frontend Engineering Tech Lead |
| **Eduard Fastovskyi** | CRM Project Lead / Senior Java Developer |
| **Yevhen Kostiuk** | Machine Learning Specialist |
| **Natalie Struk** | Database Team Lead / Senior DB Developer |
| **Oleg Lauta** | Automation QA Specialist |

---
_Last updated: 2023-Q1 · Status: draft_

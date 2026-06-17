---
title: "Zuul — Data as a Service (DaaS) ETL Platform for Annuity Modernization"
type: use-case
status: draft
date: "2024-Q2"
domain: "FinTech"
client: "Zuul"
technologies: ["Java", "Kotlin", "Vue.js 3", "TailwindUI", "AWS Lambda", "jOOQ", "Dagger", "AWS CodePipeline"]
experts: ["@YuliiaDemianova", "@AndriyStosyk", "@AnnaKhvirenko", "@ArtemSvetlovsky", "@MykhailoPopov", "@OleksandrDatso"]
tags: ["DaaS", "ETL", "InsurTech", "AnnuityData", "Serverless", "DataTransformation"]
---

# Zuul — Data as a Service (DaaS) ETL Platform for Annuity Modernization

> **One-liner summary** — We designed and built a cloud-native, serverless ETL processor from scratch to ingest, validate, and transform fragmented insurance contract files into a unified format, eliminating data-sharing latency between insurance agencies and financial advisors.

---

## Problem Overview

The transmission of financial data from insurance firms to Registered Investment Advisors (RIAs) has traditionally been bottlenecked by high latency, disparate data formats, and friction caused by manual flat-file exchanges or delayed daily updates. This fragmentation forces advisory firms to allocate heavy overhead toward data aggregation rather than focusing on client returns. 

Zuul emerged to transform this ecosystem into a modernized Data as a Service (DaaS) model. They partnered with INSART to build an engine completely from scratch that could ingest uploaded contract data, run complex calculations, and normalize the data into a single unified analytical taxonomy.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **High Data Latency & Friction** | Financial advisors frequently rely on stale daily updates or manual file parses, limiting real-time agility. |
| 2 | **Disparate Data Formats** | Insurance providers supply data through mismatched file topologies lacking a standardized layout or schema. |
| 3 | **Startup Capital Constraints** | As a pre-revenue venture, the client required an extremely cost-effective yet highly secure Proof of Concept (PoC) to attract seed investment. |
| 4 | **Role-Based Report Customization** | The system needed to cleanly partition data fields, making analytical reports dynamically editable based on unique user compliance tiers. |

---

## Proposed Solution

INSART architected and engineered a scalable, serverless ETL (Extract, Transform, Load) processing application. This system serves as a secure bridge connecting annuity providers directly with investment data analytical platforms. 

The architecture converts diverse input formats into a standardized proprietary "Zuul Format." To keep infrastructure overhead low and performance highly scalable, the team constructed the platform using AWS serverless technologies paired with a lightweight, high-performance JVM backend. 

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Registered Investment Advisors (RIAs)** | Connect to the platform to view real-time data flows, execute custom calculations, and export clean JSON structures. |
| **Financial Advisors** | Manage client annuity portfolios and review editable analytical reports tailored to their specific roles. |
| **Annuity Providers / Insurance Agencies** | Bulk-upload legacy contract profiles and investment files into the processing core. |

---

## Process / Solution Flow

The data ingestion and transformation platform processes annuity files through five core structural phases:

1. **File Ingestion** — Insurance companies and annuity carriers upload diverse contract files directly to the secure storage bucket.
2. **Taxonomy-Driven Transformation** — The serverless ETL processor parses the unstructured text/spreadsheets, using a custom financial taxonomy to map attributes into the unified "Zuul Format."
3. **Validation & Database Storage** — The application runs automated verification routines against the structured financial objects and commits them to the database.
4. **UI Visualization & Export** — The processed files populate user dashboards, allowing clients to review parameters on-screen or export data via a clean JSON file format.
5. **Calculations & Alerting** — Custom calculations trigger based on raw contract parameters, generating operational reports and data notifications for advisors.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Backend Core** | JVM Languages (Java, Kotlin) | Leverages Kotlin/Java for reliable, enterprise-grade financial arithmetic. |
| **Data Access & DI** | jOOQ, Dagger, Apache POI | jOOQ handles type-safe database queries; Apache POI handles legacy file parsing. |
| **Frontend UI** | Vue.js 3, TailwindUI | Delivered a modern, highly responsive analytical interface. |
| **Cloud Infrastructure** | AWS Cloud, AWS Lambda | Built as a fully serverless architecture to reduce runtime hosting costs to near zero. |
| **CI/CD & Testing** | AWS CodePipeline, JUnit | Provides fully automated compilation, testing, and cloud deployment pipelines. |

---

## Business Outcome

* **From Zero to Launch in 4 Months** — Successfully completed a comprehensive 1-month paid Discovery Phase, a 2-month core Development Phase, and a 1-month technical Wrap-up and Support interval.
* **Investor-Ready Platform** — Built a highly performant Proof of Concept (PoC) from the ground up, equipping the client with the tangible platform technology needed to drive strategic fundraising rounds.
* **Accelerated Sales Pipeline** — Created a robust system architecture that allowed the client to advance discussions with high-profile pipeline leads, including Pacific Life and RetireOne.
* **Defined Evolutionary Roadmap** — Mapped out the precise engineering scopes for upcoming releases, including advanced auditing, GDPR compliance configurations, multi-platform integrations, and Power of Attorney validation modules.

---

## Lessons Learned

* **Serverless Cost-Efficiency for Startups** — Combining AWS Lambda with lightweight JVM tools is a highly effective architecture pattern for early-stage FinTech companies. It minimizes infrastructure costs during low-volume sales cycles while ensuring instant scalability when large enterprise clients are signed.
* **Targeting Pipeline Requirements** — For pre-revenue platforms, gathering explicit feature requirements directly from early prospects (such as Pacific Life) during the PoC phase ensures that successive sprints directly unlock enterprise contracts.

---

## Reusable Components / Patterns

* [ ] Reusable serverless AWS Lambda configuration scripts for ETL file parsing.
* [ ] Universal data mapping layer pattern using jOOQ and Apache POI to parse flat financial documents into JSON.

---

## Resources

| Resource | Link |
|---|---|
| Core Slide Deck | [`Zuul Presentation`](https://docs.google.com/presentation/d/1gUo6M-OGUFaaY61jz0wsZo6XHbaQNaaN/edit?usp=sharing&ouid=110968320908081389046&rtpof=true&sd=true) |
| Analytical Database Design | Documented in Core Taxonomy Specs |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Yuliia Demianova** | Project Manager |
| **Andriy Stosyk** | Business Analyst |
| **Anna Khvirenko** | DBA Architect |
| **Artem Svetlovsky** | DevOps / QA Engineer |
| **Mykhailo Popov** | Frontend Engineer (Vue.js 3) |
| **Oleksandr Datso** | Backend Engineer (Java / Kotlin) |

---
_Last updated: 2024-Q2 · Status: draft_

---
title: "Guidance Residential — Modernizing Shariah-Compliant Home Financing Workflows"
type: use-case
status: draft
date: "2024-Q1"
domain: "FinTech"
client: "Guidance Residential"
technologies: ["PHP", "Laravel", "Vue.js", "MySQL", "WordPress"]
experts: ["@MariaKyryliuk", "@VladVerpeta", "@IrynaSavchenko", "@AnhelinaLinska", "@LukaYakymchuk", "@AlexDatso", "@RedjonMata"]
tags: ["HomeFinancing", "WorkflowOptimization", "LegacyMigration", "UXRedesign", "Musharaka"]
---

# Guidance Residential — Modernizing Shariah-Compliant Home Financing Workflows

> **One-liner summary** — We optimized the document ingestion and pre-qualification pipelines for the largest U.S. provider of Shariah-compliant home financing, reducing contract document delivery times from two weeks to zero while introducing a unified multi-site umbrella web architecture.

---

## Problem Overview

Guidance Residential is the premier provider of Shariah-compliant home financing in the United States, operating across 34 states. Because Islamic law prohibits standard interest-bearing loans, the company utilizes a *Musharaka* (diminishing partnership) co-ownership model. 

The client's underlying technical infrastructure (comprising their Mortgage App, Phoenix Portal, and GIOS CRM) suffered from severe operational fragmentation. Contract IDs were mismatched across systems, and homebuyers faced up to a two-week administrative delay just to receive an email link to upload mandatory contract documents. Furthermore, if a customer and an Account Executive (AE) edited a contract simultaneously, the system lacked concurrency locks, creating a high risk of critical data being completely overwritten.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Severe Operational Inefficiency** | Customers were forced to wait approximately 2 weeks for internal confirmations before receiving a manual link to provide files, leading to high drop-off risks. |
| 2 | **Data Collision & Overwriting** | Simultaneous data input by end-users and advisory staff within the contract workspace regularly caused newer data to be lost or overwritten. |
| 3 | **Mismatched Contract Mapping** | Legacy configurations generated entirely different Contract IDs for the same customer profile across different platforms. |
| 4 | **Outdated Software Ecosystem** | Core components relied heavily on legacy frameworks, including PHP 5.6/7.1, Laravel 5.6/6.5, and Vue.js 2.5, limiting system performance and modern scalability. |
| 5 | **Suboptimal Marketing Routing** | Public advertising traffic links routed prospects straight to the unsegmented main corporate website instead of intent-focused landers. |

---

## Proposed Solution

INSART initiated a fixed-price discovery and trial phase that successfully converted into a long-term Time & Material technical partnership. We attacked the system architecture in structured phases:

* **Phase 1 (Customer Experience):** Unified the contract identification mechanism across all environments and completely bypassed bloated legacy middleware (GIOS and Integra systems). We re-engineered the asset upload layer to send data directly from the front-facing Mortgage App into the Phoenix portal.
* **Phase 2 (Pre-Qualify Process):** Rebuilt user onboarding journeys by constructing intent-based landing pages, engineering a proprietary Affordability Calculator, and delivering instant Pre-Qualification letter downloads.
* **Website Redesign:** Initiated structural cleanup to migrate static web layouts from custom Laravel configurations over to WordPress, eliminating heavy page duplication and building a high-level "umbrella web app" architecture (Guidance Residential America).

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Home Buyer / Applicant** | Interacts with the public platform, computes property affordability indicators, uploads identification documents, and accesses financing agreements. |
| **Account Executive (AE) / Advisor** | Evaluates files, reviews financial requests, and completes documentation without experiencing system concurrency conflicts. |
| **Operational Admin** | Orchestrates digital static content, updates platform metadata configurations, and tracks marketing acquisition funnels. |

---

## Process / Solution Flow

### Optimized Customer Document Ingestion:
1. **Request Submission** — The applicant submits an initial digital request form on the front end.
2. **Unified ID Allocation** — The system instantly spins up a singular, synchronized Contract ID map across the Mortgage App, Phoenix, and GIOS systems.
3. **Direct File Handshake** — Bypassing traditional intermediate pipelines, the system routes a direct API connection between the Mortgage App and the Phoenix secure core.
4. **Instant Self-Service Access** — The applicant lands on a customized "Thank You" confirmation page, dynamically generating a temporary session link to pull down or upload documentation instantly.

### Modernized Pre-Qualification Funnel:
1. **Targeted Redirection** — Specialized marketing ads funnel users straight to highly specific intent landing pages instead of the main generic domain.
2. **Dynamic Affordability Valuation** — Prospects input raw financial metrics into the Affordability Calculator to generate a real-time purchasing evaluation.
3. **Questionnaire Routing** — Users choose whether to progress to the full Pre-Qualification questionnaire or jump straight into document repository workflows.
4. **Immediate In-App Download** — Upon completion, users download an official Pre-Qualification letter right on the confirmation screen without waiting for email delivery.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Mortgage Application** | PHP 7.2, Laravel 6.5, Vue.js 2.5 | Core consumer-facing application layer. |
| **Phoenix Portal** | PHP 7.1, Laravel 5.6, Vue.js 2.6 | Internal administrative data storage environment. |
| **GiOS (CRM)** | PHP 5.6 | Legacy internal database engine managing user profiles. |
| **Databases** | MySQL 5.6, MsSQL | Handles data persistence across disjointed systems. |
| **Content & SEO Layer** | WordPress, Laravel (GR-2020) | Target environment for migrating static assets to eliminate code redundancy. |

---

## Business Outcome

* **Two-Week Delay Reduced to Zero** — Accelerated the customer validation process by eliminating the 14-day internal wait time for uploading contract documentation.
* **Eliminated Data Redundancy and Overwrites** — Optimized concurrent data entry, dropping database transaction conflicts between home buyers and internal advisory teams down to zero.
* **Higher Customer Acquisition Rates** — Grouped service pages into distinct landing modules and integrated an Affordability Calculator, resulting in clearer conversion paths for digital leads.
* **Modern Architecture Blueprint** — Provided an evolutionary map to transition the client's static infrastructure to WordPress while laying the foundational groundwork for a future full-scale framework upgrade.

---

## Lessons Learned

* **Fixed-Price to T&M Evolution** — Launching a collaborative engagement via small, tightly bound, fixed-price trial phases provides the baseline visibility needed to organically scale into an enterprise Time & Material engineering relationship.
* **Middleware De-cluttering** — System latency and structural defects decrease dramatically when redundant intermediate applications (like GIOS/Integra) are removed from the direct file-upload payload flow.

---

## Reusable Components / Patterns

* [x] Shared cross-platform transactional ID generation engine blueprints.
* [x] Self-contained client-side Affordability Calculator module logic.
* [x] Static Laravel-to-WordPress migration schema rulesets for SEO optimization.

---

## Resources

| Resource | Link |
|---|---|
| Slide Deck Presentation | [`Guidance residential 26.03.2024.pptx`](https://docs.google.com/presentation/d/1lspimFbyuSwi8LWoHQ9nMI5IuQO3XCet/edit?usp=sharing&ouid=110968320908081389046&rtpof=true&sd=true) |
| Platform Main Website | [Guidance Residential](https://www.guidanceresidential.com) |
| Affiliate Real Estate Portal | [Guidance Home Services](https://www.guidancehomeservices.com) |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Maria Kyryliuk** | Project Manager / Reporter |
| **Vlad Verpeta** | Tech Lead / Reporter |
| **Iryna Savchenko** | Business Analyst |
| **Anhelina Linska** | Business Analyst (Redesign) |
| **Luka Yakymchuk** | UI/UX Designer |
| **Redjon Mata** | Full Stack Developer |
| **Alex Datso** | Manual QA Engineer |

---
_Last updated: 2024-Q1 · Status: draft_

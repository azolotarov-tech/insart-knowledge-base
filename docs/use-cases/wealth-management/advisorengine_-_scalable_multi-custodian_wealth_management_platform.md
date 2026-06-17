---
title: "AdvisorEngine — Scalable Multi-Custodian Wealth Management Platform"
type: use-case
status: draft
date: "2024-Q1"
domain: "FinTech"
client: "AdvisorEngine"
technologies: ["React", "PHP", "Symfony", "Java", "Scala", "Apache Spark", "PostgreSQL", "AWS", "Kubernetes"]
experts: ["@StanislavKoval", "@ViktorKononenko", "@VladyslavShaldieiev", "@VladyslavDerkach", "@SerhiiKornushov", "@KirillNasardion"]
tags: ["WealthManagement", "CRM", "MultiCustodian", "DigitalOnboarding", "PlatformModernization", "FinTech"]
---

# AdvisorEngine — Scalable Multi-Custodian Wealth Management Platform

> **One-liner summary** — Modernized and scaled an enterprise-grade end-to-end wealth management platform by embedding 26 billable engineering resources across 7 cross-functional scrum teams. This initiative delivered critical multi-custodian architectural shifts, high-performance automated account onboarding, and major backend framework upgrades.

---

## Problem Overview

AdvisorEngine operates a purpose-built, data-driven wealth management ecosystem designed for Registered Investment Advisors (RIAs) and Independent Broker-Dealers (IBDs). The platform aggregates business-critical workflows, including an advisor-focused CRM, portfolio performance reporting, fee billing, automated asset rebalancing, digital onboarding, and business intelligence modules. 

To capture a larger market share and onboard high-tier institutional clients, AdvisorEngine needed to execute the Multi-Custodian Initiative (MCI). This required migrating a rigid, legacy codebase into a multi-tenant, cloud-native architecture capable of simultaneously balancing data from multiple distinct clearing custodians under single investor households. Under heavy structural pressure from parent enterprise Franklin Templeton to deliver predictable features rapidly, the platform required deep outstaffing development power and tech consulting to resolve scalability challenges and process inefficiencies.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Rigid Monolithic Architecture** | Legacy core accounts and household databases were incapable of handling multi-custodian data aggregation in one unified portal workspace. |
| 2 | **Heavy Technical & Security Debt** | Major application clusters relied on heavily outdated software foundations, including PHP 7, Symfony 3/4, and Apache Spark 2, triggering immediate security risks. |
| 3 | **3rd-Party Integration Latency** | Critical business flows—such as automated asset transfers (ACATS) and third-party aggregation portals (DST)—frequently encountered long API response delays and communication failures. |
| 4 | **PDF Builder Rendering Blocks** | The existing Report Packager (RPS) engine layout code made it incredibly difficult for managers to implement UI modifications or build flexible, presentation-quality PDF templates directly from the backend. |
| 5 | **Agile Delivery Predictability** | Fast-evolving feature demands from major clients generated friction across internal product branches, resulting in delayed product timelines and low delivery schedule visibility. |

---

## Proposed Solution

INSART integrated 26 billable engineers, project managers, and automated QA specialists directly into 7 of AdvisorEngine's 10 internal cross-functional engineering teams. Rather than acting purely as transactional outstaffing, our senior engineers joined the core Architecture Board to guide core technical decisions alongside the client's executive leadership.

The joint team restructured the data layer to support the Multi-Custodian Initiative (MCI) and fully refactored custodian onboarding links for Charles Schwab and Fidelity. On the operational side, INSART introduced key consulting improvements to the client's Scrum approach—such as capacity-based planning and complexity-based estimation models—and built a dedicated transparency metrics dashboard to identify and mitigate team attrition risks early.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Independent Broker-Dealers (IBDs) & RIAs** | Utilize the purpose-built CRM to manage profiles, track billing workflows, configure configurable fee splits, and automate compliance audits. |
| **Individual Account Holders** | Access self-navigation features through a configurable client portal, track dynamic wealth benchmarks, and trigger document vaults. |
| **Firm Managers & Reps** | Design and generate presentation-quality PDF report package templates to execute on-demand or distribute automatically to households. |

---

## Process / Solution Flow

The core system handles automated multi-custodian operations, digital onboarding, and asset management end-to-end:

1. **Multi-Custodian Consolidation** — The platform ingests and correlates parallel asset streams, allowing investors to manage multiple custodian accounts under a single household view.
2. **Onboarding & Risk Modeling** — Prospective investors launch the digital onboarding workflow, filling out automated asset opening configurations, profile builders, and risk assessment forms.
3. **Custodian Handshake & Funding** — The platform triggers customized API steps with custodians (such as Schwab or Fidelity), utilizing deep DocuSign workflows to execute instant account openings.
4. **Automated Account Transfer (ACATS)** — Users initiate full or partial asset migrations across external firms, while the platform safely buffers third-party payload delays.
5. **Rebalancing & Trade Reconciliation** — The rebalancing engine processes pending allocations, coordinates trades with third-party tools (iRebal, Smartleaf), and calculates net-of-fees or gross-of-fees data streams.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Frontend** | React, TypeScript, jQuery, Material UI | White-labeled client dashboard layouts and customizable info widgets. |
| **Backend Core** | PHP + Symfony Framework, Java, Scala | Monolith backend workflows; INSART holds the primary Java engineering expertise on the project. |
| **Big Data / Analytics** | Apache Spark | Upgraded from version 2 to 3.3.1 to optimize core data aggregation pipelines. |
| **Database** | PostgreSQL | Core repository for structured financial objects and system data. |
| **Messaging & Queues** | Amazon MQ | Asynchronously brokers actions across distributed platform environments. |
| **Infrastructure** | Amazon Web Services (AWS), Kubernetes (K8S) | Powers secure container orchestration and cloud-native scaling. |
| **CI/CD & Monitoring** | Jenkins, Grafana, ELK Stack | Manages continuous build automation and comprehensive real-time cluster observability. |

---

## Business Outcome

- **Successful Multi-Custodian Launch** — Completely rebuilt the core data schema to support multi-tenant accounts from diverse clearinghouses under one household, enabling AdvisorEngine to successfully land large institutional clients.
- **Eradicated Legacy Tech Debt** — Systematically migrated the core monolith stack from PHP 7 to PHP 8, shifted Symfony from version 3 through to 5.4, and updated Spark data layers to version 3.3.1.
- **Streamlined Onboarding Pipelines** — Completed critical Charles Schwab refactoring (Phase 6/8) and Fidelity refactoring (Phase 2/3), introducing instant automated post-account-opening ACH routing and joint funding.
- **Stabilized Project Delivery** — Enforced complexity-based estimations and capacity-based sprint planning, which smoothed out engineering spikes and enhanced delivery predictability under tight market deadlines.
- **High-Level Operational Visibility** — Rolled out an internal INSART-designed people metrics dashboard, giving management complete visibility into team engagement levels, performance trends, and critical role impacts.

---

## Lessons Learned

- **Decoupling Core Ingestion Layouts** — Deep architectural modifications like the Multi-Custodian Initiative require completely uncoupling old data dependencies and systematically rewriting data-access layers step-by-step to prevent platform regression.
- **Insulating Against External Downstream Delays** — When dealing with volatile third-party custodian endpoints (such as ACATS or aggregate data services), the platform must implement robust asynchronous callback queues to protect the user experience from API latency.

---

## Reusable Components / Patterns

- [ ] Standardized multi-custodian database mapping templates.
- [ ] Automated framework upgrade path checklists (Symfony 3 to 5.4 progression tracks).
- [ ] Operational vendor transparency and engineering capacity monitoring dashboards.

---

## Resources

| Resource | Link |
|---|---|
| Slide Decks | [`AdvisorEngine (05.02.2024).pptx`](https://docs.google.com/presentation/d/1ozAuoAZJVjt00PAdVqPUBdJg_CYp_Wkd/edit?usp=sharing&ouid=110968320908081389046&rtpof=true&sd=true), [`AdvisorEngine (19/06/23).pptx`](https://docs.google.com/presentation/d/15cWzCRrPioBXYCqT92rDS4gYcWkgBy5R/edit?usp=sharing&ouid=110968320908081389046&rtpof=true&sd=true) |
| Corporate Platform Portal | [AdvisorEngine Platform Home](https://www.advisorengine.com) |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Stanislav Koval** | Java Lead / System Architecture Board Representative |
| **Viktor Kononenko** | Technical Delivery Reporter |
| **Vladyslav Shaldieiev** | Account Management Lead |
| **Vladyslav Derkach** | Front-End Engineering Lead |
| **Serhii Kornushov** | PHP & Symfony Engineering Lead |
| **Kirill Nasardion** | Quality Assurance Team Lead |

---
_Last updated: 2024-Q1 · Status: draft_

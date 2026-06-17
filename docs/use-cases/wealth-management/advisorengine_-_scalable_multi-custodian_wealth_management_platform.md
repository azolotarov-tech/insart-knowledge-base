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

> **One-liner summary** — Modernized and scaled an enterprise-grade end-to-end wealth management platform by embedding 26 billable engineering resources across 7 cross-functional scrum teams[cite: 7]. This initiative delivered critical multi-custodian architectural shifts, high-performance automated account onboarding, and major backend framework upgrades[cite: 7, 8].

---

## Problem Overview

AdvisorEngine operates a purpose-built, data-driven wealth management ecosystem designed for Registered Investment Advisors (RIAs) and Independent Broker-Dealers (IBDs)[cite: 7, 8]. The platform aggregates business-critical workflows, including an advisor-focused CRM, portfolio performance reporting, fee billing, automated asset rebalancing, digital onboarding, and business intelligence modules[cite: 7]. 

To capture a larger market share and onboard high-tier institutional clients, AdvisorEngine needed to execute the Multi-Custodian Initiative (MCI)[cite: 8]. This required migrating a rigid, legacy codebase into a multi-tenant, cloud-native architecture capable of simultaneously balancing data from multiple distinct clearing custodians under single investor households[cite: 8]. Under heavy structural pressure from parent enterprise Franklin Templeton to deliver predictable features rapidly, the platform required deep outstaffing development power and tech consulting to resolve scalability challenges and process inefficiencies[cite: 7].

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Rigid Monolithic Architecture** | Legacy core accounts and household databases were incapable of handling multi-custodian data aggregation in one unified portal workspace[cite: 8]. |
| 2 | **Heavy Technical & Security Debt** | Major application clusters relied on heavily outdated software foundations, including PHP 7, Symfony 3/4, and Apache Spark 2, triggering immediate security risks[cite: 8]. |
| 3 | **3rd-Party Integration Latency** | Critical business flows—such as automated asset transfers (ACATS) and third-party aggregation portals (DST)—frequently encountered long API response delays and communication failures[cite: 8]. |
| 4 | **PDF Builder Rendering Blocks** | The existing Report Packager (RPS) engine layout code made it incredibly difficult for managers to implement UI modifications or build flexible, presentation-quality PDF templates directly from the backend[cite: 8]. |
| 5 | **Agile Delivery Predictability** | Fast-evolving feature demands from major clients generated friction across internal product branches, resulting in delayed product timelines and low delivery schedule visibility[cite: 7]. |

---

## Proposed Solution

INSART integrated 26 billable engineers, project managers, and automated QA specialists directly into 7 of AdvisorEngine's 10 internal cross-functional engineering teams[cite: 7]. Rather than acting purely as transactional outstaffing, our senior engineers joined the core Architecture Board to guide core technical decisions alongside the client's executive leadership[cite: 7].

The joint team restructured the data layer to support the Multi-Custodian Initiative (MCI) and fully refactored custodian onboarding links for Charles Schwab and Fidelity[cite: 7, 8]. On the operational side, INSART introduced key consulting improvements to the client's Scrum approach—such as capacity-based planning and complexity-based estimation models—and built a dedicated transparency metrics dashboard to identify and mitigate team attrition risks early[cite: 7].

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Independent Broker-Dealers (IBDs) & RIAs** | Utilize the purpose-built CRM to manage profiles, track billing workflows, configure configurable fee splits, and automate compliance audits[cite: 7]. |
| **Individual Account Holders** | Access self-navigation features through a configurable client portal, track dynamic wealth benchmarks, and trigger document vaults[cite: 7]. |
| **Firm Managers & Reps** | Design and generate presentation-quality PDF report package templates to execute on-demand or distribute automatically to households[cite: 8]. |

---

## Process / Solution Flow

The core system handles automated multi-custodian operations, digital onboarding, and asset management end-to-end:

1. **Multi-Custodian Consolidation** — The platform ingests and correlates parallel asset streams, allowing investors to manage multiple custodian accounts under a single household view[cite: 8].
2. **Onboarding & Risk Modeling** — Prospective investors launch the digital onboarding workflow, filling out automated asset opening configurations, profile builders, and risk assessment forms[cite: 7].
3. **Custodian Handshake & Funding** — The platform triggers customized API steps with custodians (such as Schwab or Fidelity), utilizing deep DocuSign workflows to execute instant account openings[cite: 7].
4. **Automated Account Transfer (ACATS)** — Users initiate full or partial asset migrations across external firms, while the platform safely buffers third-party payload delays[cite: 8].
5. **Rebalancing & Trade Reconciliation** — The rebalancing engine processes pending allocations, coordinates trades with third-party tools (iRebal, Smartleaf), and calculates net-of-fees or gross-of-fees data streams[cite: 7].

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Frontend** | React, TypeScript, jQuery, Material UI[cite: 7, 8] | White-labeled client dashboard layouts and customizable info widgets[cite: 7, 8]. |
| **Backend Core** | PHP + Symfony Framework, Java, Scala[cite: 7] | Monolith backend workflows; INSART holds the primary Java engineering expertise on the project[cite: 7]. |
| **Big Data / Analytics** | Apache Spark[cite: 7] | Upgraded from version 2 to 3.3.1 to optimize core data aggregation pipelines[cite: 8]. |
| **Database** | PostgreSQL[cite: 7] | Core repository for structured financial objects and system data[cite: 7]. |
| **Messaging & Queues** | Amazon MQ[cite: 7] | Asynchronously brokers actions across distributed platform environments[cite: 7]. |
| **Infrastructure** | Amazon Web Services (AWS), Kubernetes (K8S)[cite: 7] | Powers secure container orchestration and cloud-native scaling[cite: 7]. |
| **CI/CD & Monitoring** | Jenkins, Grafana, ELK Stack[cite: 7] | Manages continuous build automation and comprehensive real-time cluster observability[cite: 7]. |

---

## Business Outcome

- **Successful Multi-Custodian Launch** — Completely rebuilt the core data schema to support multi-tenant accounts from diverse clearinghouses under one household, enabling AdvisorEngine to successfully land large institutional clients[cite: 8].
- **Eradicated Legacy Tech Debt** — Systematically migrated the core monolith stack from PHP 7 to PHP 8, shifted Symfony from version 3 through to 5.4, and updated Spark data layers to version 3.3.1[cite: 7, 8].
- **Streamlined Onboarding Pipelines** — Completed critical Charles Schwab refactoring (Phase 6/8) and Fidelity refactoring (Phase 2/3), introducing instant automated post-account-opening ACH routing and joint funding[cite: 7].
- **Stabilized Project Delivery** — Enforced complexity-based estimations and capacity-based sprint planning, which smoothed out engineering spikes and enhanced delivery predictability under tight market deadlines[cite: 7].
- **High-Level Operational Visibility** — Rolled out an internal INSART-designed people metrics dashboard, giving management complete visibility into team engagement levels, performance trends, and critical role impacts[cite: 7].

---

## Lessons Learned

- **Decoupling Core Ingestion Layouts** — Deep architectural modifications like the Multi-Custodian Initiative require completely uncoupling old data dependencies and systematically rewriting data-access layers step-by-step to prevent platform regression[cite: 8].
- **Insulating Against External Downstream Delays** — When dealing with volatile third-party custodian endpoints (such as ACATS or aggregate data services), the platform must implement robust asynchronous callback queues to protect the user experience from API latency[cite: 8].

---

## Reusable Components / Patterns

- [ ] Standardized multi-custodian database mapping templates[cite: 8].
- [ ] Automated framework upgrade path checklists (Symfony 3 to 5.4 progression tracks)[cite: 7, 8].
- [ ] Operational vendor transparency and engineering capacity monitoring dashboards[cite: 7].

---

## Resources

| Resource | Link |
|---|---|
| Master Slide Deck | `AdvisorEngine (05.02.2024).pptx`[cite: 7] |
| Historic Service Delivery | `Monthly Service Delivery (19/06/23).pptx`[cite: 8] |
| Corporate Platform Portal | [AdvisorEngine Platform Home](https://www.advisorengine.com)[cite: 7] |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Stanislav Koval** | Java Lead / System Architecture Board Representative[cite: 7, 8] |
| **Viktor Kononenko** | Technical Delivery Reporter[cite: 7] |
| **Vladyslav Shaldieiev** | Account Management Lead[cite: 8] |
| **Vladyslav Derkach** | Front-End Engineering Lead[cite: 8] |
| **Serhii Kornushov** | PHP & Symfony Engineering Lead[cite: 8] |
| **Kirill Nasardion** | Quality Assurance Team Lead[cite: 8] |

---
_Last updated: 2024-Q1 · Status: draft_[cite: 7]
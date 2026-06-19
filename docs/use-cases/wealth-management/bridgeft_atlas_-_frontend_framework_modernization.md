---
title: "BridgeFT Atlas — Frontend Framework Modernization & CRM Integration Ecosystem"
type: use-case
status: draft
date: "2019-Q4"
domain: "FinTech"
client: "BridgeFT"
technologies: ["Angular", "Angular Material", "DevExpress", "Golang", "Python", "PostgreSQL"]
experts: ["@AntonGoncharov"]
tags: ["WealthTech", "FrontendMigration", "CRMIntegration", "UIUXRedesign", "StartupScalability"]
---

# BridgeFT Atlas — Frontend Framework Modernization & CRM Integration Ecosystem

> **One-liner summary** — We accelerated the modernization of BridgeFT's Atlas application by successfully migrating its core frontend architecture from legacy AngularJS to Angular within two months and implementing critical advisory CRM integrations.

---

## Problem Overview

BridgeFT operates as a cloud-native, API-first WealthTech infrastructure platform designed to enable Registered Investment Advisors (RIAs), financial institutions, and FinTech innovators to deliver data-driven wealth management outcomes. The platform automates back-office operations and orchestrates digital wealth ecosystems by aligning essential wealth data, portfolio management automation, and performance analytics. 

At the time of engagement, BridgeFT operated as a fast-moving startup with a lean engineering group. Their primary advisor-facing application, Atlas, was heavily constrained by a legacy AngularJS frontend. The platform required an immediate framework migration to ensure future scalability, a comprehensive UI/UX overhaul to provide presentation-quality reports, and front-end integrations with leading financial CRMs. Because BridgeFT lacked internal design resources, they required an autonomous senior frontend specialist to drive this execution.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Legacy Frontend Bottleneck** | The Atlas application was built on obsolete AngularJS architecture, slowing down feature velocity and preventing the utilization of modern web rendering tools. |
| 2 | **Absence of Dedicated UI/UX Designers** | There were no UI/UX designers available on the client side, meaning the engineering team had to drive all layout, component design, and usability workflows autonomously. |
| 3 | **Disjointed CRM Connectivity** | Financial advisors utilizing the platform could not access or view integrated contact data from primary wealth management CRMs within their dashboard. |
| 4 | **Fast-Paced Startup Environment** | BridgeFT possessed unorganized operational processes typical of early-stage startups, requiring highly flexible, self-managed engineering execution. |

---

## Proposed Solution

INSART embedded a full-time Senior Frontend Developer into BridgeFT's core engineering team to collaborate directly with the Co-Founder and CTO. The solution focused on complete frontend decoupled modernization:

* **High-Velocity Migration:** Executed an aggressive, systematic framework modernization to port the entire legacy client application over to modern Angular.
* **Autonomous Interface Engineering:** Selected and configured Angular Material and DevExpress (DevExtreme) libraries to design and deliver high-fidelity data dashboards, analytical widgets, and client reporting interfaces without predefined design prototypes.
* **Documentation-Driven CRM Integration:** Analyzed external technical specifications to build UI-side application connectors for industry-standard advisory platforms.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Registered Investment Advisors (RIAs)** | Monitor practice insights, evaluate portfolio analytics, automate back-office operations, and generate client-ready reports. |
| **Financial Advisors & Wealth Reps** | Review client performance analytics, configure advisory fee billing parameters, and manage contact data synced from external CRMs. |

---

## Process / Solution Flow

The frontend overhaul and integration pipeline were executed through the following sequential steps:

1. **Architecture & API Audit** — Conducted a full code audit of the existing AngularJS application structure while analyzing third-party API documentation for external CRM services.
2. **Framework Transformation** — Migrated the baseline web application layer from AngularJS to type-safe Angular, finishing the transition within a rapid two-month timeline.
3. **UI/UX Component Redesign** — Leveraged Angular Material and DevExpress to independently craft interactive layout components, rendering smooth charting wrappers for performance analytics and advisory fee billing screens.
4. **UI-Side CRM Integration** — Developed custom front-end data consumption layers to safely ingest and display external contact lists and attributes from the Wealthbox API and Salesforce API frameworks.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Frontend Architecture** | Angular | Migrated completely away from legacy AngularJS to enable modular rendering. |
| **UI Components & Charts** | Angular Material, DevExpress | Implemented to deliver interactive dashboards, custom widgets, and financial analytics. |
| **Platform Backend** | Golang, Python | Core microservices managed by BridgeFT’s internal developer infrastructure. |
| **Database Management** | PostgreSQL | Central database storage containing aligned wealth metrics and user configurations. |
| **External Integrations** | Wealthbox API, Salesforce API | Connected directly at the user interface layer to consume advisor contact pipelines. |

---

## Business Outcome

* **Framework Upgrade Delivered in 2 Months** — Successfully completed the core architectural migration from AngularJS to Angular within an efficient two-month production window.
* **Autonomous Dashboard Redesign** — Overcame the absolute absence of client-side graphic designers by utilizing Angular Material and DevExpress to create an enterprise-grade interface for the Atlas app.
* **Expanded FinTech Interoperability** — Introduced seamless UI-side data connectivity with critical advisor platforms, including a functional one-way contacts list synchronization for Salesforce and Wealthbox.
* **Investor-Ready Product Presentation** — Enabled high-fidelity front-end visualization for core business pillars, including client reporting, fee billing, practice insights, and performance analytics.
* **Strategic Technology Foundation** — Positioned the platform to effortlessly scale up its data partnerships with multiple market data providers by securing a type-safe web core.

---

## Lessons Learned

* **Documentation-Driven Integration Capabilities** — When direct communication channels with third-party platform developers are restricted, precise mapping of standard API documentation is fully sufficient to deliver functional UI-layer integration maps.
* **Accelerating Startup Framework Transitions** — Deploying a single, dedicated, full-time senior outstaff engineer can successfully untangle monolithic frontend technical debt without disrupting the backend development velocity of the client's internal team.

---

## Reusable Components / Patterns

* [ ] Custom component migration checklist for AngularJS-to-Angular transitions.
* [ ] Angular Material data table grid configurations for displaying wealth performance analytics.
* [ ] UI-side API integration templates for parsing Wealthbox and Salesforce contact objects.

---

## Resources

| Resource | Link |
|---|---|
| Core Slide Deck | [`BridgeFT (18.09.2023).pptx`](https://docs.google.com/presentation/d/1BO7vv4n8rehkA7cNxA75s6e61Lnq154J/edit?usp=sharing&ouid=110968320908081389046&rtpof=true&sd=true) |
| Application Video Demo | [BridgeFT Atlas App Video Walkthrough](https://www.youtube.com/watch?v=nZSf6R_3mTc) |
| Technical Migration Guide | *[to be added]* |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Anton Goncharov** | Senior Frontend Developer (Full-Time INSART Resource) |

---
_Last updated: 2019-Q4 · Status: draft_

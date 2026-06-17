---
title: "Responsive AI — Microservices Reengineering & Enterprise FinTech Integrations"
type: use-case
status: draft
date: "2023-Q2"
domain: "FinTech"
client: "Responsive AI"
technologies: ["Node.js", "Nest.js", "TypeScript", "Vue.js 3", "D3.js", "Tailwind CSS", "MongoDB", "PostgreSQL", "AWS", "Docker"]
experts: ["@Mariya", "@Mykhailo", "@Oleksii", "@Victor", "@Oleh", "@Alex"]
tags: ["WealthManagement", "Microservices", "APIReengineering", "Refactoring", "PersonalFinance", "AppModernization"]
---

# Responsive AI — Microservices Reengineering & Enterprise FinTech Integrations

> **One-liner summary** — We reengineered a legacy, rigid jQuery wealth management application into an extendable microservices platform built on NestJS and Vue.js 3, developing autonomous APIs and implementing over a dozen enterprise FinTech integrations.

---

## Problem Overview

Responsive AI provides a hybrid wealth management and personal finance application designed for banks, private wealth managers, and Registered Investment Advisors (RIAs). The platform empowers advisors to monitor mass affluent clients' financial health by consolidating tracking for incomes, outcomes, checking/savings accounts, and cash movements. 

Prior to INSART's engagement, the client's legacy application was a monolithic platform built on jQuery and JavaScript. It lacked modularity, was increasingly difficult to maintain, and was fundamentally unextendable, preventing the client from building the key automated third-party integrations required by institutional banks. INSART was brought in to spearhead the platform reengineering from scratch, introducing an extendable microservice architecture.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Unextendable Monolithic Engine** | The original jQuery and raw JavaScript codebase completely limited the client's capability to integrate external CRMs, payment networks, or messaging channels. |
| 2 | **Zero Live Database Access** | Due to strict data segregation and financial infrastructure controls, the engineering team had to build and validate the new API logic entirely on mocked "dummy data." |
| 3 | **Dual Parallel Execution Requirements** | The legacy software had to run continuously in parallel with the new platform branches without causing service disruptions for live users. |
| 4 | **Extensive Integration Overhead** | The application required seamless data sync configurations across a scattered ecosystem of financial tools, electronic signatures, and headless CMS frameworks. |

---

## Proposed Solution

INSART systematically migrated the legacy architecture over to a decoupled, type-safe microservices setup utilizing NestJS (Node.js framework) and TypeScript. We designed and delivered two main autonomous API service layers:

1. **Persona API:** An autonomous engine allowing financial advisors to seamlessly manage client accounts, financial goals, household grouping structures, historical asset pools, and real-time transaction processing.
2. **Enabled API:** A dedicated pipeline layer structured to handle advisor-client onboarding steps and internal multi-format document management.

Concurrently, we built highly interactive Vue.js 3 client portals and administrative panels, using D3.js to render complex wealth analytics, focus mode projections, and cash flow data tracking graphics.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **Financial Advisors / Private Managers** | Access comprehensive summary dashboards to rapidly track client asset shifts, verify life changes, and adjust financial goals. |
| **End Investors / Clients** | Monitor income/outcomes, link banking data, upload compliance items, and request transfers or deposits across banks. |
| **System Administrators** | Utilize the administrative panel to moderate requests, track transaction states, toggle feature flags, and view global usage telemetry. |

---

## Process / Solution Flow

The reengineered system processes administrative configurations and client financial operations through a unified workflow:

1. **Client Identity Synchronization** — The advisor creates or syncs client profiles via integrated CRMs (Wealthbox or Redtail), initializing the identity tracking blocks.
2. **Account Linking & Consent** — The user links external consumer bank accounts via Plaid, establishing real-time verification vectors for checking and savings streams.
3. **Data Aggregation & Mapping** — Raw income and spending transactions flow into the Persona API, where endpoints compile household structures and dynamic cash flow summaries.
4. **Visual Analytics Render** — The front-end client portal calls the Summary and Numeric Data APIs, using D3.js layouts to present clear analytics and financial trends.
5. **Workflow Triggering** — Users execute paid premium actions—such as document uploads, automated deposit positioning, or DocuSign document execution—which triggers direct webhooks across the Admin Panel.
6. **Administrative Validation** — Firm administrators receive the client payloads within the secure Admin Workspace to confirm payment statuses or manually authorize multi-bank cash movements.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Backend Core** | Node.js, Nest.js, TypeScript | Rewrote historical JavaScript patterns into highly maintainable, strongly typed code. |
| **Frontend Portal** | Vue.js 3, D3.js, Tailwind CSS | Built modular administrative and client workspaces backed by clean data charts. |
| **Database Storage** | MongoDB, PostgreSQL | Handled multi-tiered structured application entities and transaction histories. |
| **Infrastructure & CI/CD** | AWS Cloud, Docker, Bitbucket Pipelines | Containerized microservice layers deployed through fully automated code pipelines. |
| **Testing Frameworks** | Postman, Testrail, Jest, Cypress | Supported complete backend API validation alongside full end-to-end user regression testing. |
| **FinTech Integrations** | Plaid, Wealthbox, Redtail, Tax Status | Connected raw banking streams, advisory CRMs, and official IRS tax transcript data. |
| **E-Sign & Document Apps** | DocuSign, Adobe Sign, OneSpan | Embedded compliant digital signature collection layers. |
| **Communications & CMS** | Intercom, Slack, Amazon SES, Mailgun, Prismic | Governed conversational support, team alerting, bulk email output, and headless content. |

---

## Business Outcome

* **Transitioned to a Maintainable Microservices Footprint** — Eradicated unextendable jQuery foundations, replacing them with modular NestJS API layers that allow individual microservices to scale independently.
* **Delivered 12 Production-Ready Integrations** — Successfully mapped out and built an extensive partner integration landscape spanning top-tier wealth CRMs, e-sign frameworks, communication tools, and data aggregators.
* **Maintained Uninterrupted Parallel Services** — Facilitated seamless deployments by ensuring the new platform additions operated smoothly alongside legacy systems without operational downtime.
* **Unblocked Blocked Frontend Cycles via Mock API Engineering** — Mitigated a complete lack of live database access by implementing fully mocked data endpoint payloads, allowing user interface testing and verification to proceed smoothly.
* **Enabled Granular Feature Monetization** — Constructed a feature-toggling admin engine, allowing the client to activate or deactivate custom paid modules (such as specific multi-bank transfers, DocuSign modules, or advanced analytics modes) on demand.

---

## Lessons Learned

* **Mocking-Driven Development in Regulated Arenas** — When access to live production banking databases is blocked due to compliance or client environment limits, building fully realized mocked data responses early ensures frontend and API signature validation can conclude on schedule.
* **Microservices for Platform Pivot Preparedness** — Moving away from monolithic script engines toward clean microservices ensures that future business adjustments or additional framework integrations do not impact core financial calculation features.

---

## Reusable Components / Patterns

* [ ] Reusable NestJS boilerplate patterns for rapid third-party financial CRM API mappings.
* [ ] Modular Vue.js 3 layout dashboard widgets integrated with Tailwind CSS styles.
* [ ] D3.js visualization scripts for custom tracking of personal income and expense arrays.

---

## Resources

| Resource | Link |
|---|---|
| Overview | [`Responsive AI (30.10.2023).pptx`](https://docs.google.com/presentation/d/1TG4D38_4qRw9w5bozaYwLpT8szkt-mxM1BDKaEKDNDw/edit?usp=sharing), [`Responsive AI (19.09.2023).pptx`](https://docs.google.com/presentation/d/1VURsR32dr7aj37c60zxkhECkAZ55JXVcOsAuTRyExSM/edit?usp=sharing) |
| Public Corporate Space | [Responsive AI Official Domain](https://www.responsive.ai/) |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Mariya** | Project Manager (Wrap-up / Delivery phase) |
| **Alex** | Project Manager (Initial Launch phase) |
| **Mykhailo** | Lead Frontend Engineer (Vue.js 3 / D3.js architecture) |
| **Oleksii** | Backend Engineer (NestJS / TypeScript development) |
| **Victor** | Backend Engineer (API structures & endpoints) |
| **Oleh** | Manual QA Engineer (Postman & Testrail verification) |

---
_Last updated: 2023-Q2 · Status: draft_

---
title: "Mirador Gateway Portal & RELI — Bespoke FinTech SaaS and Document Automation"
type: use-case
status: draft
date: "2024-Q1"
domain: "FinTech"
client: "Mirador"
technologies: ["React", "Node.js", "Typescript", "Gatsby.js", "MongoDB", "Cosmic.js", "UiPath", "Alkymi", "AWS"]
experts: ["@VladyslavDerkach"]
tags: ["SaaS", "WealthManagement", "RPA", "AI", "OCR", "DataExtraction"]
---

# Mirador Gateway Portal & RELI — Bespoke FinTech SaaS and Document Automation

> **One-liner summary** — We built Gateway Portal, a highly customizable SaaS portal for wealth advisors and multi-family offices, while introducing AI-driven document extraction (RELI) and RPA document retrieval systems to eliminate manual data entry.

---

## Problem Overview

Mirador provides high-end financial services to Single Family Offices, Wealth Managers, RIAs, Endowments, and Foundations. To better serve clients such as UBS, Steward Partners, and Thrivent Advisor Network, Mirador required a centralized, white-label client portal (the Gateway Portal). They also faced immense operational burdens extracting data from physical forms manually, alongside the tedious task of retrieving documents across hundreds of third-party custodian portals.

INSART was brought in to establish a robust development and delivery flow, resolve existing software instability, implement key third-party integrations, and design automations for document processing and data extraction.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Process Instability & Bug Backlog** | The Gateway Portal initially suffered from non-working legacy functionalities, leading to endless iterations of bug-fixing and client friction. |
| 2 | **Absence of testing and QA resources** | The client possessed neither a formal QA budget nor dedicated automated testing tools, resulting in software regression issues. |
| 3 | **Complex Multi-Tenant Customization** | Every wealth management client required a unique, white-labeled experience with bespoke widgets, color palettes, schemas, branding, and layouts. |
| 4 | **Inconsistent Internal Alignment** | Internal friction between the client's tech and product teams hindered progress, which was further complicated by an undefined release process. |
| 5 | **Heavy Manual Operations** | Back-office teams manually downloaded client reports across hundreds of unique portals and transcribed data from various unstructured documents. |

---

## Proposed Solution

INSART restructured the development lifecycle, moving the team toward highly efficient Scrum and Kanban methodologies, while simultaneously implementing structured E2E testing and a reliable release flow. 

We delivered three major systems:
1. **The Gateway Portal (SaaS Platform)**: A modular web application offering a highly editable admin panel where administrators can custom-tailor widgets, layouts, and colors for individual advisory networks.
2. **RELI Flow**: An AI-integrated document automation system that processes physical financial forms via OCR and routes data to downstream financial reporting databases.
3. **Retrieval Automation**: A robotic process automation (RPA) engine designed to autonomously log in, navigate, and parse client documents from third-party portals.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| **End Investors (UHNW)** | View unified net worth, check curated market content, interact with secure vaults, and connect with their advisory teams. |
| **Financial Advisors** | Showcase custom insights, manage documents, handle workflows, and configure customized dashboards for clients. |
| **Mirador Admins** | Build custom-branded client portals on the fly by customizing colors, logos, icons, widgets, and API settings from an admin panel. |
| **Back-Office Operations** | Oversee the automated extraction (RELI) and automated ingestion (Retrieval) pipeline. |

---

## Process / Solution Flow

### The RELI Document Processing Pipeline:
1. **Ingestion & Classification** — Documents are fed into the system where artificial intelligence (Alkymi) is trained to automatically recognize specific document classes.
2. **OCR & Extraction** — Optical Character Recognition (OCR) is applied to parse the document contents and extract critical financial data points.
3. **Downstream Integration** — The extracted data is automatically validated and sent to downstream wealth platforms like Addepar or SalesForce.
4. **Archiving** — Scanned original files are automatically structured and saved in ShareFile following pre-defined naming patterns.

### The Document Retrieval Pipeline:
1. **Credential Gathering** — Safe authentication criteria are securely queried from Salesforce.
2. **Autonomous Retrieval** — UiPath robots log into targeted portals (scaling up to 200+ portals and 4,000+ accounts), navigating custom structures.
3. **Parsing & Storage** — Data is parsed, filtered, structured, and saved into a local MongoDB, with alerts triggered via EzTexting services.

<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_project_structure.png" width="600">

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| **Frontend** | React, TypeScript, Styled-components, Gatsby.js, Material UI | Optimized for highly modular, configurable, and white-labeled SaaS performance. |
| **Backend** | Node.js, Express, TypeScript, HBS, Cosmic.js CMS | Headless CMS system migrated from Cosmic v1 to Cosmic v2 to support robust portal schemas. |
| **Database** | MongoDB Cloud | Distributed storage handling configuration, metadata, and portal retrieval outputs. |
| **Automation & AI** | UiPath (Studio & Orchestrator), Alkymi AI | Runs automated bots for portal downloads and AI models for structural document OCR. |
| **Security & Identity** | Okta (SSO), JWT, SAST/DAST Security Audits | Integrated custom 2FA flows and underwent rigorous security audits. |
| **Integrations** | Addepar, BlackDiamond, Salesforce, AWS Quicksight, Box | Pulls asset diagrams, pushes transactions, hosts analytical dashboards, and syncs users. |
| **Infrastructure** | GitHub, AWS, Netlify | Continuous build pipelines and serverless static hosting. |

<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_architecture.png" width="600">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_architecture_mfa.png" width="600">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_architecture_retrieval.png" width="600">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_development_process.png" width="600">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_deployment_flow.png" width="600">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_addepar_integration.png" width="300">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_black_diamond_integration.png" width="300">
<img src="https://raw.githubusercontent.com/azolotarov-tech/insart-knowledge-base/main/Assets/%20use-cases/wealth-management/mirador_reli_flow.png
" width="600">

---

## Business Outcome

- **Client-Centric SaaS Customizability** — Developed a fully editable workspace allowing advisors to dynamically configure widgets, portfolios, block architectures, and color palettes right from the admin dashboard without writing code.
- **Operational Scalability** — Successfully rolled out automated RPA portal retrieval across high-profile pilot networks, preparing the client to scale retrieval from 4 initial portals up to 200 portals and over 4,000 separate client accounts.
- **Improved Engineering Processes** — Mitigated the complete lack of QA resources by shifting developers to rigorous local testing practices, introducing E2E test flows, and eliminating chronic legacy platform bugs.
- **Enterprise Readiness** — Prepared Gateway and RELI for enterprise adoption by completing security audit compliance pipelines (both SAST and DAST), optimizing code packages, and executing smooth Okta SSO/2FA updates.

---

## Lessons Learned

- **Developer-led Testing Strategies** — When a client does not have a formal budget for QA personnel, introducing structured E2E test suites run directly by the development team can bridge the gap and stabilize a failing legacy application.
- **Process Mediation** — Introducing Kanban and structured Scrum frameworks helps developers stay isolated and productive even when conflicts exist between technical leads and product management on the client's side.

---

## Reusable Components / Patterns

- [x] Custom white-label SaaS configuration layout engines.
- [x] UiPath script logic blueprints for logging in and navigating complex MFA-protected client portals.
- [x] Standard Cosmic.js CMS data schemas for customizable landing page layouts.

---

## Resources

| Resource | Link |
|---|---|
| Code Repository | *[to be added]* |
| Slide Deck | [`Mirador (19.06.2023)`](https://docs.google.com/presentation/d/1zPYff10Jlt7ZCpXuQnxXpOuG_bL_1jnY/edit?usp=sharing&ouid=110968320908081389046&rtpof=true&sd=true) & [`Mirador (26.03.2024)`](https://docs.google.com/presentation/d/1wy7iOm25umeYHFolTv2Qa9RX0ctSs3iS/edit?usp=sharing&ouid=110968320908081389046&rtpof=true&sd=true) |
| Integration Specs | Addepar / BlackDiamond API Integration Specs |

---

## Experts

| Expert | Role on Project |
|---|---|
| **Vladyslav Derkach** | Project Leader / Reporter |

---
_Last updated: 2024-Q1 · Status: draft_

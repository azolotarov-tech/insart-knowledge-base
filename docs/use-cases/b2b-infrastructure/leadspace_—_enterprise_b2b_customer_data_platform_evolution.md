---
title: "Leadspace — Enterprise B2B Customer Data Platform Evolution"
type: use-case
status: draft
date: "2024-Q2"
domain: "MarTech / FinTech CRM"
client: "Leadspace"
technologies: [Java, JavaScript, Angular, Angular Material, Airflow, SingleStore, Redis, Keycloak, Tray.io, WebSockets]
experts: [@AntonHoncharov, @EugenePekhulia, @AndriiLyashenko, @DmytroVaravashenko, @ElenaAmelina, @ArtemVorotnikov, @MykolaShvets, @ArtemVarvashenko]
tags: [CDP, DataUnification, TotalAddressableMarket, GeospatialClustering, LowCodeIntegration, ProfileManagement]
---

# Leadspace — Enterprise B2B Customer Data Platform Evolution

> **One-liner summary** — We scaled and modernized Leadspace's Customer Data Platform by building advanced data unification interfaces, implementing automated low-code integrations, and engineering a complex geospatial clustering engine handling over 20 million company records[cite: 9, 10].

---

## Problem Overview

Leadspace operates an enterprise-grade B2B Customer Data Platform (CDP) designed to help sales and marketing organizations find, score, and convert ideal prospects via personalized multi-channel engagement[cite: 9, 10]. The core engine leverages AI, machine learning, and intent signals to unify client 1st-party data with rich 3rd-party intelligence extracted from over 40 distinct trusted data sources[cite: 9, 10]. 

To sustain rapid growth and outperform competitors, Leadspace needed to transform its platform from basic API endpoints and on-demand tools into an expansive, intuitive self-service ecosystem (Studio and Studio-Next)[cite: 9, 10]. However, expanding the platform introduced severe technical hurdles: custom-coded native enterprise integrations were too expensive to maintain, a legacy "action-based" client billing framework triggered recurring customer transparency disputes, and displaying massive Total Addressable Market (TAM) analytics across tens of millions of records severely bottle-necked standard visual interfaces[cite: 9, 10].

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | High Traditional Integration Overhead[cite: 10] | Developing, testing, and deploying native custom Java integrations for separate target marketing environments (Salesforce, HubSpot, Marketo) was highly resource-intensive and cost-prohibitive[cite: 9, 10]. |
| 2 | Legacy Billing Opacity & Overbilling[cite: 9] | The legacy billing engine calculated client invoices based on raw platform actions rather than unique records under management, causing customer friction and a complete lack of operational transparency[cite: 9]. |
| 3 | Massive Scale Geospatial Data Bottlenecks[cite: 9] | Displaying more than 20 million company location points fluidly across a map required a dynamic clustering engine that adapted seamlessly to zoom layers without cross-contaminating geographical boundaries[cite: 9]. |
| 4 | Requirement Ambiguity & Regression Risks[cite: 10] | Rapid initial development of core client modules (like the Segment Builder and TAM interface) suffered heavily from a complete lack of product requirements and massive systemic code regressions[cite: 10]. |

---

## Proposed Solution

INSART scaled up a dedicated engineering team—expanding from a single frontend developer to a high-velocity team of 7 specialists—to systematically refactor and implement feature sets for Leadspace's core sub-systems (the Apps Team and the Connect/APIs Team)[cite: 10]. 

The architecture decoupled heavy integration requirements from core engineering by deploying **Tray.io** as a specialized low-code automation middleware layer[cite: 10]. For reporting and visibility, INSART built an isolated **Profiles Under Management (PUM)** auditing architecture to create absolute cost transparency for B2B subscribers[cite: 9]. To resolve the complex visualization needs, the team engineered a custom multi-layered geospatial clustering algorithm using GeoJSON features to map and cluster up to 20 million distinct business coordinates cleanly based on dynamic viewport zoom parameters[cite: 9].

### Key Users & Roles

| Role | Responsibility |
|---|---|
| Enterprise Sales & Marketing Teams[cite: 9] | Ingest native 1st-party data, pinpoint total market whitespace opportunities, create hyper-segmented campaigns, and review data health metrics[cite: 10]. |
| Client Account Administrators[cite: 9] | Authenticate safely across corporate apps using Single Sign-On (SSO) and track consumption via clean, itemized PUM billing statements[cite: 9, 10]. |

---

## Process / Solution Flow

1. **Multi-Source Data Unification** — The ingestion pipeline streams customer datasets and matches them against extensive 3rd-party context indices gathered from 40+ trusted sources[cite: 9, 10].
2. **Low-Code Integration Routing** — Real-time event handling, multi-directional data cleaning, safety validation, and data calculations are processed using unified Tray.io automated workflows[cite: 9].
3. **Data Deployment** — Cleaned and fully enriched buyer profile insights are automatically pushed straight to client environments (Marketo, Eloqua, Salesforce, HubSpot)[cite: 9].
4. **TAM Segmentation & Space Analysis** — SingleStore and Redis process granular target queries to isolate high-value market prospects missing from the client's current sales pipeline[cite: 10].
5. **Geospatial UI Layering** — The map UI parses GeoJSON point arrays, dynamically executing clustering computations so that localized companies bundle into customizable cluster counts per zoom level[cite: 9].

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| Backend Architecture | Java, Apache Airflow, WebSockets, DBR[cite: 10] | Drives background calculation sequences, handles massive data processing pipelines, and maintains real-time UI data updates[cite: 10]. |
| Frontend Interface | JavaScript, Angular, Angular Material, Monorepo Architecture[cite: 10] | Powers a fast, self-service dashboard interface designed to manipulate complex account segmentation definitions cleanly[cite: 10]. |
| High-Speed Storage | SingleStore, Redis[cite: 10] | Facilitates instantaneous analytics, bucket tracking, and real-time total addressable market calculation routines[cite: 10]. |
| Integration Middleware | Tray.io[cite: 10] | Replaced traditional custom Java connections with an agile, no-code/low-code workflow engine to drastically cut development budgets[cite: 10]. |
| Corporate Security | Keycloak[cite: 11] | Implements enterprise-grade Single Sign-On (SSO) access controls across all isolated web products[cite: 10]. |

---

## Business Outcome

- **Drastic Reduction in Integration Costs** — Adopting low-code Tray.io workflows made configuring enterprise software integrations significantly more cost-effective compared to traditional native Java engineering[cite: 10].
- **Clean Billing Transparency & Churn Mitigation** — Successfully launched the Profiles Under Management (PUM) metric matrix, ending corporate overbilling issues and allowing sales teams to close enterprise contracts under a predictable pricing structure[cite: 9, 10].
- **Market Advantage over Competitors** — Engineered and shipped the advanced Total Addressable Market (TAM) distribution metrics dashboard ahead of competitor product timelines, significantly boosting overall system value[cite: 10].
- **Investor Traction & High-Level Demos** — Rapidly compiled and finalized the "Studio-Next" configuration prototype for the major Forrester conference, successfully demonstrating core product value to attract venture funding[cite: 10].
- **Unlocking Enterprise Scalability** — Rolled out a map engine capable of managing 20 million location records seamlessly, expanding visualization capabilities into regional marketing spaces[cite: 9, 11].

---

## Lessons Learned

- **Defeat Requirements Deficits with Agile Syncs** — When rapid feature development (such as the Segment Builder) suffers from missing product specifications, launching daily collaborative alignment meetings and frequent software micro-demos bridges the gap and protects project direction[cite: 10].
- **Enforce Early Automated Regression Testing** — Heavy analytical pipeline modifications across the Studio App and TAM modules caused recurring data regressions, proving that complex, data-heavy products require robust automated test coverage built out from day one[cite: 10].

---

## Reusable Components / Patterns

- [ ] [Low-Code Enterprise Integration Blueprint (Tray.io Design Pattern)](../../best-practices/integrations/trayio-lowcode.md)
- [ ] Layered GeoJSON Geospatial Clustering Template for 20M+ Records
- [ ] Offline Profiles Under Management (PUM) Transaction Validation Module

---

## Resources

| Resource | Link |
|---|---|
| Core Technical Deck | `Leadspace - Service Delivery` presentation file[cite: 9] |
| Architectural History Deck | `Leadspace - 29.05.23` presentation file[cite: 10] |
| Cross-Project Strategic Review | `Service Delivery Meeting -- 2024-05-29` documentation[cite: 11] |

---

## Experts

| Expert | Role on Project |
|---|---|
| Anton Honcharov[cite: 9] | Lead Frontend Engineer (Segment Builder, Studio App, TAM Dashboard)[cite: 10] |
| Eugene Pekhulia[cite: 9] | Business Analyst & Core Developer (TAM Module, SSO Security, PUM Billing Engine)[cite: 10] |
| Andrii Lyashenko[cite: 10] | Full-Stack Software Engineer (Studio App Data Unification, TAM Analytics)[cite: 10] |
| Dmytro Varavashenko[cite: 10] | Core Software Engineer (Studio App, TAM Buckets, 1st Party Data Ingestion)[cite: 10] |
| Mykola Shvets[cite: 10] | Low-Code Integration Specialist (Tray.io Pipeline Integration)[cite: 10] |

---

_Last updated: 2026-06-15 · Status: draft_
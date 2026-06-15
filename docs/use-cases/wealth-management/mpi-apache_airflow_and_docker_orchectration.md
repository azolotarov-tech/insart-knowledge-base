---
title: MPI Data Pipeline Modernization — Apache Airflow & Docker Orchestration
type: use-case
status: draft
date: 2024-Q4
domain: FinTech
client: Markov Processes International (MPI)
technologies: [Apache Airflow, Docker, Perl, MariaDB, Samba, Linux, Windows]
experts: [@GrigoriPanciohin]
tags: [DataPipeline, ETL, WorkflowAutomation, OnPremises, MonolithModernization]
---

# MPI Data Pipeline Modernization — Apache Airflow & Docker Orchestration

> **One-liner summary** — We modernized a legacy, monolithic financial data ETL pipeline using Apache Airflow and Docker containerization. This upgrade cut data source onboarding times to just 2 minutes and accelerated core data processing pipelines by 20% on the client's on-premises infrastructure.

---

## Problem Overview

Markov Processes International (MPI) provides high-end financial analysis reports to major agencies of financial advisers, evaluating investment funds, banks, and institutions against their risk claims. Their proprietary reporting algorithms—originally designed around Nobel Prize-winning economic models—rely on parsing and aggregating data from multiple third-party providers like Morningstar to guarantee market-leading report precision. 

Before INSART's engagement, MPI's internal data delivery framework operated on a 15-year-old legacy system. The backend was a rigid monolith running sequential Extract, Transform, Load (ETL) operations scheduled purely via localized Linux cron tabs. Business logic was heavily entangled with infrastructure code, server environments were configured manually, and visibility into operational pipelines was severely limited. Consequently, system failures were often discovered reactively when clients complained about broken updates. While MPI explored moving to a cloud infrastructure to solve these scaling issues, the projected operational costs forced them to pivot back to optimizing their on-premises architecture.

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | Sequential Monolithic ETL Bottlenecks | Data parsing tasks were executed completely in sequence, creating a massive processing backlog as data volume scales. |
| 2 | Entangled Code & Architecture | Core algorithmic business logic and pipeline infrastructure code were mixed together, making updates risky and costly to maintain. |
| 3 | Blind Monitoring & Reactive Fixes | Relying on standalone custom applications and cron tabs left the team unaware of data pipeline bugs until clients reported issues. |
| 4 | Prohibitive Cloud Costs | Early initiatives to rebuild pipelines inside commercial cloud environments were halted because the computational subscription fees were too high. |
| 5 | High Data Onboarding Overhead | Integrating new external financial data providers into the legacy pipeline required labor-intensive, custom manual developer configurations. |

---

## Proposed Solution

INSART proposed and built a non-disruptive optimization layer directly on top of MPI’s existing on-premises codebase, avoiding a risky ground-up rewrite of their primary algorithms. The solution introduced **Apache Airflow** as the central workflow management engine, supplemented by **Docker containerization** to isolate data environments. 

By creating a standardized, template-driven ETL task topology, the system unlocked parallelization across every stage of the ingestion pipeline This architecture unifies MPI's dual delivery streams: it simultaneously feeds both the legacy installable Windows desktop packages downloaded by clients and their modern web-based UI application platform. Airflow's built-in UI gives the internal engineering team total control over task scheduling, pipeline monitoring, and centralized error logs out of the box.

### Key Users & Roles

| Role | Responsibility |
|---|---|
| Internal Engineering Team (*Andrei Spassibojko, Vladimir Nikitin*) | Manage data pipeline sequences, quickly configure new source templates, and monitor task runs via the Airflow UI. |
| Financial Advisers & Agencies (End Clients) | Access highly accurate financial analysis datasets through desktop updates or web platforms without encountering broken pipeline packages. |

---

## Process / Solution Flow

1. **Multi-Source Data Ingestion** — External financial files are pulled from multiple providers (e.g., Morningstar) simultaneously into an on-premises staging directory via Samba file sharing[.
2. **Template Validation & Parsing** — Apache Airflow triggers isolated Docker containers running modernized Perl ETL scripts to map incoming data.
3. **Parallel ETL Execution** — Airflow coordinates parallel data transformations across Linux and Windows server environments, ensuring highly optimized hardware utilization.
4. **Early Warning Integrity Auditing** — Automated health checks validate structural correctness during package generation, isolating data bugs before packages hit production.
5. **Unified Delivery** — Validated financial analytical data is concurrently exposed to both the cloud-ready web app UI and compiled into local sync packages for desktop clients.

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| Orchestration & Scheduling | Apache Airflow | Replaced fragmented cron tabs; handles 95–99% of data workflow management needs out of the box. |
| Container Isolation | Docker | Ensures environment parity across mixed OS hosts and fast, agile local development. |
| Core Scripting Layer | Perl | Preserved the robust, 15-year-old operational algorithms while decoupling infrastructure wrapper dependencies. |
| Database Engine | MariaDB (MySQL) | Main repository for parsed financial metrics and historical data logs. |
| File Storage Integration | Samba | Facilitates multi-platform file distribution and sharing across Windows and Linux nodes. |
| Version Control & CI/CD | GitLab | Extracted from main production environments to run on dedicated development cycles. |

---

## Business Outcome

- **2-Minute Data Source Onboarding** — Streamlined integration of fresh financial feeds from hours of manual setup down to 2 minutes by deploying standardized copy-paste ETL templates.
- **20% Faster Pipeline Execution** — Introducing pipeline parallelization via Airflow accelerated data calculations by 20% compared to the legacy sequential layout.
- **Proactive Issue Detection** — Shifted from reactive client complaints to internal discovery, catching structural data issues in the package building phase before they reach clients.
- **Drastically Lower Overhead Costs** — Avoided expensive cloud compute costs by configuring the Airflow orchestration layer to leverage MPI's current on-premises server resources.
- **Seamless Global Rollout** — Deployed the updated Airflow background framework to production for all existing global clients with zero disruption to services.

---

## Lessons Learned

- **Deploy Addition Over Reconstruction** — When dealing with massive, historically proven codebases, introducing an orchestration wrapper (like Airflow) on top of the original scripts delivers optimization faster and at a much lower risk than an unneeded code rewrite.
- **Template Core Tasks Early** — Designing standard templates for repetitive data tasks requires upfront effort but maximizes long-term returns by reducing future configuration times down to minutes.
- **Account for the Learning Curve** — Moving internal operations teams from basic crontab habits to advanced DAG monitoring environments requires dedicated time for adjustments and onboarding.

---

## Reusable Components / Patterns

- [ ] On-Premises Apache Airflow Docker Ingestion Template
- [ ] Standardized Perl ETL DAG Parser Wrapper for Airflow Orchestration

---

## Resources

| Resource | Link |
|---|---|
| Presentation Slide Deck | [`[EB] Service Delivery Meeting — MPI (22-Oct-2024)`](https://docs.google.com/presentation/d/1jxO_BEBsuTTPPOVXDIpTvubJmMGY5m8hdGtBZ2-7k4U/edit?usp=drive_link) |
| Meeting Notes | [Meeting Notes](https://docs.google.com/document/d/1rSg8UVwsyqWouVxPf-4Zv718Jdw3Uubf8MNArkKnuxg/edit?usp=drive_link) |

---

## Experts

| Expert | Role on Project |
|---|---|
| Grigori Panciohin | Lead Solutions Architect (Proposed and designed the unified Apache Airflow architecture). |

---

_Last updated: 2026-06-15 · Status: draft_

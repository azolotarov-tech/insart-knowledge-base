---
title: "MPI Data Pipeline Modernization — Apache Airflow & Docker Orchestration"
type: use-case
status: draft
date: "2024-Q4"
domain: "FinTech"
client: "Markov Processes International (MPI)"
technologies: [Apache Airflow, Docker, Perl, MariaDB, Samba, Linux, Windows]
experts: [@GrigoriPanciohin]
tags: [DataPipeline, ETL, WorkflowAutomation, OnPremises, MonolithModernization]
---

# MPI Data Pipeline Modernization — Apache Airflow & Docker Orchestration

> **One-liner summary** — We modernized a legacy, monolithic financial data ETL pipeline using Apache Airflow and Docker containerization[cite: 7]. This upgrade cut data source onboarding times to just 2 minutes and accelerated core data processing pipelines by 20% on the client's on-premises infrastructure[cite: 7, 8].

---

## Problem Overview

Markov Processes International (MPI) provides high-end financial analysis reports to major agencies of financial advisers, evaluating investment funds, banks, and institutions against their risk claims[cite: 7]. Their proprietary reporting algorithms—originally designed around Nobel Prize-winning economic models—rely on parsing and aggregating data from multiple third-party providers like Morningstar to guarantee market-leading report precision[cite: 7]. 

Before INSART's engagement, MPI's internal data delivery framework operated on a 15-year-old legacy system[cite: 8]. The backend was a rigid monolith running sequential Extract, Transform, Load (ETL) operations scheduled purely via localized Linux cron tabs[cite: 7]. Business logic was heavily entangled with infrastructure code, server environments were configured manually, and visibility into operational pipelines was severely limited[cite: 7]. Consequently, system failures were often discovered reactively when clients complained about broken updates[cite: 7]. While MPI explored moving to a cloud infrastructure to solve these scaling issues, the projected operational costs forced them to pivot back to optimizing their on-premises architecture[cite: 8].

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | Sequential Monolithic ETL Bottlenecks[cite: 7] | Data parsing tasks were executed completely in sequence, creating a massive processing backlog as data volume scales[cite: 7]. |
| 2 | Entangled Code & Architecture[cite: 7] | Core algorithmic business logic and pipeline infrastructure code were mixed together, making updates risky and costly to maintain[cite: 7]. |
| 3 | Blind Monitoring & Reactive Fixes[cite: 7] | Relying on standalone custom applications and cron tabs left the team unaware of data pipeline bugs until clients reported issues[cite: 7]. |
| 4 | Prohibitive Cloud Costs[cite: 8] | Early initiatives to rebuild pipelines inside commercial cloud environments were halted because the computational subscription fees were too high[cite: 8]. |
| 5 | High Data Onboarding Overhead[cite: 8] | Integrating new external financial data providers into the legacy pipeline required labor-intensive, custom manual developer configurations[cite: 8]. |

---

## Proposed Solution

INSART proposed and built a non-disruptive optimization layer directly on top of MPI’s existing on-premises codebase, avoiding a risky ground-up rewrite of their primary algorithms[cite: 8]. The solution introduced **Apache Airflow** as the central workflow management engine, supplemented by **Docker containerization** to isolate data environments[cite: 7]. 

By creating a standardized, template-driven ETL task topology, the system unlocked parallelization across every stage of the ingestion pipeline[cite: 7, 8]. This architecture unifies MPI's dual delivery streams: it simultaneously feeds both the legacy installable Windows desktop packages downloaded by clients and their modern web-based UI application platform[cite: 8]. Airflow's built-in UI gives the internal engineering team total control over task scheduling, pipeline monitoring, and centralized error logs out of the box[cite: 7, 8].

### Key Users & Roles

| Role | Responsibility |
|---|---|
| Internal Engineering Team (*Andrei Spassibojko, Vladimir Nikitin*)[cite: 7] | Manage data pipeline sequences, quickly configure new source templates, and monitor task runs via the Airflow UI[cite: 7, 8]. |
| Financial Advisers & Agencies (End Clients)[cite: 7] | Access highly accurate financial analysis datasets through desktop updates or web platforms without encountering broken pipeline packages[cite: 8]. |

---

## Process / Solution Flow

1. **Multi-Source Data Ingestion** — External financial files are pulled from multiple providers (e.g., Morningstar) simultaneously into an on-premises staging directory via Samba file sharing[cite: 7].
2. **Template Validation & Parsing** — Apache Airflow triggers isolated Docker containers running modernized Perl ETL scripts to map incoming data[cite: 7].
3. **Parallel ETL Execution** — Airflow coordinates parallel data transformations across Linux and Windows server environments, ensuring highly optimized hardware utilization[cite: 7].
4. **Early Warning Integrity Auditing** — Automated health checks validate structural correctness during package generation, isolating data bugs before packages hit production[cite: 7].
5. **Unified Delivery** — Validated financial analytical data is concurrently exposed to both the cloud-ready web app UI and compiled into local sync packages for desktop clients[cite: 8].

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| Orchestration & Scheduling | Apache Airflow[cite: 7] | Replaced fragmented cron tabs; handles 95–99% of data workflow management needs out of the box[cite: 7, 8]. |
| Container Isolation | Docker[cite: 7] | Ensures environment parity across mixed OS hosts and fast, agile local development[cite: 7]. |
| Core Scripting Layer | Perl[cite: 7] | Preserved the robust, 15-year-old operational algorithms while decoupling infrastructure wrapper dependencies[cite: 7, 8]. |
| Database Engine | MariaDB (MySQL)[cite: 7] | Main repository for parsed financial metrics and historical data logs[cite: 7]. |
| File Storage Integration | Samba[cite: 7] | Facilitates multi-platform file distribution and sharing across Windows and Linux nodes[cite: 7]. |
| Version Control & CI/CD | GitLab[cite: 7] | Extracted from main production environments to run on dedicated development cycles[cite: 7]. |

---

## Business Outcome

- **2-Minute Data Source Onboarding** — Streamlined integration of fresh financial feeds from hours of manual setup down to 2 minutes by deploying standardized copy-paste ETL templates[cite: 7, 8].
- **20% Faster Pipeline Execution** — Introducing pipeline parallelization via Airflow accelerated data calculations by 20% compared to the legacy sequential layout[cite: 7].
- **Proactive Issue Detection** — Shifted from reactive client complaints to internal discovery, catching structural data issues in the package building phase before they reach clients[cite: 7].
- **Drastically Lower Overhead Costs** — Avoided expensive cloud compute costs by configuring the Airflow orchestration layer to leverage MPI's current on-premises server resources[cite: 8].
- **Seamless Global Rollout** — Deployed the updated Airflow background framework to production for all existing global clients with zero disruption to services[cite: 8].

---

## Lessons Learned

- **Deploy Addition Over Reconstruction** — When dealing with massive, historically proven codebases, introducing an orchestration wrapper (like Airflow) on top of the original scripts delivers optimization faster and at a much lower risk than an unneeded code rewrite[cite: 8].
- **Template Core Tasks Early** — Designing standard templates for repetitive data tasks requires upfront effort but maximizes long-term returns by reducing future configuration times down to minutes[cite: 8].
- **Account for the Learning Curve** — Moving internal operations teams from basic crontab habits to advanced DAG monitoring environments requires dedicated time for adjustments and onboarding[cite: 7].

---

## Reusable Components / Patterns

- [ ] [On-Premises Apache Airflow Docker Ingestion Template](../../best-practices/data-engineering/airflow-onprem.md)
- [ ] Standardized Perl ETL DAG Parser Wrapper for Airflow Orchestration

---

## Resources

| Resource | Link |
|---|---|
| Presentation Slide Deck | `[EB] Service Delivery Meeting — MPI (22-Oct-2024)`[cite: 8] |
| Shared Architecture Review | Internal Project Knowledge Base Notes[cite: 8] |

---

## Experts

| Expert | Role on Project |
|---|---|
| Grigori Panciohin[cite: 7] | Lead Solutions Architect (Proposed and designed the unified Apache Airflow architecture)[cite: 8]. |

---

_Last updated: 2026-06-15 · Status: draft_
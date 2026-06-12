---
title: "Smart Map & Smartsheet — AI-Assisted Construction Cost Estimation"
type: use-case
status: draft
date: 2026-Q2
domain: PropTech / Entertainment Real Estate
client: AI Inkwell
technologies: [GraphRAG, Neo4j, PostgreSQL, LLM]
experts: [O. Saienko, M. Kyryliuk]
tags: [GraphRAG, Neo4j, Postgres, KnowledgeGraph, CostEstimation, ExcelAutomation]
---

# Smart Map & Smartsheet — AI-Assisted Construction Cost Estimation

> **One-liner summary** — We engineered a GraphRAG system that converts complex, unstructured Excel calculation formulas into a Neo4j knowledge graph, enabling AI-assisted budget estimation for theme park construction using natural language queries[cite: 6].

---

## Problem Overview

AI Inkwell's enterprise client, the Walt Disney Company, faced massive manual friction when estimating budgets for new attraction park constructions[cite: 6]. Historical actual expenditures, regulatory constraints, and complex environmental/geographical data (such as mountains, rivers, and collisions) were locked within scattered, unstandardized Excel sheets[cite: 6]. Calculating a single cost item required navigating deeply nested formulas across disparate workbooks, creating an operational bottleneck that delayed project planning and increased the risk of multi-million dollar budget inaccuracies[cite: 6].

---

## Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | Deeply Nested Spreadsheet Logic | Business rules were trapped inside workbooks containing up to 500 interconnected formulas, requiring up to 20 calculation steps down a single dependency path[cite: 6]. |
| 2 | Absence of Structural Consistency | Every Excel file provided by the client featured a completely unique structure, making automated programmatic parsing highly non-trivial[cite: 6]. |
| 3 | Requirements and Scope Fluidity | The project launched without a finalized destination or clear vision of deliverables, and the client added critical data workbooks mid-implementation[cite: 6]. |
| 4 | Formula Validation Accuracy | Because the generated system had to execute queries on completely new data, matching the exact math of legacy spreadsheets with absolute precision was critical[cite: 6]. |

---

## Proposed Solution

INSART designed and developed a **Graph-based Retrieval Augmented Generation (GraphRAG)** system to bridge the gap between business spreadsheet rules and a scalable relational database[cite: 6]. 

The core approach involves a multi-step pipeline: extracting the mathematical formula logic directly from Excel workbooks and reconstructing it as a deterministic semantic web inside a **Neo4j Graph Database** (Knowledge Graph Extraction)[cite: 6]. When a user submits an inquiry, the system navigates this graph to extract a precise sub-graph context block[cite: 6]. An LLM then consumes this context to generate highly accurate, step-by-step **PostgreSQL queries** that mimic the legacy spreadsheet operations on new data tables, effectively preserving corporate intellectual property in a modern cloud native layout[cite: 6].

### Key Users & Roles

| Role | Responsibility |
|---|---|
| Project Estimators / Managers | Query historical construction spends, geographical realities, and compliance documents using plain text to generate predictive budgets[cite: 6]. |
| Executive Stakeholders | Review scalable, AI-assisted cost estimations to accelerate project funding approvals for theme park infrastructure[cite: 6]. |

---

## Process / Solution Flow

1. **Knowledge Graph Extraction** — The application ingests heterogeneous Excel files, parses out formula dependencies, and maps the logic structure to a Neo4j database[cite: 6].
2. **Reference Data Population** — Hardcoded values from the source files are mirrored into a PostgreSQL staging area to serve as a historical testing baseline[cite: 6].
3. **Natural Language Processing** — The user inputs an ad-hoc query (e.g., estimating an attraction's cost based on specific geographical and regulation inputs)[cite: 6].
4. **Subgraph Context Retrieval** — The engine runs a graph search to isolate the exact node relationships and formula dependencies matching the user's prompt[cite: 6].
5. **Iterative SQL Generation** — Powered by the subgraph context, the LLM constructs an initial PostgreSQL statement broken down into individual sub-steps rather than a massive single query[cite: 6].
6. **Cross-Validation Execution** — The system executes the broken-down SQL against the Postgres reference database, verifies the mathematical correctness against known spreadsheet values, fixes errors if needed, and delivers the validated budget response[cite: 6].

---

## Technical Stack & Architecture

| Layer | Technology | Notes |
|---|---|---|
| AI / LLM Pipeline | GraphRAG Engine + Large Language Models (LLM) | Uses contextual subgraphs to guarantee highly accurate SQL syntax generation[cite: 6]. |
| Backend API | Service API Layer | Orchestrates ingestion, graph traversal loops, and cross-database validation[cite: 6]. |
| Knowledge Graph DB | Neo4j | Holds the relational and structural mapping of calculated items and formula paths[cite: 6]. |
| Relational Database | PostgreSQL | Stores reference values for validation checks and scales transactional workflows for new project data[cite: 6]. |

---

## Business Outcome

- **Drastic Reduction in Manual Effort** — Eliminated weeks of manual spreadsheet math by introducing instantaneous natural language budget calculation interfaces[cite: 6].
- **Enhanced Financial Precision** — Maximized budget accuracy for major enterprise real estate endeavors by dynamically factoring in historical project data, terrain conditions, and local laws simultaneously[cite: 6].
- **Zero-Loss Logic Preservation** — Safely migrated legacy spreadsheet computations containing hundreds of formula layers into a highly scalable cloud database environment without dropping corporate business logic[cite: 6].
- **Strategic Venture Self-Funding** — Provided the proof-of-concept necessary to secure a fully-financed commercial execution contract directly backed by a tier-1 global enterprise[cite: 6].

---

## Lessons Learned

- **Adopt a Proactive Engineering Stance** — When handling clients with fluid requirements and an undefined target vision, developing and demonstrating assumption-based solutions beats waiting for formal parameter definitions[cite: 6].
- **Leverage Aggressive Micro-Demos** — Running short, rapid technical demonstrations ensures early architectural alignment, confirms direction, and successfully calibrates client expectations[cite: 6].
- **Prioritize Data Quality** — High-fidelity historical datasets and robust calculation reference baselines are the ultimate prerequisites for maintaining absolute precision in GraphRAG-to-SQL generation layers[cite: 6].

---

## Reusable Components / Patterns

- [ ] Spreadsheet Formula-to-Graph Topology Translator
- [ ] Subgraph Context Extraction Wrapper for Multi-Step Math Logic
- [ ] Automated Step-by-Step SQL Validation Architecture against Relational Baselines

---

## Resources

| Resource | Link |
|---|---|
| Slide Deck | `AI_Inkwell_LLM` presentation file[cite: 6] |

---

## Experts

| Expert | Role on Project |
|---|---|
| O. Saienko | Lead Solutions Engineer / Co-Presenter[cite: 6] |
| M. Kyryliuk | Core AI Developer / Co-Presenter[cite: 6] |

---

_Last updated: 2026-Q2 · Status: draft_
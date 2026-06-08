

`---`  
`title: "EnVision AI — Natural Language Analytics Platform"`  
`type: use-case`  
`status: draft`  
`date: 2026-Q2`  
`domain: B2B SaaS / Industrial Distribution`  
`client: Enmark Systems`  
`technologies: [OpenAI, .NET 10, Vue 3, Azure SQL, Highcharts]`  
`experts: []`  
`tags: [AI, Analytics, NLP, Reporting, Legacy Modernization]`  
`---`


# **EnVision AI — Natural Language Analytics Platform**

**One-liner summary** — We integrated an AI-powered assistant into a legacy reporting platform, enabling users to generate complex, customized charts and data insights from operational data using plain English.

## **Problem Overview**

Before INSART engaged, Enmark Systems acquired a reporting platform in 2023 to serve as a modern alternative to Crystal Reports for their B2B industrial distribution clients. However, this system, known as "EnVision Classic," was a monolithic web application that struggled with end-user adoption. The user interface was slow, outdated, and lacked mobile optimization. Creating custom reports was highly labor-intensive, and the report designer only supported simple aggregations, making complex queries impossible. Additionally, the system was built with poor code quality and zero automated tests, making extensions and maintenance both risky and costly.

## **Challenges Identified**

| \# | Challenge | Description   |
| :---- | :---- | :---- |
| 1 | Outdated User Experience | The legacy system was slow, non-responsive, and lacked mobile optimization, causing friction for end users. |
| 2 | High Maintenance & Extension Costs | Extending the system was costly and risky due to monolithic architecture, poor code quality, and a lack of automated tests. |
| 3 | Labor-Intensive Customization | Creating custom reports required significant effort. The standard library didn't cover special requests, and chart types were limited. |
| 4 | Limited Querying Capabilities | The built-in report designer only supported simple aggregations and filters, completely blocking users from running complex data queries. |

## **Proposed Solution**

INSART proposed and developed "EnVision AI," a modern, natural language-driven analytics platform. We embedded an AI assistant directly into the analytics application, allowing users to ask complex business questions in plain English and receive instant, accurate charts and reports. To support this, we completely modernized the underlying technology stack, focusing on clean code, automated tests, security best practices, and a fast, optimized user interface. Users can engage in multi-turn conversations to refine reports, securely query their data, and save customized charts directly into their personal dashboards.

### **Key Users & Roles**

| Role | Responsibility   |
| :---- | :---- |
| End Users (Industrial Distributors) | Query operational, sales, and inventory data using plain language to get instant answers without needing data analysts. |
| Sales & Executives | Monitor overall business health, run Year-over-Year (YOY) comparisons, and save dynamic reports to personal dashboards. |

## **Process / Solution Flow**

The system utilizes a secure, multi-stage AI pipeline to process natural language requests into complex visual reports:

1. **User Query** — A user asks a question via the chat interface (e.g., "Show me top 10 customers by sales last quarter").  
2. **Interpret Stage (GPT-5-mini)** — The system analyzes the intent and decides whether to Clarify, Reject, or Proceed. It identifies the target dataset and optimal visualization type.  
3. **Build SQL Stage (GPT-4.1)** — The AI generates precise T-SQL and executes it securely against the Analytics Database. Row-Level Security (RLS) guarantees tenants only access their own data.  
4. **Render Chart Stage (GPT-5-mini)** — The AI dynamically maps the retrieved data columns to appropriate chart axes and series, delivering the completed report via SignalR websockets.

## **Technical Stack & Architecture**

| Layer | Technology | Notes   |
| :---- | :---- | :---- |
| AI / LLM | OpenAI (GPT-5-mini, GPT-4.1), Anthropic Claude SDK, Gemini SDK | Dual-tier approach: fast routing/rendering with GPT-5-mini, and complex SQL generation with GPT-4.1. |
| Backend | .NET 10 / C\# 13, ASP.NET Core Web API, SignalR, EF Core 9 | Manages the AI pipeline execution and handles WebSocket connections for real-time chat. |
| Frontend | Vue 3, Vite, TailwindCSS | Delivers a fast, responsive, and mobile-friendly user experience. |
| Database | Azure MySQL Flexible, SQL Server with RLS, Redis | Row-Level Security (RLS) is strictly enforced to maintain multi-tenant data isolation. |
| Infrastructure | Docker, Kubernetes / Helm, Azure AKS, ACR, Key Vault | Containerized scaling and secure secret management. |
| Integrations | Highcharts 12, AG Grids | Provides 9 robust chart types out of the box. |

## **Business Outcome**

* **Rapid Delivery** — Engineered the initial Proof of Concept (PoC) from scratch in just 3 months with 4 engineers.  
* **High Revenue Growth** — By April 2026, revenue had doubled compared to March, pushing the product toward its first profitable quarter in Q2 2026\.  
* **Accelerated Acquisition** — Successfully onboarded 11 new companies within three months (Feb–Apr 2026).  
* **Churn Reversal** — 2 former clients returned specifically to access the new EnVision AI capabilities.  
* **Early Customer Success** — Achieved a 71% full success rate on early complex queries, and 5 companies fully adopted the AI before official licensing was even required.

## **Lessons Learned**

* **Prompt Engineering Details:** Writing dataset descriptions clearly enough to be prompt-effective for the LLM while remaining user-understandable is an ongoing challenge.  
* **Pipeline Confidence:** Balancing the trade-off between clarifying ambiguous queries and automatically proceeding is critical to avoid silent data hallucinations.  
* **Context Window Scaling:** As the application scaled (datasets doubling since Oct 2025), managing prompt size and token limits required careful optimization.  
* **Testing Paradigms:** AI features ship significantly faster than standard QA tests can cover, necessitating modern tools like LangChain4j for automated prompt testing.

## **Reusable Components / Patterns**

* Dual-Tier LLM Pipeline (Router vs. Generator)  
* SignalR WebSocket Streaming for AI Chat  
* Automated LLM Testing Pipeline (LangChain4j)

## **Resources**

| Resource | Link   |
| :---- | :---- |
| Slide Deck | Talk to Your Data: The EnVision AI Story |

## **Experts**

| Expert | Role on Project   |
| :---- | :---- |
| INSART Engineering Team | Frontend, Backend, QA, and Automation Engineers |

*Last updated: 2026-Q2 · Status: draft*
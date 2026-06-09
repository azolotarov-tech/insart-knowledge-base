

`---`  
`title: Enmark Systems — Integrating AI-Powered Assistant into a Legacy Reporting Platform`  
`type: use-case`  
`status: draft`  
`date: 2026-Q1`  
`domain: B2B SaaS / Industrial Distribution`  
`client: Enmark Systems`  
`technologies: [OpenAI, .NET 10, Vue 3, Azure SQL, Highcharts, Playwright, LangChain]`  
`experts: []`  
`tags: [AI, Analytics, NLP, Reporting, Legacy Modernization, GenAI Development]`  
`---`


# **Enmark Systems — Integrating AI-Powered Assistant into a Legacy Reporting Platform**

**One-liner summary** — We integrated an AI-powered assistant into a legacy reporting platform, enabling users to generate complex, customized charts and data insights from operational data using plain English, built with a 50% productivity boost using GenAI tools.

## **Problem Overview**

Before INSART engaged, Enmark Systems acquired a reporting platform in 2023 to serve as a modern alternative to Crystal Reports for their B2B industrial distribution clients. However, this system, known as "EnVision Classic," was a monolithic web application that struggled with end-user adoption. The user interface was slow, outdated, and lacked mobile optimization. Creating custom reports was highly labor-intensive, and the report designer only supported simple aggregations, making complex queries impossible. Additionally, the system was built with poor code quality and zero automated tests, making extensions and maintenance both risky and costly.

## **Challenges Identified**

| \# | Challenge | Description   |
| :---- | :---- | :---- |
| 1 | Outdated User Experience | The legacy system was slow, non-responsive, and lacked mobile optimization, causing friction for end users. |
| 2 | High Maintenance & Extension Costs | Extending the system was costly and risky due to monolithic architecture, poor code quality, and a lack of automated tests. |
| 3 | Labor-Intensive Customization | Creating custom reports required significant effort. The standard library didn't cover special requests, and chart types were limited. |
| 4 | Limited Querying Capabilities | The built-in report designer only supported simple aggregations and filters, completely blocking users from running complex data queries. |
| 5 | Data Privacy Constraints | A strict requirement prohibited sending any database data directly to the AI models (except user inputs), making contextual queries difficult. |
| 6 | Search Accuracy and "No Data" Errors | Users frequently encountered "no data found" errors (up to 20% of requests) due to exact-match database queries failing on simple typos. |

## **Proposed Solution**

INSART proposed and developed "EnVision AI," a modern, natural language-driven analytics platform. We embedded an AI assistant directly into the analytics application, allowing users to ask complex business questions in plain English and receive instant, accurate charts and reports. To support this, we completely modernized the underlying technology stack, focusing on clean code, automated tests, security best practices, and a fast, optimized user interface. Users can engage in multi-turn conversations to refine reports, securely query their data, and save customized charts directly into their personal dashboards.

### **Key Users & Roles**

| Role | Responsibility   |
| :---- | :---- |
| End Users (Industrial Distributors) | Query operational, sales, and inventory data using plain language to get instant answers without needing data analysts.Limited to 1,500 queries/month. |
| Sales & Executives | Monitor overall business health, run Year-over-Year (YOY) comparisons, and save dynamic reports to personal dashboards. |

## **Process / Solution Flow**

The system utilizes a secure, multi-stage AI pipeline to process natural language requests into complex visual reports:

1. **User Query** — A user asks a question via the chat interface (e.g., "Show me top 10 customers by sales last quarter").  
2. **Interpret Stage (GPT-5-mini)** — The system analyzes the intent and decides whether to Clarify, Reject, or Proceed(proceeds only if confidence is >80%). It identifies the target dataset and optimal visualization type.  
3. **Build SQL Stage (GPT-4.1)** — The AI generates precise T-SQL using a "like" search approach to handle user typos, enforcing a hard limit of 10,000 rows for performance. It executes securely against the Analytics Database with Row-Level Security (RLS).  
4. **Render Chart Stage (GPT-5-mini)** — The AI dynamically generates the JSON schema to map retrieved data columns to appropriate chart axes and series, delivering the completed report via SignalR websockets.

## **Technical Stack & Architecture**

| Layer | Technology | Notes   |
| :---- | :---- | :---- |
| AI / LLM | OpenAI (GPT-5-mini, GPT-4.1), Microsoft.Extensions.AI | Dual-tier approach: fast routing/rendering with GPT-5-mini, and complex SQL generation with GPT-4.1. |
| Backend | .NET 10 / C\# 13, ASP.NET Core Web API, SignalR, EF Core 9 | Manages the AI pipeline execution, implements query retry logic, and handles WebSocket connections. |
| Frontend | Vue 3, Vite, TailwindCSS | Delivers a fast, responsive, and mobile-friendly user experience. |
| Database | Azure MySQL Flexible, SQL Server with RLS, Redis | Row-Level Security (RLS) is strictly enforced to maintain multi-tenant data isolation. |
| Infrastructure | Docker, Kubernetes / Helm, Azure AKS, ACR, Key Vault | Total AI cluster and DB infrastructure optimized to just ~$1,800/month. |
| Integrations | Highcharts 12, AG Grids | Provides 9 robust chart types out of the box. |
| QA & Testing | Playwright, LangChain | Playwright for UI tests; LangChain compares scraped data objects to a SQL baseline. |

## **Business Outcome**

* **Exceptional ROI & Low Overheads** — The application boasts high profit margins. The AI license is billed at $45/user/month (min 5 users), while token costs remain exceptionally low (under $2/month total initially) and dedicated AI infrastructure runs only ~$1,800/month.
* **AI-Accelerated Delivery** — The development team achieved over 50% productivity gains by extensively using generative AI tools, with 70% to 80% of the project's codebase generated by AI. Engineered the initial PoC in just 3 months.  
* **High Revenue Growth** — By April 2026, revenue had doubled compared to March, pushing the product toward its first profitable quarter in Q2 2026 and full ROI by 2028.  
* **Accelerated Acquisition & Churn Reversal** — Successfully onboarded 11 new companies within three months (Feb–Apr 2026)and brought back 2 former clients specifically to access the AI capabilities.  
* **Early Customer Success** — Achieved a 71% full success rate on early complex queries, and 5 companies fully adopted the AI before official licensing was even required.

## **Lessons Learned**

* **Handling Strict Data Privacy:** Adhering to the rule that no database data can be sent to the AI (except user inputs) required creative engineering, such as relying purely on metadata for prompt engineering.
* **Solving "No Data" Friction:** Exact matches in database queries failed too frequently due to user typos. Shifting to a "LIKE" search combined with clarification prompts suggesting available values drastically improved user experience without changing underlying architecture.
* **AI Testing Paradigms:** AI features ship faster than standard QA can cover. The team solved this by deploying LangChain to evaluate AI responses, comparing scraped chart objects against a predefined SQL baseline to ensure column names and orders matched expected results.
* **Context Window Scaling:** As datasets doubled since Oct 2025, managing prompt size required careful optimization, particularly as interpretation happens via the cheaper GPT-5-mini.

## **Reusable Components / Patterns**

* Dual-Tier LLM Pipeline (Router vs. Generator)  
* SignalR WebSocket Streaming for AI Chat  
* AI-Driven Automated UI Testing Framework (Playwright + LangChain)
* Zero-Data-Exposure Prompting Strategy

## **Future Roadmap**

* **Q2 2026:** Rollout of dashboards, AG grids, and additional complex production datasets.
* **Q3 2026:** Integration of accounting datasets requiring Role-Based Access Control (RBAC) and dynamic conversation kickoffs.
* **Future Enhancements:** Full-text search and a semantic layer to completely eliminate typo-induced search failures, plus preemptive SQL validation.  

## **Resources**

| Resource | Link   |
| :---- | :---- |
| Slide Deck | Talk to Your Data: The EnVision AI Story |
| Meeting Notes | Service Delivery Meeting [monthly] - 2026/04/27 |
| Code Repository | [To be added] |
| Demo Video | [To be added] |

## **Experts**

| Expert | Role on Project   |
| :---- | :---- |
| INSART Engineering Team | Frontend, Backend, QA, and Automation Engineers |

*Last updated: 2026-Q2 · Status: draft*

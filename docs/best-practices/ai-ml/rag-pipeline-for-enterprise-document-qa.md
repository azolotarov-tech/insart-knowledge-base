---
title: "RAG Pipeline for Enterprise Document Q&A"
type: best-practice
status: published
date: "2025-Q2"
category: "ai-ml"
technologies: [Python, LangChain, OpenAI, Qdrant, FastAPI, PostgreSQL]
experts:
  - "@AndriiZolotarov"
  - "@AIArchitect"
tags:
  - RAG
  - LLM
  - SemanticSearch
  - Embeddings
  - EnterpriseAI
  - VectorDatabase
related_cases:
  - "../../use-cases/wealth-management/advisor-knowledge-assistant.md"
  - "../../use-cases/operations/internal-policy-chatbot.md"
---

# RAG Pipeline for Enterprise Document Q&A

> **Summary** — Enable users to ask natural language questions over large collections of internal documents while ensuring answers remain grounded in company knowledge.

---

## Context & Problem

Organizations often store critical business knowledge across PDFs, spreadsheets, policies, contracts, and knowledge bases. Traditional keyword search requires users to know exactly what they are looking for and where to find it.

Large Language Models can answer questions conversationally, but they frequently hallucinate when asked about company-specific information that is not part of their training data.

This pattern solves the problem by combining semantic search with LLM generation. Relevant document chunks are retrieved first and then provided as context to the LLM so responses remain grounded in actual company documents.

Typical constraints include:

- Thousands of documents
- Frequent document updates
- Need for source citations
- Security and access control requirements
- Low-latency user experience

---

## Solution

Implement a Retrieval-Augmented Generation (RAG) architecture that indexes document content into a vector database and retrieves the most relevant passages before generating a response.

### Overview

1. Ingest enterprise documents from supported sources.
2. Extract and clean text content.
3. Split documents into semantic chunks.
4. Generate embeddings for each chunk.
5. Store embeddings in a vector database.
6. Convert user questions into embeddings.
7. Retrieve relevant chunks.
8. Send retrieved context to the LLM.
9. Return an answer with source references.

This architecture allows the LLM to answer questions using up-to-date business information without requiring model retraining.

A vector database such as Qdrant enables semantic retrieval across millions of chunks while maintaining low response times.

The application layer handles authorization, metadata filtering, observability, and response formatting.

### Implementation Steps

1. **Document Ingestion**
   - Collect files from SharePoint, Google Drive, Confluence, or uploaded documents.
   - Extract text and metadata.

2. **Chunking**
   - Split documents into chunks of 500–1000 tokens.
   - Preserve document hierarchy and source references.

3. **Embedding Generation**
   - Generate vector embeddings using OpenAI text-embedding models.
   - Store embeddings and metadata.

4. **Index Storage**
   - Save vectors in Qdrant.
   - Include metadata such as:
     - Document ID
     - Title
     - Section
     - Access permissions

5. **Query Processing**
   - Convert user question into embedding.
   - Retrieve top-k relevant chunks.

6. **Prompt Construction**
   - Build context-aware prompt using retrieved chunks.
   - Include instructions to cite sources.

7. **Answer Generation**
   - Generate final response via GPT model.
   - Return answer with references.

8. **Monitoring**
   - Log retrieval quality.
   - Track hallucination rate.
   - Measure latency.

### Code Snippet / Example

```python
from langchain_openai import OpenAIEmbeddings
from qdrant_client import QdrantClient

embeddings = OpenAIEmbeddings()

query = "How is advisor commission calculated?"

query_vector = embeddings.embed_query(query)

qdrant = QdrantClient(host="localhost", port=6333)

results = qdrant.search(
    collection_name="knowledge_base",
    query_vector=query_vector,
    limit=5
)

context = "\n".join([
    hit.payload["content"]
    for hit in results
])

prompt = f"""
Answer the question using only the provided context.

Context:
{context}

Question:
{query}
"""
```

### Architecture Diagram

```text
+----------------+
| User Question  |
+--------+-------+
         |
         v
+----------------+
| Embedding API  |
+--------+-------+
         |
         v
+----------------+
| Vector Search  |
| (Qdrant)       |
+--------+-------+
         |
         v
+----------------+
| Retrieved Docs |
+--------+-------+
         |
         v
+----------------+
| LLM Generation |
+--------+-------+
         |
         v
+----------------+
| Final Answer   |
+----------------+
```

---

## Key Design Decisions

| Decision | Chosen Approach | Alternatives Considered | Rationale |
|-----------|----------------|-------------------------|-----------|
| Retrieval Strategy | Vector Search | Keyword Search | Better semantic understanding |
| Vector DB | Qdrant | Pinecone, Weaviate | Open-source, self-hosted option |
| Chunk Size | 800 Tokens | 200, 2000 Tokens | Balance context quality and retrieval accuracy |
| Embeddings | OpenAI Embeddings | Sentence Transformers | Higher retrieval quality and consistency |
| Source Citations | Mandatory | Optional | Improves trust and auditability |
| Hybrid Search | Optional | Vector-only | Added only when precision issues appear |

---

## Trade-offs & Limitations

### When it works well

- Knowledge bases
- Internal documentation
- Policies and procedures
- Financial and compliance documents
- Product documentation

### When to avoid it

- Real-time transactional systems
- Highly structured analytical workloads
- Cases requiring exact mathematical calculations

### Known limitations

- Retrieval quality depends on chunking strategy.
- Poor source documents produce poor answers.
- Large context windows increase cost.
- Access control must be implemented separately.
- Complex multi-document reasoning remains challenging.

---

## Lessons Learned

- Metadata quality significantly impacts retrieval precision.
- Chunk overlap improves answer completeness.
- Users trust answers more when citations are visible.
- Most hallucination issues originate from retrieval failures rather than generation failures.
- Evaluation datasets should be created before production rollout.

---

## Related Resources

| Resource | Link |
|----------|------|
| Reference implementation | [GitLab](https://gitlab.insart.com/ai/rag-reference) |
| Qdrant Documentation | https://qdrant.tech/documentation |
| LangChain Documentation | https://python.langchain.com |
| Related best practice | [Prompt Engineering Guidelines](../ai-ml/prompt-engineering-guidelines.md) |

---

## Applied In

Use cases where this pattern was used:

- [Advisor Knowledge Assistant](../../use-cases/wealth-management/advisor-knowledge-assistant.md)
- [Internal Policy Chatbot](../../use-cases/operations/internal-policy-chatbot.md)
- [Compliance Knowledge Search](../../use-cases/regtech/compliance-knowledge-search.md)

---

_Last updated: 2025-Q2 · Author: @AndriiZolotarov_

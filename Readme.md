# 🎯 Problem Statement

Organizations and individuals deal with large amounts of unstructured information every day.

Examples include:

- Business reports
- Annual reports
- Research papers
- Meeting transcripts
- Technical documents
- HR policies
- Customer complaints
- Project documents
- Product documentation
- Legal/business documents
- Emails

Manually reading these documents to identify important information is time-consuming.

### Objective

Build an AI-powered application that accepts text or documents and automatically generates:

1. Short Summary
2. Detailed Summary
3. Key Points
4. Important Entities
5. Action Items

The application should be capable of processing both small and large documents while minimizing hallucinations and preserving important information.

# 🏗️ High-Level Architecture

The project evolves through multiple stages.

### Initial Architecture

```text
                  User
                    |
                    v
             Upload / Paste Text
                    |
                    v
              Text Processor
                    |
                    v
              Document Loader
                    |
                    v
               Text Chunking
                    |
                    v
                   LLM
                    |
                    v
           Structured Output
                    |
       +------------+-------------+
       |            |             |
       v            v             v
   Summary      Key Points     Entities
                                  |
                                  v
                            Action Items
```

---
# 🧩 Advanced Architecture

The final version introduces RAG, agents, LangGraph, APIs and MCP.

```text
                           User
                             |
                             v
                       FastAPI Backend
                             |
                             v
                       LangGraph Agent
                             |
              +--------------+--------------+
              |              |              |
              v              v              v
             RAG          Tools/APIs       MCP
              |              |              |
              v              v              v
        Vector Database   External       MCP Servers
              |           Systems           |
              |              |              |
              +--------------+--------------+
                             |
                             v
                            LLM
                             |
                             v
                    Structured Response
                             |
             +---------------+----------------+
             |               |                |
             v               v                v
         Summary         Key Points      Action Items
```

---

# 🛠️ Technology Stack

## Backend

- Python
- FastAPI
- LangChain
- LangGraph
- Pydantic
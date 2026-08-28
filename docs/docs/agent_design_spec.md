# Agent Design Document: Academic & ML Research Scout Agent

## 1. Job to Be Done (Scope)
* **Core Function:** A targeted AI Research Scout that monitors, summarizes, and synthesizes recent research papers (arXiv, GitHub repos, technical blogs) tailored to Machine Learning and Data Science workflows.
* **User & Usage Frequency:** Data Science Student / ML Practitioner; used 2 to 3 times per week to generate weekly research briefs and prepare background literature for coursework and project proposals.
* **Build Scope:** Scoped for a ~10-hour build using open APIs and standard tool connectors.

---

## 2. Platform Selection & Justification
* **Chosen Platform:** Scripted Python Agent (using LangChain / LlamaIndex or simple API scripts with OpenAI / Anthropic API).
* **Justification:** 
  * **Free/Low-Cost Path:** Utilizes free APIs (arXiv API, GitHub API, Tavily Search free tier) and local Python execution without requiring paid platform subscriptions like Claude Cowork or Custom GPTs.
  * **Customization & Precision:** Scripted workflow allows exact control over JSON schema parsing, prompt template management, and custom guardrail assertions.
* **Alternative Evaluated:** Custom GPT / Claude Project. *Why rejected:* Limited out-of-the-box integration with raw arXiv XML endpoints and custom output formatting without custom action setup.

---

## 3. Data Sources & Tool Access Plan

| Tool / Data Source | Purpose | Access Plan / Method |
| :--- | :--- | :--- |
| **arXiv API** | Querying academic preprints | Public REST API (Free, no API key required) |
| **GitHub REST API** | Searching related open-source ML repos | Public REST API (Free GitHub Personal Access Token) |
| **Tavily / DuckDuckGo Search** | Finding technical blog summaries | Free tier API key or `duckduckgo-search` library |
| **Local Markdown Storage** | Saving structured literature briefs | Local directory or GitHub repository storage |

---

## 4. Draft Instructions (System Prompt)

```text
You are an expert AI Research Scout specializing in Machine Learning, Data Science, and NLP.

Your objective is to locate, analyze, and summarize relevant technical literature and code repositories based on user queries.

RULES:
1. Always ground paper summaries in facts provided by the arXiv abstract/text. Do NOT invent methodologies or benchmark results.
2. Structure every paper summary into three bullet points:
   - Core Contribution / Novelty
   - Technical Approach / Architecture
   - Key Results & Limitations
3. If code is available, link the primary repository and list the framework used (e.g., PyTorch, TensorFlow).
4. Maintain a neutral, precise, and academic tone.
5.

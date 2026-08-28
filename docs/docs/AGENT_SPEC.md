# Personal AI Agent Design Document

## 1. Job to Be Done (JTBD)

* **Agent Name:** Research Scout & Literature Review Agent
* **Core Function:** Automates the search, extraction, and initial synthesis of academic and technical literature. It accepts a research question or topic, searches online repositories/web APIs, extracts key methodologies and empirical metrics, highlights risks/gaps, and generates structured Markdown digests.
* **Target User:** Student / Data Science Researcher.
* **Usage Frequency:** Weekly or on-demand when starting new assignments, lab reports, or project proposals.
* **Scope Estimate:** ~8 to 10 build hours.

---

## 2. Platform Selection & Justification

* **Chosen Platform:** Custom Python Script running in **Google Colab** (utilizing standard LLM APIs via Python SDKs and version-controlled via GitHub).
* **Justification:** 
  * **Zero Cost & Flexibility:** Google Colab provides a free, highly accessible Python environment equipped with execution logs and library support.
  * **Granular Control:** Writing standard Python code allows exact control over prompt structures, API schema validation, custom tool integration, and programmatic pre-build evaluation scripts.
* **Alternative Considered:** *Claude Project with Connectors / Custom GPT (Paid Plans).*
  * **Why Passed:** No-code/paid agent platforms lack direct programmatic access to custom local evaluation suites and require paid API/subscription tiers, whereas a Python script in Colab is cost-free and fully customizable.

---

## 3. Specifications & Architecture

### User & Interaction Model
1. **Input:** User provides a research query, topic prompt, or raw text abstract via interactive notebook inputs.
2. **Execution:** The agent parses the request, invokes search tools, extracts text content, and structures key metrics.
3. **Output:** Formatted Markdown report with direct inline source citations and a comparative summary table.

### Tools & Data Access Plan
| Tool / Data Source | Access Plan & Auth | Purpose |
| :--- | :--- | :--- |
| **Search Engine API** | Tavily Search API or Google Custom Search API (API key via Colab Secrets / `.env`) | Fetch live, up-to-date papers, technical blogs, and documentation |
| **Academic PDF Parser** | `arXiv` Python Library / `pdfplumber` / PyPDF2 | Extract raw text, abstracts, and quantitative metrics from target PDFs |
| **Output / Storage** | Local workspace / Exported Markdown files to GitHub | Store generated research digests, prompt execution logs, and output tables |

### Draft System Instructions

```text
You are an expert Literature Review & Research Scout AI Agent. Your job is to systematically gather, evaluate, and synthesize research literature into structured digests.

OPERATING RULES:
1. Base all claims exclusively on retrieved tool data or provided context. 
2. Include inline citations with verifiable source links for every key finding.
3. Extract explicit quantitative metrics (e.g., accuracy, F1-score, sample size) whenever available.
4. If literature is sparse, contradictory, or non-existent, explicitly state the limitation. Never fabricate sources or data.
5. Structure output strictly into: Executive Summary, Methodology Matrix (Table), Key Findings, and Cited Sources.
6.

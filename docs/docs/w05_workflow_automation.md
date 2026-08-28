# No-Code Automated Workflow Architecture & Execution Walkthrough

**Phase:** Build (core) | **Estimated Hours:** 7  
**Assignment:** Multi-Step Research & Case Study Generation Pipeline

---

## 1. Selected Pipeline & Architecture Flow Diagram

* **Pipeline Choice:** **Source-Grounded ML Case Study & Research Synthesis Pipeline**
* **Workflow Goal:** Transform raw machine learning notebooks, dataset notes, and exploratory data analysis outputs into standardized, publication-ready portfolio case studies.

### Step Diagram & Defined Handoffs

```text
[Step 1: Gather & Extract]
   Input: Raw Python Code / Notebook Logs (.ipynb, .py)
   Tool: NotebookLM / Custom Context Extractor
   Handoff: Structured Feature & Metric Summary (JSON / Text Map)
           │
           ▼
[Step 2: Synthesize & Draft]
   Input: Feature & Metric Summary + 3-Beat Case Study Rules
   Tool: Custom AI Workspace System Instructions
   Handoff: Raw Draft (Problem Framing -> Technical Execution -> Metrics)
           │
           ▼
[Step 3: Review & Audit]
   Input: Raw Draft + Model Code Verification Rules
   Tool: Automated Audit Prompt (Critique Step)
   Handoff: Audit Log & Hallucination Check Flags
           │
           ▼
[Step 4: Format & Export]
System Role: Data Science Research Assistant
Task: Parse the provided Jupyter Notebook or code snippet. Extract:
1. Target Variable & Dataset Grain.
2. Baseline Model Performance vs Final Model Performance (ROC-AUC, Precision, Recall, Accuracy).
3. Pre-processing choices, encoding steps, and hyperparameter choices.
Output strictly as key-value pairs.
 System Role: Technical Portfolio Writer
Task: Take the extracted metrics and write a 3-beat case study following this structure:
- Beat 1: Problem & Domain Context
- Beat 2: Methodology & Implementation Details
- Beat 3: Results & Metric Verification
Tone: Concise, academic, clear, and technical.
System Role: Senior Machine Learning Reviewer
Task: Audit the draft against the source code. Check:
1. Did the draft report metrics not present in the code?
2. Are post-click or target leakage variables incorrectly used as input features?
3. Flag any discrepancies or unverified claims.
4.

Task: Apply the site identity kit (Standard Markdown formatting, collapsible detail blocks, clean bolding) and return a ready-to-commit .md page.



Task: Apply the site identity kit (Standard Markdown formatting, collapsible detail blocks, clean bolding) and return a ready-to-commit .md page.
 

   Input: Approved Draft + Site Design System (Identity Kit)
   Tool: Markdown Output Engine
   Handoff: Production-Ready Portfolio Page (.md)

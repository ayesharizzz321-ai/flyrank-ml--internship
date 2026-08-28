# Understanding AI Agents, Workflows, and Model Context Protocol (MCP)

**Phase:** Build (core) | **Estimated Hours:** 5  
**Assignment:** Workflows vs. Agents & MCP Implementation Explainer

---

## 1. Executive Explainer (750 Words)

### 1.1 The Distinction Between Workflows and Agents
In contemporary AI system design, the distinction between a **workflow** and an **agent** hinges on control flow, decision autonomy, and path determinism.

* **Workflows (Deterministic Orchestration):** A workflow is a structured system where Large Language Models (LLMs) and tools are orchestrated through predefined, fixed execution paths. In a workflow, human developers predetermine the exact sequence of steps—such as prompt chaining, routing, parallel processing, or evaluation loops. The LLM operates as a domain processor within fixed boundaries: given input $X$, it follows step $A$, hands off to step $B$, and outputs result $Y$. Workflows are predictable, highly reliable, and easy to audit, making them ideal for standardized tasks.

* **Agents (Autonomous Reasoning & Dynamic Execution):** An agent, in contrast, is an architecture where an LLM dynamically controls its own control flow and execution path. Rather than following a static checklist, an agent operates within a feedback loop: it evaluates an open-ended goal, assesses its current environment, determines which tools to call, inspects the tool outputs, and autonomously decides the next step—repeating this process until it judges the objective complete. Agents trade deterministic predictability for adaptive problem-solving capability.

---

### 1.2 Model Context Protocol (MCP) and Its Three Primitives
The **Model Context Protocol (MCP)** functions as an open standard (analogous to a "USB-C port" for AI applications) that standardizes how LLM clients discover, authenticate, and interact with external data sources and local computational environments. Instead of writing custom API integrations for every unique data source, MCP provides a universal interface divided into three core primitives:

1. **Tools (Executable Actions):** Functions exposed by an MCP server that allow the model to perform side-effecting operations or compute tasks in the real world (e.g., executing a SQL query, reading a local file, making an HTTP API call, or running a Python script).
2. **Resources (Contextual Data Streams):** Read-only data endpoints provided by the MCP server that expose file contents, API schemas, log streams, or database tables directly into the LLM's context window.
3. **Prompts (Reusable Control Frameworks):** Pre-designed prompt templates and system instructions hosted on the server level to standardize how users interact with specific tools or resources.

---

### 1.3 Classification of the FL-04 Pipeline
The FL-04 case study generation pipeline built previously is strictly a **Workflow**, not an agent. It follows a rigid 4-step linear chain: 
1. *Gather & Extract* $\rightarrow$ 
2. *Synthesize & Draft* $\rightarrow$ 
3. *Review & Audit* $\rightarrow$ 
4. *Format & Export*.

The execution path never changes based on intermediate outputs. The system cannot independently choose to loop back, run an external database query, or select alternative tools without explicit human intervention at each handoff step.

---

### 1.4 Upgrading FL-04 to an Autonomous Agent
To convert the static FL-04 workflow into an autonomous **Portfolio Maintenance Agent**, the pipeline requires two structural components: an autonomous decision loop and an MCP server connection.

```text
[User Goal: "Audit and Add New Case Study"]
                    │
                    ▼
          ┌───────────────────┐
          │ Agent Loop (LLM)  │◄────────────────────────┐
          └─────────┬─────────┘                         │
                    │ Evaluates State & Tool Output     │
        ┌───────────┴───────────┐                       │
        ▼                       ▼                       │
┌──────────────┐        ┌──────────────┐                │
│ Tool Call A  │        │ Tool Call B  │                │
│ Read Local   │        │ Execute ML   │                │
│ Git Workspace│        │ Metric Check │                │
└───────┬──────┘        └───────┬──────┘                │
        │                       │                       │
        └───────────┬───────────┘                       │
                    ▼                                   │
         [MCP Server Response] ─────────────────────────┘

# AI-Enabled Operations in Insurance · P&C Commercial Lines

A self-contained interactive case study showing how agentic AI can be applied to P&C Commercial Lines operations — from the business case through to a fully evaluated underwriting agent.

Built as a single HTML file. No server, no dependencies, no install required.

---

## What it covers

**01 · The Business Case**
The strategic rationale for AI-enabled insurance operations. Why the combined ratio is the right value anchor, and how operational transformation in underwriting, claims, and customer service connects to it.

**02 · AI Value Map**
A visual mapping of AI initiatives across underwriting, claims, and customer service — traced through to their impact on Loss Ratio, Expense Ratio, and Combined Ratio. Includes prioritisation logic and directional impact estimates.

**03 · Worked Example: P&C UW Agent**
An end-to-end worked example of an agentic underwriting intake agent built with LangGraph. Three sub-sections:

- **Diagnosis** — current state process map, operational pain points, and value drivers for a regional hub processing ~75,000 submissions/year
- **Agent** — 5-node LangGraph architecture with deterministic routing, RAG over appetite and pricing knowledge bases, and 3 mandatory HITL checkpoints
- **Live Results** — 72 synthetic submissions evaluated end-to-end using an Evidence-Driven Development (EDD) framework with 8 acceptance criteria (CA01–CA08), tracked in Arize Phoenix

---

## How to use

**Option A — open locally**
Download `ai_ops_insurance_case_study.html` and open it in any browser. Works fully offline.

**Option B — view rendered**
If GitHub Pages is enabled on this repo:
`https://fsuarezdetangil-dev.github.io/ai-ops-insurance-case-study/ai_ops_insurance_case_study.html`

---

## Technical stack (agent example)

| Layer | Tool |
|---|---|
| Orchestration | LangGraph |
| LLM | Azure OpenAI (GPT-4o) |
| RAG | Azure Cognitive Search (KB-Appetite, KB-Pricing) |
| Document extraction | Azure AI Document Intelligence |
| Observability | Arize Phoenix · LangSmith |
| Evaluation | EDD framework · LLM-as-Judge · CA01–CA08 |
| State persistence | SQLite (dev) → Redis (prod) |

---

## Evaluation methodology

The agent was evaluated using an **Evidence-Driven Development (EDD)** framework — a structured approach that defines explicit acceptance criteria before building, then measures each criterion against actual agent outputs.

Public experiment: [Arize Phoenix — Insurance Agents](https://app.phoenix.arize.com/s/Insurance_Agents/datasets/RGF0YXNldDox/experiments)

---

## Notes for reviewers

- All figures in the business case section are sourced from public P&C carrier disclosures and industry benchmarks. Directional estimates are clearly labelled.
- The agent example uses synthetic submission data. No real policyholder or underwriting data was used.
- HITL checkpoints are a design principle, not optional — binding authority stays human at every critical decision point.
- The CA-06 regression (HITL routing, –1.2 pp v1→v2) is intentionally left open as a realistic illustration of the iterative improvement cycle. Cluster B (19 false positives, over-escalation) is the next iteration target.

---

*Feel free to adapt, extend, or sanitise further for your own use case.*

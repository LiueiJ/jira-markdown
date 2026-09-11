---
jira_key: MEDUSA-29
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-29"
server: etas
kind: motivation
type: Sub-task
status: Done
priority: Medium
project: MEDUSA
assignee: ""
reporter: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: "[[MEDUSA-26 Intern Orientation for Yiran]]"
created: "2026-07-29T03:28:26.000+0000"
updated: "2026-08-06T08:00:29.000+0000"
synced-at: "2026-09-11T01:13:13.361Z"
jira-orphaned: false
profile: Medusa
---

## 描述

Yiran should do research regarding following topics:

#### **1. Background**

We are selecting the technology stack for our upcoming AI Agent product. To make an informed decision, we need a technical survey of current Agent architectures, popular development frameworks, and the **Model Context Protocol (MCP)** to evaluate their development costs and capabilities.

#### **2. Scope of Research**

- **Agent Architectures:** Compare Single-Agent vs. Multi-Agent setups and analyze how they manage state/context in multi-turn conversations.

- **Development Frameworks:** Compare the following frameworks in a matrix:

- - **Langchain/LangGraph:** Stateful, graph-based orchestration (great for complex loops).

- - **AutoGen:** Event-driven multi-agent conversation framework.

- - or others...
- **Tool Calling:** Evaluate how frameworks handle parallel tool execution and error recovery.

- **MCP (Model Context Protocol):** Research how MCP connects LLMs to external data and evaluate how to build a custom MCP Server for our internal APIs.

#### **3. Deliverables**

1. **AI Agent Framework Comparison Report** for presentation.

1. **A simple MCP Server Demo** (a basic Python/TypeScript script that allows an LLM to read a local file).

#### **4. Acceptance Criteria**

- Framework comparison matrix completed.

- Custom MCP Server demo successfully run locally.

- Recommendations presented to the team to guide our tech selection.

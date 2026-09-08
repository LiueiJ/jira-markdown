---
jira_key: MEDUSA-42
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-42"
server: etas
kind: motivation
type: Sub-task
status: Done
priority: Medium
project: MEDUSA
assignee: tao9sgh
reporter: tao9sgh
tags: []
components: []
fix-versions: []
epic: null
parent: "[[MEDUSA-37 M1-Setup Agent Skeleton based on FastAPI and LangGraph]]"
created: "2026-08-18T01:43:17.000+0000"
updated: "2026-08-28T05:23:12.000+0000"
synced-at: "2026-09-08T01:43:02.635Z"
jira-orphaned: false
profile: Medusa
---

# MEDUSA-42 Create a minimal FastAPI backend skeleton

> [!jira] Done · Medium · [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] · 更新于 2026-08-28T05:23:12.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/MEDUSA-42)

## 描述

Create a minimal FastAPI backend skeleton for Agentic Cobra to expose the existing orchestration runtime through HTTP endpoints.

The API must provide a reusable application factory and a local Uvicorn entry point. It should initialize application settings and the &#91;MainOrchestrator|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93; lazily, cache them for the lifetime of the process, and expose structured configuration errors.

Implement the following endpoints:

- GET /health to validate runtime configuration and return a sanitized public settings summary.
- &#91;POST /chat|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93; to execute a non-streaming orchestration turn with &#91;message|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93;, optional &#91;thread_id|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93;, optional conversation &#91;history|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93;, and optional trace output.
- &#91;POST /chat/stream|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93; to stream orchestration events as Server-Sent Events (SSE), including normalized event payloads and structured error events.

Add automated API tests covering health checks, configuration failures, synchronous chat behavior, and SSE streaming behavior. Register an &#91;agentic-cobra-api|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93; console script that starts the service on 127.0.0.1:8000.

---
jira_key: MEDUSA-43
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-43"
server: etas
kind: motivation
type: Sub-task
status: Done
priority: Medium
project: MEDUSA
assignee: ""
reporter: tao9sgh
tags: []
components: []
fix-versions: []
epic: null
parent: "[[MEDUSA-38 M1-Setup Frontend Minimal View based on Electron and React]]"
created: "2026-08-18T01:51:49.000+0000"
updated: "2026-08-18T01:54:47.000+0000"
synced-at: "2026-09-06T01:15:42.846Z"
jira-orphaned: false
---

# MEDUSA-43 Create Streamlit Frontend for Chat Streaming Validation

> [!jira] Done · Medium ·  · 更新于 2026-08-18T01:54:47.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/MEDUSA-43)

## 描述

Create a Streamlit-based chat console for interacting with the Agentic Cobra runtime and visually validating streaming agent execution.

The frontend must provide:

- A conversational chat interface with persisted session messages and configurable thread ID.
- Runtime configuration inputs for AUTOSAR paths, Python executable, and LLM connection settings.
- Repository-root .env loading and saving for frontend-configured values.
- Local Python runtime availability validation before an agent turn starts.
- Direct streaming consumption to render incremental reply content, agent status, progress, subagent events, tool activity, and final trace data.
- A backend health-check control using the configured FastAPI URL and GET /health.
- Error handling for invalid configuration, runtime failures, and HTTP connection errors.

The frontend should be started with:

       

uv run streamlit run frontend/app.py

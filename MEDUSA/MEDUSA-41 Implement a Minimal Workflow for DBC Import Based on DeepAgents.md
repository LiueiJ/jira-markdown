---
jira_key: MEDUSA-41
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-41"
server: etas
kind: motivation
type: Sub-task
status: Done
priority: Medium
project: MEDUSA
assignee: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]"
reporter: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: "[[MEDUSA-37 M1-Setup Agent Skeleton based on FastAPI and LangGraph]]"
created: "2026-08-07T03:28:13.000+0000"
updated: "2026-08-18T01:26:31.000+0000"
synced-at: "2026-09-11T02:40:25.212Z"
jira-orphaned: false
profile: Medusa
---

## 描述

Description

Implement a 4-node minimal workflow that only covers the “user requests DBC import” scenario. The flow must support cobra-dbc-import skill execution, failure retry, and structured result output. The goal is to deliver a working end-to-end loop first, and return a “next step: ConfGen” hint on success.

Workflow Scope

1. bootstrap_request: initialize minimal task state
2. precheck_and_plan: validate DBC path, project prerequisites, and key Parameter.ini fields
3. run_dbc_import_skill: invoke cobra-dbc-import skill to run import
4. decide_retry_or_finish: decide retry or finish (success/failure) based on execution result

Acceptance Criteria

1. When user input is “I want to import DBC”, the full workflow is triggered and returns a structured result
2. run_dbc_import_skill invokes the skill through a unified Tool contract with standard input/output fields
3. On failure, the workflow performs one automatic retry; if retry still fails, return failed or blocked
4. On success, return a success summary, key artifact/log references, and a “next step: run ConfGen” recommendation
5. End-to-end flow records minimal traceable state: active_step, retry_count, last_execution_ref, route_decision, terminal_reason

Out of Scope

1. Stage 2/3/4 implementation
2. Generic multi-skill orchestration
3. Full diagnostic attribution and complete human-review gate mechanism

Deliverables

1. DBC-only minimal graph implementation
2. Skill integration point and tool runtime routing implementation
3. Basic tests for: success, failure with retry, final failure, success response with next-step hint

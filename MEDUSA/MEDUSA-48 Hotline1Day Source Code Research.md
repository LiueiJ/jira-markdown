---
jira_key: MEDUSA-48
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-48"
server: etas
kind: motivation
type: Story
status: To Do
priority: Medium
project: MEDUSA
assignee: "[[FIXED-TERM_YANG_Ye_(ETAS-ECMXSF-CN)|FIXED-TERM YANG Ye (ETAS-ECM/XSF-CN)]]"
reporter: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-08-28T05:12:58.000+0000"
updated: "2026-09-03T08:31:11.000+0000"
synced-at: "2026-09-11T01:13:13.361Z"
jira-orphaned: false
profile: Medusa
---

## 描述

**Background**

The hotline1day agent was developed by an overseas team and currently runs on Azure, utilizing the **Claude Code SDK** (Anthropic). Due to domestic network policies and compliance requirements, **Claude models are inaccessible in Mainland China**. We must evaluate the effort required to switch to a domestic alternative (e.g., DeepSeek, Qwen, or Moonshot) before the migration proceeds. While the BD team will handle cloud resource provisioning, development needs to understand the application's logic to verify functionality post-migration and post-model-swap.

**Scope of Work (Learning & Investigation)**

The intern is required to dig into the provided codebase and prepare a knowledge-sharing session. The investigation must cover the following areas:

1. **Code Structure & Architecture**

- - Map out the folder structure (e.g., MVC, Microservices, Serverless).

- - Identify entry points (e.g., main.py, index.js, or compiled binaries).

- - Identify key configuration files (config.yaml, .env, settings.py).

- - List external services the agent relies on (e.g., databases, message queues, blob storage).

2. **Local Development & Testing**

- - Set up the local development environment (Python/Node/Java version requirements).

- - Identify dependencies (review requirements.txt, package.json, or go.mod).

- - Successfully run the application locally in a development mode.

- - Document the exact commands for building, running, and testing.

3. **CRITICAL: AI Model Dependency Assessment (Claude -> Domestic)**

- - Locate all code sections where the **Claude Code SDK** is imported, instantiated, and invoked (e.g., chat completion, streaming, function calling).

- - Map out the input/output data structures expected by the Claude SDK (system prompts, message formats, tool definitions, response parsing).

- - Research and evaluate **domestic model** (prioritize **DeepSeek**) for API compatibility.

- - Perform a **gap analysis**: Identify breaking changes (e.g., different tool-calling schemas, different streaming formats, different context window limits).

- - Provide a preliminary assessment: Is it a drop-in replacement (just change the endpoint/api key), or does it require significant code refactoring (rewriting the prompt engineering and tool-calling logic)?

4. **Infrastructure & Terraform (Migration Dependencies)**

- - Review the existing Terraform scripts used for Azure.

- - Identify the "stateful" resources (Storage Accounts, Redis, Databases) that require data migration.

- - Understand the networking variables (VPCs, Subnets, Security Groups) currently defined.

- - **Note:** The goal is *not* to rewrite the Terraform for Aliyun, but to extract the *logic* and *variables* so the BD team knows exactly what to provision on Alibaba Cloud (using Aliyun ROS/Terraform).

---
jira_key: MEDUSA-30
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-30"
server: etas
kind: motivation
type: Sub-task
status: Done
priority: Medium
project: MEDUSA
assignee: "[[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]]"
reporter: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: "[[MEDUSA-26 Intern Orientation for Yiran]]"
created: "2026-07-29T03:31:41.000+0000"
updated: "2026-08-26T02:44:58.000+0000"
synced-at: "2026-09-11T01:13:13.361Z"
jira-orphaned: false
profile: Medusa
---

## 描述

#### **1. Background**

Instead of studying heavy orchestration platforms, we want to look at a concrete, ready-to-use Agent application on GitHub. By deconstructing a complete, running project that features a chat UI, tool integration, and streaming responses, we can quickly learn how a production-grade Agent application is built end-to-end.

#### **2. Scope of Analysis**

- **Source Code & Tech Stack:** Find a highly-starred, open-source Agent app on GitHub. Analyze its frontend (e.g., Next.js, Streamlit) and backend (e.g., FastAPI, LangChain/LangGraph) tech stack.

- **Streaming Chat (Stream):** Deconstruct how the streaming response (SSE - Server-Sent Events or WebSockets) is implemented from the LLM, through the backend, to the frontend UI without lag.

- **Tool Calling & Execution:** Analyze how the frontend triggers, displays, and handles the "loading/thinking" states when the Agent is calling external tools (e.g., web search, database queries).

- **Deployment:** Review its deployment setup (e.g., Docker, Vercel, or local run instructions) to understand its operational complexity.

#### **3. Deliverables**

1. **Case Study Report** containing:

- - The link to the GitHub repository and instructions on how to run it locally.

- - A brief analysis of how the frontend UI, backend server, and Agent engine communicate.

- - Key takeaways on how they implemented **Streaming** and **Tool Calling UI** states.

1. **(Optional)Live Demo:** Set up and run the project locally to demonstrate its UI, streaming chat, and tool calling to the team.

#### **4. Acceptance Criteria**

- Prepare presentation of tech stack and solution of the Agent Application.

- Optional: Deliver a 15-minute live demo and walkthrough of the codebase for the team.

## 评论

> [!note]+ 2026-08-20 07:20 · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]]
> I cloned and ran the Hotline1Day source code, and set up a developer account to bypass the login and registration process. Its frontend structure is relatively simple, with only three functional modules: Agent, Harness, and Database. Existing databases can be downloaded using a script, while the Agent module supports uploading local files. ![[MEDUSA-30-image-2026-08-20-15-09-18-818.png]]![[MEDUSA-30-image-2026-08-20-15-19-03-490.png]]On the chat page, users can switch and select different workflows here.![[MEDUSA-30-image-2026-08-20-15-20-17-631.png]]

-------

> [!note]+ 2026-08-19 03:56 · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]]
> Evaluated four open-source frameworks: full-stack-ai-agent-template; AIOS-source-code-for-MVP; Langflow; Chatbot-UI. Langflow does not meet our development requirements. The full-stack-ai-agent-template is overly complex and contains too many unnecessary components. Of the remaining two, AIOS is the best fit because it already supports packaging as a desktop application with Electron. Chatbot UI can serve as a reference for a clean and simple interface layout. 

-------

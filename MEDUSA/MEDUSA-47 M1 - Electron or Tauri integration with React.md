---
jira_key: MEDUSA-47
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-47"
server: etas
kind: motivation
type: Story
status: In Progress
priority: Medium
project: MEDUSA
assignee: cin8sgh
reporter: tao9sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-27T06:44:49.000+0000"
updated: "2026-09-02T08:54:18.000+0000"
synced-at: "2026-09-06T01:15:42.846Z"
jira-orphaned: false
---

# MEDUSA-47 M1 - Electron or Tauri integration with React

> [!jira] In Progress · Medium · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]] · 更新于 2026-09-02T08:54:18.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/MEDUSA-47)

## 描述

DoD:

1. Build App installer with Electron. Agent can run normally.

2. Compare Electron with Tauri.

3. Analyze the memory locations of chat history, checkpoints, Skills...

4. Add time consume information for each step.

5. Highlight which Agent/SubAgent is doing the current job

## 评论

> [!note]+ 2026-09-02 08:54 · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]]
> A Windows desktop application has already been packaged using Electron. Users can install it using the `.exe` file and download future versions through the in-app update button.
>
>
> Users’ conversation history is stored in IDB format under:
>
> {color:#4c9aff}C:\Users\<username>\AppData\Roaming\agentic-cobra-frontend\chat\session.json{color}
> Users can resume their previous conversations after closing and reopening the application.

-------

> [!note]+ 2026-09-02 06:03 · [[FIXED-TERM_CHEN_Yiran_(ETAS-ECMXSF-CN)|FIXED-TERM CHEN Yiran (ETAS-ECM/XSF-CN)]]
> The main disadvantages of Tauri compared with Electron are:
>  * **Requires Rust:** Our current technology stack consists of React, TypeScript, and Python. Adopting Tauri would require us to maintain an additional Rust-based main process and build toolchain.
>  * **More complex Python integration:** The FastAPI/DeepAgents backend would need to run as a sidecar managed by Rust. Electron can directly start, stop, and monitor it, as well as pass environment variables using Node.js {{{}child_process{}}}.
>  * **Less consistent rendering:** Tauri uses the system’s WebView2, whose version and policies may vary across corporate computers. Electron bundles a fixed Chromium version.
>  * **Smaller ecosystem:** Electron offers more mature solutions for installation, updates, process management, debugging, and enterprise deployment.
>  * **More complex troubleshooting:** A Tauri project involves React, Rust, WebView2, and a Python sidecar, while Electron mainly involves React, Node.js, and Python.
>
> If installer size or memory usage becomes a clear bottleneck, or if the team develops solid Rust expertise and a reliable cross-WebView testing framework, we can reassess the possibility of using Tauri.

-------

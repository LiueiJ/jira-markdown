---
jira_key: MEDUSA-39
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-39"
server: etas
kind: motivation
type: Story
status: Done
priority: Medium
project: MEDUSA
assignee: ""
reporter: tao9sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-05T03:25:54.000+0000"
updated: "2026-08-26T02:41:00.000+0000"
synced-at: "2026-09-06T01:15:42.846Z"
jira-orphaned: false
---

# MEDUSA-39 M1 - Simple DBC Import Enhancement and Quality Validation

> [!jira] Done · Medium ·  · 更新于 2026-08-26T02:41:00.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/MEDUSA-39)

## 描述

1. **SubAgent**: Add a dedicated &#91;dbc_import|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93; subagent. The main agent delegates DBC Import requests to it, and no other agent can invoke the DBC Import tool.

1. **Tool Wrapper**: Provide a typed &#91;cobra_dbc_import|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93; LangChain tool that runs:

Cobra.exe --ProjectPath <project> --isolarPath <isolar> --dbcimport

Support an explicit &#91;cobra_exe_path|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93; or unique project-local executable discovery, and return structured success/failure results with command output, exit code, Cobra-log diagnostics, and next actions.

1. **Skill**: Add DBC Import guidance for &#91;Parameter.ini|vscode-file://vscode-app/c:/Program%20Files/Microsoft%20VS%20Code/125df4672b/resources/app/out/vs/code/electron-browser/workbench/workbench.html&#93;, DBC/ECU mapping, file preconditions, safe configuration changes, CLI execution, and output/log validation.

1. **Workflow**: Register DBC Import as the first deterministic workflow step; track its state and require user confirmation before dependent steps continue.

## 评论

> [!note]+ 2026-08-26 02:40 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]
> 1. Add Sub Agent DBCImporter Expert to handle DBC Import tasks. DBC Import Skill is assigned to this subAgent.
>  # Cobra.exe DBCImport Addon can be called as Agent tool with a tool wrapper.
>  # Smoke test DBC Import finished based on project:[Browse RTA Engineering / AUTOSAR_RTA_XIP - Bitbucket (etas-dev.com)](https://bitbucket.etas-dev.com/projects/RTAENG/repos/autosar_rta_xip/browse?at=refs%2Fheads%2Ffeature%2FRTAXIP-3775-rta-bip-cobra-smart-confgen)

-------

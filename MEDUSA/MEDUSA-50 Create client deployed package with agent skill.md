---
jira_key: MEDUSA-50
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-50"
server: etas
kind: motivation
type: Story
status: Done
priority: Medium
project: MEDUSA
assignee: aiu2sgh
reporter: aiu2sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-28T05:29:59.000+0000"
updated: "2026-09-03T05:19:52.000+0000"
synced-at: "2026-09-06T01:15:42.846Z"
jira-orphaned: false
---

# MEDUSA-50 Create client deployed package with agent skill

> [!jira] Done · Medium · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] · 更新于 2026-09-03T05:19:52.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/MEDUSA-50)

## 描述

The knowledge base is planned to be created with two parts:

1. Client deployed package with public data
2. Server based RAG system with private data which can answer question which can not be solved alone on client side.

This ticket is used to setup and create the first package in client side.

Only smoking test is considered. 

No golden dataset for testing, no improvement for the whole pipeline.

## 评论

> [!note]+ 2026-09-01 09:07 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> With the agentic skill, it is able to setup the environment directly based on stonegaze-client-portable.zip

-------

> [!note]+ 2026-09-01 09:05 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Query CLI also works with local Ollama model:
>
> ![[MEDUSA-50-image-2026-09-01-17-03-55-704.png]]
>
> ![[MEDUSA-50-image-2026-09-01-17-05-10-440.png]]

-------

> [!note]+ 2026-09-01 09:02 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Agentic Skill works for query:
>
> ![[MEDUSA-50-image-2026-09-01-17-01-51-099.png]]
>
> ![[MEDUSA-50-image-2026-09-01-17-02-18-728.png]]

-------

> [!note]+ 2026-09-01 08:57 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Standalone client created on branch [RTA MEDUSA Internal Project / StoneGaze - Bitbucket (etas-dev.com)](https://bitbucket.etas-dev.com/projects/MEDUSA/repos/stonegaze/commits?until=dev/stonegaze-client)

-------

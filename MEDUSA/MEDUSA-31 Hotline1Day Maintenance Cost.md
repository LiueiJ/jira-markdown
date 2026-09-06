---
jira_key: MEDUSA-31
jira_url: "https://jira.etas-dev.com/browse/MEDUSA-31"
server: etas
kind: motivation
type: Sub-task
status: In Progress
priority: Medium
project: MEDUSA
assignee: ""
reporter: aiu2sgh
tags: []
components: []
fix-versions: []
epic: null
parent: "[[MEDUSA-1 Hotline1Day Migration to CN Infrastructure]]"
created: "2026-08-03T02:45:01.000+0000"
updated: "2026-08-04T02:56:17.000+0000"
synced-at: "2026-09-06T01:15:42.846Z"
jira-orphaned: false
---

# MEDUSA-31 Hotline1Day Maintenance Cost

> [!jira] In Progress · Medium ·  · 更新于 2026-08-04T02:56:17.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/MEDUSA-31)

## 描述

Except the migration cost, there are maintenance cost needed for cloud-based solution

- Domain name for ETAS hotline1 day.
  1. Managed IaaS provides second level domain name(boschcloud.com.cn), 100Euro/Month, including domain name management fee and SSL certificate cost.
  2. ETAS also purchase one domain name for this service. Time efforts might be one month, including purchasing and ICP.  The cost of Domain name management and SSL certificate might be 500+ Euro/Year.
- Alibaba Cloud LLM Service.
  - BD proposed ETAS to use Aliyun Bailian AI . ETAS needs to choose one LLM of Aliyun Bailian. Please refer to the attachment. (referring to [Token_Price.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/813671/813671_Token_Price.xlsx)
- Tech Differences
  1. Infrastructure resources will be handed by BD/ISA-PUC3 team.
  2. Dev team should just focus on application deployment.

## 评论

> [!note]+ 2026-08-04 02:42 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Domain name for ETAS hotline1 day:
>  * choose solution 1 for short period solution, long period solution TBD.
>  * domain name use: etai.boschclound.com.cn
>
> Alibaba Cloud LLM Service:
>  * choose qwen3.5-plus and deepseek-v4-flash after TA's suggestion

-------

---
jira_key: ARC-16044
jira_url: "https://jira.etas-dev.com/browse/ARC-16044"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: ""
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-04-20T12:21:23.000+0000"
updated: "2026-09-03T07:07:11.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-16044 Leapmotor ZCU (Zone Controller) & DCU (Domain Controller)

> [!jira] New ·  ·  · 更新于 2026-09-03T07:07:11.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-16044)

## 描述

Customer: Leapmotor

Controller:  ZCU and Domain Controller

Chip platform: TBD

RTA-CAR version:12.3.1 or later than 12.8.0

Please evaluate whether RTA-CAR supports the following features. 

If not, the ETAS team needs to discuss technical solutions internally based on the evaluation results and develop a detailed delivery plan and cost.

Customer's Requirement:

With the Domain Controller (DCU) acting as the Gateway and Edge Node, the current external diagnostic interface is limited to the OBD port via D-CAN (Pins 6 and 14). To ensure the normal execution of diagnostic functions for all vehicle controllers, the DCU must fulfill the following requirements. **(Note: The protocol conversion direction is described from the perspective of the request transmission path.)**

COM requirements are summarized here : [ARC-16073](https://jira.etas-dev.com/browse/ARC-16073)  [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] 

DIAG Requirements are summarized here : [ARC-16074](https://jira.etas-dev.com/browse/ARC-16074)  [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]

## 关联

- relates to: [[ARC-14706 Leapmotor ZCU]]

## 评论

> [!note]+ 2026-04-22 09:53 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]  I have requested PRM for clarification on the feature support. the information are in ARC-16073 ARC-16074.  

-------

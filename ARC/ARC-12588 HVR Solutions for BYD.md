---
jira_key: ARC-12588
jira_url: "https://jira.etas-dev.com/browse/ARC-12588"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-09-08T03:55:27.000+0000"
updated: "2025-12-28T00:06:31.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-12588 HVR Solutions for BYD

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2025-12-28T00:06:31.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-12588)

## 描述

BYD is interested with our RTA-HVR solutions especially the feature **virtual machine re-flash function** demonstrated in the demo.

BYD Engineering team has requested for EAP package.

BYD is expecting HVR solutions including GUI tooling support

Target HW : Renesas RH850 U2A

 

project background:

1.first implement in power domain controller with 4 in1(electronic control MCU、DCDC、OBC、PDU)

2.If success, It will be implement in power domain controller with 7 in 1

More use cases:

1.for the 4 in 1 controller, different ECU system should be separated development, RTA-HVR can provide multiple VMs, every VM can run different system and not affect each other 

2.RTA-HVR provide visualization dashboard, it can help customer to Dynamically adjust computing resources

 

Business scope: POC Project -> Mass production project

## 评论

> [!note]+ 2025-09-24 08:29 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Bray_George_(ETAS-ECMXPC-Yok1)_X|Bray George (ETAS-ECM/XPC-Yok1) [X]]]  we need a plan for this Business.first step, BYD need the sample project based on Renesas to ramp-up
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] fyi

-------

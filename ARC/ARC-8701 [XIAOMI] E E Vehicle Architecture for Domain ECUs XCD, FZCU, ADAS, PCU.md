---
jira_key: ARC-8701
jira_url: "https://jira.etas-dev.com/browse/ARC-8701"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: mas1yok
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-01-16T06:02:13.000+0000"
updated: "2026-09-03T17:07:50.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-8701 [XIAOMI] E/E Vehicle Architecture for Domain ECUs: XCD, FZCU, ADAS, PCU

> [!jira] New ·  · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] · 更新于 2026-09-03T17:07:50.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-8701)

## 描述

XIAOMI is about to start new project based on EE architecture. In this project they will not be using any CAN / LIN as the underlying protocol. This is fully based on Ethernet. 

1. Customer intends to use the newly introduced AUTOSAR module - IEEE 1722 Transport protocol based on the spec **AUTOSAR_CP_SWS_IEEE1722TransportLayer.pdf**
  1. Customer Expectation:
    1. ACF_CAN - related Control functions, communication management, callbacks are properly implemented in RTA-CAR
    2. Customer is willing to accept stage-wise deliverables ( currently under discussion! shall provide clarification upon alignment with customer! )
2. There is an interest for TSN Qbv supported in RTA-CAR product

Present Situation : Cost negotiations on going regarding the project

 

**ECU Setup**

 

ECU
uC/SoC
Compiler

PCU 

 

 

 

 
ST SR6 (variant not known)
GHS

XCD
Unknown
Unknown

FZCU
Unknown
Unknown

ADAS
Unknown
Unknown

## 评论

> [!note]+ 2026-09-03 17:07 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] how does this set of Xiaomi ECUs related to the existing Xiaomi project (ARC-2051)? E.g. are they planning to a second generation of their vehicle backbone, moving from IFX to ST silicon? And in any event, is this still alive at all?

-------

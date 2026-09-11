---
jira_key: ARC-5308
jira_url: "https://jira.etas-dev.com/browse/ARC-5308"
server: etas
kind: motivation
type: Motivation
status: Done
priority: ""
project: ARC
assignee: "[[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]]"
reporter: "[[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]"
tags: [jira/label/motivation_wo_need]
fix-versions: []
epic: null
parent: null
created: "2024-06-21T09:42:54.000+0000"
updated: "2025-05-23T09:26:38.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

HYCET is a subsidiary of Great Wall Motor (GWM)

- CycurHSM2.x project is just running together with RTA-CAR (LD_RTA_BSW_SEC 6.0)

 

Request is to move to RTA-CAR 12.x with CryptoDriver for CycurHSM3

- ECU: Motor Control Unit (MCU)
- Target Device: **Renesas RH850 U2B6** (Crypto Driver for CycurHSM3)
- seems that customer just bought RTA-OS
- FBL is done by customer himself
- ISOLAR 9.2 is used for configuration and code generation
- Communication Network: CAN-FD

Aim of HYCET is to be a supplier of GWM for MCU. For now a development license is enough.

 

**Feature request**:

- SecOC (Message Authentication)

 

**Timing**:

- SoP for GWM: Mid 2025 (Hycet might not be the first supplier, it is not clear for now)
- Milestoneplan requested from customer

## 评论

> [!note]+ 2024-06-27 01:42 · [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]]
> Hi  Sven,  5 years ago, they purchased the RTA-CAR 9.1 . Till now,  no upgrade for the toolchain.  Currently,  Li linlu are communicating with them for the cycurHSM topic. And also talk about the RTA-CAR tool upgrade.

-------

> [!note]+ 2024-06-26 22:41 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]] In this case can you please assign the activity to the colleague who leads this project and can provide relevant information to us related to it.

-------

> [!note]+ 2024-06-25 11:11 · [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]]
> Hi  Sven,
>
> What's the action for me? In ETCN, another colleague follow this topic
>
> Allen 

-------

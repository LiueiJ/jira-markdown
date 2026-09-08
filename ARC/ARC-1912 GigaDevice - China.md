---
jira_key: ARC-1912
jira_url: "https://jira.etas-dev.com/browse/ARC-1912"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: npr5kor
reporter: npr5kor
tags: [MCAL, Motivation_wo_Need]
components: []
fix-versions: []
epic: null
parent: null
created: "2023-07-26T12:29:34.000+0000"
updated: "2026-09-03T16:02:42.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-1912 GigaDevice - China

> [!jira] Accepted ·  · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] · 更新于 2026-09-03T16:02:42.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-1912)

> 标签：#jira/label/mcal #jira/label/motivation_wo_need

## 描述

BOSCH China is searching the local semiconductor for local ECUs, GigaDevice purchased GTM and XCAN Ips from BOSCH, and now would like ETAS to develop MCAL.     

Also an opportunity to sell a complete RTA-CAR solution with MCAL with GigaDevice end customers in the  future.

**Scope:**

1. Architecture: ARM M7
2. Expected deliver date Nov 2024
3. FPGA board can be provided (In China) in Aug 2023,  EVB board can be provided (oversea)in Aug 2024
4. Safety – ASIL-B
5. Muti-core support

![[ARC-1912-Scope.jpg]]

## 关联

- relates to: [[ARC-14702 RTA-OS port for Bosch Unicon devices ]]

## 评论

> [!note]+ 2024-02-05 08:16 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Added meeting minutes from ETAS [^ETAS RTA Solutions GigaDevice 2024-02.pdf]

-------

> [!note]+ 2024-02-04 21:17 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Gigadevice got approval as 1 of 4 local chip suppliers for BOSCH PS&CC, now they want a cooperation with ETAS to integrate OS and MCAL, and visited ETAS & BOSCH on the 2nd Feb.
>
> Notes:
>
> **Agenda & Key Notes:**
>  # Michael: introduced ETAS, key product and overall customer landscape
>  # Monica & Fei: presented GigaDevice, its product portfolio, and GigaDevice’s idea about BSW
>  # Open Discussion on BSW model:
>  # ETAS is **quite open** to the idea of BSW model from GigaDevice. {*}An initial draft BSW model{*}, which {*}was aligned between both sides{*}, can be found in below. Two Paths: Blue one goes {*}for BSW customization for mainsteam application (e.g. Powertrain) from Bosch/UAES{*}. Yellow one goes for BSW for OEMs. This focuses on non-Bosch ECU business. ETAS and GD cooperate tightly to potentially achieve Win-win.
>  # ETAS’s key services in: BSW, MCAL including CDD, RTE, HSM Firmware, OS porting and toolchain etc.; GD end: SDK, part of MCAL&CDD, relative documents
>
> ![[ARC-1912-GigaDevice-ETAS-Bosch_Collaboration-Model.png]]
>
> **AIs:**
>  # **AI for ETAS:** share the slides about ETAS, RTA-CAR etc. shown during the meeting ([@Kuerbitz Michael (ETAS-VOS/PRM-ARC)](mailto:Michael.Kuerbitz@etas.com))
>  # **AI for ETAS:** share the document with regard to ETAS Hypervisor solution ([@Binder Pascal (ETAS-VOS/XEO-ARC5)](mailto:Pascal.Binder@etas.com))
>  # **AI for GD:** give an initial proposal for the business model of BSW&Toolchain under three partys: “ETAS”-“GigaDevice”-“OEMs”({*}Yellow path{*} above). Based on this proposal, let’s see then how to proceed on this topic. ([@Fang He(何芳)](mailto:fang.he@gigadevice.com) , [@Fei Jin(金菲)](mailto:fei.jin@gigadevice.com))

-------

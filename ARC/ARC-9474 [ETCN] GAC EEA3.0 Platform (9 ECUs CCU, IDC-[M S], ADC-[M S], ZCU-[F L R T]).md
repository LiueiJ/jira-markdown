---
jira_key: ARC-9474
jira_url: "https://jira.etas-dev.com/browse/ARC-9474"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-03-06T08:17:55.000+0000"
updated: "2025-08-26T06:59:36.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-9474 [ETCN] GAC EEA3.0 Platform (9 ECUs: CCU, IDC-[M|S], ADC-[M|S], ZCU-[F|L|R|T])

> [!jira] Canceled ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2025-08-26T06:59:36.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-9474)

## 描述

**Project Scope**

**High-level :  (from GAC)**

**![[ARC-9474-image-2025-03-20-09-28-57-908.png]]**

 

**Project start date (SOW) & Project End date (SOP)**

 The five deliveries milestones scheduled by GAC . Expect RTA-CAR to pass the GAC SPEC tester 

 

![[ARC-9474-image-2025-03-20-09-33-03-601.png]]

  **Revenue  :** 10M RMB

 

**AUTOSAR CP Scope** 

- ZCU
  - 4 Geographical Zone Controllers
  - Front, Tail, Left, Right
  - Running AUTOSAR CP
  - ASIL-D
- ADC
  - Out of scope: running Linux
- IDC
  - Out of scope: running Android & Linux
- CCU
  - Out of scope: running Linux & QNX

## 评论

> [!note]+ 2025-06-25 23:44 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> Move status to **Canceled** as opportunity is lost.

-------

> [!note]+ 2025-03-26 15:04 · [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]]
> - The mass-produced CCU chip is S32G399 which have A core and M core, the M core running AUTOSAR CP
>  * the SPEC list contains all of controller's SPEC, the file which is named "EEA3.0" is the requirement for CCU

-------

> [!note]+ 2025-03-26 07:23 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Looks like [^XXX-整车软件架构项目_-_软件需求 (4).docx] tells us there are 9 ECUs in the platform but only the ZCUs are CP relevant:
>  * ZCU
>  ** 4 Geographical Zone Controllers
>  ** Front, Tail, Left, Right
>  ** Running AUTOSAR CP
>  ** ASIL-D
>  * ADC
>  ** Out of scope: running Linux
>  * IDC
>  ** Out of scope: running Android & Linux
>  * CCU
>  ** Out of scope: running Linux & QNX

-------

> [!note]+ 2025-03-25 03:29 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  I have created this motivation for GAC.  and corresponding needs tickets and assigned to respective PRMs. We have collected a list of features requested by GAC for DIAG, SecOC, & COM . At present we want to know how much of that we already support in our RTA-CAR 12.6.0. and how much we can support through the roadmap. we will provide GAC with a quotation by April-4th . We will like to know the status of the contract and project by End of April / Early may. 

-------

> [!note]+ 2025-03-20 09:08 · [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]]
> maybe there is a misunderstanding:
>
> 1)the SOW means Technical specification which is provided by GAC
>
> 3)the SOW has total GAC customized SPEC list which can be used as a source of evaluation for Supplier
>
> 4)The official SOW will be released by GAC Procurement, but it's too late for us 
>
> 5)The draft SOW will be completed at the end of March. Supplier could refer to the draft  SOW to prepare technical exchange and technical  solution, the draft SOW will not be released to supplier only support on-site preview too~~~

-------

> [!note]+ 2025-03-20 01:43 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> **Next Steps :**
>
> CN team to collect the list of GAC Features that is expected to be supported in RTA-CAR .
>
> **21st March** - DIAG related feature list will be gathered by CN team
> **Before 28th March** - DIAG RT shall comment on the list provided to see what is already supported and what is not supported in RTA-CAR 
> **Before 28th March** - COM & SecOC related features will be gathered by CN team
>
> **Before 4th April** - COM & SecOC RT comment on the list provided to see what is already supported and what is not supported in RTA-CAR
> **April 7th - 11th** - CN team to provide preliminary quotation to GAC  and prepare SoW
>
> All stakeholders kindly understand that COEMs does not share any specs or docs prior to contracts. CN team is trying their best to collect as much info as possible. Kindly request your support when requested. Many thanks

-------

> [!note]+ 2025-03-06 08:32 · [[LIU_Qing_(ETAS-ECMXSF-CN)_X|LIU Qing (ETAS-ECM/XSF-CN) [X]]]
> Example input files for project in 2024[^GAC AH8 SOMEIP CMX_ADC汇总表V1.21.xlsx][^AH8_Proj_BOSCH_Radar_CMX_V1.1_2023.9.18.xlsx][^AH8_E2E_Data_ID_20230427.pdf]

-------

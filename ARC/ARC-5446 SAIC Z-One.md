---
jira_key: ARC-5446
jira_url: "https://jira.etas-dev.com/browse/ARC-5446"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: "[[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]"
reporter: "[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2024-06-28T09:32:16.000+0000"
updated: "2025-05-19T05:13:41.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

# ECU Scope

**ECU:** Gateway + ADAS + Light +Cockpit ECU

**uC:** TC387

**Compiler:** Tasking 6.3r1p1

**Connectivity:** 

- CAN: 8-11 channels
- LIN: 4 channels
- ETH (DoIP, OTA-Slave): 1 channel
- Self-Diagnostic: DoCAN, DoIP
- Calibration: XCPonCAN
- TimeSync: TimeGateway over CAN
- Gateway features:
  - ComGw: CAN-LIN
  - PduGw:  CAN-CAN
  - TpGw:    ETH-CAN, CAN-CAN

# Competitive Situation

 Using existing Vector for application and function verification

# OEM Specification

- **SMTC 2 800 004** (Technical requirement for ECU diagnostic development 20170803)

# Timescales

- **PPV**: Feature complete at **2024.11.30** where require ETAS **2024.10.30** for feature complete delivery
- **SOP**: 2024.12.30
- **The box marked yellow and blue are where we need support to take into RTA-CAR+**
  - no need to be an RTA-CAR x.y release version in between during this period
  - we need developers to concentrated to work with us for bug fix especially BSW race condition, adapt BSWMD AutoGen, and integration as shown in below box2
- CN-Hub will go onsite for ConfGen adaptation for EcuExtract and DEXT, MCAL migration, BSW migration, SWC migration to RTA-CAR during CW33 - CW35

![[ARC-5446-image-2024-08-15-10-57-55-821.png]]

## 关联

- relates to: [[RTAXIP-1529  [SAICZONE_RIP-CES_TC387TK] Application]]

## 评论

> [!note]+ 2025-05-19 05:13 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Updated status :
>
> We lost this Acquisition in September'2024. 'Cancelled' the motivation to keep it relevant and upto date.
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]  fyi. 

-------

> [!note]+ 2024-08-15 03:07 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> SAICZONE final SOR has been shared with us 2024.08.14.
>
> A review meeting with key stakeholders **before 2024.08.16** (requested response time to SAICZONE) required:
>
> **Goal of the review meeting: decision for a working model on SAICZONE delivery fulfilling**
>  * continuous delivery
>
>  * 
>  ** RTA-CAR installer
>  ** Reference integration package on each RTA-CAR installer
>  *** continuous software integration
>  * Bi-weekly continuous RTA-CAR installer packing **(before 2024.10.30)**
>  ** ConfGen adaptation
>  ** Component bug fix (BSW, Rte)
>  *** Multi-Core Client-Server (Hotline labels=SAICZONE)
>  *** Missing/Incorrect MemoryMapping section definition
>  *** Missing SwAddrMethod in BSWMD
>  *** Critical Zone Protection
>  ** Component Change Requests
>  *** Dcm/Dem: OEM Spec SMTC 2 800 004
>  *** Split CAN stack across multiple CPU cores
>  *** Taking component from {color:#de350b}*12.4* {color}to **{color:#de350b}12.?{color}** for SAICZONE: **WdgM Master-Satellite, NvM Master-Satellite**
>  *** **BswM Master-Satellite, Dem Master-Satellite, StbM Master-Satellite**
>  ** Additional Components/Tools
>  *** Exclusive Area (ARC-5449)
>  *** Etm (Ethernet testability module for TCP/IP protocol conformance testing)
>  *** Tm
>  *** Dbg
>  *** RamTst

-------

> [!note]+ 2024-08-12 06:43 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Via Tan Yang:
> {quote}ETAS will support EP phase by CW38 with below setup:
>  # Migrate to RTA-CAR: **2024.09.01**
>
>  * Onsite engineer
>
>  # Build RTA-CAR baseline for SAICZONE on SAICZONE laptops
>
>  # RTA-CAR ConfGen and use case collection for SAICZONE EcuExtract: Liu Jie (TpL)
>  # RTA-CAR ConfGen and use case collection for SAICZONE DEXT (converted from CDD): Zhang Yuan
>  # Migrate other BSW configurations: Zhang Junsheng
>  # Software and MCAL integrator:      Wang Chao
>
>  # Support integrate ETAS RTA-CAR baseline with SAIC SWC
>
>  * ETAS Global: **RTA-CAR ConfGen adaptation** for SAICZONE EcuExtract, DEXT (converted from CDD)
>
>
>  # Support for EP testing: **2024.09.15**
>  # Onsite support SAICZONE for EP test
>  # Onsite support and training for SAICZONE developers
>
>
>  # Discuss and optimize multicore architecture: **begin of Sep.**
>  # Best practices proposal by ETAS for Multicore distribution
>  # Identify SAICZONE request for new features/changes to meet SAICZONE architecture and performance demands
>
>
>
> With above plan, we identify below {*}TODOs{*}:
>  * ETAS ({*}by Aug.12nd){*}: provide RTA-CAR 12.3.1 release version, multicore baseline (RTAXIP-978) to Ms. Ge Qi
>  * SACIZONE({*}ASAP, latest before Aug. 23rd{*}): provide EcuExtract, DEXT to ETAS for  **RTA-CAR ConfGen adaptation**
>  # ETAS: necessary process supporting SACIZONE sharing EcuExtract, DEXT
>
>
>
> **Yang TAN** 
> Software defined Vehicle Operating System # China 
>
>
>
> {quote}
> See also: https://jira.etas-dev.com/browse/RTAXIP-1529

-------

> [!note]+ 2024-07-01 08:44 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> We have received informal verbal communication (via lbo9sgh / [[Tracey_Nigel_(ETAS-ECMPG_ETASTCR-GB)|Tracey Nigel (ETAS-ECM/PG ETAS/TCR-GB)]] ) that ETAS will be awarded the project, so we should assume that we need to start moving.
>
> One key aspect of the ECU architecture is that it will have 15 (fifteen) CAN busses and therefore it will be mandatory (for performance/throughput reasons) for us to support the split of the CAN stack across multiple CPU cores in a safe way (i.e. without any race conditions or data corruption due to incorrectly assigned mutexs).

-------

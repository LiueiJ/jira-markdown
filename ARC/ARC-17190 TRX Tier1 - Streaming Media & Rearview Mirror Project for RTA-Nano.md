---
jira_key: ARC-17190
jira_url: "https://jira.etas-dev.com/browse/ARC-17190"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]"
reporter: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-07-22T09:10:43.000+0000"
updated: "2026-08-18T02:29:36.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

1.  **Project Scope & Target Platform**

- **Customer**: TRX, targeting a Xiaomi streaming rearview mirror and camera ECU project.
- MCU: **YTM32B1MC03H0MLHT** (backup: YTM32B1MD14G0MLHT).
- AUTOSAR solution planned: **RTA-Nano ( Proxy : RTA-CAR** **😊)**
- Compiler: **IAR 9.60.3.422**.
- Resources:
- PFlash: 512 KB
- RAM: 64 KB
- Customer reserves 20–30% Flash for future expansion.
- **PFA dosc from customer  [Appendix T12_Flash Programming Specification on CAN&CANFD_CAN&CANFD节点刷写要求-V2.4-20260323.pdf!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/810129/810129_Appendix+T12_Flash+Programming+Specification+on+CAN%26CANFD_CAN%26CANFD%E8%8A%82%E7%82%B9%E5%88%B7%E5%86%99%E8%A6%81%E6%B1%82-V2.4-20260323.pdf)[kunlun流媒体内后视镜及摄像头总成SOR包-20260626.zip!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/810131/810131_kunlun%E6%B5%81%E5%AA%92%E4%BD%93%E5%86%85%E5%90%8E%E8%A7%86%E9%95%9C%E5%8F%8A%E6%91%84%E5%83%8F%E5%A4%B4%E6%80%BB%E6%88%90SOR%E5%8C%85-20260626.zip)**

1.  **Current System Configuration**

- Communication:
- 1 CAN network
- No Ethernet
- Current Xiaomi project is CAN-only (LIN belongs to a different platform project).

- Signals:
- 106 RX COM signals
- 57 TX COM signals.

1.  **Software Scope**

       Target BSW includes:

- RTA-COM (Com, PduR, Nm, IPduM)
- RTA-CAN (CanIf, CanSM, CanTp)
- RTA-SEC (SecOC, KeyM)
- RTA-BASE (EcuM, BswM, XCPonCAN)
- RTA-DIAG (Dcm, Dem)
- RTA-RTE
- RTA-OS
- Vector Crypto implementation.

1.  **Memory Assumptions**

Current assumptions:

- Xiaomi Application: ~60 KB
- MCAL: ~100 KB
- ETAS CP Lite target: <118 KB
- FBL (DoCAN): ~80 KB
- Total expected footprint: ~358 KB.

1.  **Bootloader / Update Architecture**

**Customer confirmed:**

- Internal ECU contains:

- MCU
- Video chip with external SPI Flash

- External camera must also be updated through I2C private protocol.
- Recommendation proposed:

- FBL handles MCU update only.
- External device updates handled by Application software.

1.  **Customer Timeline**

**Milestone**
**Date**

Technical feasibility & proposal
24 Jul

Nomination decision
31 Jul

Initial delivery (OS Port, COM, UDS, OTA if required)
07 Sep

Production-ready / Full features
07 Oct

**Customer goals:**

- 7 Sep vehicle integration milestone.
- 7 Oct production-ready status required.

 ** 

**To be Confirmed** 

1. **RTA-Nano Feasibility**

- Whether ETAS can achieve the **<118 KB memory footprint**. Feedback required from the PF experts based on the information shared.  [ If the information is supplied is still not enough  –  at least a confidence rating is required]
- **Business decisions tbc:**
- **Option 1** : The target business is for RTA-Nano . Since the product is not ready, we are likely to start with RTA-CAR . Licensing cost , positioning of the product and switching timeline ( RTA-CAR -> RTA-Nano) need to be discussed.
- **Option 2** : If we can achieve the tech. goals using RTA-CAR itself, then we let the customer maintain the project with RTA-CAR . But the there can be impact on licensing cost. We may need to offer discounts.

1. **OTA Requirement :** OTA support requirement remains under OEM (Xiaomi) confirmation.

1. **SecOC Requirement**

- Customer is evaluating whether a SecOC deviation is possible.
- OEM confirmation is still pending.

1. **PBL + SBL Requirement :** Currently assumed to be applicable.

1. **Private Controller Requirement**

- Customer clarification is still pending.
- However technical discussion confirms that:

- Video-chip Flash update is required.
- Camera update through I2C private protocol is required.

- Therefore, this requirement likely applies.

1. **Multiple Communication Networks Requirement**

- TBC by the customer.
- We can assume for now this is applicable because updates involve multiple devices and interfaces.

1. **Resource footprint**

Still not fully known:

- Actual MCAL footprint.
- Actual CP Lite generated code size.
- RAM consumption.
- Whether all required security modules fit within the memory constraints.

 ** 

**Major Risks**

**Project Timeline (High)**

Customer expects:

- Initial integration package by 7 Sep.
- Production-ready state by 7 Oct.

This leaves only ~6 weeks from nomination to first delivery and ~2 additional months to SOP-quality functionality.

**Memory Risk (High)**

512 KB Flash is still constrained considering:

- FBL ≈ 80 KB
- MCAL ≈ 100 KB
- APP ≈ 60 KB
- Flash reserves requirement 20–30%
- Security-related modules (SecOC/KeyM)
- Diagnostic functions.

**Feature Scope Risk**

**RTA-OS Porting is required - can start with Base ports. Puts a lot of pressure on timeline**

Pending decisions on:

- OTA
- SecOC
- External device flashing architecture could significantly impact effort and footprint.

## 评论

> [!note]+ 2026-08-18 02:29 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
>
> Hi Alex, Although the customer has lost the project, the platform remains live.
>
> Once the customer triggers the bidding procedure, ETCN will participate.

-------

> [!note]+ 2026-08-17 12:08 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] I would expect that RTA-CAR would, if configured well, consume 200kB for the listed use-cases.
>
>
>
> Is this project acquisition still live?

-------

> [!note]+ 2026-07-30 08:54 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]  thanks for the feedback on the CAR status for this request. I suspected that would be case. 
>
> I understand 118 KB is not possible with CAR, but what can be a target size... do you think its possible under 256 KB ? 
>
> [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]  thanks for the summary. 
>
> When the biz comes close to tech. & biz. level discussions, i will try to position RTA-CAR for start and Nano for later stages i.e. end of the year perhaps 
>
> but still I am not fully confident if we can get it under 118 KB even with Nano for requirements... maybe one of you can shed some light on it. 
>
> we need to dig a bit more with the customer to understand the use cases and stack usage. [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]  we need to follow-up on this biz. 

-------

> [!note]+ 2026-07-22 19:25 · [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  and [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]  I did review this request and here is my input: 
>  * This is a target use case for NANO, but timeline doesn't fit 
>  * So, we offer it to the customer as NANO, and make RTA-CAR works in the background for this implementation 
>  * Pricing and overall pitch should be NANO to maintain low price for smaller ECU without compromising RTA-CAR pricing
>  * Customer doesn't need to be confused with CAR vs. NANO --> our offer is NANO and we map out what can be done behind the scene and share it with the customer 
>  * We should explain to the customer what NANO can do and convince them to stick to NANO's features only, which behind the scene can be conceived out of CAR, but keep the focus on NANO, and if the customer insisted on the full features set, then we should explore the following: 
>  ** Create an overarching plan for the customer showing the following:
>  *** Initial delivery plan some features that fit in 118KB only (CAN, DIAG, lightweight BSW and RTE as defined by NANO specs, RTA-OS) and no SecOC in the initial delivery, OR, whatever we design the features set as per our current release plan
>  *** Subsequent delivery for other optimized features like DEM and XCP, etc. after going through the exercise of initial delivery
>  ***  Most important condition is to avoid customizing a solution to the customer 
>
> We can have a call tomorrow at 7 am EST and chat about this opp. Most important thing to me is win the business as first opp for NANO in China to prove the technical and commercial hypotheses we have for China market. 

-------

> [!note]+ 2026-07-22 11:05 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] I think based on the timelines we have to look at offering based on RTA-CAR, but configured as small as possible using lessons learned developing RTA-NANO. We have a project that could be used. Based on the features listed, with RTA-CAR, 118KB is likely not achievable, in particular XCP and DEM are expensive. We also have some planned improvements coming in CAN, removing PduR and Mem, which will not be ready in time. We also do not know the size of Vector Crypto stack?

-------

> [!note]+ 2026-07-22 09:47 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> Customer share Spec and SOR to ETAS, please find the attachment.
>
> Appendix T12_Flash Programming Specification on CAN&CANFD_CAN&CANFD节点刷写要求-V2.4-20260323.pdf
>  * OTA required or not?  OTA is required; old APP will be store in Main ECU.
>  * SecOC mandatory or waiver possible?     wait for feedback.
>  * PBL+SBL requirement?    Yes, mandatory.
>  * A/B bank requirement?   No requirement.

-------

> [!note]+ 2026-07-22 09:20 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]  
>
> There is a clear biz for RTA-Nano . Minosar did not meet the criteria. Nano is still not in product form yet. I guess we will have to do with RTA-CAR for now... that is a biz discussion for next step. for now, we need your support with the following asap :  
>
> **Immediate (This Week)**
>
> **ECM**
>  # Confirm with PF: [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] 
>
>  * 
>  ** With the shared details ( Details in the ticket + [^Appendix T12_Flash Programming Specification on CAN&CANFD_CAN&CANFD节点刷写要求-V2.4-20260323.pdf][^kunlun流媒体内后视镜及摄像头总成SOR包-20260626.zip]) - Can PF experts help confirm RTA-Nano / RTA-CAR fit within 118 KB Flash target?
>  ** What cane be the expected RAM footprint?
>  ** Any benchmark available which is comparable to YTM32 ? 
>  *** it would be ideal to share the features and stacks used in the benchmark analysis. we can use this in our acquisition discussion.
>
>  # RTA-Nano technical feasibility for: (does the following features covered in scope of RTA-Nano )
>
>  * SecOC + KeyM
>  * XCPonCAN
>  * UDS + FBL
>  * Existing YTM32 support status.
>
> **ETCN Sales** : [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]  could you please confirm with the customer ? 
>  * OTA required or not?
>  * SecOC mandatory or waiver possible?
>  * PBL+SBL requirement?
>  * A/B bank requirement?
>
> [[Hotz_Ingo_(ETAS-ECMPRM-EMW)|Hotz Ingo (ETAS-ECM/PRM-EMW)]] [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] [[HUANG_Song_(ETASCCN1)|HUANG Song (ETAS/CCN1)]] fyi. 

-------

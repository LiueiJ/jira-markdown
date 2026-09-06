---
jira_key: ARC-2051
jira_url: "https://jira.etas-dev.com/browse/ARC-2051"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: mas1yok
reporter: bal9yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2023-09-12T12:25:23.000+0000"
updated: "2025-06-25T23:42:32.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-2051 Xiaomi - 4 Domain ECUs: XCD, FZCU, ADAS, PCU

> [!jira] Accepted ·  · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] · 更新于 2025-06-25T23:42:32.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-2051)

## 描述

**Target** 
**4 Domain ECUs: XCD, FZCU, ADAS, PCU**

**In-house CP BSW cooperation**

**MCU**
TC397/387

**Planned start date**
2023.09

**Planned end date**
2024.05

**Working model**
On-site engineering

Back-End Team engineering

XIAOMI OEM enterprise standard BSW development

**Content**
1.RTA-CAR 12.2 delivery(Autosar R21-11)

2.XM OEM enterprise standard BSW delivery

3.XIAOMI XCD/FZCU/ADCU/PCU BSW integration

4.Support XM In-house BSW development integration

 

Xiaomi story [kickoff_RTA_xIP_CE_TC397TK_1220.pptx](https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/2021202323_PJ_ERS_Sgh_FreeTech_AUTOSAR/01_Draft/00_Start/02_ProjectKickOff/kickoff_RTA_xIP_CE_TC397TK_1220.pptx)

MI-Spec folder [10_RequirmentsDocuments/15_RequirementsGathering/MI](https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/2021202323_PJ_ERS_Sgh_FreeTech_AUTOSAR/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments/15_RequirementsGathering/MI)

Requirmemtns seems to be quite close to Geely, potentially because Xiaomi hired Zeekr Engineers

## 关联

- relates to: [[ARC-4518 Lock configuration concept and rollout]]
- mitigates: [[RTAXIP-906 [MI_RIP-CES_TC397TK] RIP Application]]
- mitigates: [[RTAXIP-985 [MI_RIP-CES_TC397TK] DoIP Payload Type MISpec T14 2_3_2_3]]
- mitigates: [[RTAXIP-987 [MI_RIP-CES_TC397TK] MISpec T14 2_8_3_3 TLS (1.2) cipher suites]]

## 评论

> [!note]+ 2024-07-03 06:17 · [[Schneider_Markus_(ETAS-ECMENG-GM)|Schneider Markus (ETAS-ECM/ENG-GM)]]
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] , there is no request anymore for new SecOC feature. No need to create a Need.

-------

> [!note]+ 2024-07-02 22:00 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[Schneider_Markus_(ETAS-ECMENG-GM)|Schneider Markus (ETAS-ECM/ENG-GM)]] Can you create a **Need** for the expected SecOC implementation, please?

-------

> [!note]+ 2024-02-21 21:00 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]] I have seen a question by [[Schneider_Markus_(ETAS-ECMENG-GM)|Schneider Markus (ETAS-ECM/ENG-GM)]] about the use of SecOC in the customer project and there was the question about a customer specification for it. Can you please provide your answer here?

-------

> [!note]+ 2023-10-31 13:24 · [[Roettgermann_Matthias_(ETAS-ECMXPC-Abt1)|Roettgermann Matthias (ETAS-ECM/XPC-Abt1)]]
> Dear Yang,
>
>
>
> please find below the expert answers to the action items 1,2,4,5:
>
>
> | **Open points** | **Answers** |
> | 1. Use-case: shall support granularity of Time stamp between two consecutive CAN frame less than 1ms |
>     Solution-Polling: may not be enough
>     {*}Action Item by ETAS{*}: ETAS to come back with proposal|With CAN HW timestamping support there is no need to use interrupt processing -> capturing of time stamp is done by CAN HW, SW processing may happen asynchronously|
> | 2. ETH Interrupt: sporadic use case with high load, how do deal without Interrupt? |
>     ETAS(Volker): interrupt is possible but requires spinlock to avoid to break buffers. Some additional buffer could be added to remove spinlock, but this will increase RAM consumption.
>     Xiaomi: They are not concerned about RAM but CPU.
>     {*}Action Item by ETAS{*}: ETAS shall evaluate the latency/locking introduced by spinlocks when Multicore prototype deployment for XIAOMI is available|Recommendation: do the runtime measurement when Multicore prototype for Xiaomi is available
>
> Assumption is that Ethernet stack in "empty" operation does not consume much runtime -> still recommended to use fast polling mode. Further runtime optimization possible via switching controller to NO_COM when no data needs to be transferred.|
> | 4. Time consumption of Xcore CDD in some use cases + sample project |
>    {*}Question to ETAS{*}: Is there an existing setup available at Germany which can give some reference data to XIAOMI or shall we feedback when Multicore prototype for XIAOMI available ?|Do the runtime measurement when Multicore prototype for Xiaomi is available
>
> Assumption: * overall core load is reduced because frequency of signal processing can be fine tuned according to the need and because no locks are needed
>  * latency increased (depends on polling frequency, runtime for MemCopy), but mitigation measures available (certain paths could use interrupt mode)|
> | 5. XIAOMI will have DoCAN<->DoCAN at E3 milestone (2024.1.15) on core2. According to ETAS proposal in Xiaomi_BswDistribution.xlsx, Diag stack will be on Core3 |
>    {*}Question to ETAS{*}: When both Tp Routing on core2 and core3, is Diag on Core3 be OK ?|Task of CanTp_MainFunction is only "house keeping", e.g. timeout handling. Segmentation happens in callbacks from Can_MainFunction_Write -> placement of CanTP_MainFunction does not really matter, but could also be placed on Core 2
>
> General approach for diagnosis application TX: * first call (StartOfTransmission) buffered via XCoreCDD to avoid locks on the fast path
>  * Further calls (CopyTxData) will be called directly in context of Can_MainFunction_Write without any locks
>  * Last call (EndOfTransmission) is a direct call and just releases the ownership of the buffer|
>
>
>
>
>
> Mit freundlichen Grüßen / Best regards
>
> **Volker Stuerzl**
> ETAS-VOS/ENG-ARC

-------

> [!note]+ 2023-10-16 21:14 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> Is it planned for this project to use {*}CycurHSM2{*}?

-------

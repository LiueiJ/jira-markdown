---
jira_key: ARC-13728
jira_url: "https://jira.etas-dev.com/browse/ARC-13728"
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
created: "2025-11-26T05:33:01.000+0000"
updated: "2026-09-03T16:24:20.000+0000"
synced-at: "2026-09-11T01:13:09.700Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

## About G-Pulse :

- ECU Development Partner for FAW ( unlike Bosch model. They are development partner )
- G-Pulse is part of the Infineon - reseller group.
- For large applications such BMS, Motor controller - customer use Infineon MCUs
- Have Lab in the office for ECU testing.
- Use AVL solution for HIL testing
- G-Pulse have a 3 year Frame contract with ETAS - CP tooling.
- Customer is interested in HVR demo on TC4Dx

## Small Microcontroller use case:

1. G-Pulse consider using CP & HSM on small microcontrollers.
  1. Application : ITS ( Integrated Thermal Systems ) , WCT ( Water Charger ) , WPC ( Water Pump ) , PTC ( Peripheral Touch Controller) , EAC (Electronic Air Control )
2. **FuSa level** : QM -> ASIL-B

### **Motivation for AUTOSAR -lite**

1. SW - All SW is in-house - So no cost for customers like FAW but for G-Pulse.
2. Customer looking for suppliers who can provide off-the shelf CP Stack - lite…
  1. All the Customer use-cases on the below MCU's are **Single-core application**.
    1. Main stack is LIN & CAN for their sensors
 1. Simple tasks , BCC1 task is ok .
 2. Timer triggered is fine. No need for event triggered.
 3. ATM, customer is using commercial, Non-standard Software.
 4. It is mainly for cost-saving.
 5. Customer does not use - Extended Tasks.
 6. Global projects - bring requirements for more stacks and Functional safety cases

![[ARC-13728-image-2025-11-26-13-31-26-957.png]]

- PTC  ( ~2 million ) & WPC ( ~2 million ) has the large volumes  - Biggest market share. More than 50%
- Architecture is almost the same.
- **CYT is very important for G-Pulse.**
- For ITS & EAC - there are some AUTOSAR solutions are used for some customer. For other customers G-Pulse use in-house light weight solutions. Volume : 100 K / year ( used in camera modules )

1. ### Std. Modules

1. 1. NVM, WDG may also be needed.
  2. ETH, J1939 is NOT needed.
  3. COM Stack, Diag. services ( UDS, Diag. event mgmt ), maybe OBD services. CAN NM is needed.
  4. SEC stack is mandatory.

## Customer Current Status

1. Customer would like to know the key difference between AUTOSAR Lite & Std. AUTOSAR  ?
2. Customer has no pain point until now. They are happy with their in-house soln.
  1. Higher requirements from Europe market.
  2. If ETAS soln. & tooling  can support the in-coming project requirements then G-Pulse is interested in RTA-CAR Nano
3. Only reason they explore for AUTOSAR 'lite' is for future proofing for the global projects.
4. High-level need : Functional Safety , ASPICE , & Tool Chain certification
5. Compilers : IAR, GHS
6. G-Pulse has production license for RTA-CAR
  1. Some of the G-Pulse customers are in older version of RTA-CAR and so G-Pulse has to stay in the customer version of RTA-CAR

- Current version G-Pulse is using for their dev. Is RTA-CAR 12.3.2
- Another platform uses RTA-CAR 9.1.0
- There are CyberSecurity - requirement from PATAC.
  - Need a price to support : CycurHSM and SUM_SSC .
- PATAC is using light weight SSC.
- **G-Pulse want to know the cost only for SUM_SSC**
- Only security features, secure bootloader, secure flash and secure communication
- ETAS : to check if SSC can be offered separately ? Explore the dependencies for SSC ?
- G-Pulse: Can you provide the approximate reduction of Code size for each module to evaluate the flash of Chip. with the configuration provided ?

**FAW** :

- FAW wants to move from HUAWEI to other tool solutions 
  - HUAWEI cannot support Global chips.
  - FAW is familiar with Vector tooling chains and Neusar

- Need to follow-up to explore FAW business ... ( TBC )

 

**RTA-CCM** :

- Sathish shared the CCM solutions .
- There is a need for G-Pulse customer to use CCM - ISO standard to go global .
- Need further follow-up with G-Pulse.

 

## Customer Project Configurations ( based on RTA-CAR )

 

Can be found here : \\fe13606\eswsw\temp\mas1yok\G-Pulse

(cannot attach in this ticket for all the IT reasons in the world)

## 关联

- is informed by: [[RTAXIP-2991 [G-Pulse] Migrate RTA-CAR from 12.3.2 to 12.9.0]]

## 评论

> [!note]+ 2026-05-25 14:59 · [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] I don't know the status of this opportunity so far, but let's pick it up in our call this week and take it from there. We can also prepare some material for NANO that addresses their requirements. 

-------

> [!note]+ 2026-04-06 16:54 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> Great thanks [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] I think we have everything we need now to propose to give customer an overview of what is possible with RTA-CAR e.g. for CYT2xx , and what RTA-CAR Nano will do to enable 'AUTOSAR lite' on the smaller chips like PSoC4. Could you arrange a call, please invite Omar and myself and we will present and discuss next steps with them.

-------

> [!note]+ 2026-03-13 09:31 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] good news. you can find the project with configuration completed and migrated  from 12.3.2 -> 12.9.0 .   more details in this ticket : [RTAXIP-2991] [G-Pulse] Migrate RTA-CAR from 12.3.2 to 12.9.0 - Jira (etas-dev.com) 
>
> Please take a look . We need to provide customer a feedback of our product team analysis. Based on your further evaluations if you can help me with some evaluation reports and help me pitch our nano -  I can then share with customer and see if we can make some inroads. if anything please reach out to me. 
>
> thanks .
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] fyi. 

-------

> [!note]+ 2026-03-02 15:52 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] any news on if ETCN can take up this initial migration and analysis topic?

-------

> [!note]+ 2025-12-01 12:09 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]  Since the project is already based on RTA-CAR 12.3.2, I presume we can use our RTA-CAR Tooling migrator to migrate to the latest version. imo, the actual work is to analyze if any further optimizations can be made on the customer project.   let me check if anyone's available for initial migration task. 

-------

> [!note]+ 2025-11-27 14:13 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> Thanks [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] . I think the next step would be to get the project generating and building so we can answer those questions. If we can get it generating and building on the latest version we can also see what impact our new improvements have, and share these with them. Therefore, do you have any capacity in ETCN to migrate the project and get it building? 

-------

> [!note]+ 2025-11-26 06:13 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] Customer is interested in RTA-CAR nano. they have shared with us their project Configurations ( based on RTA-CAR ). They want to know the Code size and Flash consumption for their project and the gain by using RTA-CAR nano ( i am aware it is still not a thing yet . ) . Based on best practices and the information I compiled in the ticket, could we please do some analysis on the customer configuration and provide a feedback to them with some Code & flash consumption in total and for specific BSW stack etc., Could you please support ? Thanks 

-------

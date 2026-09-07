---
jira_key: ARC-13785
jira_url: "https://jira.etas-dev.com/browse/ARC-13785"
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
created: "2025-12-03T01:25:59.000+0000"
updated: "2026-07-09T01:22:59.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-13785 Neusoft SmartGo Cockpit ADAS solution based on QC8797

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-07-09T01:22:59.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13785)

## 描述

**Business Scope :**  ETAS shall provide a BIP & Eng. support to customer. 

**Customer : Neusoft SmartGo**

**Customer's Status**:

- J6+external U2A, other Qualcomm Gen4 SOC + U2A
- Rich experience of RTA-CAR usage
- Migrate U2A application algorithm to 8775 internal R52 and then test them.
- Tested application algorithm on 8797 R52.
- previous (2025Q3) won 8797 production project for FAW do not use AUTOSAR CP on SAIL, baseline shall be ready at June 2026.

**Customer current plans**:

- Customer got nomination July 7th from BAIC to offer Cockpit ADAS solution on QC8797 for cockpit ADAS driving solution on Beijing 2026 Car exhibition.
- Customer is evaluating hardware solution and if chose solution (b) then RTA-CAR will need to adapt onto 8797
  - a. QC8797 + RH850U2B (run AUTOSAR Classic)
  - b. QC8797 (run AUTOSAR Classic) + tinny MCU (Power Mgt)

**ETAS status:**

- ISOALR-M 12.10 based MCAL & CDD modules adaption is ready for 8797 SDK package ([https://jira.etas-dev.com/browse/ARC-13777](https://jira.etas-dev.com/browse/ARC-13777))
- Provide trail use in April 2026 of RTA-CAR12.9.0, ISOALR-M 12.10 and RTA-CAR 12.9.0 based BIP to Neusoft SmartGo

**Challenges:**

- Evaluate if there is hypervisor requirement on R52 or bypass hypervisor
  - Neusoft SmartGo prefer no QC EL2 HYP so can
    - (1) same as much CPU and SRAM
    - (2) more efficient SAIL IoC and Ipc.
  - Neusoft SmartGo accept to use QC EL2 HYP
    - but must be SMP multicore support, so that they can run AUTOSAR multicore on SAIL
    - This QC EL2 HYP is Blocker where we cannot receive QC support **

**Need:**

- **Mgt support for evaluate and propose collaborate with Qualcomm for <QC EL2 HYP to support SAIL SMP multicore> to ENABLE RTA-CAR multi core bring up and software debug, deployment.**
- Porting 8797 Os port, compiler Arm Compiler for Embedded FuSa 6.16.2 LTS: [https://jira.etas-dev.com/browse/ARC-13891](https://jira.etas-dev.com/browse/ARC-13891)**{**}

**Scope**

- Want to reduce cost of hardware solution to change U2A to lower price MCU, e.g F1M.
- Architecture of MCU: 3 lockstep cores, split CAN bus
- Core0: Normal Can, diagnostic and other BSW stacks.
- Core1: Drive Can, ADAS Can, radar algorithm
- Core2: algorithm for APA, SPI
- One image with multicore CP solution
- (TBC) Has security requirement for both R and A cores: secure boot, secure communication and secure diagnostic

![[ARC-13785-image-2025-12-03-09-22-53-956.png]]

**Draft deployment need on QAM8797P SAIL as shown below**

- No FuSa
- lock-step multicore
- split CAN bus
- Cluster0 - system services and cockpit CAN
- Cluster1 - Drive CAN, ADAS CAN, radar algorithm
- Cluster2 - APA CAN, APA algorithm

![[ARC-13785-image-2025-12-03-09-24-14-823.png]]

## 关联

- is satisfied by: [[OSOPP-259 Update QC-R52-ARM to support QAM8797P]]
- is satisfied by: [[ARC-13777 Updates to ISOLAR-M 12.9.x needed to support QCPP]]

## 评论

> [!note]+ 2025-12-03 01:56 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [@TAN Yang (ETAS-ECM/XSF-CN)](mailto:Yang.Tan@bosch.com),
>
> **Reg. OS Porting** 
>  # 
>  ## Yes. We can start the Base porting activity with our CN OS team in December
>  ## We need HW to do it properly. Board bring up activity is the critical part and this cannot be simply evaluated using manuals ( you probably know it already 😊 ).
>  ## If the board is not there, we can look into the manuals and understand the diff. between the Gen 4 & Gen 5 QC SoCs and prepare appropriately for Porting activities. But without the HW we cannot progress further.
>
> [@XIE Allen (ETAS-ECM/XSF-CN)](mailto:Allen.XIE@etas.com) can you please prepare the backlog for the QC 8797 activity ?
>  # If HW is becoming a bottleneck, we can purchase one from ETCN to not lose much time waiting for the customer to share it. ( We need one anyways for our next PoC deliverables to QC . Whether PF does this PoC or we in ETCN manage it – doesn’t matter, we need HW anyways - [@Krishnaveni Vairavan Subramaniam (ETAS-ECM/XEO2)](mailto:Subramaniam.KrishnaveniVairavan@etas.com) we need to follow-up on this PoC activity beyond 8650 and QCPP preparations).
>
>
>
> **Reg. ISOLAR-M** 
>  # 
>  ## Relevant tooling updates are mandatory to progress with our Qualcomm Partner Program. Neusoft’s business case only emphasizes it. We can mitigate that and fast track it. [[Krishnaveni_Vairavan_Subramaniam_(ETAS-ECMXEO2)|Krishnaveni Vairavan Subramaniam (ETAS-ECM/XEO2)]] we need to follow-up. 
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  fyi

-------

> [!note]+ 2025-12-03 01:54 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> **Comments from** [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] ** 
>
> It seems we need to catch up the lead opp. where we at ETAS need to **accelerate**
>
>
>
> At CNHhub – followup
>  * SAIL run as SMP multicore (lock-step) at EL1 without EL2 SAIL hyp – answer [@Tracey Nigel (ETAS-ECM/PG ETAS/TCR-GB)](mailto:nigel.tracey@etas.com)
>  * {*}HSM / Security Needs{*}: To be check with Zhixing externally [@ZHANG Cong (ETAS-ECM/XSF-CN)](mailto:Cong.ZHANG@etas.com), [@TAN Yang (ETAS-ECM/XSF-CN)](mailto:Yang.Tan@bosch.com)
>
> At CNHhub – no risk/Next Step during December
>  * MCAL/CDD ISOLAR-M plugin: porting effort LOW for MCAL/CDD CodeGen from QAM8650P SAIL.SI.1.1 to QAM8797 SAIL.SI.2.0 as I could confirm very much compatibility of them
>  * RTA-CAR 12.9.0 BIP
>
> At PF/Hub
>  * OS port alpha: RISK [@Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)](mailto:Sathish.Madanmohan@etas.com), can York/Hub team start porting in December on manual without hardware test on hand ?
>  * Neusoft Zhixing to send ETAS 1 PCBA by begin of Jan 2026 [@TAN Yang (ETAS-ECM/XSF-CN)](mailto:Yang.Tan@bosch.com)
>
> At PF
>  * ISOLAR-M: RISK ARC-13777 [@Karthi Krishna Shekaar (MS/EMT-ETAS)](mailto:Karthi.Krishna@etas.com), can ISOLAR-M close this by end of Dec ?

-------

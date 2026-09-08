---
jira_key: ARC-9902
jira_url: "https://jira.etas-dev.com/browse/ARC-9902"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: [CEA2.0]
components: []
fix-versions: []
epic: null
parent: null
created: "2025-03-28T05:04:40.000+0000"
updated: "2026-08-28T06:31:18.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)

> [!jira] Accepted ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-08-28T06:31:18.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-9902)

> 标签：#jira/label/cea20

## 描述

**Project Milestones**  

 

**No.**
**Milestone**
**Timeline**
 

1
Start AUTOSAR Package Integration
2025.6
 

2
Start HSM Package Integration
2025.9
 

**3**
**Start AGT testing**
**2025.12**
 

**4**
**Start DV Testing**
**2026.05**
**VCTC expect production quality SW by 2026.04 for their DV testing** 

**5**
**SOP**
**2027.5**
 

 

**Currently migrating to RTA-CAR 12.6.0**

 

**Hardware & Compiler details**  :

- CDCU/LDCU/RDCU will use TC499
- Rear DCU should use TC489
- OS & HSM support for GHS and Hightec Compiler

 

**Required CP Stack and Modules for CEA 2.0 Project development**

 

**BSW Stack**
**Modules**

BASE
EcuM, BswM, StbM, Det

COM
Com, ComM, PduR, IPduM, Nm

CAN
CanIf, CanNm, CanSM, CanTP, CanSync

DIAG
Dem, Dcm, Fim, Dlt

MEM
NvM, MemIf, Fee, Ea

Safety Module
WdgM, WdgIf, E2E

LIN
LinIf, LinNM, LinTp, LinSM

Security
Idsm ,CryIf, Csm, Secoc

RTE
E2EXF, SOMEIPXF

OS
Multicore support, SC4 class , Safety level : ASIL-D

Hardware Drivers
CanTrcv, EthTrcv, LinTrcv

Tranceivers
CAN / LIN / Ethernet ( dependent on target HW )

 

**Use cases** :

- Gateway : Support Com Gateway and Diag Gateway. DOIP 2 DOIP
- AUTOSAR Tool support for MPU Configurations , OS Stack dynamic protection
- Multicore  :  Should support CAN CHANNEL 0 to CORE0/ CAN CHANNEL 1 to CORE1 / LIN Channel to CORE2 . The Cross Core communication should be possible.
- **TSN**: Support for the following
  - IEEE 802.1Qav
  - 802.1 AS
  - 802.1p VLAN TAG Priority

 

**The Security HSM basic feature on the IFX TC499**

1. Security HSM Integration
2. Secure Boot
3. Secure Flashing
4. Key Management
5. Crypto Algo
6. HSM User Application Update
7. Supplier HSM CORE Update (It can be upgraded to the highest version within the maintenance period)
8. Adapt the VW’s Bootloader solution for Secure Flashing, Secure Boot Feature.
9. TRNG/PRNG Support
10. Support for X.509 certificates
11. X.509 Certificates Securely Stored in HSMs, Support Certificates Read/Write and Parser
12. Integration Service for the HSM Configuration/ Development Base on the VW’s Security Requirement
13. HSM Knowledge Transfer
14. Zonal Controller Upgrade Support (HSM Update should be included )
15. SecOC Communication， Performance is good enough ,No Message Delay or Lost
16. Secure Storage, Write & Read From Hsm DFlash
17. Support TLS 1.3
18. Support DTLS 1.3

 

- More details and commercial aspects in the attached RFQ [CEA2.0 RFQ AUTOSAR_Purchasing_Embedded Software Development_v2.0.docx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/561758/561758_CEA2.0+RFQ+AUTOSAR_Purchasing_Embedded+Software+Development_v2.0.docx)

## 关联

- is satisfied by: [[ARC-10778 CDCU Full Ethernet Switch Software based on REALTEK 9071CP  ]]
- is satisfied by: [[ARC-10779 CryptoDriver & CycurHSM3.x shall support HW-CSP APIs for devices with Host sided acceleration capability]]
- is satisfied by: [[ARC-9904 [VW-China] TSN Support in RTA-CAR]]
- is satisfied by: [[ARC-2273 TLS1.3 Client for ISO15118-20 V2G stack]]
- is satisfied by: [[ARC-10627 LDF Importer enhancement to complete LinTpConfig ]]

## 评论

> [!note]+ 2025-10-23 08:26 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Can set the "Customer Due Date" field for the needs  ARC-12575 , ARC-12713 , ARC-13382, ARC-13172  please so it reflects the commitments against which we need to deliver?

-------

> [!note]+ 2025-10-23 06:03 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> we had F2F meeting with VW CARIAD (23/10/2025)  reg. the CEA 2.0 project feature deliverables.
>
> **VW has 2 milestones for CEA 2.0 :**
>  # End of Dec’2025 – AGT Testing
>  # End of Apr’2026 – DV testing
>
> For AGT testing, customer will freeze their SW and tooling versions of the 3{^}rd{^} party & for DV testing – customer will receive production quality SW, Tooling & HW from 3{^}rd{^} party .
>
> After lengthy discussion with customer, customer agreed to accept the following from us :
>  # RTA-CAR 12.11.0prx in December . This means,
>  # RTA-CAR 12.11.0prx Mid of Dec’2025 [ Resp : PF ]
>  # Their current project fully migrated in working order for AGT testing [ Resp : ETCN Hub ]
>  # Customer understands that the missing features ( ARC-12575 , ARC-12713 , ARC-13382, ARC-13172 ) ** wont be available in the early preview.
>
>
>  # The Missing features shall be delivered in the subsequent preview releases prior to their DV testing .
>  # Customer has agreed to take the production software : RTA-CAR 12.11.0 in May’2026. ( Even though they mentioned they need this by End of April’2026.)
>  # They may still need some updates to SW such as bug fixes based on their DV testing.
>
> We now need to deliver these features within the mentioned timeline. As you may know during our acquisition time, we agreed to VCTC to support their CEA 2.0 project needs and help them successfully deliver the project.
>
> VCTC will start the next evaluation for CEA 3.0 project in May’2026.  These features we currently support them is evolving into CEA 3.0. The customer mentioned there may be more features required (they don’t know yet) for the next architecture.
>
> This VW CEA 2.0 / 3.0 is strategically important for our global success with VW. Requesting your support in delivering the features for CEA 2.0 and help position for 3.0 acquisition phase.
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]]  fyi

-------

> [!note]+ 2025-10-12 06:37 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> The below features are important for CEA 2.0 project.
>
> **Required Features & its current status:**
>  * ARC-12713  **Transceiver drivers support for TLIN1022 ; DP83TC812S ; RTL9000BS     [ R: Nandita ]** 
>  * **Status:** Feasible only in Q2.2026
>  * For present situation, Nandita’s team has enabled CN hub with Bootstrap solution to continue with CEA 2.0 project development.
>
>
>  * ARC-12799  **CEA 2.0 BswM Multicore usecase support in RTA-CAR  [ R : Vihitha ]**
>  * **Status:** Currently targeted for RTA-CAR 12.13.0
>
>
>  * ARC-12575  **Server-Client support for TLS 1.3 (Incl. PSK feature) [ R : Sven ]**
>  * **Status:** Currently targeted for RTA-CAR 12.11.0
>
>  **Customer Milestone & expectations :**
>
>  ** {color:#de350b}Cariad's internal milestone requires completion of their basic software development by the {color}*{color:#de350b}Week-6 of 2026 (Feb’6) {color}* ( Customer communicated this information last Friday - Oct-10)
>  * Customer is currently using RTA-CAR 12.6.0. They can upgrade to higher version of RTA-CAR prior to that milestone timelines. Customer expects the above features should be available in that version of RTA-CAR.
>
> {color:#de350b}Customer expects us to provide a clear roadmap plans for the requested features and version of RTA-CAR they should upgrade, before Oct-17th{color}
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]] 

-------

> [!note]+ 2025-09-04 07:30 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]]  as discussed created the needs ticket https://jira.etas-dev.com/browse/ARC-12575 for TLS 1.3 Server support . According to VW, they need TLS1.3 support for both Client-Server. Customer expectation of their use case demo by Nov'2025 (demo by CN-Hub )
> Please contact  [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] , tech.lead for this CEA2.0 project
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]] [[Sivaramakrishna_Ayaswamy_(MSEMS-ETAS)|Sivaramakrishna Ayaswamy (MS/EMS-ETAS)]] fyi

-------

> [!note]+ 2025-09-04 04:57 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Customer Draft TLS Specification is uploaded: 0_TLS_Specification_v3.0_20250904_cn.pdf and translated version 0_TLS_Specification_v3.0_20250904_tr_en.docx.  Only interior TLS applicable feature shall be taken care of.

-------

> [!note]+ 2025-08-25 06:58 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Based on the recent discussions with customer ([^RE_ CEA2_0 TC4x9 Project Weekly Regular Meeting.msg]), I have summarized the customer's expectations from ETAS  below:
>  # {*}Training Expectations{*}:
>
>  ** Training related to MPU and MEMMAP should be provided by a local team in China for easier understanding.
>  # {*}MPU Feature Requirements{*}:
>
>  ** VW want to focus on dynamic OS stack protection during task or ISR switches (depending on ETAS OS).
>  ** Focus on dynamic memory section protection during OS application switches. customer preferred features should be configurable using the ETAS tool, without requiring additional C-code implementation from the VW side.
>  ** For TC49X, which supports 5 cores, each core must handle several OS applications with different ASIL levels. The MPU settings should be configurable dynamically based on the customer's design.
>  # {*}Memmap File Automation{*}: 
>
>  ** The MEMMAP file, strongly tied to the MPU feature, should ideally be generated automatically by the ETAS tool based on configurations.
>  ** It would be beneficial for an ETAS expert to introduce and explain whether this functionality is supported.
>  ** planning ongoing from ETCN to provide training to VW project team.
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  fyi

-------

> [!note]+ 2025-05-13 05:13 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> VCTC requires this SEC feature ARC-10779  by end of {*}August, 2025{*}.
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]  
>
> [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]]  [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]]  
>
> [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]]

-------

> [!note]+ 2025-04-21 04:19 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] VW is asking for DTLS 1.3 feature support , this is not part of the original RFQ. I have linked the https://jira.etas-dev.com/browse/ARC-1743 to this motivation for further follow-up .

-------

> [!note]+ 2025-04-13 13:32 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] For the TSN features that VW’s current needs :
>
> **Std 802.1AS – already supported in RTA-CAR** 
>
> **Std 802.1Qav – partially supported** 
>
> **Std 802.1p VLAN TAG Priority --> Ethstack Upper Layer’s supports VLAN Tag and prioritization, Eth Driver needs to also support it.** 
>
>  ** 
>
> **[@Hotz Ingo (ETAS-ECM/PRM-EMW)](mailto:Ingo.Hotz@etas.com) Business requirement for winning the CEA2.0 , we need to show VW, our roadmap plans of the unsupported TSN features  ( starting from the above-mentioned standards ). This is critical during the acquisition phase !   Nandita’s team has documented a list of supported TSN features in RTA-CAR and attached the spreadsheet in ARC-9904 !**   
>
>  ** As for TLS 1.3 – we already support many features ARC-2273  and some planned (ARC-2825) . [@HUANG Song (ETAS/CCN1)](mailto:Song.HUANG@etas.com) we need to discuss with VW to ensure what we already have in RTA-CAR meets their current needs or not ! we also have some in roadmap plans. We can align with [@Schran Sven (ETAS-ECM/XPC-Fe3)](mailto:Sven.Schran@etas.com) to get more details if needed . But we need to work with customer to build something they need !

-------

---
jira_key: ARC-14622
jira_url: "https://jira.etas-dev.com/browse/ARC-14622"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: "[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]"
reporter: "[[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-01-22T04:56:53.000+0000"
updated: "2026-09-04T00:36:23.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

## **SAFe sometime can sink a org to a process trap where doing things 'right' is more important than doing 'right' things where the right focus(what values to contribute and deliver) could become ambiguous, especially execution level are bucked without enough explore of what deliver needs at the end user.**

## **SOP timeline : M.2027** 

- **B-sample: Dec 1st 2026 (with RTA-CAR full release)**
- **A-sample: Jul 1st 2026 (feature complete)**

**Required timeline**

- **E09** RTA-CAR ESR / Release *- depends on issues to be reported and how PF to manage (goal is to save PF effort as much as possible)*
- **E11/2026 maturity needs**
  - **Xpeng ET milestone E11/2026:** **winter test**

**Business Scope** :  ETAS shall provide a RTA-CAR Multicore solution fit for XPeng ADAS ECU required Multicore use cases and performances.

**Customer** : XPeng

**XPeng's Existing experience:**

- XPeng is using ETAS RTA-CAR for others ECUs
- XPeng is using Vector DaVinci for ADAS ECU where RTA-CAR cannot satisfy XPeng ADAS ECU Multicore use cases
  - XPeng is planning to switch to IFX TC4Z9+Tasking **Tasking SmartCode 10.4r1** for ADAS
  - XPeng is planning to switch to Renesas U2B24E +GHS 2025.1.4 for another ECU

**XPeng EEA Architecture: 5.0 TSN Ring Network**

- **Topology**

           ![[ARC-14622-image-2026-07-01-22-44-31-578.png]]

- **XPU**
  - **Timeline** to deploy time sync solution:
    - Feature complete: Jun 2026 (We are delayed)
    - Bench Integration Test: Aug 2026 - time sync precision ready
    - RTA-CAR Release: E09/2026
    - Vehicle Test: E12/2026
  - Buses
    - ETH Bus: 1 TM and 1 TS
    - CAN Bus: 1 TM and multiple TS possible for XPU (TC4z9)
    - CAN: 8 channels, signal > 10K
    - SignleGW, TpGW ETH-CAN/CAN-CAN, DpIP+DoCAN, XCPoCAN+XCPoE
  - Cores: 6 cores
  - Multicore Distribution
    - Time syn capabilities - High precision (Can - 500us, ETH - 5us) time sync (the 3 use cases in SOW)
 - PF - improve ETH TSyn precision to acceptance creatira
 - Hub - support Xpeng E07/2026 integration test at Shanghai
 - timeline - E09/2026 RTA-CAR release version

- - - TSN Ring Network: 
 - *Info: ECU MCAL will support TSN CB*
 - 802.1as-2020  Multiple timeBase: (*Info by E12/2026, most features of  802.1as-2020 will be supported as PoC*.) ([ARC-16795](https://jira.etas-dev.com/browse/ARC-16795))
    - App like DDS need to mapping Vlan priority to Eth package priority
 - BSW: Vlan priority shall be able to send from SoAd->EthIF->Eth Drivers
 - I*nfo: MCAL shall support TSN QBV, SP, QAV, TSN Qbu, Qci, TSN CB*
    - Diagnostics over CAN XL (TP) ([ARC-16796](https://jira.etas-dev.com/browse/ARC-16796))
    - Multicore distribution use cases:
 - EthStack/:  EthStack + DDS will be deployed to same core
 - Interrupt Context support for transmission & reception needed for Udp/Tcp/SoAd/DoIP/XCPoE ([ARC-15161](https://jira.etas-dev.com/browse/ARC-15161))
 - SomeIp/Sd was there in the last project, but not will not be used for this new architecture incl. this project.
 - DDS is source code integrated by XPeng as CDD of SoAd uppler layer
 - no COM integration needed
 - No CodeGen needed
 - do not required RTA-CAR DDS CodeGen module
 - The SWC to use DDS interface shall be able to deploy to different cores
 - both Control FLow /Data flow - S/R interfaces
 - No Need for FFI
 - event triggered / Periodic scheduling: include both
 - Can Stack: E09/2026 - no channle split in case CPU load is OK, otherwise need to split on CAN channels to different cores
 - Data path(Transmit, Receive): core based Com MF for different channels
 - Bus Monitoring (BusOff): Yes  (CanSM MF on channels) ([ARC-16355](https://jira.etas-dev.com/browse/ARC-16355))
 - Control path: SetControllerMode: Yes (CanSM MF on channels) ([ARC-16355](https://jira.etas-dev.com/browse/ARC-16355))
 - CanTSyn: CanTSyn MF on channels ([ARC-15550](https://jira.etas-dev.com/browse/ARC-15550))
 - ComM: ComM MF on channels ([ARC-16791](https://jira.etas-dev.com/browse/ARC-16791))
 - CanIf Reception/Transmit: add vendor specific callout parameter - ETAS to hold follow up meeting with Xpeng to clarify detailed needs. ([ARC-16792](https://jira.etas-dev.com/browse/ARC-16792))
 - Partition Restart ([ARC-16794](https://jira.etas-dev.com/browse/ARC-16794)) 
 - ETAS to hold follow up meeting between PF and Xpeng to clarify detailed needs.
 - use cases
 - timeline

**Status** : contract signed

- highlights: security feature and SC4 Mixed-ASIL integration are managed out of SOW with agreed by customer

**Motivations**

- ETAS is negotiate with XPeng the feasibility to use RTA-CAR for ADAS ECU. And XPeng is interested to select RTA-CAR in case the multicore use cases as well as gPTP performances can be satisfied.
- Realizing the Mutlicore Tsyn solution will enable RTA-CAR for ALL customers for such use cases.

**Multicore Distribution Vector vs. ETAS**

- RTA-CAR 12.9.x MC Capability EN.xlsx [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] , [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]

 

RTA-CAR 12.12.0pr5 can be a stable start version for this Xpeng project with workflow fixes status in [RH-16753](https://rtahotline.etas.com/jira/projects/RH/queues/issue/RH-16753)

## 关联

- relates to: [[RTAXIP-3363 [Xpeng-bip]-cde-TC4Z9TK-1290]]
- has dependence relation with: [[RTAXIP-3448 [Xpeng-bip] Define the version of RTA-CAR to use as XPeng delivery]]

## 评论

> [!note]+ 2026-08-25 06:13 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> NETCOM **TimeServices_XPeng_CodeDrop_21.08.2026 [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]** 
>  * use case 3:
>  ** {color:#de350b}functional fail {color}(1st screenshot): time synch to after 600 years :)
>  ** {color:#de350b}precision fail  ({color}2nd screenshot): before time synch to after 600 years, EthTs-EthTM **precision FAIL**
>  * use case 1/2
>  ** not yet test
>
> ![[ARC-14622-image-2026-08-25-14-28-07-335.png]]
>
> ![[ARC-14622-image-2026-08-25-14-28-19-766.png]]

-------

> [!note]+ 2026-06-04 12:09 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> # RTA-CAR can achieve gPTP time precision - < 1us for 1 Hops
>
> Here comes a overview of testings on RTA-CAR 12.9.0 / RTA-CAR 12.12.0pr2 with target TC4z9
>  * w/o StbM/EthTSyn/CanTSyn CodeDrop 5.29 on 12.10 for ARC-14648
>  * w/o BswM CodeDrop 6.4 on 12.10 for ARC-14802
>  * w/ ARC-15299 Os port for TC4Z9 with Tasking SmartCode 10.4r1
>  * w/ workaround for ARC-15550, ARC-16355, RH-15836,  RH-15984, RH-15985, RH-15808/ARC-16282, RH-16205, RH-16157, RH-16390, RH-16411, RH-16474
>  * w/o workaround for {color:#de350b}RH-15989{color}
>
> {*}Result{*}: [rta-bip_cdes_tc4z9tasking_1290_p3_mc_cansplit_timesync_uc3_twoPort](https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000029068_PJ_ECM_Xpeng__Autosar_CP_BIP_FSQP_Contract_/01_Draft/30_Implementation/20_Software/branch/rta-bip_cdes_tc4z9tasking_1290_p3_mc_cansplit_timesync_uc3_twoPort) **rev.84419 /** [rta-bip_cdes_tc4z9tasking_12120pr2_p3](https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000029068_PJ_ECM_Xpeng__Autosar_CP_BIP_FSQP_Contract_/01_Draft/30_Implementation/20_Software/branch/rta-bip_cdes_tc4z9tasking_12120pr2_p3) **rev84813 /**  [/rta-bip_cdes_tc4z9tasking_12120pr2_p3_CodeDropTimeServices_CanSM](https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000029068_PJ_ECM_Xpeng__Autosar_CP_BIP_FSQP_Contract_/01_Draft/30_Implementation/20_Software/branch/rta-bip_cdes_tc4z9tasking_12120pr2_p3) **rev85118** / [bip_cdes_tc4z9tasking_12120pr2_p3_with_timeTuple_withWorkarounds_withoutPHC_CodeDropTimeServices_UpdatedCanTSyn_UpdatedCanSM](https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000029068_PJ_ECM_Xpeng__Autosar_CP_BIP_FSQP_Contract_/01_Draft/30_Implementation/20_Software/branch/rta-bip_cdes_tc4z9tasking_12120pr2_p3) **rev85250**
>  # Time sync over ETH precision for **Use-case 1** test
> #### **{color:#00875a}PASS ( < 1 us){color}**
>
>  # Time sync over ETH precision for **Use-case 3** test
> ### **{color:#00875a}PASS ( < 0.2 us){color}**  
>
>  * 
>  ** will test {color:#de350b}*FAILED without workaround*{color}
>  ** {color:#de350b}*need PF fix according to your analysis, especially the highlighted Defect Tickets - very important*{color}
>
>  # Time sync over CAN precision for Use-case 1/2/3 ALL test **{color:#00875a}PASS{color}**
>
> **Request: PF to detailed analysis and propose solution**
>
> *(reform the ARC/RH tickets as components for each use cases for better ref for you in case needed)*
>
> ![[ARC-14622-image-2026-07-10-19-49-56-827.png]]
>
>
>
> Details of Reported Change Requests and Defects of Use-Case 3:
>  * **RH-15984 apply also for Use case 2**
>
> ![[ARC-14622-image-2026-07-07-10-42-42-047.png]]
>
> Details of Reported Change Requests and Defects of Use-Case 1:
>  * **RH-15984 apply also for Use case 2**
>
> ![[ARC-14622-image-2026-07-09-08-26-45-371.png]]
>
>
>
> ![[ARC-14622-image-2026-07-10-20-03-01-853.png]]

-------

> [!note]+ 2026-02-26 06:36 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> added contract & sow : [^20210294_GZ XIAOPENG_SRM-GZXP-JS-20210122-00186.pdf][^20210294_GZ XIAOPENG_SRM-GZXP-JS-20210122-00186 TA_tr.docx][^20210294_GZ XIAOPENG_SRM-GZXP-JS-20210122-00186  TA.pdf]

-------

> [!note]+ 2026-02-09 06:10 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> ### **We** **successfully won the Xiaopeng** **AutoSar-CP** {*}project full-domain controller fixed point. ({*}{*}2026.02.07){*}  
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Hotz_Ingo_(ETAS-ECMPRM-EMW)|Hotz Ingo (ETAS-ECM/PRM-EMW)]] [[Sollazzo_Giuseppe_(ETAS-ECMENG-EMW)|Sollazzo Giuseppe (ETAS-ECM/ENG-EMW)]]  
>
> This is a multi-core time synchronization project targeting high-level autonomous driving. This will enhance our competitiveness in China market upon successful delivery. Despite some product gaps compared to Vector, the customer chose ETAS due to its technical expertise and commitment during the acquisition phase. {*}The customer has also requested ETAS toolchain upgrades to further close the gap with Vector{*}. With strong relationships now established, the customer has expressed willingness to pursue deeper strategic cooperation with ETAS.
>
> Thanks to all that was involved to make this acquisition possible :
>
> CN team : [[HUANG_Song_(ETASCCN1)|HUANG Song (ETAS/CCN1)]] [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]] [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
>
> and special thanks to : [[Dillmann_Vadim_(ETAS-ECMXPC-Abt1)|Dillmann Vadim (ETAS-ECM/XPC-Abt1)]] [[Pereira_Joao_(XCEVO-XPC-Brg1)|Pereira Joao (XC/EVO-XPC-Brg1)]] [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]]  for their active contribution to the  demos and solution proposal to multi-core time sync which was highly praised by the customer .
>
> Next steps : 
>  * prepare SOW ( ETCN is preparing it ) 
>  * CRs for RTA-CAR ( [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] working on it)
>  * BIP/RIP (depend on SOW discussion with customer ) project kick-off and execution 

-------

> [!note]+ 2026-02-04 12:51 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] ,
>
> This timeline is incorrect: in case we got LOI and need to start, the timeline for feature complete will likely to be by 3 months.
>
> - very likely the LOI can be within Feb 2026, therefore the feature complete need to be Q2/May-Jun 2026, Q3 will be unlikely late.
>
> ![[ARC-14622-image-2026-02-04-13-49-49-528.png]]

-------

> [!note]+ 2026-01-26 13:05 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> I have moved the need content to a need ticket (ARC-14648) and asked the NETCOM team to take a look.

-------

> [!note]+ 2026-01-23 09:57 · [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] Please help contact the appropriate owner and push this forward as soon as possible. This is our window to remove VECTOR, we must quickly take action

-------

> [!note]+ 2026-01-23 01:46 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> Invite [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]] as watcher who may also receive updated information here, however the analysis/technical proposal/timeline shall not be committed to customer before internally aligned with ECM CNHub .
>
> Invite [[Dillmann_Vadim_(ETAS-ECMXPC-Abt1)|Dillmann Vadim (ETAS-ECM/XPC-Abt1)]]  Multicore initiatives watcher.

-------

> [!note]+ 2026-01-22 08:22 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] , [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> can requirement analysis team look at the Needs

-------

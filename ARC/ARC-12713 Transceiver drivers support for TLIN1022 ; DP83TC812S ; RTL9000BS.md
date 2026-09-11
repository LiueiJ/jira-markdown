---
jira_key: ARC-12713
jira_url: "https://jira.etas-dev.com/browse/ARC-12713"
server: etas
kind: motivation
type: Need (Subtask)
status: Analyzed
priority: High
project: ARC
assignee: "[[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]"
reporter: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/cea20, jira/label/netdrv, jira/label/mcal]
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-09-16T08:58:29.000+0000"
updated: "2026-04-22T15:17:46.000+0000"
synced-at: "2026-09-10T08:07:27.706Z"
jira-orphaned: true
profile: CEA2.0 Needs
---

## 描述

Customer has requested the support for the below transceivers

TI :

- TLIN1022
- DP83TC812S

Realtek :

- RTL9000BS

**Customer Expectation** :

**beta** version before end of Oct'25 .

## 关联

- is contained in: [[RTAXIP-3209 [ETCN Customer PI Planning] Dec 2025]]
- fulfills: [[ARCREL-68 Cariad - 01]]
- is satisfied by: [[ARC-13424 [NETDRV][VW-CEA] Support for Eth Trcv  RTL9000BS - Release]]
- is satisfied by: [[ARC-15870 Transceiver drivers support for  TLIN1022 ; DP83TC812S - Custom Bundle on RTA-CAR 12.11.0]]
- is satisfied by: [[ARC-13287 [NETDRV][VW-CEA] Support for Eth Trcv  DP83TC812S - prototype]]
- is satisfied by: [[ARC-13423 [NETDRV][VW-CEA] Support for Eth Trcv  DP83TC812S - Release]]
- is satisfied by: [[ARC-15867 [NETDRV][VW-CEA] Support for LIN Trcv  TLIN1022]]
- is satisfied by: [[ARC-13288 [NETDRV][VW-CEA] Support for Eth Trcv  RTL9000BS - prototype]]

## 评论

> [!note]+ 2026-04-22 13:31 · [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]]
> Setting assignee to [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] who was previously set as the owner.
>
> This is because for need tickets, Assignee now represents the owner of the need.

-------

> [!note]+ 2026-03-03 16:15 · [[Venkatesh_Raghavendra_(MSEMS2-ETAS)_X|Venkatesh Raghavendra (MS/EMS2-ETAS) [X]]]
> [[Binder_Pascal_(ETAS-ECMXPC-Abt2)|Binder Pascal (ETAS-ECM/XPC-Abt2)]] : Could you kindly create a Capability ticket for TLIN1022 device support ?

-------

> [!note]+ 2026-02-23 10:13 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
>  ![[ARC-12713-screenshot-1.png]] 
>
> RTL9000BS not in scope
> TLIN1022 requested

-------

> [!note]+ 2026-02-04 11:44 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] as informed/discussed please connect with [[Binder_Pascal_(ETAS-ECMXPC-Abt2)|Binder Pascal (ETAS-ECM/XPC-Abt2)]] for further planning of the topic.

-------

> [!note]+ 2025-12-03 06:52 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> MoM 02.12.2026 (meeting with #[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]])
> -	We are currently working on the prototype for the DP83TC812S transceiver (ARC-13287)
> Snapshot to be available by E’Jan’26. @Venkatesh Raghavendra (MS/EBD1-ETAS) please share the snapshot with Sathish and Liu Jie when ready.
> -	In the next PI01.26, we plan to begin prototype development for the RTL9000BS (ARC-13288), subject to hardware availability, which we are still awaiting. Prototype to be available by B'Apr'26.
> -	Regarding RT8, the plan is to deliver it as an ESR on top of the RTA-CAR 12.11.0, which is tentatively expected to be available by the end of May. 
> In the meantime, as originally planned for PI 26.02, the NET DRV team will bring forward the two RT8-related activities into the early sprints of the PI (ARC-13423 and ARC-13424). 
> This will allow us to provide an RT8-ready finalized snapshot by 29th May 2026. 
> COEM integration can then take this snapshot on the RTA-CAR 12.11.0, integrate it, and deliver it to the customer. R: [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
>
> By parallelizing the work, we can gain time within PI 26.02 and meet the expected timelines. This is the approach we have aligned on.

-------

> [!note]+ 2025-10-23 08:04 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Feedback from [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] : 
>
> Customer has agreed to provide us a development board. I have told them we need it latest by Mid- November. They are going to follow-up with their HW team .  
> ----
> As discussed we will proceed with prototype development for Eth Trcv DP83TC812S for PI25.04 (ARC-13287), with a plan that HW will be available by November for functional testing.
>
> Please note that once the dev board will be available at CN hub, we would need support from your end to establish the project stand and HW setup.
>
> The Trcv needs to be integrated into the project and remote setup made available for testing.

-------

> [!note]+ 2025-10-16 15:00 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> Following the PI planning, we could accommodate a prototype (ARC-13287) for only one transceiver in PI25,04, while the other transceiver prototype (ARC-13288 ) would be addressed in the subsequent PI.
>
> A prototype (Add-on, not integrated into RTA-CAR) will include a functional transceiver with basic validations, subject to hardware availability.
>
> To align with our proposed schedule, we would need the hardware to be available by mid-Nov'26
>
> Currently, we have planned for the DP83TC812 in PI25.04. Please confirm which hardware can be made available on priority so that the same can be worked on in 25.04 accordingly.

-------

> [!note]+ 2025-10-15 05:24 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> following up on Nandita's queries. details here :  [^RE_ *HIGH RISK* RE_ CEA2_0 TC4x9 Project Weekly Regular Meeting ----  Transceiver request.msg]

-------

> [!note]+ 2025-10-13 10:48 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  For prototyping, we would need the HW setup (transceivers) for SW driver testing.
>
> Do you have any timelines on the HW availability? Would this be supported by the CN hub?

-------

> [!note]+ 2025-09-29 06:48 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> this is critical for VW CEA 2.0 project and we need this production ready trcvs in RTA-CAR 12.10.0.  
>
> [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] fyi 

-------

> [!note]+ 2025-09-26 01:48 · [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]]
> [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]]  Thanks very much for your more information to support us.
>
> Have a nice day.
>
> Allen

-------

> [!note]+ 2025-09-25 10:42 · [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]]
> For further clarification, please reach out to my team Agile Master [[Varsha_Srinivasan_(MSEMS2-ETAS)_X|Varsha Srinivasan (MS/EMS2-ETAS) [X]]] 

-------

> [!note]+ 2025-09-25 10:41 · [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]]
> Corresponding Bootstrap setting with the following image name 
>
> DP83TC_BootStrapSetting1.jiff
>
> DP83TC_BootStrapSetting2.png
>
> DP83TC_BootStrapSetting3.png
>
> DP83TC_BootStrapSetting4.png
>
> DP83TC_BootStrapSetting5.png
>
> DP83TC_BootStrapSetting6.png
>
> DP83TC_BootStrapSetting7.jiff
>
> DP83TC_BootStrapSetting8.png

-------

> [!note]+ 2025-09-25 10:38 · [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]]
> [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]], Please find the comparison report for DP83TC812S-Q1 vs DP83TC817S-Q1 as attached.
>
> [^DP83TC_Comprehensive_Register_Documents_Analysis.pdf]
>
> ^*+_Disclaimer:_+* The reports are generated via GitHub Copilot, 100% accuracy is not guaranteed.^   

-------

> [!note]+ 2025-09-25 10:30 · [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]]
> Corresponding Bootstrap details
>
> ![[ARC-12713-RTL9000BS_BootstrapSetting1.png]] ![[ARC-12713-RTL9000BS_BootstrapSetting2.png]]

-------

> [!note]+ 2025-09-25 10:29 · [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]]
> [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]] , Please find the comparison report for RTL9000AA vs RTL9000BS as attached
>
> [^RTL9000_Comprehensive_Analysis_20250924_185052.pdf][^RTL9000_Enhanced_Register_Analysis_20250924_175725.pdf]
>
> **+_Disclaimer:_+** The reports are generated via GitHub Copilot, 100% accuracy is not guaranteed. 

-------

> [!note]+ 2025-09-25 02:18 · [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]]
> [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]] 
>
> Thanks very much for your fast sharing the code. 
>
> Best regards,
>
> Allen

-------

> [!note]+ 2025-09-24 11:58 · [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]]
> [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]] : I have attached  [^EthTrcv_11_StdAutomPhy.zip] prototype code for DP83TC817SVRHARQ 
>
> I will share the comparison report and boot strap setting details at the earliest.
>
> Regards
>
> Vijay Shekar

-------

> [!note]+ 2025-09-24 03:07 · [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  [[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]] Could you please support to provide the prototype for DP83TC817SVRHARQ as soon as possible. Thanks
>
> The local team resources are available, they need your input to start immediately.
>
> Best regards,
>
> Allen

-------

> [!note]+ 2025-09-22 08:42 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> As discussed, in the meantime, to unblock the customer, we could suggest them some alternate mechanisms (Boot strapping)
>
> Our Eth Technical expert ([[Vijay_Shekar_H_S_(MSEMS2-ETAS)|Vijay Shekar H S (MS/EMS2-ETAS)]] ) will provide the bootstrapping details with [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]] 
>  * TLIN1022 (Available in RTA-CAR TLIN1021)
>  * DP83TC812S
>  ** No comparable device available in RTA-CAR as of date.
>  ** PF dev team have a prototype available for DP83TC817SVRHARQ. This could be used as reference by China hub.
>  * RTL9000BS (Available in RTA-CAR  - RTL9000AA)
>  ** RTL9000AA Supports RGMII / RMII interfacing, while RTL9000BS supports SGMII.
>
> Next steps:
>
> [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]]  will share the plan to customer and discuss the possible options. Feedback will be provided to PF team soon.

-------

> [!note]+ 2025-09-22 03:13 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> As discussed I understand that none of the transceiver drivers are available with the respective silicon vendor, and thus in house development was requested.
>
> The  estimates for the transceiver development are approximately as follows:
>  * TLIN1022 = ~2.5 months
>  * DP83TC812S = ~3 months
>  * RTL9000BS = ~3 months
>
> This covers only basic functionality to enable Ethernet communication over Trcv, if additional features such as sleep/wake, cable diagnostics etc. are needed, we could discuss further.
>
> We could offer them an incremental delivery approach, with an early prototype followed by release.
>
> The main challenge we face is that the NetDrivers team in PF fully allocated, with the backlog booked through Q1 2026 (including high-priority and critical requests)
> Given this situation, it will be very difficult to start earlier.
>
> I also understand that a Q2'26 start would not be acceptable for the customer. 
> Therefore, I suggest we have a discussion to align on feasible timelines and define what we can propose to the customer, while keeping them actively engaged.

-------

> [!note]+ 2025-09-16 09:09 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  VW has come back and insisted that ETAS provide support for the above mentioned Transceivers. They require Beta version by end of Oct'25.  Is there any feasibility to provide support in that timeline ? can you please provide me with a realistic roadmap plans before Friday ? We have a weekly meeting and we need to communicate our side plans. thanks 
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] fyi

-------

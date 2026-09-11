---
jira_key: ARC-17378
jira_url: "https://jira.etas-dev.com/browse/ARC-17378"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]"
reporter: "[[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-08-19T01:43:45.000+0000"
updated: "2026-09-10T15:50:38.000+0000"
synced-at: "2026-09-11T01:13:09.700Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

Here is requirement from Keboda,

MCU: Renesas RCAR U5L2,RH850/U2A

RTA-CAR V12.12.0 or later.

whether RTA-CAR could support BMW eth nPDU Communication or not?

If no, what’s the plan?

Please share any information, thank you.

## 评论

> [!note]+ 2026-09-10 15:50 · [[Pianta_Nicola_(ETAS-ECMXPC-Yok2)|Pianta Nicola (ETAS-ECM/XPC-Yok2)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]], noted. 

-------

> [!note]+ 2026-09-08 11:37 · [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] please be aware that [[Pianta_Nicola_(ETAS-ECMXPC-Yok2)|Pianta Nicola (ETAS-ECM/XPC-Yok2)]] is now responsible for the AAA team. [[Pianta_Nicola_(ETAS-ECMXPC-Yok2)|Pianta Nicola (ETAS-ECM/XPC-Yok2)]] please can you check Nandita's request below.

-------

> [!note]+ 2026-09-08 09:51 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] Thanks for sharing.
> Could you kindly create a NEED.
> [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] As we are currently tight on bandwidth, I would like to request support from AAA team for the specification evaluation.
> [[Dillmann_Vadim_(ETAS-ECMXPC-Abt1)|Dillmann Vadim (ETAS-ECM/XPC-Abt1)]] FYI

-------

> [!note]+ 2026-09-08 09:10 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 
>
> please support to create Need as Nandita requirement, thank you.

-------

> [!note]+ 2026-09-08 09:09 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] 
>
> Please find the Spec by this link: [EES30_LH 11668200_nPDU Communication.pdf](https://bosch-my.sharepoint.com/:b:/r/personal/rew1sgh_bosch_com/Documents/03_Customer/46_Keboda/EES30_LH%2011668200_nPDU%20Communication.pdf?d=wa69327d6f32b401983e0c16f72258509&csf=1&web=1&e=YOauJm)
>
> Customer requires ETAS that "Do not disclose the document to any third party."

-------

> [!note]+ 2026-08-20 05:39 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
>
>  ![[ARC-17378-screenshot-1.png]] 
>
> Based on the available architecture in our Comm.stack, support for BMW Ethernet nPDU communication appears technically feasible. 
> The AUTOSAR SoAd already provides container-based communication concept that could be used to map the CAN messages to Ethernet PDUs via Header IDs and PduR routing. 
>
> However, the internal processing of the nPDU Manager is currently unknown. 
> Without understanding whether it performs only some kind of mapping or additional BMW-specific functionality, any assessment remains speculative. 
>
> It would therefore be beneficial to obtain the technical specification of the nPDU Manager to accurately assess the required functions and corresponding effort.
>
> Kindly create a Need accordingly. 
>
> Thanks!

-------

> [!note]+ 2026-08-19 08:38 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  do we have nPDU Comm support in our Eth stack?  If Yes, Are there any gaps? If NO, do we have any plans in the pipeline?  Thanks 

-------

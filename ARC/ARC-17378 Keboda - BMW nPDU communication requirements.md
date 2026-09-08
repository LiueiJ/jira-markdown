---
jira_key: ARC-17378
jira_url: "https://jira.etas-dev.com/browse/ARC-17378"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: npr5kor
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-19T01:43:45.000+0000"
updated: "2026-08-20T05:39:01.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-17378 Keboda - BMW nPDU communication requirements

> [!jira] New ·  · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] · 更新于 2026-08-20T05:39:01.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-17378)

## 描述

Here is requirement from Keboda,

MCU: Renesas RCAR U5L2,RH850/U2A

RTA-CAR V12.12.0 or later.

whether RTA-CAR could support BMW eth nPDU Communication or not?

If no, what’s the plan?

Please share any information, thank you.

## 评论

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

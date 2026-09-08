---
jira_key: ARC-17468
jira_url: "https://jira.etas-dev.com/browse/ARC-17468"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: wea2bo
reporter: tst1sgh
tags: [CycurHSM]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-01T14:20:27.000+0000"
updated: "2026-09-04T11:57:03.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-17468 [VCTC_Security] Immobilizer Requirements on CEA2.0&CEA1.X

> [!jira] New ·  · [[Wegmann_Alexander_(ETAS-ECMXPC-Bo)|Wegmann Alexander (ETAS-ECM/XPC-Bo)]] · 更新于 2026-09-04T11:57:03.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-17468)

> 标签：#jira/label/cycurhsm

## 描述

This is a Immobilizer security CycurHSM solution opportunity from VCTC. it will be used on their CEA2.0 first and latter on CEA1.x Platform vehicle. For detail technical requirement you can see the attachment document. the following ECU will be influenced:

- CEA2.0:
- Engine Control Unit (ECM), Inverter, Front-Inverter, CCU, LZCU, RZCU,TZCU, NGX/FLC(ADAS)
- All ECU already have HSM HW support.
- CEA1.X
- Engine Control Unit (ECM), Transmission Control Unit(TCM), CDCU, LDCU, RDCU, NGX/FLC(ADAS)
- All ECU already have HSM HW support.
- FOR Detail ECU supplier and Detail HW information will be update latter.

Milestone:

- CycurHSM Dev package to support CEA2.0 project application need be ready by end of December,2026.  VCTC need finish the integration on ECU by March,2027.
- First vehicle with Immobilizer function VTA start Planned in CW32/2027.

## 评论

> [!note]+ 2026-09-04 11:56 · [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]
> Added U2A as required HW. Also CycurHSM-SDK needs to be supported

-------

> [!note]+ 2026-09-04 11:50 · [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]
> Hi [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] ,
>
> we have looked at the attached documents. They aren't clear specifications. This means we need to discuss the final solution with VCTC.
>
> 1) If VCTC accepts our 1. concept proposal in general => price of 150k€ for the implementation is ok. 
>
> 2) Concept must be agreed on before mid of October, if we have an agreement and it isn't more complex than our first proposal/doesn't need more time, than we can provide an Alpha release by end of December 2026.  And QM Release in April 2026

-------

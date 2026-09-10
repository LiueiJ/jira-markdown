---
jira_key: ARC-13738
jira_url: "https://jira.etas-dev.com/browse/ARC-13738"
server: etas
kind: motivation
type: Need (Subtask)
status: Analyzed
priority: High
project: ARC
assignee: "[[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]"
reporter: "[[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/cea20, jira/label/diag]
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-11-27T06:32:50.000+0000"
updated: "2026-02-24T07:25:01.000+0000"
synced-at: "2026-09-10T08:07:27.706Z"
jira-orphaned: false
profile: CEA2.0 Needs
---

## 描述

**Use Case:** Customer needs to implement RoutineService with RequestRoutineResults operation in APP SWC which also needs to pass in parameter.

**Current Situation:** On RTA-CAR 12.6.0, '**DcmDspRequestRoutineResultsIn**' and items under it are not configurable due to the upper multiplicity of those parameters are all 0;  **DcmRbDspRequestRoutineResultsIn** exists but has conflict with **DcmDspRoutineUsePort** setting as true; And from R20-11, we found AUTOSAR Specification of DCM already supports **DcmDspRequestRoutineResultsIn.**

**Needs:** Support DcmDspRequestRoutineResultsIn in ClientServerInterface RoutineServices as AUTOSAR Standard

## 关联

- is contained in: [[RTAXIP-3209 [ETCN Customer PI Planning] Dec 2025]]
- is satisfied by: [[ARC-5305 [ACF][Diag] Supporting of parameters in request message of DiagnosticRequestRoutineResults ]]

## 评论

> [!note]+ 2026-02-10 05:10 · [[Allen_Jacob_(ETAS-ECMXPC-Yok2)|Allen Jacob (ETAS-ECM/XPC-Yok2)]]
> [CarAut_3]
>
>  ARC-5305 has been linked to this Capability while this ticket was in Detailed or later state.
>
> This addition was triggered by Jain Vihitha (MS/EBD-ETAS).
>
> [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]

-------

> [!note]+ 2025-12-10 23:12 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Hello, [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]], do we have the plan to analyze this need?

-------

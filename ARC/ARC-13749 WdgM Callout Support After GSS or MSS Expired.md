---
jira_key: ARC-13749
jira_url: "https://jira.etas-dev.com/browse/ARC-13749"
server: etas
kind: motivation
type: Need (Subtask)
status: Analyzed
priority: Medium
project: ARC
assignee: vih4kor
reporter: aiu2sgh
tags: [CEA2.0, SysLib]
components: []
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-11-28T08:55:48.000+0000"
updated: "2026-02-24T07:25:00.000+0000"
synced-at: "2026-09-08T01:46:40.034Z"
jira-orphaned: false
profile: CEA2.0 Needs
---

# ARC-13749 WdgM Callout Support After GSS or MSS Expired

> [!jira] Analyzed · Medium · [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] · 更新于 2026-02-24T07:25:00.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13749)

> 标签：#jira/label/cea20 #jira/label/syslib

## 描述

**Use Case:** 

Customer requires to log the context information after WdgM supervised status expired on the same ECU partition of fault.

**Current Situation:** 

Expired status of WdgM Master can only be notified by mode switch or polled by CS interface by APP but only FirstExpiredSEID and FirstExpiredMainFunctID can be accessed instead of the whole debugger variable WdgM_Rb_FirstExpiredEntityInfo_stPtr; On satellite side, only WdgM_Rb_ErrorHandler_Callout_SatPlus_Satellite_<Partition> callout exists but the timing is too late for logging expired information.

**Needs:** 

Prefer to have CallOut on GSS reaching state EXPIRED instead of the notification over RTE or calling WdgM_GetGlobalStatus in a process scheduled immediately after WdgM_MainFunction as this would be simple (no additional process development with WdgM header inclusion), less complicated (compared to notification via RTE) and avoids any delay (as there might be delay in executing the runnable based on RTE notification).

It is similar to Callout provided based on MSS in the Satellite_plus, thereby it will be consistent.

## 关联

- is contained in: [[RTAXIP-3209 [ETCN Customer PI Planning] Dec 2025]]
- is satisfied by: [[ARC-14950 [WdgM] Callout to log the context information after GSS/MSS expiry]]

## 评论

> [!note]+ 2026-02-23 09:24 · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Kanti Sirkar Mrinal (MS/EMT4-ETAS)]]
> Hi [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]],
>
> This new requirement is feasible and can be implemented. Below are my analysis points:
>  # It is a non-AUTOSAR requirement, and this Callout should be user-configurable, with the default setting being disabled.
>  # Upon GSS expiry, the GSS-Expired-Callout should be included in the Master MainFunction.
>  # Upon MSS expiry, the MSS-Expired-Callout should be integrated into the Satellite-Plus/Lite-Master MainFunction.

-------

> [!note]+ 2025-12-10 23:12 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Hello, [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]], do we have the plan to analyze this need?

-------

> [!note]+ 2025-12-02 11:28 · [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]]
> Initial discussions and analysis attached [^RE Customer WdgM Use Case Support on RTA-CAR 12.6.0.msg]

-------

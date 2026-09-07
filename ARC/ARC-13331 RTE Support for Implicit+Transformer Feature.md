---
jira_key: ARC-13331
jira_url: "https://jira.etas-dev.com/browse/ARC-13331"
server: etas
kind: motivation
type: Need (Subtask)
status: Satisfied
priority: Urgent
project: ARC
assignee: aiu2sgh
reporter: mas1yok
tags: [CEA2.0]
components: []
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-10-14T00:51:21.000+0000"
updated: "2026-05-06T17:13:45.000+0000"
synced-at: "2026-09-07T09:18:38.885Z"
jira-orphaned: false
---

# ARC-13331 RTE Support for Implicit+Transformer Feature

> [!jira] Satisfied · Urgent · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] · 更新于 2026-05-06T17:13:45.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13331)

> 标签：#jira/label/cea20

## 描述

**Problem** :

The RTE currently fails to support a critical configuration in customer project. VW's software architecture relies on implicit access for SR (Sender-Receiver) ports handling SomeIP comms. However, the RTE does not support the feature that combines Implicit Access Points with Transformer functionality (Implicit+Transformer). This limitation causes incompatibility and hinders proper communication and data flow between the SWCs and SomeIP signals.

**Requirement** : 

RTE support for the Implicit Transformer feature to address the limitations and fulfill customer project requirements.

**Context**:

The issue was addressed in the past via SomeIpXfAdp solution in the older RTA-CAR 9.1 (which was used by Xpeng in their project and Cariad since CEA 1.0. Customer's project depends on Implicit access )

**Impact**:

Customer's is deeply unsatisfied that an existing critical functionality from RTA-CAR 9.1 has been removed in RTA-CAR 12.6.0 and claim that feature is an integral part of their solution. Citing this issue, they raise concerns about future project migrations. 

 

**Experts to consult on this issue  :**

[[Kaiser_Marc_(ETAS-ECMESY3)|Kaiser Marc (ETAS-ECM/ESY3)]] 

[[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] 

[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] 

[[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]

## 关联

- is contained in: [[RTAXIP-3209 [ETCN Customer PI Planning] Dec 2025]]
- is satisfied by: [[ARC-13382 Support for Inter-Ecu Implicit S/R with Transformers via LDCOM]]

## 评论

> [!note]+ 2026-05-06 17:13 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] we think this is done in RTA-RTE 12.10.0, please shout if you disagree! Thanks

-------

> [!note]+ 2026-04-22 13:31 · [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]]
> Setting assignee to [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] who was previously set as the owner.
>
> This is because for need tickets, Assignee now represents the owner of the need.

-------

> [!note]+ 2025-10-15 09:01 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> Following discussion with [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]], this Need is for LdCom, reception only.
>
> We may support Tx and Rx for completeness, but the Need is strictly only this.

-------

> [!note]+ 2025-10-14 14:40 · [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]]
> hi [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]],
> the capability(ARC-13354) and it's ACF is created. 
>
> [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] this seems to be an urgent request for VW project. Could you please prioritize the capability. 
>
> PS: The feature was aligned with [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Tchouante Auges (ETAS-ECM/XPC-Abt1)]]. 

-------

> [!note]+ 2025-10-14 01:10 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] This is  a critical  issue for VW CEA2.0 project. Customer expect this solution (at least a preview ) before end of December'2025 .  we plan to  manage the issue with cobra scripts until a proper solution.  kindly support . 
>
> [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] [[Kaiser_Marc_(ETAS-ECMESY3)|Kaiser Marc (ETAS-ECM/ESY3)]]  is aware of the problem and the required solution to address the issue.
>
> [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Duong Thi Ngoc (ETAS-ECM/XPC-Yok1)]] [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Tchouante Auges (ETAS-ECM/XPC-Abt1)]] [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]] [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] [[Kaiser_Marc_(ETAS-ECMESY3)|Kaiser Marc (ETAS-ECM/ESY3)]] 

-------

---
jira_key: ARC-10779
jira_url: "https://jira.etas-dev.com/browse/ARC-10779"
server: etas
kind: motivation
type: Need (Subtask)
status: Analyzed
priority: High
project: ARC
assignee: tan9sgh
reporter: tst1sgh
tags: [CEA2.0, Cap_Used_PIP26.1_SEC_Prep, CycurHSM3.x, PIP26.1_SEC_Prep, SEC, SEC-SecServices]
components: []
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-05-09T05:23:20.000+0000"
updated: "2026-07-01T15:29:51.000+0000"
synced-at: "2026-09-07T09:18:38.885Z"
jira-orphaned: false
---

# ARC-10779 CryptoDriver & CycurHSM3.x shall support HW-CSP APIs for devices with Host sided acceleration capability

> [!jira] Analyzed · High · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] · 更新于 2026-07-01T15:29:51.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-10779)

> 标签：#jira/label/cea20 #jira/label/cap_used_pip261_sec_prep #jira/label/cycurhsm3x #jira/label/pip261_sec_prep #jira/label/sec #jira/label/sec-secservices

## 描述

CycurHSM 3.x Support VCTC CEA2.0 TC499/TC489 will have the CSP function supported APIs. Which need the RTA-CAR 12.11 Crypto Driver to support this CycurHSM3.x CSP API.

VCTC will need this feature ready by end of **December, 2025**.

The following is the Example use case for the CSP and HSM Core:

![[ARC-10779-image-2025-05-09-13-19-52-581.png]]   

Currently, the Crypto Driver Plug-In package delivered to VCTC project team find the HSM key could not be load to HSM RAM problem.  **It is a bug of CryptoDriver**.  Based on the analysis of cryptoDrv code, the key slot ID doesn’t be as input for CSAI, just the internal variable as key handle from CryptoDrv, so this internal variable shall be initialized in CryptoDrv level.  **for detail you can contact Lukas or Yingge**. this need to be solved in next **QA release end of March,2026**.

## 关联

- is contained in: [[RTAXIP-3209 [ETCN Customer PI Planning] Dec 2025]]
- depends on: [[ARC-12437 CycurHSM3 shall support CSS]]
- satisfies: [[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]
- is satisfied by: [[ARC-12438 [CryptoAuHSM3] Support of HW-CSP in rba_CryptoAuHSM3 crypto driver]]

## 评论

> [!note]+ 2026-05-11 20:45 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] looks like this was done, can this Need be closed?

-------

> [!note]+ 2026-04-22 13:31 · [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]]
> Setting assignee to [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] who was previously set as the owner.
>
> This is because for need tickets, Assignee now represents the owner of the need.

-------

> [!note]+ 2026-01-20 07:57 · [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]]
> Add the Crypto driver bug, which cause HSM key load to RAM failed. which need to be fixed in the next QA release by end of March, 2026.

-------

> [!note]+ 2025-08-14 12:24 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> based on CycurHSM3 planning the Customer Due Date is moved from E07/2025 to E2025.

-------

> [!note]+ 2025-07-02 12:25 · [[Pandit_Rohan_(ETAS-ECMXPC-Fe3)|Pandit Rohan (ETAS-ECM/XPC-Fe3)]]
> Currently concept work for HW-CSP(Hardware Crypto Service Provider) is in progress and expected to be completed by CW28/2025.
>
> [[Pala_Diego_(ETAS-ECMXPC-Bo)_X|Pala Diego (ETAS-ECM/XPC-Bo) [X]]] will invite the cryptodriver team members to share the new concept and the APIs for HW-CSP in upcoming weeks.

-------

> [!note]+ 2025-07-01 15:13 · [[Pandit_Rohan_(ETAS-ECMXPC-Fe3)|Pandit Rohan (ETAS-ECM/XPC-Fe3)]]
> Updated in [2025+06+24+-+PSC+Meeting+Protocol](https://confluence.etas-dev.com/spaces/RTAC/pages/564538311/2025+06+24+-+PSC+Meeting+Protocol)
>
> **Customer Milestone request E08/2025 for first alpha w/o CSS**
>
> **CryptoDriver needs to support CSS on TC4x**
>
> **Use Cases: Secure Boot** 
>
> **SecOC (needs RTA-SEC)**
>  * have to be aligned with CycurHSM3 development
>  * current status on CycurHSM3 development - generic Alpha version to **support TC4x** might be feasible
>
> Feature (CSS) supported is possible to support **earliest E2025**

-------

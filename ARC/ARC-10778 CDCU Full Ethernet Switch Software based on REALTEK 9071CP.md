---
jira_key: ARC-10778
jira_url: "https://jira.etas-dev.com/browse/ARC-10778"
server: etas
kind: motivation
type: Need (Subtask)
status: New
priority: Low
project: ARC
assignee: tst1sgh
reporter: tst1sgh
tags: [CEA2.0]
components: []
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-05-09T05:08:51.000+0000"
updated: "2026-05-11T20:54:39.000+0000"
synced-at: "2026-09-07T09:18:38.885Z"
jira-orphaned: false
---

# ARC-10778 CDCU Full Ethernet Switch Software based on REALTEK 9071CP

> [!jira] New · Low · [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] · 更新于 2026-05-11T20:54:39.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-10778)

> 标签：#jira/label/cea20

## 描述

Security Full Ethernet Switch Software Solution is needed for the CAE2.0 platform CDCU . which need to be  based on REALTEK 9071CP Chip. The following is the function required:

1, CycurGATE and routing engine Integrated with 9071CP HW accelerator.

2, RTA-OS

3, IDS-M

4, Diagnostic stack with TCP/IP

5, TSN/gPTP

6, ISOLAR configuration tool for RTA-CAR + ONS Use-Cases

7, MACsec（Optional）

the project schedule will follow the CEA2.0 platform schedule.

 

Currently we plan to promote the opportunity in the following steps:

1, We need the project scope and schedule confirmation and price information feedback to customer for budget preparation.    by **5/12/2025** 

2,  WE need prepare the project proposal and communication with VCTC for the technical detail clarification, and roughly performance evaluation. which will support the customer to make the RFQ be prepared.  by **6/15/2025**

3, the RFQ will be released and prepare the project bidding.  TBD

## 关联

- relates to: [[ARC-8550 [COM] PoC for AR switch firmware for Realtek]]
- satisfies: [[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]

## 评论

> [!note]+ 2026-05-11 20:54 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] this looks a bit suspect, deadline looming but no clear actions from us, and as [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] suggests this would be with Switch Team so could be lost in any transfer or responsibility.

-------

> [!note]+ 2026-04-22 13:31 · [[Lay_Nick_(ETAS-ECMXPC-Yok1)|Lay Nick (ETAS-ECM/XPC-Yok1)]]
> Setting assignee to [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] who was previously set as the owner.
>
> This is because for need tickets, Assignee now represents the owner of the need.

-------

> [!note]+ 2025-05-22 04:39 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> ARC-8550  pertains to collaborative work at the ComStack level with switch vendors Realtek and Broadcom. It focuses on a proof of concept (POC) to enable an AUTOSAR communication stack on Ethernet switches.
>
> While it is related to the current ticket, it does not directly analyze or address it. There may be some overlaps or overarching themes.
>
> This Need ticket represents a broader scope, aiming at a complete end-to-end switch solution led by the ONS team.

-------

> [!note]+ 2025-05-21 09:58 · [[Allen_Jacob_(ETAS-ECMXPC-Yok2)|Allen Jacob (ETAS-ECM/XPC-Yok2)]]
> From ARC-8550:
> {quote}Hi [[Allen_Jacob_(ETAS-ECMXPC-Yok2)|Allen Jacob (ETAS-ECM/XPC-Yok2)]] ,
>
> the features mentioned in ARC-10778 are different and not in scope in this enabler fragment.
>
> That means, this work here does not support on the analysis of [https://jira.etas-dev.com/browse/ARC-10778].
> {quote}

-------

> [!note]+ 2025-05-19 14:34 · [[Allen_Jacob_(ETAS-ECMXPC-Yok2)|Allen Jacob (ETAS-ECM/XPC-Yok2)]]
> *RTA-CAR Needs Grooming*
>
> [[Shukla_Siddharth_(ETAS-ECMXPC-Fe1)_X|Shukla Siddharth (ETAS-ECM/XPC-Fe1) [X]]] where is this work being analysed?

-------

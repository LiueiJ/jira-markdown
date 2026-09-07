---
jira_key: ARC-6719
jira_url: "https://jira.etas-dev.com/browse/ARC-6719"
server: etas
kind: motivation
type: Motivation
status: Done
priority: ""
project: ARC
assignee: ""
reporter: ec82abt
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2024-09-09T09:20:44.000+0000"
updated: "2025-06-20T13:55:11.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-6719 GWM project

> [!jira] Done ·  ·  · 更新于 2025-06-20T13:55:11.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-6719)

## 描述

The customer project is using RTA-CAR 9.2.x and try to use CycurHSM3 with it. On top of CycurHSM3 the customer needs as well the Crypto Driver for CycurHSM3 (CryptoAuHSM3), but RTA-CAR 9.2.x don't support this CryptoDriver as it is the old generation with many architecturalrestrictions.

Requested Delivery Date: M09/2024

## 评论

> [!note]+ 2025-06-20 13:55 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] What have be Done for this Motivation? We have not delivered what was requested, right? Then I guess the correct status would be **Canceled** and Opportunity Lifecycle state is {*}Lost{*}?

-------

> [!note]+ 2024-09-09 09:52 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> There is no CycurHSM3 driver available in RTA-CAR 12.x, yet. The CSAI between CycurHSM2 and CycurHSM3 is different, otherwise we could also use one driver for both. The CN Hub can try it out, but we can neither support nor recommend anything here as we never spend any minute in such kind of analysis. The only hint we can give is that it will be significant effort as there were a lot of changes during the last 3 years (incl. a generation switch).

-------

> [!note]+ 2024-09-09 09:40 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] what is the possibility of the CN hub being able to support this customer request with some sort of "Frankenstein" solution e.g. by generating the HSM3 driver from a RTA-CAR 12.x release and then integrating that code with the CryIf code coming from RTA-CAR 9.x. I would expect that the CryptoDriver part of the interface would be very similar between the HSM2 and HSM3 drivers right?

-------

> [!note]+ 2024-09-09 09:27 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] Can you please review the information and correct it in case something is wrong. Please update as well the concrete project name in the Summary.

-------

> [!note]+ 2024-09-09 09:26 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> Requested Delivery Date for CryptoDriver is not feasible as the development plan is to have it for RTA-CAR 12.x in maturity for RA in 12/2024.

-------

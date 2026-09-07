---
jira_key: ARC-15294
jira_url: "https://jira.etas-dev.com/browse/ARC-15294"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-12T07:11:03.000+0000"
updated: "2026-09-03T15:39:14.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-15294  VCTC : VW-CARIAD CEA 3.0

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-03T15:39:14.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-15294)

## 描述

Currently in preparation for Project Acquisition :

A new proposal was raised by **Frank Han from CARIAD China CEO** for **VW CEA 3.0** arch.

 

he proposed architecture is a **mixed multi-core MCU deployment of AUTOSAR and Zephyr**.

- **AUTOSAR Classic** is used for the **static, deterministic, and safety-/real-time-critical functions**.
- **Zephyr** is used for the **dynamic POSIX-like functions**, for some dynamic features(**VW said that they need dynamic in MCU**), and other non-safety-critical service functions.
- The recommended implementation is **domain separation by core**:
- one or more cores running AUTOSAR
- one or more cores running Zephyr

- Communication between the two domains is handled through **well-defined IPC mechanisms**, such as shared memory, mailbox, or message-based interfaces.

This approach makes it possible to combine:

- **static configurability and determinism**
- with **limited dynamic software capability**

 

The current question inside **ETAS** is not mainly whether the architecture is technically feasible, but rather:

**Which internal organization should take ownership of this demand?**

Should it be handled by the **ECM organization**, or by the **open-source project team SCORE**?

 

It is an AUTOSAR-based embedded control platform **extension Zephyr open source**  for VW CEA 3.0 programs.

## 关联

- is refined by: [[ARCANA-1299 Support for CARIAD POC for the Zonal control unit]]

## 评论

> [!note]+ 2026-07-30 03:56 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [^Volkswagen CEA 3.0 POC  Scope and SOW Preparation.msg]
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  we will be starting the CEA 3. 0 POC very soon. 
>
> **Summary of the** **ETAS Deliverables for this POC**
>  * Provide a standard Infineon TC499 BIP (Basic Integration Platform). 
>  * No Volkswagen-specific customization is required.
>  * No porting to a Volkswagen hardware board is required. 
>  * No bootloader implementation is required.
>  * No Volkswagen DBC or ARXML file integration is required. 
>  * The BIP only needs to demonstrate CAN and Ethernet communication on the standard Infineon TC499 demo board using ETAS's own demo DBC configuration. 
>
> **Responsibilities of IAV**
>  * After delivery of the BIP, IAV will take ownership of Zephyr OS modifications and ZAL layer adaptations. ETAS is not expected to participate in these software modification activities.
>
> This is an important activity we will do to position ourselves for CEA 3.0 acquisition phase. 
>
> [[HUANG_Song_(ETASCCN1)|HUANG Song (ETAS/CCN1)]] [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] [[Wendel_Kim_Julian_(ETASCVW)|Wendel Kim Julian (ETAS/CVW)]] [[Hotz_Ingo_(ETAS-ECMPRM-EMW)|Hotz Ingo (ETAS-ECM/PRM-EMW)]]  fyi

-------

> [!note]+ 2026-07-27 05:53 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Latest updates from ETCN sales - CARIAD meeting minutes : [^0715-meeting with CEA team layer 4.msg]

-------

> [!note]+ 2026-06-26 06:03 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  despite the commercialization challenges with Zephyr, customer is willing to try the PoC. PFA updated status  [^RE_ CEA 3_0 - status update.msg]
>
> TSN & CP-Flex will be critical for this activity. we may need an alignment if our sales team conclude this PoC contract with Cariad
>
> [[Buts_Svitlana_(ETAS-ECMXPC-Abt1)|Buts Svitlana (ETAS-ECM/XPC-Abt1)]] [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] [[Mitchell_Stuart_(ETAS-ECMXSF-NA)|Mitchell Stuart (ETAS-ECM/XSF-NA)]] [[Bauer_Benedikt_(ETAS-ECMXPC-Fe1)|Bauer Benedikt (ETAS-ECM/XPC-Fe1)]] [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Tchouante Auges (ETAS-ECM/XPC-Abt1)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]  fyi

-------

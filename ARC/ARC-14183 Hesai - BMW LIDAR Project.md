---
jira_key: ARC-14183
jira_url: "https://jira.etas-dev.com/browse/ARC-14183"
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
created: "2026-01-08T13:04:00.000+0000"
updated: "2026-06-16T13:39:06.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-14183 Hesai - BMW LIDAR Project

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-06-16T13:39:06.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-14183)

## 描述

** 

- BMW has requested Hesai to deliver a POC before April. Based on that BMW will decide if they will nominate Hesai for their subsequent project development activities. ( I believe there is more than one Tier in contention for this BMW project from China. Our KAM is trying to find that out. Hence this PoC is very crucial for Hesai’s nomination & winning BMW projects )
- For this PoC CAN , Crypto modules are not included.
- For this PoC – Focus is mainly on **Diag Basics + FBL ( Eth based )** should be integrated and conformed to AmTS
- Hesai will confirm with BMW reg. the AmTS scope of this PoC & BAC Modules needed to be integrated for this PoC

 ** 

1.  **Timeline & Project Context**

 ** 

- **PoC Delivery:** End of **March 2026** on **Target HW (TC367)**.
- **BMW Nomination Decision:** April 2026.
- If Hesai is nominated:
- **First BMW Project SOP:** Mid-2027.
- Likely a **Lidar Project**.

 

1.  **BMW’s Acceptance Criteria for this PoC :**

 ** 

- **AmTS Conformity – Maturity Level 4**
- **Diagnostics Basics:** 100% conformity.
- DTCs (Hesai to confirm with BMW).

- **UDS-Flash / Esys-Flash**
- Key UDS services for flashing.
- Programming sequence (Hesai to confirm).

- **State-Control Client (SM)**.
- **StBM TimeSync & SMC Testcases satisfied**.

 

- **Diagnostic Artifacts**
- FA-Files, PDX-Template, Symphony Files, BN-Catalog, Zedis Export. (Hesai believes ETAS should have the know-how of these files based on our Prior experience )
- DTCs & Diagnostic jobs included in ZEDIS Export should be fully implemented and operational.

 

- **Flash Bootloader (FBL)**
- UDS-based flashing (completion in 2 months).
- Ethernet-based (DoIP), **No CAN** for PoC.

 

1.  **Hesai Requests ETAS to provide detailed information on the following topics (Deadline: Jan 14)**

 ** 

- **Expert Availability**
- Global & local ETAS support with BMW experience.

- **Reusable Components**
- BAC modules & ETAS SW from past projects.

- **Virtualization**
- Any HW-independent solutions (involving BAC modules ) available for PoC activities.

- **FBL Support**
- Ethernet-based FBL (DoIP) – reuse from past ETAS solutions.
- Detailed information reg. the past FBL solution delivered to BMW customer ?

 

- **Target HW: TC367**
- Any BMW projects delivered on TC3XX?
- Any Ethernet-based FBL delivered for TC367?

 

- **Our experience in handling** : FA-Files, PDX-Template, Symphony Files, BN-Catalog, Zedis Export.

 

1.  **PoC Scope** 

- **Hesai**
- AmTS conformity testing.
- Multi-core not priority: decision based on HW resource consumption.
- Use RTA-CAR 12.3.2 / 12.3.3.
- TBC : Hesai to confirm the BAC modules with customer.
- TBC : Hesai DTC’s required for this PoC
- TBC : Hesai to share the FBL requirements ( such as programming sequence etc., )

 

- **ETAS**
- Product feature support. ( from Martin’s summary – I believe this should be fine )
- BMW project expert support.
- Generate standard interfaces for BAC SWC (e.g., RTE).
- Due to ETAS's global BMW experience, Hesai prefers ETAS to integrate BAC for this PoC .
- FBL support and dependency resolution.
- **Estimation of cost & timeline feasibility for the above ( BAC Integration, FBL implementation )**

 

- **Risks**
- Customer expects risk assessment.  This is needed for their Project Planning activities.

 

- **Critical Timeline**
- PoC delivery by **End of March 2026**.

## 关联

- relates to: [[ARC-1343 BMW EES25 (formerly SP2025) Platform]]

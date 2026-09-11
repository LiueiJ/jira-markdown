---
jira_key: ARC-15590
jira_url: "https://jira.etas-dev.com/browse/ARC-15590"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]"
reporter: "[[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-03-31T00:06:43.000+0000"
updated: "2026-09-03T06:27:52.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

## **SOP timeline : under clarification**

**Expected Feature complete :** **under clarification**

Business **Scope** :  ETAS shall provide a RTA-CAR Multicore solution **without HSM** fit for **Geely BaseTech 3.5 ADCU**.

- Target: IFX TC377
- compiler: Tasking

Customer : BTL

- existing experiences: RTA-CAR 9.1/9.3

OEM: Geely

BTL scope of response to Geely ADCU

1. **low-end variant (ASDM4)**
  - ETH: No
  - CAN: 3 CAN channel  (multiple nodes)
  - ![[ARC-15590-image-2026-03-31-08-21-11-450.png]]
2. **high-end variant (ASDM)**
  - ETH: 1 channel
  - CAN: 5 channels (multiple nodes)
  - ![[ARC-15590-image-2026-03-31-08-22-19-297.png]]

**Status of SoW**: to be start

**Motivations**

- ETAS is negotiate with BTL the feasibility to use RTA-CAR for Geely BaseTech3.0 ADCU.
- Identifying gaps of RTA-CAR for BaseTeh 3.5 and plan accordingly will enable RTA-CAR for Geely BaseTech 3.5 customers.

**Needs:**

- I**dentifying gaps of RTA-CAR for BaseTeh 3.5 SWRS ADCU**
  - BaseTech 3.5 SWRS ADCU Specification: **negotiating with BTL to share to ETAS**
    - Rough estimation **[[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]]**  you can refer to this one at first time **1234567890-003-ZONE_CONTROLLER-BT-SWRS-ZEEA3.pdf**
 - Suggest to start with
 - Switch
 - DoIP - Generic
 - DoIP InVehicle requirement
 - SomeIP
 - Time Synchronization
 - Gateway
 - Generic
 - Gateway to External IP
 - Gateway to Internal IP
 - Gateway IP-CAN
 - Diagnostic and Boot-loader Gateway
 - RTP
 - VMM
 - UsageMode
 - EEPM
 - SecOC

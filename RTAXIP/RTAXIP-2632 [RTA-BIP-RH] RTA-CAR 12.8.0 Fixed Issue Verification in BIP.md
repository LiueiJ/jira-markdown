---
jira_key: RTAXIP-2632
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2632"
server: etas
kind: motivation
type: Bug
status: Closed
priority: Low
project: RTAXIP
assignee: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]"
reporter: "[[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-rh]
fix-versions: []
epic: null
parent: null
created: "2025-10-15T11:43:19.000+0000"
updated: "2026-03-26T07:09:21.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

color: Color value is invalid

NvM master/multicore - motivation: always ask by customer

- Cariad: not decided yet
  Target release date: open
  Needs from Sisi:
  - features list &bugsfixed (hotline): high demands
  [Dashboard - RTA Hotline](https://rtahotline.etas.com/jira/secure/Dashboard.jspa?selectPageId=18001)
  e.g. RH-13446, RH-12551
  TODO: to check and plan to test again for next RCAR 1280
  **=> BIP feature list, NEEDs:**

- add service discovery for Sever

- SecOC/E2E

- IpduM container

Nvm Master?muticore

## 评论

> [!note]+ 2026-03-26 07:07 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Duplicate with RTAXIP-2678

-------

> [!note]+ 2026-03-09 07:50 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Hi anh [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] , [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] , What purpose of this ticket?

-------

> [!note]+ 2025-10-29 08:54 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]],
> I've made a small try to filter 4 tickets from 18 hotline tickets randomly: [^hotline_BIP_NEEDs_ticket.xlsx]
> I do see around 200 tickets from CN hotline dashboard: [Dashboard - RTA Hotline](https://rtahotline.etas.com/jira/secure/Dashboard.jspa?selectPageId=18001)
>
> **What's next**
>
> **Action 1:** You're demanding to follow with product release. => TO DO: I could check/follow up with product team.
> {*}Action 2{*}: could you align with [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]] which one is BIP NEEDs ticket for BIP
>
>
> | # | Hotline ticket | Problem | Status | Solution | Expected CAR | Activities | BIP NEEDs ticket. | What's Next? |
> | 6 | RH-12907 | [ConfGen][Gateway] ComIPdu without ComSignal generated for gatewayed Pdu | Closed | No | 12.8.0 | Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0. | Open | No Action needed for BIP. |
> | 7 | RH-12824 | [CanTrcv] Incorrect Macro Naming in CanTrcv_Cfg.h | Closed | Yes | 12.8.0 | Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0. | Open | No Action needed for BIP. |
> | 17 | RH-13029 | Feedback on data type issues in the CanIf_Init() function of RTA-CAR 12.6.0 | Closed | Yes | 12.8.0 | Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0. | Open | No Action needed for BIP. |
> | 18 | RH-13047 | [ConfGen] XCP Pdu CanIfRxPduCanIdType is forcedly generated to STANDARD_NO_FD_CAN | Closed | Yes | 12.8.0 | Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0. | Open | No Action needed for BIP. |

-------

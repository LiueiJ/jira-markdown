---
jira_key: ARC-9198
jira_url: "https://jira.etas-dev.com/browse/ARC-9198"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: ""
reporter: but9fe
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-02-10T13:52:13.000+0000"
updated: "2026-09-03T06:36:44.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-9198 VCTC Domain ECUs

> [!jira] Accepted ·  ·  · 更新于 2026-09-03T06:36:44.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-9198)

## 描述

VCTC business situation, background, status

- VCTC is OEM. Carizon is supplier of VCTC
- VCTC has purchased RTA-CAR dev license and production license in 2024 already
- For new EE architecture based on RH850 U2A16 and for following ECU's:
  - CDCU - Central Domain Controller Unit (incl IVI,..)
  - LDCU - Left Domain Controller Unit  (body, chassis,..)
  - RDCU - Right Domain Controller Unit  (powetrain,..)

- VCTC has ISOLAR-B in use already and is familiar with it
- VCTC and ETAS are in contract process for CycurHSM for same platform
- Development license and Production license CycurHSM RH850 / U2A16
- Competitor (Vector) offered source code => VCTC is requesting CycurHSM source code to ETAS
- Purpose: able to do own configuration, able to add own code
- Compromise proposal (config tool plus secure space scripting) accepted by VCTC already
- No need for VKMS
- Security level of VCTC ("CEA spec") is higher than CN average but lower than VW security requirements
- VCTC may purchase CycurHSM for further HW targets in future
- e.g. BMS, already in discussion

## 评论

> [!note]+ 2025-02-10 14:02 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Opp won in 2024:
>
> Cariad China CEA platform Autosar CP develop license project has been locked down, include 2*floating+1*MAC+4*dongle, around 8.66 million CNY. Acquisition was tough, thanks to everyone contribution.
>
> Value
> 0→100，          Ice break in VW group, would influence Cariad global even VW global middleware in future, Local for global！
> 100→1000，    Start point for VOS and SFs, as customize middleware, OEM standard design, and vehicle virtualization etc., Local for local!
>
> Next
> Short term        Start project delivering, management visit, build solid customer relation further
> Middle term      Start CP mass-product license acquisition and dig other SFs opportunity, build etas full product cooperation
> Long term         Next generation platform cooperate, even influence global chance

-------

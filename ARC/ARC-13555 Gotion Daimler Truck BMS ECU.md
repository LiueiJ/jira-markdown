---
jira_key: ARC-13555
jira_url: "https://jira.etas-dev.com/browse/ARC-13555"
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
created: "2025-11-05T06:17:45.000+0000"
updated: "2026-09-03T06:59:51.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-13555 Gotion Daimler Truck BMS ECU

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-03T06:59:51.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13555)

## 描述

**Business Opp:****{**}

Daimler is currently in discussion with Gotion (Tier-1) for providing HSM and CP solutions that meets Daimler Truck technical requirements.  By E.2025 Daimler will announce the nomination. From sources, Gotion is more likely to receive the nomination. 

- Daimler is recommending Vector to Gotion for development.
- Gotion is a customer of ETAS and use RTA-CAR 9.2.1.  has a strong relationship with ETAS.
  - Gotion has communicated to Daimler that they intend to use ETAS RTA-CAR and HSM for the development.
  - Opportunity for ETAS to sell latest RTA-CAR & HSM to Gotion and indirectly get the Daimler business.
- **Attached DTSS specs** [Security Spec_Daimler Truck.7z!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/659649/659649_Security+Spec_Daimler+Truck.7z)

**Present need :**

- Gotion has requested ETAS to support is making a strong argument to Daimler. failing to to provide compelling arguments (as below), Gotion will be forced to use Vector solution.
  - WHY RTA-CAR 12.5 is needed rather than 9.2.1 for Daimler Truck for Cybersecurity requirement.?
  - WHY must RTA-CAR rather than Vector DaVinci for Daimler Truck ?
  - Any proof that ETAS CP / HSM solutions being used in parts of Daimler already ? 
    - for e.g. we seem to have some experience to use RTA-CAR 12.5 and CycurHSM work with the Standard Security Architecture (SSA) software from Daimler together : [How to integrate Daimler SSA - XSF-DE Landing page [Public] - Confluence (etas-dev.com)](https://confluence.etas-dev.com/spaces/ARCP/pages/523901726/How+to+integrate+Daimler+SSA)

**TBC :  More technical information to follow once we Gotion gets nominated**

## 评论

> [!note]+ 2025-11-05 14:23 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Daimler and DaimlerTruck historically had quite a lot in common, but nevertheless were different enough to have different architecture baselines :
>
>
> | Daimler | DaimlerTruck |
> | --- | --- |
> | STAR2 | SLP9 |
> | STAR3 | SLP11 |
> | MMA | ? |
> | MB.OS | ? |
>
>
>
> Current Daimler Projects [Jira query](https://jira.etas-dev.com/issues/?jql=type%20%3D%20Motivation%20AND%20(cf%5B14103%5D%20%3D%20Mercedes-Benz%20OR%20cf%5B14103%5D%20%3D%20Daimler)) 
>
> Current Daimler Truck Projects [Jira query](https://jira.etas-dev.com/issues/?jql=type%20%3D%20Motivation%20AND%20cf%5B14103%5D%20%3D%20DaimlerTruck) 
>
> From [[Kougioumtzis_Theodoros_(ETAS-ECMXSF-DE)|Kougioumtzis Theodoros (ETAS-ECM/XSF-DE)]]  (Daimler & Daimler Truck OEMSolM):
> {quote}with Daimler Truck we have different projects and collaborations running.
>  * ETAS defining together with Daimler Truck the central security specification.
>  * PoC standalone Ids-M for non AUTOSAR ECUs
>  * ECU project with Tier1 Wuerth
>  * Communications BSW central department for 10 Sensor ECUs
>  * PoC RTA-CAR (Ethernet) à done
>  * SSA integration Wiki Page
>
>
> {quote}

-------

> [!note]+ 2025-11-05 06:32 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]]  has already provided the following Feedback to Gotion reg. Sec support . More details in the attached email chain [^Gotion Daimler Truck BMS project opportunity support needed.msg]. 
>
> We need to provide augmentation for CP  support.
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] fyi

-------

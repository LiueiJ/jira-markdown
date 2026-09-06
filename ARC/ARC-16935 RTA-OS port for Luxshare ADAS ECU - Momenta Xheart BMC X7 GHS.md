---
jira_key: ARC-16935
jira_url: "https://jira.etas-dev.com/browse/ARC-16935"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: hut1yok
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-07-09T06:00:20.000+0000"
updated: "2026-09-03T16:09:44.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-16935 RTA-OS port for Luxshare ADAS ECU - Momenta Xheart BMC X7 GHS

> [!jira] New ·  · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] · 更新于 2026-09-03T16:09:44.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-16935)

## 描述

**Background**

Luxshare require ETAS to create new OS port to support Momenta(Xheart): BMC X7 chip

Target Chip: BMC X7

Target Core: ARM Cortex-R52 core

2+2 DCLS, 1 Cluster

Compiler: GHS v2021.1.4

Expectation date:2026/07 + 6 weeks

UM: plan to be available before 2026/07/20

EVB: ETCN will support to setup remote environment in ETCN hub which could be access and debug by York engineer.

Task:

- Create new OS port to support this Chip.
- Please support to estimate the cost and schedule.

**Sales Pipeline Stages:**

Lead generation

**Products / use-cases**

ADAS ECU

**OEMs**

Chery

**Competitors**

Vector

**RTA potential**

Luxshare is a legacy RTA-CAR customer and currently use it.

Luxshare could pay OS port development license and ProD. license.

**ToDos**

 * !check.png! Fill out with ETCN hub.

 * !check.png! Check whether the motivation type is correct.

 

![[ARC-16935-image-2026-07-09-14-32-42-872.png]] ![[ARC-16935-image-2026-07-09-14-30-08-203.png]]![[ARC-16935-image-2026-07-09-14-31-23-052.png]]![[ARC-16935-image-2026-07-09-14-31-59-852.png]]

## 关联

- is satisfied by: [[OSOPP-443 New port for Luxshare ADAS ECU - Momenta Xheart BMC X7 GHS]]

## 评论

> [!note]+ 2026-09-03 16:09 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> There has to be some RTA-CAR production license money **at the very least** to make it worth our effort to do this. What sort of ECU project is this and is Chery the only customer or do they plan to sell this as a platform to more customers?

-------

> [!note]+ 2026-08-03 01:31 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] 
>
> Hi Tom, Luxshare need pay the RTA-OS development and production license for this BMC X7 project, Luxhsare might purchase M&S for 1 set RTA-CAR. 
>
> no FBL, HSM and new RTA-CAR requirement.

-------

> [!note]+ 2026-07-31 10:36 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> As per the ETAS business model - is this a new project where Luxshare will pay another production license? I need to know the overall business scope. What other aspects to the sale is there? FBL, HSM, new RTA-CAR production license?

-------

> [!note]+ 2026-07-30 09:20 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] Hi Tom,
>
> ETAS could get the revenue for OS port development license and production license, meantime to defense RTA-CAR position in Luxshare.
>
> KAM is working hard and push the procedure with customer.

-------

> [!note]+ 2026-07-30 09:10 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Thanks for the info [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]].
>
> My understanding is they won't pay for the port development fee.
>
> Please could you loop in the KAM so we can understand what kind of revenue we can expect from selling licenses.

-------

> [!note]+ 2026-07-30 01:27 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] 
>
> LuxShare has **explicitly positioned itself as a Tier 1 automotive supplier** rather than a vehicle OEM (Original Equipment Manufacturer)itiger.com.
> #### 🚗 Automotive Strategy & Capabilities:
>  * {*}Focus Areas{*}: Integrated driving and parking domain controllers (e.g., DAC1.1), in-vehicle networking, wiring systems, and thermal management solutions.
>  * {*}Strategic Partnerships{*}:
>  ** **Chery Automobile** (2022): Formed a joint venture for R&D, mass production platforms, and overseas market expansion for automotive componentsacnnewswire.com.
>  ** {*}Leoni AG (2025){*}: Acquired a 50.1% stake in Leoni’s Wiring Systems Division (WSD), a major German automotive wiring harness supplier. This significantly enhanced LuxShare’s automotive footprint in Europe and globallyleoni.com.
>  * {*}Tier 1 Capabilities{*}: LuxShare provides **integrated solutions from core components to system assembly** for automotive clients, including design, manufacturing, and supply chain management.
>
> Luxshare has used Horizon J6x and RTA-CAR in mass production for Chery in past years. 
>
> in this opportunity, LuxShare has been nominated by Chery ADAS project with Xheart (Momenta) BMC X7 chip,
>
> Luxshare tend to use ETAS RTA-CAR solution in safety island even the Xheart has whole solution with Vector Davinci. 

-------

> [!note]+ 2026-07-29 14:50 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] who is LuxShare and what kind of company are they? (are they a Tier 1?)
>
> Have they already won a successful acquisition, or do they want this OS port to help customer acquisitions?

-------

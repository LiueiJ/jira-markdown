---
jira_key: ARC-15108
jira_url: "https://jira.etas-dev.com/browse/ARC-15108"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: rew1sgh
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-03T11:03:13.000+0000"
updated: "2026-06-18T08:52:51.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-15108 RTA-OS port for Ecarx IVI Domain - SemiDrive E3620B R52 GHS

> [!jira] Canceled ·  · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] · 更新于 2026-06-18T08:52:51.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-15108)

## 描述

**Background**

Tier1 ECARX plan to select SemiDrive E3620B + GHS compiler v2023.5.4

**Products / use-cases**

IVI + T-Box ECU

**OEMs**

FAW

**Competitors**

EB

**RTA potential**

OS port Dev. license,  ProD. license fee.

Engineer service fee, 

**ToDos**

 * !check.png! Fill out with ETCN hub.

 * !check.png! Check whether the motivation type is correct.

## 关联

- duplicates: [[ARC-15304 [ECARX] OS Porting SemiDrive E3620B/3650 GHS]]

## 评论

> [!note]+ 2026-03-18 14:53 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Closed as it duplicates https://jira.etas-dev.com/browse/ARC-15304

-------

> [!note]+ 2026-03-18 13:49 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] 
>
> Dear Darren, as i understanding, 2 tickets point to same project.
>
> the ARC-15304 is created by TanYang.
>
> i will check with him and try to merge into this ticket.

-------

> [!note]+ 2026-03-18 08:08 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]This motivation seems to be the same thing as ARC-15304. If that's right, then please move this to the parent motivation and then merge with ARC-15304.
>
> In general we'd not have motivations for OS ports only as this isn't good business strategy for us - it only makes sense for us to do OS ports as a way to sell **all** of RTA-CAR for a bigger and more valuable project. So the normal pattern for this would be:
>  * Create a motivation for the whole business opportunity (ECU project or platform at a customer)
>  ** Add a need for the OS port that is required
>  ** Add other needs if there are any
>
> There is some more guidance in the motivation work instruction here: [https://confluence.etas-dev.com/spaces/RTAC/pages/507946111/Motivation+tickets+CAR+Work+Instructions]

-------

> [!note]+ 2026-03-12 13:10 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> | *Offer # 367* |  |
> | **Description** | RTA-OS support for SemiDrive E3620B R52 GHS (final release) |
> | **Order Required By** | ASAP |
> | **Hardware Required By** | Before PS |
> | **Release** | 26.May.2026 |
> | **Cost** | € 40,000.00 |
>
> *Note: The price does not consider ETCN preview releases*
>
> *Note: Any lateness in the order or the requirements sign-off will cause +at least+ day for day slippage to deliveries.*

-------

> [!note]+ 2026-03-10 12:12 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Sync with Wanwei:
>  * ETCN has offered the same price as the port for this device with the IAR compiler - 60k€ for single variant and 80k€ for all variants.
>  * Total contract incl. licenses + engineering fees may come to 1.5m - 2.0m RMB (185k€ - 250k€).
>  * If we win the project we'll likely get the nomination before 20th March.
>  * China team will do early version by 15th April. After that York team can take over if we get the project nomination.
>  * [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] to give official price indication.
>
> [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Duong Thi Ngoc (ETAS-ECM/XPC-Yok1)]] when could we schedule this one in for? Also, when should the order required by date be?

-------

> [!note]+ 2026-03-05 10:13 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Duong Thi Ngoc (ETAS-ECM/XPC-Yok1)]] [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] [[XIE_Allen_(ETAS-ECMXSF-CN)|XIE Allen (ETAS-ECM/XSF-CN)]] 
>
> Hi Ngoc, Hi Tom
>
> CC Allen
>
> EcarX expect use E3620B first, this target variant is high priority.
>
> meanwhile this OS port should update to support E3650 in the end.
>
> the target compiler is {color:#de350b}GHS v2022.1.4.{color}
>
> customer expect to get the {color:#de350b}multi-core York preview{color} OS port before 1st April. 
>
> ETCN need some days to prepare a OS demo code to EcarX.

-------

> [!note]+ 2026-03-05 09:42 · [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Duong Thi Ngoc (ETAS-ECM/XPC-Yok1)]]
> ![[ARC-15108-image-2026-03-05-09-42-34-508.png]]
>
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] , could you please create OSOPP ticket? Thanks

-------

> [!note]+ 2026-03-04 08:46 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> OS opp. sync
>  * Estimation from York OS side in progress.
>  * Customer is planning to start their project in the beginning of 8th April. 
>  * By this time, they want to get RTA-CAR ready before 8th April.
>  * They are currently discussing whether to use GHS or IAR, but discussions with customer indicates they want to use GHS more. ECARX in the past has always used GHS, but due to restrictions with the GHS compiler, they're evaluating the IAR compiler. They're doing the comparison.
>  * Li Yang is doing the IAR compiler port as planned. Original plan is to focus on the E3620P for Sungrow. Sungrow have ordered this. Base port multi-core will be finished in March. Next step, is the E3620B [https://jira.etas-dev.com/browse/ARC-14710]. Base port multi-core for E3620B is planned for end of April.
>  * Luning is doing the GHS compiler evaluation. Base porting from IAR to GHS is not so much effort. Testing to take ~2-3 weeks.
>  * Total contract could be 1-2 m RMB.
>
> ToDo
>
> (x) Tom to provide official price and schedule.

-------

> [!note]+ 2026-03-03 13:05 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] 
>
>  [E3650 E3620](https://bosch-my.sharepoint.com/:f:/r/personal/rew1sgh_bosch_com/Documents/99_Semi/2_SemiDrive%E8%8A%AF%E9%A9%B0/E3/E3650%20E3620?csf=1&web=1&e=VTio0A)
>
> please find the UM

-------

> [!note]+ 2026-03-03 12:46 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] Do you have the E3620B reference manual?

-------

> [!note]+ 2026-03-03 11:08 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] 
>
> Hi Tom, please estimate the cost and schedule.

-------

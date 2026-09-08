---
jira_key: ARC-16270
jira_url: "https://jira.etas-dev.com/browse/ARC-16270"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: rew1sgh
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-05-18T04:42:30.000+0000"
updated: "2026-07-31T08:47:21.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-16270 SAIC ZCU

> [!jira] New ·  · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] · 更新于 2026-07-31T08:47:21.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-16270)

## 描述

**Background**

SAIC plan to choose ST Stellar P3E for ZCU platform.

Target Chip: ST Stellar P3E

Target Core: 

- ARM Cortex-R52 core only.
- Compiler:  HighTec ARM toolchain 10.0

Expectation date:  2026/06/30

Task:

- Create new OS port to support 

[[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Duong Thi Ngoc (ETAS-ECM/XPC-Yok1)]]

Please support to estimate the cost and schedule.

**Products / use-cases**

VCU

**OEMs**

COEM Leapmotor

**Competitors**

None

**RTA potential**

OS porting service fee,

OS port development license fee

No RTA-CAR license involved in project.

**ToDos**

  !check.png! Fill out with ETCN hub.

  !check.png! Check whether the motivation type is correct.

## 评论

> [!note]+ 2026-07-31 08:47 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Sync with Sathish:
>  * SAIC don't have anything ready, they're evaluating suppliers, long way off from a test drive
>  * ST hardware is only sample so won't be going on the road anyway
>  * ST are in bidding process for project
>  * Therefore unlikely it goes on the road even in a test driv 

-------

> [!note]+ 2026-07-30 14:20 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] or [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]  please could you confirm with SAIC whether the single-core alpha port will stay in the lab or will be used on the road?
>
> This will decide whether we can do a Core Port or a single-core target port preview.

-------

> [!note]+ 2026-07-30 13:58 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] 
>
> feedback from KAM of SAIC 's information:
>  * ST management put this project in strategical position, they promise to SAIC that they can convince ETAS DE to provide P3E OS port for free.
>  * It is a very important platform project, but not so urgent. So the project schedule isn’t so tight.
>  * ST is competed with other silicon vender.

-------

> [!note]+ 2026-07-30 12:00 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Short update:
>  * We can offer a Core Port IF SAIC do not plan to use the PoC on the road AND David has capacity to make one.
>  * I'm checking with Alessandro on the former, and with David on the latter.
>  * Otherwise, we'll have to try and squeeze in a single-core target port.
>  * From a reuseability perspective, a Core port is the clear winning solution from our side so I'm hoping to go down this road.

-------

> [!note]+ 2026-07-30 08:49 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> Hello all,
>
> I'm already on it and have a meeting today with Benedikt to figure out what we can do. I will update as soon as we have a plan.
>
> FYI [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 

-------

> [!note]+ 2026-07-30 08:43 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  Alessandro from ST has been requesting for this OS port ( Alpha level / Single core support ) by Sep'26   . He has raised it with [[Hotz_Ingo_(ETAS-ECMPRM-EMW)|Hotz Ingo (ETAS-ECM/PRM-EMW)]]  . This is a big biz opportunity for ST . SAIC delivering for AUDI. They are using our partnership to build their biz. This could also be a potential project biz for ETAS. this is something we need to closely follow-up. attached [^RE_ RTA-OS alpha version for SAIC.msg]for the full context. 
>
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] please involve the respective KAM for SAIC to follow-up. 
>
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] fyi

-------

> [!note]+ 2026-07-30 01:54 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] 
>
> I second you,
>
> The project has advanced to the SAIC‘s internal project initiation phase, and final approval is still pending official confirmation.

-------

> [!note]+ 2026-07-29 14:48 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] - if they only want the OS port and there is no other RTA-CAR business here, then this will be at the back of the queue of work. It doesn't make business sense for us to prioritise before all the other ports for which there is wider OS business.  What are SAIC doing for the rest of their AUTOSAR solution on the ZCU? 

-------

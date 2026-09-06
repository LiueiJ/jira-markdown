---
jira_key: ARC-17242
jira_url: "https://jira.etas-dev.com/browse/ARC-17242"
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
created: "2026-07-29T07:35:51.000+0000"
updated: "2026-08-18T06:04:32.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-17242 RTA-OS port for Keboda TBD ECU - R-CAR U5L2 GHS

> [!jira] New ·  · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] · 更新于 2026-08-18T06:04:32.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-17242)

## 描述

**Background**

Keboda inquiry whether ETAS RTA-OS could support R-CAR U5L2 for ECU or not.

Target Chip: R-CAR U5L2

Target Core: ARM Cortex-M33 core

Compiler: greenhills comp 2025.1.4

Expectation Final Release date:2026/10/30

Task:

- Create new OS port to support
- Please support to estimate the cost and schedule.

**Sales Pipeline Stages:**

Lead generation

**Products / use-cases**

TBD Controller

**OEMs**

BMW

**Competitors**

Vector, iSoft

**RTA potential**

Keboda is a legacy RTA-CAR customer, and currently use it.

Keboda could pay OS port Development license fee and Production license fee.

**ToDos**

 * !check.png! Fill out with ETCN hub.

 * !check.png! Check whether the motivation type is correct.

## 关联

- is satisfied by: [[OSOPP-447 Create RCar U5L2 target port for M33 (Main&ICUM) using GHS]]

## 评论

> [!note]+ 2026-08-11 06:21 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]] 
>
> Hi Michael， Keboda will use windows environment,
>
> For compiler option, they accept the etas's proposal.

-------

> [!note]+ 2026-08-10 11:24 · [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 
> These are the compiler options were are currently using to develop the RCar U5L4:
>  * -cpu=cortexm33
>  * -Ogeneral
>  * -align8
>  * -c99
>  * --gnu_asm
>  * --no_commons
>
> So far this development is limited to the linux compiler version v2025.1.4
> I think Keboda is requesting for the windows compiler is that correct?

-------

> [!note]+ 2026-08-03 06:21 · [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 
> Sure we can suggest compiler options first, give me some days to clarify them with the developer first.
> For the additional effort, my guestimation would be something around ~10,000€. I'll provide an official offer together with the compiler options later this week.

-------

> [!note]+ 2026-08-03 06:04 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]] 
>
> Hi Michael
>
> I suggest that ETAS proposal the compiler option first, then ask customer to confirm. 
>
> what's your comments?
>
> about the cost, customer could share part of OS port development fee, please share the price indication. 

-------

> [!note]+ 2026-08-03 05:57 · [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 
> We are still in an very early comissioning phase of the hardware. 
> So far we haven't created/analyzed the possible/relevant compiler options, which fits best.
> Once we are at a state, where we can share some more information, we will do.
>
> In case Keboda has already some compiler options in mind, they might can share them with us and we can check if that fits to our expecations.
> Please be aware eventhough we already in development of this port, we need to charge some additional development fee to Keboda to add the U5L2 hardware variants.
>
> Will come back to you as soon as possible.

-------

> [!note]+ 2026-08-03 05:31 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]] 
>
> Hi Michael
>
> Got it. It would be perfect if the current development could cover U5L2.
>
> Could you share the CR for the current compiler options and the addition of the U5L2 variant?
>
> I will check with the customer and provide feedback to the team.

-------

> [!note]+ 2026-08-03 05:21 · [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 
> Is there an additional compiler option set, which is requested by the customer?
> We are currently in development of the U5L4 for the same compiler version.
> So in case the request is limited to hardware variant and compiler version, we might be able to add this request to the ongoing development.
> Otherwise it will be not possible to confirm the requested customer timeline end of October.

-------

> [!note]+ 2026-07-29 09:36 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]] 
>
> Yes, Both,
>
> Keboda require OS port for Main Core, meantime they require for CycurHSM.
>
> please contact with SEC team for detail information about HSM core OS port.

-------

> [!note]+ 2026-07-29 09:32 · [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> Is this request for the ICUM/HSM or Main Core?

-------

> [!note]+ 2026-07-29 08:43 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
>
> Customer could wait for final release until end of October,
>
> before that, ETCN could provide core port to customer if Kebeda wish to evaluate the chip. 

-------

> [!note]+ 2026-07-29 08:35 · [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] What's the scope of their project? I'd like to investigate whether a Core Port satisfy their immediate needs whilst we develop the full port.

-------

> [!note]+ 2026-07-29 07:43 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] [[Knarr_Michael_(ETAS-ECMXPC-Fe1)|Knarr Michael (ETAS-ECM/XPC-Fe1)]] [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Duong Thi Ngoc (ETAS-ECM/XPC-Yok1)]] 
>
> Hi Tom, Hi Michael, Hi Ngoc,
>
> please estimate the cost and schedule (Target date:2026.10.30），thank you.

-------

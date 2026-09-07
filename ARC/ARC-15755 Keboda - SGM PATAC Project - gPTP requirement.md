---
jira_key: ARC-15755
jira_url: "https://jira.etas-dev.com/browse/ARC-15755"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: ""
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-04-08T12:11:28.000+0000"
updated: "2026-06-19T09:26:46.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-15755 Keboda - SGM PATAC Project - gPTP requirement

> [!jira] New ·  ·  · 更新于 2026-06-19T09:26:46.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-15755)

## 描述

- RTA-CAR 9.2.2
- GM-SUM V2.3.3
- IFX TC397
- as Slave Node

Keboda require ETAS to estimate whether RTA-CAR V9.2.2 could support follow usage scenario? how much effort and cost will be spent by customer?

1. The MCU must support receiving four clock domains simultaneously and prioritize synchronization with Domain0.

2. When the Slave node detects that the current time synchronization domain is invalid, it must switch to a valid time synchronization domain with the next highest priority, and the application must complete the switching of the time synchronization domain call within the next 10 ms. The priority order is: Domain0 > Domain1 > Domain2 > Domain3.

3. Upon continuously receiving the Sync message and the Follow_Up message, all slave nodes must use the latest pDelay value and neighborRateRatio to complete time synchronization. The synchronization algorithm includes the following requirements:

   TS_Requirement:

   (1) Obtain the start time of the Sync message transmission at the grandmaster side, i.e., the preciseOriginTimestamp value in the Follow_Up message.

   (2) Obtain the residence time of the Sync message in the switch, i.e., the correctionField value in the Follow_Up message.

   (3) Obtain the propagation delay of the Sync message. The propagation delay is calculated by the slave node.

   (4) Obtain the time offset 𝑇𝑑𝑖𝑓𝑓 between the reception of the Sync message by the node and the calculation of the synchronized time. This offset is calculated using the slave node’s reference clock.

   (5) Calculate the synchronized time of the slave node using the following formula:

   𝑇𝑠𝑦𝑛𝑐 = preciseOriginTimestamp + correctionField + pDelay + neighborRateRatio * 𝑇𝑑𝑖𝑓𝑓

4. In a time synchronization system, redundant grandmasters and redundant paths may generate multiple time synchronization domains. The master-slave attributes of the gPTP port on each time synchronization node must be independently configurable in different time synchronization domains, and each node must be capable of running all time synchronization domains simultaneously.

![[ARC-15755-image-2026-04-08-20-14-27-175.png]]

## 评论

> [!note]+ 2026-04-15 10:28 · [[Pereira_Joao_(XCEVO-XPC-Brg1)|Pereira Joao (XC/EVO-XPC-Brg1)]]
> Hello [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] can you please check the following points? 
>
> 1. The MCU must support receiving four clock domains simultaneously and prioritize synchronization with Domain0.
> {color:#00875a}Multiple time domains are supported. Regarding prioritization, see comment on point 2. {color}
>
> 2. When the Slave node detects that the current time synchronization domain is invalid, it must switch to a valid time synchronization domain with the next highest priority, and the application must complete the switching of the time synchronization domain call within the next 10 ms. The priority order is: Domain0 > Domain1 > Domain2 > Domain3.
>
> {color:#00875a}Application can monitor the state of the time base(one for each domain) and consume the time from a different time bases in case timebase status is invalid. {color}{color:#ff8b00}As mentioned above the application on each node shall take care of defining which domain it needs to consume based on the status returned by StbM{color}.  [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] {color:#ff8b00}Can you please clarify that this is there expectation?{color}
>
> 3. Upon continuously receiving the Sync message and the Follow_Up message, all slave nodes must use the latest pDelay value and neighborRateRatio to complete time synchronization. The synchronization algorithm includes the following requirements:
>
>    TS_Requirement:
>    (1) Obtain the start time of the Sync message transmission at the grandmaster side, i.e., the preciseOriginTimestamp value in the Follow_Up message.
>    (2) Obtain the residence time of the Sync message in the switch, i.e., the correctionField value in the Follow_Up message.
>    (3) Obtain the propagation delay of the Sync message. The propagation delay is calculated by the slave node.
>    (4) Obtain the time offset 𝑇𝑑𝑖𝑓𝑓 between the reception of the Sync message by the node and the calculation of the synchronized time. This offset is calculated using the slave node’s reference clock.
>    (5) Calculate the synchronized time of the slave node using the following formula:
>
>    𝑇𝑠𝑦𝑛𝑐 = preciseOriginTimestamp + correctionField + pDelay + neighborRateRatio * 𝑇𝑑𝑖𝑓𝑓
>
> {color:#ff8b00}NeighborRateRatio is currently not supported. Therefore current calculation is based on the following formula:{color}
>
> {color:#ff8b00}{{𝑇𝑠𝑦𝑛𝑐 = PreciseOriginTimestamp + {color}{color:#ff8b00}PathDelay {color}{color:#ff8b00}+ CorrectionField + 𝑇𝑑𝑖𝑓𝑓}}{color}
>
> {color:#ff8b00}Rate correction in StbM is supported. {color}
>
> 4. In a time synchronization system, redundant grandmasters and redundant paths may generate multiple time synchronization domains. The master-slave attributes of the gPTP port on each time synchronization node must be independently configurable in different time synchronization domains, and each node must be capable of running all time synchronization domains simultaneously.
>
> {color:#ff8b00}All time domains are also gatewayed to Can bus? 
> ![[ARC-15755-image-2026-04-15-11-07-47-545.png]]{color}

-------

> [!note]+ 2026-04-09 01:53 · [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] 
>
> Keboda's current project is already in the stable mass production phase.
>
> If supporting the above gPTP application scenario requires an upgraded version of RTA-CAR, we can try to convince the customer.
>
> Please help analysis whether the latest RTA-CAR version meets the above application scenario.

-------

> [!note]+ 2026-04-09 01:29 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]  thanks for creating the ticket. we can get clarification about this requirement.  But why should we support in RTA-CAR 9.2.2 ? Is there any reason customer cannot migrate to latest version? jfyi, We generally dont recommend to back port new features to older versions. In this case, 9.x.x version is out of maintenance. we stopped supporting any updates to that version of RTA-CAR. If customer insist support for 9.2.2, then the effort will be huge and cost will be very high. Also, new LTS (Long term support) for 9.x.x will be put in place. imo, time wise and cost wise it is not the best option. 
>
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] could you please confirm if this gPTP requirement is already supported or not? thanks.

-------

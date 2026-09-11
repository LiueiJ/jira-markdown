---
jira_key: RTAXIP-3863
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3863"
server: etas
kind: motivation
type: Task
status: Closed
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-rh]
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2026-07-09T04:25:01.000+0000"
updated: "2026-07-24T08:56:10.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

Motivation: [RH-14510 ](https://rtahotline.etas.com/jira/browse/RH-14510)need to be verified on RTA-CAR 12.11

Input:

- SW BIP base from: [RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886) &#91;RTA-BIP-12.11.0&#93;Porting to RTA-CAR 12.11.0
- feature/[RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886)-rta-bip-12110-porting-to-rta-car-12110

Output: 

- Verify if the resolution of RH ticket is yet available in RTA-CAR 12.11 and compatible to BIP

## 关联

- clones: [[RTAXIP-3861 [RTA-BIP-RH] Check the resolution of RH-14656 - [Generate ECU Configuration] Issue relates to generate "Dem" elements]]
- is satisfied by: [[RTAXIP-3892 [RTA-BIP-RH] Check the resolution of RH-14510]]
- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]
- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

## 评论

> [!note]+ 2026-07-23 07:09 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> Issue description from RH-14510: Conflict between RTA_BSW and RTA_RTE code gen for ComTimeoutNotification Function name.
>
> Currently, when **bsw conf-gen** name Rx timeout notification will be: Rte_COMCbk__TOut_XXX
>
> but in {*}RTA_RTE gen{*}, the name function of ComTimeoutNotification will be Rte_COMCbkTOut_XXX.
>
> ?? ??
>
> Issue is solved in {color:#00875a}*RTA-CAR 12.11.0*{color}, Rx timeout notification will be gen by **bsw conf-gen** with correct prefixes and match with **RTA_RTE gen**
>
>
>
> BSW Conf-Gen:
>
> ![[RTAXIP-3863-image-2026-07-23-14-10-02-401.png]]
>
> RTA-RTE gen:
>
> ![[RTAXIP-3863-image-2026-07-23-14-10-14-740.png]]
>
> ![[RTAXIP-3863-image-2026-07-23-14-10-20-171.png]]
>
> RTA-RTE gen pass. Log file attached:
>
> [^rta-rte.log]
>
> [^RteErr.xml]

-------

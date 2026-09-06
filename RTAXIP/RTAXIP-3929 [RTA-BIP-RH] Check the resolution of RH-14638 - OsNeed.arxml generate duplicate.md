---
jira_key: RTAXIP-3929
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3929"
server: etas
kind: motivation
type: Task
status: Closed
priority: Medium
project: RTAXIP
assignee: gua6hc
reporter: puy1hc
tags: [RTA-BIP-RH]
components: []
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2026-07-21T09:16:01.000+0000"
updated: "2026-07-28T03:39:41.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3929 [RTA-BIP-RH] Check the resolution of RH-14638 - OsNeed.arxml generate duplicate Counter with same OsCounterMaxAllowedValue

> [!jira] Closed · Medium · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]] · 更新于 2026-07-28T03:39:41.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3929)

> 标签：#jira/label/rta-bip-rh

## 描述

Motivation [[RH-14638]](https://rtahotline.etas.com/jira/browse/RH-14638) need to be verified on RTA-CAR 12.11 or 12.10

Input:

- SW BIP base from: [RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886) &#91;RTA-BIP-12.11.0&#93;Porting to RTA-CAR 12.11.0
- feature/[RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886)-rta-bip-12110-porting-to-rta-car-12110

Output: 

- Verify if the resolution of RH ticket is yet available in RTA-CAR 12.11 and compatible to BIP

## 关联

- clones: [[RTAXIP-2743 [RTA-BIP-RH] Check the resolution of RH-14332 - RTA-RTE gen error with DoIP_BSWMD.arxml]]
- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]
- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

## 评论

> [!note]+ 2026-07-28 03:39 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> **Issue Description from RH-14638:** I got the issue after generate RTE code, OsNeed.arxml generate duplicate Counter with same OsCounterMaxAllowedValue with already counter configuration. 
>
> Issue is solved in {*}RTA-CAR 12.11.0{*}, after RTE gen, "OsCounterMaxAllowedValue" is no longer generated.
>
> ![[RTAXIP-3929-image-2026-07-28-10-37-39-204.png]]
>
> RTE gen log:
>
> [^rta-rte.log]
>
> Gen file after RTA_RTE:
>
> [^osNeeds.arxml]

-------

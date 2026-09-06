---
jira_key: RTAXIP-3924
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3924"
server: etas
kind: motivation
type: Task
status: Closed
priority: Medium
project: RTAXIP
assignee: gua6hc
reporter: pka3hc
tags: [RTA-BIP-RH]
components: []
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2026-07-20T10:43:38.000+0000"
updated: "2026-07-24T08:55:35.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3924 [RTA-BIP-RH] Check the resolution of RH-14736 - Issue relates to "NvMSingleBlockCallBack" after RTE-gen

> [!jira] Closed · Medium · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]] · 更新于 2026-07-24T08:55:35.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3924)

> 标签：#jira/label/rta-bip-rh

## 描述

Ticket [RH-14736 ](https://rtahotline.etas.com/jira/browse/RH-14736)is reported and is confirmed as defect of **RTA-CAR 12.8**. This issue is resolved in **RTA-CAR 12.10**

**![[RTAXIP-3924-image-2026-07-20-17-39-22-119.png]]**

So that we need to verify this information with **RTA-CAR 12.11** (reopen ticket if necessary).

Input:

- SW BIP base from: [RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886) &#91;RTA-BIP-12.11.0&#93;Porting to RTA-CAR 12.11.0
- feature/[RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886)-rta-bip-12110-porting-to-rta-car-12110

Output: 

- Verify if the resolution of RH ticket is yet available in RTA-CAR 12.11 and compatible to BIP

## 关联

- is cloned by: [[RTAXIP-3925 [RTA-BIP-RH] Check the resolution of RH-16035 - Auto block length for Dem-forwarded NvM blocks with Ea device]]
- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]
- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

## 评论

> [!note]+ 2026-07-24 02:56 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> {*}Issue reported in RH-14736 d{*}{*}escription{*}{*}:{*} Conf-gen file: “ _{color:#ff0000}RTA_BIP_NvM_EcucValues.arxml{color}_ ” is generate "Rte_NvMNotifyJobFinished__" with wrong naming convention.
>
> This led to RTA_BSW generate wrong block naming and function name of "NvMSingleBlockCallBack” cannot be mapped between BSW-gen and RTE-gen
>
> Issue is solved in {color:#00875a}*RTA-CAR 12.11.0*{color}, SW build error and "Rte_NvMNotifyJobFinished__" block naming convention had been resolved when execute Conf-Gen and RTA-BSW gen step:
>
> ![[RTAXIP-3924-image-2026-07-24-09-50-50-808.png]]
>
> ![[RTAXIP-3924-image-2026-07-24-09-54-25-655.png]]
>
> RTA_BSW gen log:
>
> [^rta-bsw.log]
>
> RTA_RTE gen log:
>
> [^rta-rte.log]
>
> Scons SW build log:
>
> [^2026_07_23_191014_currentlog.log]

-------

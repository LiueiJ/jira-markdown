---
jira_key: RTAXIP-3829
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3829"
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
created: "2026-07-02T03:23:40.000+0000"
updated: "2026-07-27T11:53:32.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

Ticket [RH-13992](https://rtahotline.etas.com/jira/browse/RH-13992) is reported and is confirmed as defect of RTA-CAR 12.8, 12.9. This issue will fixed in RTA-CAR 12.11

So that we need to verify our test case with RTA-CAR 12.11

Input:

- SW BIP base from: [RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886) &#91;RTA-BIP-12.11.0&#93;Porting to RTA-CAR 12.11.0
- feature/[RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886)-rta-bip-12110-porting-to-rta-car-12110

Output: 

- Verify if the resolution of RH ticket is yet available in RTA-CAR 12.11 and compatible to BIP

## 关联

- is cloned by: [[RTAXIP-3860 [RTA-BIP-RH] Check the resolution of RH-14634 - Gen BSW Code gen get error after generating RTE Code Gen]]
- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]
- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

## 评论

> [!note]+ 2026-07-27 11:51 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> **Issue Description from RH-13992:** 
>
> **Problem description**
> ==============
> The function PduR_GwMcTx_Transmit_Func is called to trigger transmit but lower layer (CANTP) is not IDLE state.
>
> **Root cause**
> ========
> PduR_GwMcTx_Transmit_Func is triggered to transmit by **PduR_GF_Tp_TxConfirmation_Func** but state of lower layer (CANTP) is not IDLE. There is no mechanism to call back to transmit. Just called by CanTp_TxConfirmation after the second request store in Queued.
>
> ----------
>
> Issue is solved in {color:#00875a}*RTA-CAR 12.11.0*{color}, 
>
> Solution:
>
> In {*}CanTp{*}: Move CanTp_SubState = CANTP_IDLE to before PduR_CanTpTxConfirmation call, so the channel is ready when PduR immediately triggers the next transmission from within the callback. [ARCALM-27556] 
>
> ![[RTAXIP-3829-image-2026-07-27-17-38-10-930.png]]
>
> Test executed and pass: 
> | [Testcase SWTS_BIP_TpGw_025: Queued physical requests | #i__-174398368_201] | pass |
> | [Testcase SWTS_BIP_TpGw_026: Parallel Queued physical request with segmented data | #i__-174398368_322] | pass |
> | [Testcase SWTS_BIP_TpGw_045: Parallel Queued physical request with segmented data - 2 | #i__-174398368_473] | pass |
> | [Testcase SWTS_BIP_TpGw_046: Parallel Queued physical request with segmented data - 3 | #i__-174398368_624] | pass |
> | [Testcase SWTS_BIP_TpGw_048: Parallel Queued physical request with segmented data - 4 | #i__-174398368_775] | pass |
> | [Testcase SWTS_BIP_TpGw_044: Parallel Queued physical Response with segmented data | #i__-174398368_916] | pass |
>
> Test report attached:
>
> [^T16_GW_report.html]

-------

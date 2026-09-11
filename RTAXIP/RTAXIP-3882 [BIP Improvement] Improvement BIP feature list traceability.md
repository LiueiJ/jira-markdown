---
jira_key: RTAXIP-3882
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3882"
server: etas
kind: motivation
type: Task
status: Review
priority: Medium
project: RTAXIP
assignee: "[[Le_Thi_Huong_Giang_(MSETA-Hub-CN)|Le Thi Huong Giang (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: []
fix-versions: [RTA-BIP-cdes-tc397tk-1211, RTA-BIP-cdes-tc397tk-1290-r2.0]
epic: null
parent: null
created: "2026-07-13T03:28:42.000+0000"
updated: "2026-09-10T04:18:23.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Motivation**: 

- Our team added trace tag for feature list but it isn't good enough

![[RTAXIP-3882-image-2026-07-13-10-15-38-773.png]]

- **Problem**:
  - 1 tag contains many sub items (requirements)
  - We can't ensure that all sub-items have software requirement, test/review.

**Expectation:**

- 1 tag only have 1 item
- Define Plan for test to cover updated tags (include task, description of each tasks)

## 评论

> [!note]+ 2026-09-10 03:55 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> Dear [[Huynh_Quang_Truong_(MSETA-Hub-CN)|Huynh Quang Truong (MS/ETA-Hub-CN)]] ,
>
> We have create PR: [Feature/RTAXIP-3882 improve bip feature list traceability - Pull Request #642 - Bitbucket (etas-dev.com)](https://bitbucket.etas-dev.com/projects/RTAENG/repos/autosar_rta_xip/pull-requests/642/overview)
>
> Please use this file to support your review: [^RTAXIP3882_Checking.xlsx]
>
> Thank you in advance!

-------

> [!note]+ 2026-09-09 14:44 · [[Le_Thi_Huong_Giang_(MSETA-Hub-CN)|Le Thi Huong Giang (MS/ETA-Hub-CN)]]
> Dear anh [[Huynh_Quang_Truong_(MSETA-Hub-CN)|Huynh Quang Truong (MS/ETA-Hub-CN)]],
>
> We have found some points that needs to be updated. Could you please pause your review activities and wait until anh Nam and I confirm that the updates are completed and you can resume the review?
>
> Thank you so much for your understanding.

-------

> [!note]+ 2026-09-09 14:38 · [[Le_Thi_Huong_Giang_(MSETA-Hub-CN)|Le Thi Huong Giang (MS/ETA-Hub-CN)]]
> Dear anh [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]],
>
> I have run traceability check and found some findings that need you to verify and update:
>  * Content of excel file as below but in repo **{color:#0747a6}STRS 039{color}** is trace to {color:#ff8b00}*SWRS_BIP_DIAG_004*{color} too.
>
> ![[RTAXIP-3882-image-2026-09-09-21-21-33-725.png]]![[RTAXIP-3882-image-2026-09-09-21-25-05-201.png]]
>  * Content of excel file as below but in repo **{color:#0747a6}STRS 099{color}** is **{color:#ff8b00}not trace{color}** to any SWRS, **{color:#0747a6}STRS 101{color}** trace to **{color:#ff8b00}SWRS_BIP_XCP_ON_CAN_005{color}** and {*}{color:#ff8b00}SWRS_BIP_XCP_ON_ETH_005{color}{*}.
>
> ![[RTAXIP-3882-image-2026-09-09-21-27-56-054.png]]
>
> ![[RTAXIP-3882-image-2026-09-09-21-26-49-365.png]]
>
> ![[RTAXIP-3882-image-2026-09-09-21-28-57-384.png]]
>  * With WDGM, the content in repo is correct. Could you please help me update the content in excel file as below?
>
> ![[RTAXIP-3882-image-2026-09-09-21-31-06-149.png]]![[RTAXIP-3882-image-2026-09-09-21-32-22-690.png]]
>
> Once you have completed the updates, I will rerun the traceability check. If the contents in two places are consistent, I will inform the reviewer that they can start the review.
>
> Thank you so much.

-------

> [!note]+ 2026-09-09 12:40 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> Dear Reviewer [[Huynh_Quang_Truong_(MSETA-Hub-CN)|Huynh Quang Truong (MS/ETA-Hub-CN)]] ,
>
> We have note down improvement need and related description for **feature list** and **SWRS** into this file: [^RTAXIP3882_Checking.xlsx]
>
> The file is organized base on module. Please use it for your review, thank you.

-------

> [!note]+ 2026-09-09 07:14 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> Update below Pdu ID based on current BIP configuration:
>
> ![[RTAXIP-3882-image-2026-09-09-14-13-26-799.png]]
>
>
>
> ![[RTAXIP-3882-image-2026-09-09-14-13-57-415.png]]
>
> ![[RTAXIP-3882-image-2026-09-09-14-14-15-272.png]]
>
> ![[RTAXIP-3882-image-2026-09-09-14-14-26-084.png]]

-------

---
jira_key: RTAXIP-3373
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3373"
server: etas
kind: motivation
type: Change Request
status: Closed
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Hoang_Danh_(MSETA-Hub-CN)|Nguyen Hoang Danh (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2026-03-24T02:22:51.000+0000"
updated: "2026-07-09T05:26:24.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Background:**

In BIP, KeyM_MainBackgroundFunction and rba_EthTls_BackgroundMainFunction are performed in Os_Cbk_Idle. This isn't good design. They should be run can be controlled by Os Background Task

![[RTAXIP-3373-image-2026-03-24-09-25-08-601.png]]

 

**Action:**

- Implementation shall be fixed in latest BIP
- For running BIP projects, this also needs to be checked, information fowards to all PjM.

## 关联

- relates to: [[RTAXIP-3865 [XIP] Change request]]
- is satisfied by: [[RTAXIP-3499 [RTA-BIP-UC][Improvement] Move mainfunctions in Os_Cbk_Idle to real Background Task]]

## 评论

> [!note]+ 2026-05-03 09:41 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> closed as RTAXIP-3499 was done

-------

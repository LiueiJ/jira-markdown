---
jira_key: RTAXIP-3797
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3797"
server: etas
kind: motivation
type: Story
status: Closed
priority: Medium
project: RTAXIP
assignee: ""
reporter: "[[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: [RTA-BIP-cdes-tc397tk-1290-r2.0]
epic: null
parent: null
created: "2026-06-25T04:10:53.000+0000"
updated: "2026-07-27T07:05:55.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Context:**

During RTE generation, I find that there are 3 BSWMD files of rba_CryptoCCL included in the project. One of them is the official file, the other 2 are SrcFix files.

 

**Impact:**

2 Rte exclusive areas of rba_CryptoCCL are using information from SrcFix/gen file, which will cause error if we no longer include SrcFix files during RTE generation.

 

**Suggested Fix:**

- Remove SrcFix during RTE generation.

![[RTAXIP-3797-image-2026-06-25-11-32-20-003.png]]

- Add resource filter to remove everything related to SrcFix from project in the future.

![[RTAXIP-3797-image-2026-06-25-11-33-30-173.png]]

![[RTAXIP-3797-image-2026-06-25-11-34-02-366.png]]

- Remove 2 exclusive areas that mapped to SrcFix/gen file, or map them to other file.

![[RTAXIP-3797-image-2026-06-25-11-39-41-746.png]]

## 关联

- is satisfied by: [[RTAXIP-3884 [BIP][12.9.0][BIP Issue] SrcFix inclusion during RTE gen]]

## 评论

> [!note]+ 2026-06-25 06:24 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Thanks [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]  for reporting this. I move it to CNN Epic (for China need)

-------

> [!note]+ 2026-06-25 04:48 · [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]
> Dear brother [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] , please help review this issue and apply fix to BIP.

-------

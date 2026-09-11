---
jira_key: RTAXIP-3372
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3372"
server: etas
kind: motivation
type: Bug
status: Closed
priority: High
project: RTAXIP
assignee: "[[Le_Thi_Huong_Giang_(MSETA-Hub-CN)|Le Thi Huong Giang (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2026-03-24T01:48:24.000+0000"
updated: "2026-04-23T07:45:08.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Background:**

In BIP, this line is wrong. **NetworkHandle is ComM Channel ID, NM_NUMBER_OF_CHANNELS is max NM channels**. When some of ComM channels have NM variant as None (not all channels have NM feature), may not enter the StateChangeIndication. For example, NetworkHandle is 4, but NM_NUMBER_OF_CHANNELS is 2.

**![[RTAXIP-3372-image-2026-03-24-09-49-40-551.png]]**

**Action:**

- Implementation shall be fixed in latest BIP
- For running BIP projects, this also needs to be checked, information fowards to all PjM.

## 关联

- is fixed by: [[RTAXIP-3401 [RTA-BIP-UC] Wrong Usage  of NM_NUMBER_OF_CHANNELS in Nm_StateChangeIndication]]

## 评论

> [!note]+ 2026-04-23 07:45 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> closed as RTAXIP-3401 is done

-------

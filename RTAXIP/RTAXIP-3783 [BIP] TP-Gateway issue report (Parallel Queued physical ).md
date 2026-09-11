---
jira_key: RTAXIP-3783
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3783"
server: etas
kind: motivation
type: Story
status: Closed
priority: Medium
project: RTAXIP
assignee: "[[Vo_Quoc_Tien_(MSETA-Hub-CN)|Vo Quoc Tien (MS/ETA-Hub-CN)]]"
reporter: "[[Vo_Quoc_Tien_(MSETA-Hub-CN)|Vo Quoc Tien (MS/ETA-Hub-CN)]]"
tags: [jira/label/bip, jira/label/rta-bip-uc]
fix-versions: [RTA-BIP-cdes-tc397tk-1290-r2.0]
epic: null
parent: null
created: "2026-06-16T08:36:47.000+0000"
updated: "2026-07-07T10:28:58.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

I encountered an issue when rerunning the CALP script tests for the TP gateway:

The parallel queuing segmented data feature (multiple-frame) does not work in BIP package version 12.9.0.

The following test cases failed: SWTS_BIP_TpGw_025, SWTS_BIP_TpGw_026, SWTS_BIP_TpGw_045, SWTS_BIP_TpGw_046, SWTS_BIP_TpGw_048.

![[RTAXIP-3783-image-2026-06-16-15-56-03-664.png]]

## 关联

- is satisfied by: [[RTAXIP-3818 [BIP] TP-Gateway issue report (Parallel Queued physical )]]

## 评论

> [!note]+ 2026-06-16 08:59 · [[Vo_Quoc_Tien_(MSETA-Hub-CN)|Vo Quoc Tien (MS/ETA-Hub-CN)]]
> Hi [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> I have created a ticket to follow up on the issue reported for the TP Gateway module.
>
> Please review it and add a ticket for BIP_NEED. Thank you.

-------

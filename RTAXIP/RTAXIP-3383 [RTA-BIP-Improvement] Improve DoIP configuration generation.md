---
jira_key: RTAXIP-3383
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3383"
server: etas
kind: motivation
type: Task
status: Open
priority: Medium
project: RTAXIP
assignee: ""
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2026-03-26T03:56:47.000+0000"
updated: "2026-05-04T01:03:30.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Background**: In TC397 BIP project, There any many manual change/review inside generated RTA_BIP_DoIP_EcucValues.arxml.

**IMPACT**:

- - This is make our solution is inefficient, not-friendly, not easy to use and re-use.
  - User feel our tool isn't good.

Input/Info:

1) In [RTAXIP-3264](https://jira.etas-dev.com/browse/RTAXIP-3264), Some configuration was removed to solve conf-gen error but the output RTA_BIP_DoIP_EcucValues.arxml isn't good.

![[RTAXIP-3383-image-2026-03-26-11-12-19-485.png]]

**TODO**:

- Check DoIP configuration generation
- Try to generate DoIP module automatically by RTA-CAR Config-gen
- Report to hotline if there is any issue/gap/unsupported feature.

**Expected outcome:**

- No Change in RTA_BIP_DoIP_EcucValues.arxml after conf-gen.
- Regression test without any error.
- A DFlash dump analysis script is available for offline investigation of field issues without altering the original target state.
- The overall solution improves feasibility assessment, technical transparency, and field troubleshooting efficiency for BIP projects using TC397.

## 关联

- is a follow-up of: [[RTAXIP-3264 Fix DoIP config-gen error - RH-14335]]

## 评论

> [!note]+ 2026-05-04 01:03 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] is doing it

-------

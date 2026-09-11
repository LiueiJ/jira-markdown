---
jira_key: RTAXIP-3791
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3791"
server: etas
kind: motivation
type: Bug
status: Closed
priority: Highest
project: RTAXIP
assignee: "[[Nguyen_Hoang_Danh_(MSETA-Hub-CN)|Nguyen Hoang Danh (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: [RTA-BIP-cdes-tc397tk-1290-r2.0]
epic: null
parent: null
created: "2026-06-18T09:42:26.000+0000"
updated: "2026-07-13T02:58:36.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

Thank [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] and [[XU_Yinchuan_(ETAS-ECMXSF-CN)|XU Yinchuan (ETAS-ECM/XSF-CN)]] for your finding.

**Issue #1**: During implement new "NvM Multicore" feature, we add new NVMBlock0_Core1 and add static configuration. This will break our BIP workflow as we bypassed Config-gen step.

![[RTAXIP-3791-image-2026-06-18-16-40-27-696.png]]

 

![[RTAXIP-3791-image-2026-06-23-10-35-31-686.png]]

![[RTAXIP-3791-image-2026-06-23-10-39-56-279.png]]

![[RTAXIP-3791-image-2026-06-23-10-35-42-121.png]]

**Expectation**: Please check and update and try to run config-gen for the NvBlock.

**Issue #2**: Error when generating BSW Source:

![[RTAXIP-3791-image-2026-06-23-14-14-54-635.png]]

## 关联

- relates to: [[RTAXIP-3792 [Workflow Bug] Use Config-gen for NVMBlock0_Core1]]

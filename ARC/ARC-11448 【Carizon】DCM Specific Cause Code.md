---
jira_key: ARC-11448
jira_url: "https://jira.etas-dev.com/browse/ARC-11448"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: ""
reporter: fet1cgd4
tags: [Product]
components: []
fix-versions: []
epic: null
parent: null
created: "2025-06-27T06:06:32.000+0000"
updated: "2026-06-18T08:39:10.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-11448 【Carizon】DCM : Specific Cause Code

> [!jira] Canceled ·  ·  · 更新于 2026-06-18T08:39:10.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-11448)

> 标签：#jira/label/product

## 描述

**Carizon** has a OEM scenario request Etas tooling support below function:

1.When ETAS tool is needed to implement DCM NRC 0x22, Dcm supports adding an additional self in the negative response message to store the specific reason for replying to 0x22,

2.It is necessary to add DCM.NC22_SPECIFIC_CAUSE-CODE enable configuration on the tool configuration to determine whether to enable specific functionality and interfaces for specific reasons,

3.Static code is required to provide the Dcm_FirstSpecificCauseCode user interface and obtain the specific reason when the Dcm protocol stack returns NRC 0x22;

Note:current customer is switching to use RTA CAR12.3.3;

ETAS CN hub has provide the methods for modifying static code and verified well wit customer , however, long term solution (including the tooling chain & static code modification) expected for SOP quality grantee.

## 关联

- relates to: [[ARC-9493 ETCN - Customers & CN Market Requirements for RTA-CAR Product]]

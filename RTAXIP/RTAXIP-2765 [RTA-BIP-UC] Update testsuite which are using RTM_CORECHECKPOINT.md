---
jira_key: RTAXIP-2765
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2765"
server: etas
kind: motivation
type: Bug
status: Closed
priority: High
project: RTAXIP
assignee: ""
reporter: "[[Huynh_Quang_Truong_(MSETA-Hub-CN)|Huynh Quang Truong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2025-11-21T08:42:58.000+0000"
updated: "2026-03-23T02:55:38.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

#### **1. Motivation**

- **Context**: Testsuite (EcuMBswM) is using RTM_CORECHECKPOINT to log the timing of software like: Startup, shutdown...
- **Problem**: 
  - Current testsuite takes only the end checkpoint, conclude it as the final time report. Missing the start checkpoint.
  - Example:
    - Incorrect Test: 

- - - - RTM_CORECHECKPOINT_CORE_COMRUN  reports to Rtm_CoreLifecycle = 1000 ticks
 - RTM_CORECHECKPOINT_CORE_STARTU reports to Rtm_CoreLifecycle = 10 ticks
 - Time report from startup to COMRUN equals to 1000 ticks
    - Correct Test: 
 - RTM_CORECHECKPOINT_CORE_COMRUN  reports to Rtm_CoreLifecycle = 1000 ticks
 - RTM_CORECHECKPOINT_CORE_STARTU reports to Rtm_CoreLifecycle = 10 ticks
 - Time report from startup to COMRUN equals to 1000 - 10 ticks
- **Impact**: Testing report is incorrect. Software can't detect the correct timing of software.

#### **2. Proposed Change**

- Review and update the calling of checkpoint in software
- Update testsuite, using start checkpoint and end checkpoint when using Rtm checkpoint.

#### **3. Impact Analysis with Confirmation**

Use the table below to confirm which areas will be affected:

Area
Description
Impact

Requirement
Will new requirements be added or existing ones updated?
No

Design
Will architecture or interface definitions change?
No

Configuration/

Integration
Will new parameters or software/ templates be introduced?
No

Testing
Will new test cases be needed or regression testing impacted?
Yes

Documentation
Will user guides or onboarding materials be updated?
No

Toolchain / CI
Will automation scripts or CI pipelines be affected?
No

Stakeholders
Will this improve delivery or collaboration with partners?
No

Compliance
Will this help meet internal/external process standards or audit readiness?
No

 

### ✅ **Definition of Done (DoD)**

- Software reviewed and approved
- Test results documented

## 关联

- is satisfied by: [[RTAXIP-3321 [RTA-BIP-UC] Update testsuite which are using RTM_CORECHECKPOINT]]

## 评论

> [!note]+ 2026-03-23 02:55 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> close due to RTAXIP-3321 was done

-------

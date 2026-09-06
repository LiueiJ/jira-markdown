---
jira_key: RTAXIP-3418
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3418"
server: etas
kind: motivation
type: Story
status: Closed
priority: High
project: RTAXIP
assignee: ""
reporter: lno2hc
tags: [BIP_NEEDs]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-30T06:56:48.000+0000"
updated: "2026-07-09T05:26:24.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3418 [RTA-BIP-UC] NvM master/multicore - motivation: always ask by customer

> [!jira] Closed · High ·  · 更新于 2026-07-09T05:26:24.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3418)

> 标签：#jira/label/bip_needs

## 描述

#### 1. **Motivation**

- **Context**: This NEED originates from repeated customer requests always <via email and hotline>, specifically regarding multicore support in NvM. It has been a recurring topic during project acquisition and technical workshops.
- **Problem**: The current BIP-1270 lacks formalized support for NvM master/multicore configurations. There is no requirement, design, or test specification to ensure correct behavior in multicore environments.
- **Impact**:
  - **Xpeng is requesting this feature --> High Priority**
  - **Developers** face uncertainty when integrating NvM in multicore setups, leading to workaround implementations.
  - **Testers** lack coverage for multicore scenarios, risking to show NvM multicore capability/  undetected defects.
  - **Stakeholders** experience delays and reduced confidence in product readiness.
- **Urgency**: Without addressing this, multicore projects may face integration failures/ limitation, increased support load, and non-compliance with ETAS process standards.

#### 2. **Proposed Change**

- Update BIP feature list
- Create formal requirement for NvM master/multicore support.
- Update design documentation to define behavior and interfaces for multicore scenarios.
- Extend configuration templates to support multicore parameters.
- Develop test specifications and regression tests for multicore use cases.
- Update User Manual to include guidance for multicore configuration and integration.

#### 3. **Impact Analysis with Confirmation**

Area
Description
Impact
Remarks

Requirement
Will new requirements be added or existing ones updated?
Yes
 

Design
Will architecture or interface definitions change?
Yes
 

Configuration
Will new parameters or templates be introduced?
Yes
?Cobra updates

Testing
Will new test cases be needed or regression testing impacted?
Yes
 

Documentation
Will user guides or onboarding materials be updated?
Yes
 

Toolchain / CI
Will automation scripts or CI pipelines be affected?
Possibly
 

Stakeholders
Will this improve delivery or collaboration with partners?
Yes
 

Compliance
Will this help meet internal/external process standards or audit readiness?
Yes
PEP 1.6.1

#### ✅ Definition of Done (DoD)

- Requirement document reviewed and approved + BIP feature list updated.
- Design updated with multicore support details (documents of concept at least).
- Configuration templates extended.
- Test specification and results documented.
- User Manual updated with multicore integration guidance.

## 关联

- relates to: [[RTAXIP-3865 [XIP] Change request]]

## 评论

> [!note]+ 2026-04-03 16:12 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]] : is this duplicated?

-------

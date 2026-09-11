---
jira_key: RTAXIP-2641
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2641"
server: etas
kind: motivation
type: Story
status: Closed
priority: High
project: RTAXIP
assignee: "[[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc, jira/label/xip-projects]
fix-versions: [RTA-BIP-cdes-tc397tk-1290-r1.0]
epic: null
parent: null
created: "2025-10-23T05:49:01.000+0000"
updated: "2026-07-07T11:53:40.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

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

- relates to: [[RTAXIP-3369 [Xpeng-bip]-cde-TC4Z9TK-1290-p2-MC-Mem]]
- is satisfied by: [[RTAXIP-3415 [RTA-BIP-UC] NvM master/multicore - Create Test Spec]]
- is satisfied by: [[RTAXIP-3417 [RTA-BIP-UC] NvM master/multicore - Integration NvM/RTE/OS (include Manual)]]
- is satisfied by: [[RTAXIP-3419 [RTA-BIP-UC] NvM master/multicore - Create Test Result]]
- is satisfied by: [[RTAXIP-3426 [RTA-BIP-UC] NvM master/multicore Analyze and propose design/solution]]

## 评论

> [!note]+ 2026-03-26 07:22 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> changed priority: low -> High
>
> ![[RTAXIP-2641-image-2026-03-26-14-21-58-794.png]]

-------

> [!note]+ 2025-10-29 02:24 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Thanks [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]],
>
> NEEDs_seed review, 12.29.2025:
>  # Changed NEEDs_seed to "BIP_NEEDs" backlog.
>  # plan for RTA-BIP-cdes-tc397tk-1290
>  # Motivation/priority: Lowest/ not urgent

-------

> [!note]+ 2025-10-29 00:30 · [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]
> Hi [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] , that's why we call it Pre-Integration. We shall prepare in advance, not when request come we do it.
>
> Advantage:
>  * we can know the new feature if it's expected.
>  * we can know the new feature if there is a bug.
>  * we can know what's the status of the new feature, we can say we have it in acquisition phase.
>  * we need to regular add new feature into BIP, as BIP is a feature pool, we can use feature pool to test new RTA-CAR version. 
>
> 1. One Geely project, base on RTA-CAR12.6.0 used this solution.
>
> 2. It's not urgent. I prefer implement it on RTA-CAR12.9.0. 

-------

> [!note]+ 2025-10-28 10:35 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> **[Review NEEDs_seed if it's confirmed to BIP_NEEDs]**
>
> Hi [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]], 
>  # Could you help to check and/or refine the BIP NEEDs_Seed for NvM Multicore related as it's your initial request for backlog of BIP development?
>
>  # Specially for motivation/ obviously evident of customer requests <email, hotline, wechat etc>
>  # Please also share the priority to BIP development.
>
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]], [[Vo_Quoc_Tien_(MSETA-Hub-CN)|Vo Quoc Tien (MS/ETA-Hub-CN)]], [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]] : also please review,

-------

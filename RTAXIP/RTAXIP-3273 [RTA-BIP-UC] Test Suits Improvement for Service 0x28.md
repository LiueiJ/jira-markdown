---
jira_key: RTAXIP-3273
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3273"
server: etas
kind: motivation
type: Change Request
status: Closed
priority: High
project: RTAXIP
assignee: ""
reporter: aiu2sgh
tags: [RTA-BIP-UC]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-05T07:29:41.000+0000"
updated: "2026-03-13T10:57:10.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3273 [RTA-BIP-UC] Test Suits Improvement for Service 0x28

> [!jira] Closed · High ·  · 更新于 2026-03-13T10:57:10.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3273)

> 标签：#jira/label/rta-bip-uc

## 描述

#### 1. **Motivation**

- **Context**:
  - Service 0x28 was updated for BIP 1290 in [RTAXIP-2657](https://jira.etas-dev.com/browse/RTAXIP-2657)
  - But The test suite isn't updated according
- **Problem**: Current BIP quality isn't ensure.
- **Impact**:
  - **Developers** encounter easy to miss these test for service 0x28
  - **Testers** lack coverage for Rx/Tx separation scenarios.
- **Urgency**: Without this test, it will take longer time for review and accept the pull request.

#### 2. **Proposed Change**

- Update the automation script test for service 28 scenarios which is implemented in ticket: [RTAXIP-2638](https://jira.etas-dev.com/browse/RTAXIP-2638)  and test again

- - Enable Rx / Disable Tx for NM
  - Enable Rx / Disable Tx for Normal CAN and NM
  - Disable Rx / Enable Tx for NM
  - Disable Rx / Enable Tx for Normal CAN and NM
- Log capture need be provided after testing

#### 3. **Impact Analysis with Confirmation**

Area
Description
Impact

Requirement
Will new requirements be added or existing ones updated?
Yes

Design
Will architecture or interface definitions change?
No

Configuration
Will new parameters or templates be introduced?
No

Testing
Will new test cases be needed or regression testing impacted?
Yes

Documentation
Will user guides or onboarding materials be updated?
NO

Toolchain / CI
Will automation scripts or CI pipelines be affected?
Possibly

Stakeholders
Will this improve delivery or collaboration with partners?
No

Compliance
Will this help meet internal/external process standards or audit readiness?
Yes

#### ✅ Definition of Done (DoD)

- Test specification and results documented for all 0x28 scenarios.

**Reference**: Implementation ticket [RTAXIP-2657](https://jira.etas-dev.com/browse/RTAXIP-2657)

## 关联

- relates to: [[RTAXIP-3284 [BIP] Test Suits improvement for Service 0x28]]
- duplicates: [[RTAXIP-2758 [RTA-BIP][12.8.0] Improve test case for service 28 ]]

## 评论

> [!note]+ 2026-03-13 10:57 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Done as all linked tickets are done

-------

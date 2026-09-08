---
jira_key: RTAXIP-2661
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2661"
server: etas
kind: motivation
type: Change Request
status: Closed
priority: Medium
project: RTAXIP
assignee: dyn9hc
reporter: had1hc
tags: [RTA-BIP-UC]
components: []
fix-versions: []
epic: null
parent: null
created: "2025-10-29T07:27:04.000+0000"
updated: "2026-07-09T05:26:24.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-2661 [RTA-BIP-UC] Improve Requirements, Test Specification, and Test Results for Eth-COM

> [!jira] Closed · Medium · [[Nguyen_Hoang_Danh_(MSETA-Hub-CN)|Nguyen Hoang Danh (MS/ETA-Hub-CN)]] · 更新于 2026-07-09T05:26:24.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-2661)

> 标签：#jira/label/rta-bip-uc

## 描述

#### **1. Motivation**

Clearly explain **why** this NEED is important. Include:

- **Context**: The customer project is based on the BIP baseline, and the SOW includes Ethernet features (ETH-COM). While BIP has these features, there are no requirements, test specifications, or test reports available for them.
- **Problem**: There are no requirements, test specifications, or test reports for Eth-related features on BIP. It is challenging and time-consuming to perform full testing of the Ethernet features, and it is still not possible to confirm whether these features are functional.
- **Impact**: 
  - **Tester**: Unable to confirm if the Ethernet feature is functional.
  - **Stakeholders** face delivery risks and reduced confidence in product quality.
- **Urgency**: Without addressing these gaps, future projects based on BIP that require Ethernet may face delays, encounter repeated errors during Ethernet testing, and experience quality issues.

#### **2. Proposed Change**

- Add Eth-related requirements, Test Specs and Test Report. ( can reused from Magna for Eth-Com, Eth-SomeIP)
- Add automation test for Eth features.

#### **3. Impact Analysis with Confirmation**

Use the table below to confirm which areas will be affected:

Area
Description
Impact

Requirement
Will new requirements be added or existing ones updated?
Yes

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
Yes, auto test for Eth

Stakeholders
Will this improve delivery or collaboration with partners?
Yes

Compliance
Will this help meet internal/external process standards or audit readiness?
Yes

 

### ✅ **Definition of Done (DoD)**

Clearly state what must be delivered for the ticket to be considered complete:

- Requirement document reviewed and approved.
- Test specification created, reviewed and approved.
- Test results documented created, reviewed and approved.
- Automation script is created. ( optional)
- User Manual for Eth-COM (rst format)

**Input:**

- Eth-COM can refer from Magna: manual test case => convert to automation script if can

## 关联

- relates to: [[RTAXIP-3865 [XIP] Change request]]
- clones: [[RTAXIP-2650 China NEEDs Ticket - template]]
- is satisfied by: [[RTAXIP-3590 [RTA-BIP-UC] Create Requirement for ETH-COM]]
- is satisfied by: [[RTAXIP-3591 [RTA-BIP-UC] Create Test spec for ETH-COM]]
- is satisfied by: [[RTAXIP-3592 [RTA-BIP-UC] Create test script and test result for ETH-COM]]

## 评论

> [!note]+ 2025-12-29 10:48 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> [[Ho_Anh_Dang_(MSETA-Hub-CN)|Ho Anh Dang (MS/ETA-Hub-CN)]] - could you share the Inputs reference, derived solution for this needs from the Magna project?

-------

> [!note]+ 2025-10-29 07:52 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Ho Anh Dang (MS/ETA-Hub-CN)]]
> The new NEEDs_Seed ticket is created.
> CC: [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]] , [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] 

-------

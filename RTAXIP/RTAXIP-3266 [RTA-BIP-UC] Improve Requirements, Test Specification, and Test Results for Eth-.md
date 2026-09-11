---
jira_key: RTAXIP-3266
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3266"
server: etas
kind: motivation
type: Story
status: Closed
priority: Medium
project: RTAXIP
assignee: ""
reporter: "[[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2026-03-04T06:47:51.000+0000"
updated: "2026-07-03T08:28:40.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

#### **1. Motivation**

Clearly explain **why** this NEED is important. Include:

- **Context**: The customer project is based on the BIP baseline, and the SOW includes Ethernet features (ETH-SOME/IP). While BIP has these features, there are no requirements, test specifications, or test reports available for them.
- **Problem**: There are no requirements, test specifications, or test reports for Eth-SOME/IP features on BIP. It is challenging and time-consuming to perform full testing of the Ethernet features, and it is still not possible to confirm whether these features are functional.
- **Impact**: 
  - **Tester**: Unable to confirm if the Ethernet feature is functional.
  - **Stakeholders** face delivery risks and reduced confidence in product quality.
- **Urgency**: Without addressing these gaps, future projects based on BIP that require Ethernet may face delays, encounter repeated errors during Ethernet testing, and experience quality issues.

#### **2. Proposed Change**

- Add Eth-Some/IP requirements, Test Specs and Test Report.
- Add automation test for Eth features.(Optional)

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
No

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
- User Manual for Eth-SOME/IP (rst format)

**Input:**

- undefined

## 评论

> [!note]+ 2026-07-03 08:28 · [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]
> close due to duplocate ticket

-------

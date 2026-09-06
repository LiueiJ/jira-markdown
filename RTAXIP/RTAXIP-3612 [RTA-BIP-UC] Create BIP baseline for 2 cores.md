---
jira_key: RTAXIP-3612
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3612"
server: etas
kind: motivation
type: Change Request
status: Open
priority: Medium
project: RTAXIP
assignee: had1hc
reporter: had1hc
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-05-07T07:50:24.000+0000"
updated: "2026-05-18T06:35:57.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3612 [RTA-BIP-UC] Create BIP baseline for 2 cores

> [!jira] Open · Medium · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Ho Anh Dang (MS/ETA-Hub-CN)]] · 更新于 2026-05-18T06:35:57.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3612)

## 描述

###  

Each ticket should include the following sections:

#### **1. Motivation**

Clearly explain **why** this NEED is important. Include:

- **Context**: When engineers port the BIP baseline to another target, they often encounter challenges because the new target has a different number of cores than the baseline (5 cores). This requires them to adjust the configuration to reduce the number of cores. However, this task is error-prone due to a lack of experience and uncertainty about which documents to consult. As a result, the time required for configuration and testing is longer than expected, often requiring the assistance of a senior engineer.
- **Problem**: There is no guide, document, or baseline available for the task of reducing the number of cores in the BIP baseline.
- **Impact**: 
  - Developer/Tester: The task requires a significant amount of time to complete, whereas standardizing all the required steps would free up engineers to focus on higher-value work.
- **Urgency**: The time required for porting in the upcoming project will increase.

#### **2. Proposed Change**

- The software baselines for 1, 2, 3 and 4 cores are created and tested.
- The design of BSW module distribution changes depending on the core configuration.
- The document on how to reduce core is created.

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
Yes

Configuration/

Integration
Will new parameters or software/ templates be introduced?
Yes

Testing
Will new test cases be needed or regression testing impacted?
No

Documentation
Will user guides or onboarding materials be updated?
Yes

Toolchain / CI
Will automation scripts or CI pipelines be affected?
No

Stakeholders
Will this improve delivery or collaboration with partners?
Yes

Compliance
Will this help meet internal/external process standards or audit readiness?
No

!star_yellow.png! Additional Information

Effort Estimation: 60 hours

Affected Version/s: &#91;To be specified by team&#93;

### ✅ **Definition of Done (DoD)**

Clearly state what must be delivered for the ticket to be considered complete:

- Software for 1, 2, 3,  and 4 cores
- BSW modules distribution design
- User Guide on how to reduce core.

## 关联

- clones: [[RTAXIP-3609 [RTA-BIP-UC] Create BIP baseline for 1 core]]
- is cloned by: [[RTAXIP-3613 [RTA-BIP-UC] Create BIP baseline for 3 cores]]

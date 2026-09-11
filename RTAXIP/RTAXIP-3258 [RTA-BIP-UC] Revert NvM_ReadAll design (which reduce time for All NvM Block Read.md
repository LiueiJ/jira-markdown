---
jira_key: RTAXIP-3258
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3258"
server: etas
kind: motivation
type: Change Request
status: Closed
priority: High
project: RTAXIP
assignee: ""
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: [RTA-BIP-cdes-tc397tk-1290-r1.0]
epic: null
parent: null
created: "2026-03-03T02:49:23.000+0000"
updated: "2026-07-07T11:44:53.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

#### **1. Motivation**

Clearly explain **why** this NEED is important. Include:

- **Context**: During optimize the first Nm message timing (For Ecarx), we did some change in design which changing NvM_ReadAll task to background. But Customer doesn't accept this solution and [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]  and [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]  decide to roll-back to old design
- **Problem**: Customer doesn't accept the new solution due to it will increase time for read important blocks which Application needs them
- **Impact**: Revert design for startup sequence
- **Urgency**: Revert t old design which almost customer needs it and the new design isn't good enough.

#### **2. Proposed Change**

- Revert design for startup sequence.

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
Yes

Configuration/

Integration
Will new parameters or software/ templates be introduced?
Yes

Testing
Will new test cases be needed or regression testing impacted?
Yes

Documentation
Will user guides or onboarding materials be updated?
Yes

Toolchain / CI
Will automation scripts or CI pipelines be affected?
Yes

Stakeholders
Will this improve delivery or collaboration with partners?
Yes

Compliance
Will this help meet internal/external process standards or audit readiness?
No

 

### ✅ **Definition of Done (DoD)**

Clearly state what must be delivered for the ticket to be considered complete:

- Software is reverted with old design with reviewed and approved
- Test specification modified, reviewed and approved.
- Get Test results, reviewed and approved.
- Automation script is updated with old design.
- User Manual updated based on old design.

## 关联

- relates to: [[RTAXIP-3187 [RTA-BIP] Check and fix ErrorHook after reset ECU]]
- is satisfied by: [[RTAXIP-3290 [RTA-BIP-UC] Revert NvM_ReadAll design (which reduce time for All NvM Block Read at startup phase)]]

## 评论

> [!note]+ 2026-03-13 10:54 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Done as all linked tickets are closed

-------

> [!note]+ 2026-03-03 03:00 · [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]
> Hi [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] , (y) please revert, thanks.

-------

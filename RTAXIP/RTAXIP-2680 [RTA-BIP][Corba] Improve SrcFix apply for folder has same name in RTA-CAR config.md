---
jira_key: RTAXIP-2680
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2680"
server: etas
kind: motivation
type: Story
status: Open
priority: Low
project: RTAXIP
assignee: ""
reporter: "[[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: [RTA-BIP-cdes-tc397tk-1280]
epic: null
parent: null
created: "2025-11-05T07:44:09.000+0000"
updated: "2026-04-23T08:35:12.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

###  

Each ticket should include the following sections:

#### **1. Motivation**

Clearly explain **why** this NEED is important. Include:

- **Context**: During migrate RTA-BIP, There is an issue related to SrcFix folder. If user change name folder gen bsw to another folder of RTA config, SrcFix can not work.
- **Problem**: It will have an issue can not apply SrcFix when generate another folder of bsw to compare.
- **Impact**: 
  - User got confused when compare 2 folder gen if name config is changed
- **Urgency**: Not important

#### **2. Proposed Change**

Describe **what needs to be done** to address the need:

- Modify source code corba to apply with same name folder gen in RTA-CAR config

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
Yes

Testing
Will new test cases be needed or regression testing impacted?
No

Documentation
Will user guides or onboarding materials be updated?
No

Toolchain / CI
Will automation scripts or CI pipelines be affected?
yes

Stakeholders
Will this improve delivery or collaboration with partners?
No

Compliance
Will this help meet internal/external process standards or audit readiness?
No

 

### ✅ **Definition of Done (DoD)**

Clearly state what must be delivered for the ticket to be considered complete:

- SrcFix can apply for another folder name different with bsw name.

## 评论

> [!note]+ 2026-04-23 08:35 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> Maybe in future release of RTA-CAR srcfix can be replaced by convergence plugin with source fix.

-------

> [!note]+ 2025-11-25 11:28 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> This is new feature of cobra, If should be check and do it later with low priority
>
> --> Remove from sprint 6 to avoid confuse 

-------

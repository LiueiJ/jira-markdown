---
jira_key: RTAXIP-3830
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3830"
server: etas
kind: motivation
type: Change Request
status: Closed
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2026-07-02T06:01:17.000+0000"
updated: "2026-07-09T11:02:45.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

###  

Each ticket should include the following sections:

#### **1. Motivation**

Clearly explain **why** this NEED is important. Include:

- **Context**: There is 1 bug of RTA-CAR 12.9.0 which is confirm by Hotline [RH-14324](https://rtahotline.etas.com/jira/browse/RH-14324)

![[RTAXIP-3830-image-2026-07-02-13-08-08-362.png]]

![[RTAXIP-3830-image-2026-07-02-13-08-31-922.png]]

- **Problem**: IocNeeds.arxml make error when generate RTA-BSW 12.9.0
- **Impact**: user experience/workflow isn't efficient and friendly
- **Urgency**: not urgent

#### **2. Proposed Change**

As confirmation and proposal was shared by hotline, we have workaround solutions:

- Remove **IocNeeds.arxml** before BSW-Gen
- Update Cobra PreBSWGenHook for remove this automatically and update Cobra AfterBSWGenHook to revert this
- NOTE: **IocNeeds.arxml** has to be reverted after BSW-GEN

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
Yes

Documentation
Will user guides or onboarding materials be updated?
Yes

Toolchain / CI
Will automation scripts or CI pipelines be affected?
Update COBRA

Stakeholders
Will this improve delivery or collaboration with partners?
Collaboration with COBRA team

Compliance
Will this help meet internal/external process standards or audit readiness?
No

 

### ✅ **Definition of Done (DoD)**

Clearly state what must be delivered for the ticket to be considered complete: RTA-BSW generation is successful without any manual remove IocNeeds.arxml.

- Update Cobra.
- Test new feature in RTA-CAR 12.9.0.
- Document Cobra flow for new feature.
- Merge into Cobra repository.
- Merge into BIP repository. !check.png!

## 关联

- relates to: [[RTAXIP-3832 [RTA-BIP] Update Cobra Pre/After_BSWGenHook to fix issue IocNeeds.arxml for RTA-CAR 12.9.0]]
- clones: [[RTAXIP-2650 China NEEDs Ticket - template]]

## 评论

> [!note]+ 2026-07-09 11:02 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> done as ticket [RTAXIP-3832] [RTA-BIP] Update Cobra Pre/After_BSWGenHook to fix issue IocNeeds.arxml for RTA-CAR 12.9.0 - Jira (etas-dev.com) is done

-------

> [!note]+ 2026-07-02 06:15 · [[Nguyen_Hoang_Danh_(MSETA-Hub-CN)|Nguyen Hoang Danh (MS/ETA-Hub-CN)]]
> Hi A [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] ,
>
> I have created the BIP_Needs ticket for IocNeeds.arxml issue.
>
> Could you please check this ticket? and move to CNN if need
>
> Thank you.

-------

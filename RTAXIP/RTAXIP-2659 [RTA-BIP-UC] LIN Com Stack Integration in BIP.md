---
jira_key: RTAXIP-2659
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2659"
server: etas
kind: motivation
type: Change Request
status: In Progress
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: [RTA-BIP-cdels-tc397tk-1211]
epic: null
parent: null
created: "2025-10-28T12:13:14.000+0000"
updated: "2026-08-24T02:32:58.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

#### 1. **Motivation**

- **Context**:
  - This NEED originates from customer **Cariad** and hotline ticket [RH-12551](https://rtahotline.etas.com/jira/browse/RH-12551). The issue was reported during LDF file import using RTA-CAR 12.6.0pr1 and confirmed for improvement in 12.8.0.
  - "Huaxu_RTA_BIP_cdels_TC397TK_12110" is in Acquisition phase and this project need Lin communication and plan to start in Sep/2026
- **Problem**:
  - Current BIP doesn't have Lin Stack (include LinIf, LinTp)
  - [RH-12551](https://rtahotline.etas.com/jira/browse/RH-12551) is reported and need to be awared when integrate Lin
- **Impact**:
  - **Developers** don't have reference which make difficult and slow down integation phase.
  - **Testers** don't have enough test cases for Lin testing.
- **Urgency**: Huaxu project will start in Sep/2026 --> we need to have baseline before it.

#### 2. **Proposed Change**.

- Create new develop branch "**RTA_BIP_cdels_TC397TK_1211**" for adding lin
- Update requirement documents to include these improvements (Basic LinIf, LinTp- can refer to ECARX semidrive project for LDF and implementation).
- Validate changes in RTA-CAR 12.11.0 with regression tests for LDF import scenarios.
- Update User Manual and ISOLAR-A documentation for LDF import behavior.

#### 3. **Impact Analysis with Confirmation**

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
Possible

Stakeholders
Will this improve delivery or collaboration with partners?
Yes

Compliance
Will this help meet internal/external process standards or audit readiness?
Yes

#### ✅ Definition of Done (DoD)

- Linif, LinTp are integrated and software are reviewed and approved.
- Requirement and design documents reviewed and approved.
- Regression tests executed for LDF import scenarios.
- User Manual updated with configuration guidance.

**Reference**:

- Hotline Ticket [RH-12551](https://rtahotline.etas.com/jira/browse/RH-12551). (attached hotline ticket [RH-12551.pdf!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/656957/656957_RH-12551.pdf))
- Semidrive project [RTAXIP-3510](https://jira.etas-dev.com/browse/RTAXIP-3510)

## 关联

- satisfies: [[RTAXIP-3959 [RTA-BIP-UC] LIN Com Stack Integration in BIP]]
- is satisfied by: [[RTAXIP-3958 Porting LinIf from Semi Drive project into BIP 12.11.0 - Prepare base project]]

## 评论

> [!note]+ 2026-07-27 02:43 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> "Huaxu_RTA_BIP_cdels_TC397TK_12110" is in Acquisition phase and this project need Lin communication and plan to start in Sep/2026 --> We need prepare for this.

-------

> [!note]+ 2025-10-29 23:21 · [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]
> Hi [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] , let me share more information for Lin stack topic:
>  * Lin Stack is easy to integrate. That's why we never added into BIP before.
>  * Lin Stack is quite stable, no issue at all. 
>  * Lin Stack is not so popular in China market. Not every project has it. 
>  * Also LinTp is rare used, basically CanTp is there.
>  * Lin Stack requires additional license.
>
> But it's fine we add Lin Stack into BIP but with low priority, thanks.

-------

> [!note]+ 2025-10-29 06:40 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> + copied [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]  and [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]:
> What's the reason/motivation to not included LIN for BIP Feature list?

-------

> [!note]+ 2025-10-29 01:59 · [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]
> Hi a [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]],
> Currently, BIP does not have implementation for LIN stack. So we do not have this issue.
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]], Could you help me check we apply  LIN stack or not for improve BIP. If apply LIN stack, we will consider this ticket will be bip_need ticket. 

-------

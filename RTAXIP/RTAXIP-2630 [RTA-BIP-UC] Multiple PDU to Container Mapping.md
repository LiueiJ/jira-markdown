---
jira_key: RTAXIP-2630
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2630"
server: etas
kind: motivation
type: Change Request
status: Open
priority: Low
project: RTAXIP
assignee: "[[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]"
reporter: "[[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-uc]
fix-versions: []
epic: null
parent: null
created: "2025-10-15T08:30:22.000+0000"
updated: "2026-03-08T07:10:30.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

#### 1. **Motivation**

- **Description:** Within this module there are two different approaches of multiplexing several I-PDUs into one resulting PDU to be transferred on a communication bus:
  - **I-PDU Multiplexing** means using the same I-PDU ID transferred from the PDU Router to the Communication Hardware Abstraction Layer with more than one unique layout of the corresponding I-PDU
  - **Multiple PDU to Container Mapping** means collecting several I-PDUs into one Container PDU, which is transferred via the PDU Router as one (large) I-PDU. This has the advantage of the larger frame sizes of newer bus systems, allowing an efficient usage of bandwidth in combination with smaller I-PDU sizes (usually 8 bytes).
In BIP SW, there is a only implementation of **I-PDU Multiplexing ,**  lack of **Multiple PDU to Container Mappin.**

- **Context**: This NEED originated from internal technical discussions and customer expectations, confirmed by Cong (ETAS-ECM/XSF-CN) on 22/10/2025. The topic has been raised multiple times during acquisition and BIP feature alignment sessions bi-weekly with ECM-CN.
  - Jira ticket requested/discussed: [RTAXIP-2630](https://jira.etas-dev.com/browse/RTAXIP-2630)
- **Problem**: The current BIP 1270 software only supports **I-PDU Multiplexing**, which allows multiple layouts for the same I-PDU ID. However, it lacks support for **Multiple PDU to Container Mapping**, which is a more efficient method for utilizing larger frame sizes in modern bus systems.
- **Impact**:
  - **Developers** are limited in optimizing bandwidth usage for newer communication protocols.
  - **Testers** cannot validate container mapping scenarios, leading to gaps in coverage.
  - **Stakeholders** may perceive the product as lacking modern multiplexing capabilities.
- **Urgency**: Without this feature, BIP may fall short in meeting customer expectations and lose competitiveness in projects requiring efficient data packaging.

#### 2. **Proposed Change**

- Introduce support for **Multiple PDU to Container Mapping** in BIP software, BIP feature list.
- Update requirement documents to formally define this feature.
- Extend design to support container PDU structures and mapping logic.
- Modify configuration templates to allow container mapping setup.
- Create test specifications and regression tests for container mapping scenarios.
- Update User Manual with usage guidelines and configuration examples.

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

- Requirement document reviewed and approved.
- Test specification and results documented.
- Test result
- SW implementation with review and approve
- Automation Scipt
- User Manual updated with container mapping guidance.
- Refer ( need check again): from Liu Jie

 

CC: [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]  [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]

## 关联

- relates to: [[RTAXIP-2633 [RTA-BIP][12.8.0] Discuss about improvement of BIP]]
- is parent of: [[RTAXIP-2631 BIP Seeds]]

## 评论

> [!note]+ 2025-10-27 06:14 · [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]]
> Hi [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] 
> For implementation of Multiple PDU to Container Mapping, there will be some points we will apply for this requirement. Could you help to confirm that we will follow with reason above or not
> *1. Choose tranmission of dynamic containers with short header, *not static container:
>  - Overview:
> The Container layout can either be dynamically defined using headers in front of the contained I-PDUs or statically without headers but defined static positions for contained I-PDUs.
> Dynamic Container:
> ![[RTAXIP-2630-image-2025-10-28-18-05-31-471.png]]
> Static Container:
> I-PDus continouly without
>  - Motivation:
> ![[RTAXIP-2630-image-2025-10-28-18-05-55-022.png]]
>
> . **Choose tranmission of dynamic containers with Quêud collection semantics** , not choose Triggered Transmission and Last-is-Best semantics
>  - Motivation:
> ![[RTAXIP-2630-screenshot-3.png]]

-------

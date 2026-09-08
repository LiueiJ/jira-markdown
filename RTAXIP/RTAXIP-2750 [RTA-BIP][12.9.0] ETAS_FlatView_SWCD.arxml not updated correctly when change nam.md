---
jira_key: RTAXIP-2750
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2750"
server: etas
kind: motivation
type: Story
status: Closed
priority: Low
project: RTAXIP
assignee: gua6hc
reporter: lno2hc
tags: [RTA-BIP-RH]
components: []
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2025-11-18T07:53:20.000+0000"
updated: "2026-07-27T02:03:02.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-2750 [RTA-BIP][12.9.0] ETAS_FlatView_SWCD.arxml not updated correctly when change name SWC - RH-15358

> [!jira] Closed · Low · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]] · 更新于 2026-07-27T02:03:02.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-2750)

> 标签：#jira/label/rta-bip-rh

## 描述

###  

Each ticket should include the following sections:

#### **1. Motivation**

Clearly explain **why** this NEED is important. Include:

- **Context**: During generate bsw, if another SWC is updated and some SWC is deleted, the previous SWC which deleted still keep in ETAS_FlatView_SWCD.arxml and will be generate another.
- **Problem**: There will be confused when user add another SWC instead of.
- **Impact**: 
  - User got confuse when 2 SWC be generated in ETAS_FlatView_SWCD.arxml
- **Urgency**: Medium

#### **2. Proposed Change**

Describe **what needs to be done** to address the need:

- Check the issue and raise rta-hotline if it's an issue

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
No

Stakeholders
Will this improve delivery or collaboration with partners?
No

Compliance
Will this help meet internal/external process standards or audit readiness?
No

 

 

 

Refer to: [RH-15358](https://rtahotline.etas.com/jira/browse/RH-15358)

## 关联

- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]

## 评论

> [!note]+ 2026-07-24 08:38 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> **Issue Description in RH-15358:** After BSW code generation, the EcuExtract(System_EcuExtr.arxml) is updated.
>
> More information: In BIP project, there are two WdgM SWCD arxml files: 
>
> _WdgM_Cfg_SWCD.arxml_
>
> _WdgM_Master_Cfg_SWCD_missing.arxml_
>  * Manual execution will only generate one CPT_WdgM in EcuExtract.
>  * EcuExtract as part of BSW code generation will generate two CPT_WdgM which is wrong, the splitable doesn’t work and it doesn’t merge the two sources.
>
> Issue is solved in {*}RTA-CAR 12.11.0{*}, after RTA_BSW EcuExtract is trigger automatic but will not generate two CPT_WdgM.
>
> ![[RTAXIP-2750-image-2026-07-24-15-34-25-237.png]]
>
> ![[RTAXIP-2750-image-2026-07-24-15-35-01-113.png]]
>
> ![[RTAXIP-2750-image-2026-07-24-15-36-35-663.png]]
>
>
>
> RTA_BSW gen log:
>
> [^rta-bsw.log]
>
> System extract gen:
>
> [^System_EcuExtr.arxml]

-------

> [!note]+ 2026-03-09 07:10 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> After checking with [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]] , The issue still happen on CAR 12.9.0. Let check this issue wiht the BIP 12.9.0

-------

> [!note]+ 2026-02-24 09:28 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] Could you check this for more details? 

-------

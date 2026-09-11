---
jira_key: RTAXIP-3320
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3320"
server: etas
kind: motivation
type: Story
status: Closed
priority: High
project: RTAXIP
assignee: "[[Le_Thi_Huong_Giang_(MSETA-Hub-CN)|Le Thi Huong Giang (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/xip-projects]
fix-versions: []
epic: null
parent: null
created: "2026-03-16T06:34:44.000+0000"
updated: "2026-07-17T07:36:08.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

Currently no existing cobra script for target RH850 U2A16 available. Target specific adaption needs to be done for Cariad MQB project. Related Script derived from [Branches for RTA Engineering / Cobra - Bitbucket (etas-dev.com)](https://bitbucket.etas-dev.com/projects/RTAENG/repos/cobra/branches?base=refs%2Fheads%2Fdevelop%2FCobra_for_CARIAD) branch: develop/Cobra_for_CARIAD.

- OS port RH850x2GHS_5.0.4=U2A16
- Compiler Greenhils comp201815
- RTA-CAR version **RTA-CAR_12.11.0VCTCESR1pr1**
- RTA-CAR Project available at [LIU Jie (ETAS-ECM/XSF-CN) / cariad_lzcu_mqb - Bitbucket (etas-dev.com) ](https://bitbucket.etas-dev.com/projects/~AIU2SGH/repos/cariad_lzcu_mqb/commits?until=feature/RTAXIP_3204_BSW_Gen)branch: feature/RTAXIP_3204_BSW_Gen

 

**Context:**

- Cobra for Cariad is a split branch from the mainstream Cobra a long time ago to develop customer-specific requirements. At some time, there has been a request for MemMap and MemLay for GHS compiler with RH850 U2A8 target, but Cobra for Cariad hasn't been aware of this update yet.
- We can start by bringing the code from mainstream Cobra to Cobra for Cariad and continue to develop on it until Cariad development team as well as the customer is satisfied.

 

**Input:**

- Cobra mainsteam branch with code for GHS U2A8: [develop/RTA-CAR-12-9-X|[Browse RTA Engineering / Cobra - Bitbucket (etas-dev.com)](https://bitbucket.etas-dev.com/projects/RTAENG/repos/cobra/browse?at=refs%2Fheads%2Fdevelop%2FRTA-CAR-12-9-X)]
- Cobra for Cariad branch: [develop/Cobra_for_CARIAD|[Browse RTA Engineering / Cobra - Bitbucket (etas-dev.com)](https://bitbucket.etas-dev.com/projects/RTAENG/repos/cobra/browse?at=refs%2Fheads%2Fdevelop%2FCobra_for_CARIAD)]
- RTA-CAR Project available at [LIU Jie (ETAS-ECM/XSF-CN) / cariad_lzcu_mqb - Bitbucket (etas-dev.com) ](https://bitbucket.etas-dev.com/projects/~AIU2SGH/repos/cariad_lzcu_mqb/commits?until=feature/RTAXIP_3204_BSW_Gen)branch: feature/RTAXIP_3204_BSW_Gen

 

**DOD:**

- Cobra.exe with newest MemMap MemLay workflow that is accepted by Cariad development team, tested OK with provided RTA-CAR Project branch above.
- Updated ParamDef for Linker, MemMap, MemLay (If changes are to be made to adapt to new target).
- Updated Cobra guide (if needed due to major changes in the workflow).

## 关联

- is satisfied by: [[RTAXIP-3292 [Cariad MQB] MemMapGen Script for RH850 U2A16]]

## 评论

> [!note]+ 2026-03-17 06:57 · [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]
> Dear [[Le_Thi_Huong_Giang_(MSETA-Hub-CN)|Le Thi Huong Giang (MS/ETA-Hub-CN)]] , the description for this ticket has been updated. As we have discussed before, please prioritize finishing this ticket as soon as possible to get feedback from Cariad development team and improve it when requested. If you have anything unclear, please feel free to reach me for information or guidance.

-------

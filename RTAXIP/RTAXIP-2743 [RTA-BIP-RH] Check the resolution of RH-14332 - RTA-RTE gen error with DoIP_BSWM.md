---
jira_key: RTAXIP-2743
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2743"
server: etas
kind: motivation
type: Task
status: Closed
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-rh]
fix-versions: [RTA-BIP-cdes-tc397tk-1210, RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2025-11-14T09:16:05.000+0000"
updated: "2026-07-23T06:55:10.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

Motivation [RH-14332](https://rtahotline.etas.com/jira/browse/RH-14332) need to be verified on RTA-CAR 12.11 or 12.10

 

Input:

- SW BIP base from: [RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886) &#91;RTA-BIP-12.11.0&#93;Porting to RTA-CAR 12.11.0
- feature/[RTAXIP-3886](https://jira.etas-dev.com/browse/RTAXIP-3886)-rta-bip-12110-porting-to-rta-car-12110

Output: 

- Verify if the resolution of RH ticket is yet available in RTA-CAR 12.11 and compatible to BIP

## 关联

- is cloned by: [[RTAXIP-3861 [RTA-BIP-RH] Check the resolution of RH-14656 - [Generate ECU Configuration] Issue relates to generate "Dem" elements]]
- is cloned by: [[RTAXIP-3929 [RTA-BIP-RH] Check the resolution of RH-14638 - OsNeed.arxml generate duplicate Counter with same OsCounterMaxAllowedValue]]
- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]
- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

## 评论

> [!note]+ 2026-07-23 06:52 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Thanks [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]] .
>
> Next time please log work and update status of the ticket

-------

> [!note]+ 2026-07-23 03:57 · [[Nguyen_Tran_Phuong_Nam_(MSETA-Hub-CN)|Nguyen Tran Phuong Nam (MS/ETA-Hub-CN)]]
> **Issue Description:** {color:#de350b}RTA-{color}{color:#ff0000}BSW genertated{color} **{color:#ff0000}DoIP_BSWMD.arxml{color}** {color:#ff0000}doesn’t have <CALL-TYPE> tag,{color} which made error with RTA-RTE gen
>
> Issue is solved in RTA-CAR 12.11.0, below error had been reported in RH-14332 is now resolved when execute RTA-BSW gen step:
>
> 1. Target ARObject: <IMPLEMENTED-ENTRY-REF> 'BSW-CALLED-ENTITY' references incompatible MODULE-ENTRY. - Line: 32. {color:#172b4d}[Infos]{color} <IMPLEMENTED-ENTRY-REF> : </AUTOSAR_DoIP/BswModuleDescriptions/DoIP/IB_DoIP/DoIP_SoAdTpTxConfirmation>
>
>
>
> ![[RTAXIP-2743-image-2026-07-23-10-55-29-272.png]]
>
> 2. Target ARObject: <IMPLEMENTED-ENTRY-REF> 'BSW-CALLED-ENTITY' references incompatible MODULE-ENTRY. - Line: 39. {color:#172b4d}[Infos]{color} <IMPLEMENTED-ENTRY-REF> : </AUTOSAR_DoIP/BswModuleDescriptions/DoIP/IB_DoIP/DoIP_SoAdTpCopyRxData>
>
>
>
> ![[RTAXIP-2743-image-2026-07-23-10-56-11-064.png]]
>
> 3. Target ARObject: <IMPLEMENTED-ENTRY-REF> 'BSW-CALLED-ENTITY' references incompatible MODULE-ENTRY. - Line: 43. {color:#172b4d}[Infos]{color} <IMPLEMENTED-ENTRY-REF> : </AUTOSAR_DoIP/BswModuleDescriptions/DoIP/IB_DoIP/DoIP_SoConModeChg>
>
>
>
> ![[RTAXIP-2743-image-2026-07-23-10-56-35-808.png]]
>
> 4. Target ARObject: <IMPLEMENTED-ENTRY-REF> 'BSW-CALLED-ENTITY' references incompatible MODULE-ENTRY. - Line: 21. {color:#172b4d}[Infos]{color} <IMPLEMENTED-ENTRY-REF> : </AUTOSAR_DoIP/BswModuleDescriptions/DoIP/IB_DoIP/DoIP_Init>
>
>
>
> ![[RTAXIP-2743-image-2026-07-23-10-56-54-348.png]]
>
> 5. Target ARObject: <IMPLEMENTED-ENTRY-REF> 'BSW-CALLED-ENTITY' references incompatible MODULE-ENTRY. - Line: 28. {color:#172b4d}[Infos]{color} <IMPLEMENTED-ENTRY-REF> : </AUTOSAR_DoIP/BswModuleDescriptions/DoIP/IB_DoIP/DoIP_TpTransmit>
>
>
>
> ![[RTAXIP-2743-image-2026-07-23-10-57-06-964.png]]
>
>
>
> RTA-RTE gen pass. Log file attached:
>
> [^rta-rte.log]
>
> [^RteErr.xml]

-------

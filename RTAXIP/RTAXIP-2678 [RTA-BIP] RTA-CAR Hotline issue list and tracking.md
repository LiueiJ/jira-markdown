---
jira_key: RTAXIP-2678
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2678"
server: etas
kind: motivation
type: Story
status: In Progress
priority: Medium
project: RTAXIP
assignee: puy1hc
reporter: nus1hc
tags: [RTA-BIP-RH]
components: []
fix-versions: []
epic: null
parent: null
created: "2025-11-04T11:54:39.000+0000"
updated: "2026-09-07T08:08:03.000+0000"
synced-at: "2026-09-07T08:10:44.636Z"
jira-orphaned: false
---

# RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking

> [!jira] In Progress · Medium · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] · 更新于 2026-09-07T08:08:03.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-2678)

> 标签：#jira/label/rta-bip-rh

## 描述

Everyone, We will list/track all RTA-CAR issues here for Defects or Needs (New Features/Workflow change), if you raise hotline ticket please add it to here:

**How-To create tickets:**  [RTA-Hotline ticket management](https://confluence.etas-dev.com/spaces/VCN/pages/570605534/RTA-Hotline+ticket+management)

- Ticket start with &#91;VNCNMS &#93;&#91;Project Name&#93; <Problem statement description.
- AND linked the project Jira ticket with the hotline ticket.

**How to follow with PF/ Global FAE?**

- Ticket start with &#91;VNCNMS &#93;&#91;Project Name&#93; <Problem statement description> &#91;follow by PF CRs/Bugfix + RTA-CAR Version&#93;
- Hotline ticket needs to follow up but not come with PF CRs/Bugfix ticket (escalation after 3 times reminds).
  - Linked the Hotline ticket in this ticket [RTAXIP-2678](https://jira.etas-dev.com/browse/RTAXIP-2678) for easier review if a hotline ticket closed without PF CRs/bugifx ticket addressed.
  - Regular review hotline ticket, IF created PF CRs/bugfix ticket and **closed** then create CNN ticket start with &#91;RTA-BIP-RH&#93; for bugfix, &#91;RTA-BIP-UC&#93; related feature needs with specific use-cases, AND removed hotline linked ticket as we follow CNN with the PF CRs/bugifx ticket

Legend:

!lightbulb_on.png! = L2/L3 checked and proposed a solution. ETA-Hub-CN needs to verify the solution and/or follow up with a validation ticket.

!help_16.png! = L2/L3 is still investigating. No solution is available yet.

!check.png! = Issue has been verified successfully.

Ticket
Found In Version
Title
Status
Follow up action

[RH-13209](https://rtahotline.etas.com/jira/browse/RH-13209)
12.7.0
&#91;VNCNMS&#93;&#91;ECARX&#93; Auto Exclusive Area Lock Analysis of RTA-CAR 12.7.0 is not easy to use
!lightbulb_on.png!
Verify with RTA-CAR 12.12.0 ([RTAXIP-3826](https://jira.etas-dev.com/browse/RTAXIP-3826))

[RH-14324](https://rtahotline.etas.com/jira/browse/RH-14324)
12.8.0
&#91;VNCNMS&#93;&#91;BIP&#93; Rte_Rips_CSSafety_Cfg_IocNeeds.arxml causes RTA-BSW generation error
!check.png!
Verify with RTA-CAR 12.11 ([RTAXIP-3864](https://jira.etas-dev.com/browse/RTAXIP-3864))

[RH-14332](https://rtahotline.etas.com/jira/browse/RH-14332)
12.8.0
&#91;VNCNMS&#93;&#91;BIP&#93; RTA-RTE generation error with DoIP_BSWMD.arxml
!check.png!
Verify with RTA-CAR 12.11.0 ([RTAXIP-2743](https://jira.etas-dev.com/browse/RTAXIP-2743))

[RH-14335](https://rtahotline.etas.com/jira/browse/RH-14335)
12.8.0
&#91;VNCNMS&#93;&#91;BIP&#93; Conf-gen error with DoIP connection
!lightbulb_on.png!
Follow up development plan; [ARC-14047](https://jira.etas-dev.com/browse/ARC-14047) has no committed target yet

 

Follow [RH-16165](https://rtahotline.etas.com/jira/browse/RH-16165), [ARCCFGEN-2402](https://jira.etas-dev.com/browse/ARCCFGEN-2402)

. Need to verify again with RTA-CAR 12.12

[RH-14448](https://rtahotline.etas.com/jira/browse/RH-14448)
12.8.0
&#91;VNCNMS&#93;&#91;BIP&#93; Issue with OS trap allocation for Tricore (Tasking compiler)
!check.png!
Verified successfully with OsPort TriCoreTasking V5.0.26 ([RTAXIP-3428](https://jira.etas-dev.com/browse/RTAXIP-3428))

[RH-14496](https://rtahotline.etas.com/jira/browse/RH-14496)
12.8.0
&#91;VNCNMS&#93;&#91;BIP&#93; Generate ECU Configuration - System Diagnostic issue
!lightbulb_on.png!
Verify with RTA-CAR 12.12 ([RTAXIP-3993](https://jira.etas-dev.com/browse/RTAXIP-3993)

)

[RH-14510](https://rtahotline.etas.com/jira/browse/RH-14510)
12.8.0
&#91;VNCNMS&#93;&#91;BIP&#93; Conflict between RTA_BSW and RTA_RTE code generation for ComTimeoutNotification
!check.png!
Verify with RTA-CAR 12.11 ([RTAXIP-3863](https://jira.etas-dev.com/browse/RTAXIP-3863))

[RH-14656](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-14656)
12.8.0
&#91;VNCNMS&#93;&#91;BIP&#93; Generate ECU Configuration issue related to Dem elements
!lightbulb_on.png!
Verify with RTA-CAR 12.12 ([RTAXIP-3861](https://jira.etas-dev.com/browse/RTAXIP-3861))

[RH-14634](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-14634)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; BSW code generation error after RTE generation
!lightbulb_on.png!
Verify with RTA-CAR 12.12 ([RTAXIP-3860](https://jira.etas-dev.com/browse/RTAXIP-3860))

[RH-14636](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-14636)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; CryptoDriverAccess is not added to Crypto_Cfg_BSWMD.arxml
!check.png!
Not issue, Update BIP as documentation with RTA-CAR 12.11([RTAXIP-4023](https://jira.etas-dev.com/browse/RTAXIP-4023))

[RH-14638](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-14638)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; OsNeed.arxml generates duplicate Counter with same OsCounterMaxAllowedValue
!check.png!
Verify with RTA-CAR 12.11 ([RTAXIP-3934](https://jira.etas-dev.com/browse/RTAXIP-3934)

)

[RH-14736](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-14736)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; Issue related to NvMSingleBlockCallBack after RTE generation
!check.png!
Verify with RTA-CAR 12.11 ([RTAXIP-3924](https://jira.etas-dev.com/browse/RTAXIP-3924))

[RH-14775](https://rtahotline.etas.com/jira/browse/RH-14775)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; Issue related to generate ComTimeOutNotification using Conf-Gen of RTA-CAR 12.9.0
!check.png!
NA

[RH-16035](https://rtahotline.etas.com/jira/browse/RH-16035)
12.9.0
&#91;VNCNMS&#93;&#91;Semidrive&#93; Auto block length for Dem-forwarded NvM blocks with Ea device
!check.png!
NA

[RH-13992](https://rtahotline.etas.com/jira/browse/RH-13992)
12.9.0
&#91;PduR&#93; PduR should support TP gateway queued multicast CANTP
!check.png!
Verify with RTA-CAR 12.11 ([RTAXIP-3829](https://jira.etas-dev.com/browse/RTAXIP-3829))

[RH-16507](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-16507)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; Undefined Extern Symbol for NvM RAM Block when SWCs are mapped to different partitions
!help_16.png!
Wait for Hotline ticket

[RH-15767](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-15767)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; RTE Generation Error due to shared NvBlockDescriptor access by NvM SWCs on different cores
!check.png!
NA

[RH-16603](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-16603)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; Unexpected Changes in ETAS_FlatMap.arxml After Running Generate ECU Configuration Wizard
!check.png!
Verify with RTA-CAR 12.11 ([RTAXIP-3939](https://jira.etas-dev.com/browse/RTAXIP-3939))

[RH-16617](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-16617)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; IocNeeds.arxml cause RTA-BSW generation error
!lightbulb_on.png!
Verifiy with RTA-CAR 12.12 (ensure include >= RTA-RTE 12.11.1 version) ([RTAXIP-3976](https://jira.etas-dev.com/browse/RTAXIP-3976)

)

[RH-16513](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Frtahotline.etas.com%2Fjira%2Fbrowse%2FRH-16513&data=05%7C02%7Ckhoa.nguyenanh3%40vn.bosch.com%7C5b77409eb6434c3664d908dedb2de154%7C0ae51e1907c84e4bbb6d648ee58410f4%7C0%7C0%7C639189187281701461%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=bT2QsTPquevz0fXKmKtPwHhvevCLF5NKQHjc%2FhKBPVo%3D&reserved=0) 
12.9.0
&#91;VNCNMS&#93;&#91;WBTL&#93; Page size 2 KB not supported by Fee
!lightbulb_on.png! solution provided by &#91;~venkatachalam.v@in.bosch.com&#93;
???

[RH-13446](https://rtahotline.etas.com/jira/browse/RH-13446)
RTA-CAR 12.6.0
&#91;Cariad&#93;&#91;IpduM&#93; IpduM_InitValues CodeGen Issue
!lightbulb_on.png!
Verify with RTA-CAR 12.11 ([RTAXIP-2658](https://jira.etas-dev.com/browse/RTAXIP-2658))

[RH-16635](https://rtahotline.etas.com/jira/browse/RH-16635)
12.11.0
&#91;VNCNMS&#93;&#91;CAEA-VW&#93; Missing Wdg tasks activation of osNeeds.arxml RTA-CAR 12.11.0
!lightbulb_on.png! The issue will be fixed in RTE 12.11.2 ([RTE-23136](https://jira.etas-dev.com/browse/RTE-23136))
Create ticket for verification

[RH-16680](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-16680) 
12.11.0
VNCNMS]&#91;ANY&#93; &#91;12.11.0&#93; Intermittent failure to generate RIPS Cssafety source files in RTA-CAR 12.11.0
💡Workarounds for 12.11.0, the issue has been fixed in RTA-CAR 12.12.0
Verify with RTA-CAR 12.12 ([RTAXIP-3992](https://jira.etas-dev.com/browse/RTAXIP-3992)

)

[RH-16671](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-16671) 
12.11.0
&#91;RH-16671&#93; &#91;VNCNMS&#93;&#91;ANY&#93; &#91;12.11.0&#93; RTA-CAR Migration Issue: paramdef files are not updating to version 12.11.0
!lightbulb_on.png!
Verify with RTA-CAR 12.12 (TBD)

[RH-16035](https://rtahotline.etas.com/jira/browse/RH-16035)
12.9.0
&#91;VNCNMS&#93;&#91;ECARX&#93; Auto block length for Dem-forwarded NvM blocks with Ea device
!lightbulb_on.png!
Verify docmentation with RTA-CAR 12.12, 12.13; Verify feature in RTA-CAR 12.14 ([RTAXIP-3925](https://jira.etas-dev.com/browse/RTAXIP-3925))

[RH-16739](https://rtahotline.etas.com/jira/servicedesk/customer/portal/1/RH-16739)
12.9.0
&#91;VNCNMS&#93;&#91;ANY&#93; Compilation Error Due to Missing Function Declaration in Generated RTE Files for a CSSafety Integration Use Case
!check.png!
Verify with RTA-CAR 12.11 ([RTAXIP-4014](https://jira.etas-dev.com/browse/RTAXIP-4014))

 
 
 
 
 

[RH-10257](https://rtahotline.etas.com/jira/browse/RH-10257)
12.9.0/12.11.0/12.12.0.pr2
&#91;VNCNMS&#93;&#91;Xpeng&#93; Multicore Protection - Request to review and evaluate change of SoAd ExclusiveArea which has more than one successor ExclusiveArea
!lightbulb_on.png!
Verify with RTA-CAR 12.12 ([RTAXIP-4042](https://jira.etas-dev.com/browse/RTAXIP-4042)

)

[RH-16592](https://rtahotline.etas.com/jira/browse/RH-16592)
12.11.0
&#91;VNCNMS&#93;&#91;Xpeng&#93; ConfGen question for DoIPChannel
!lightbulb_on.png!
Defect fix [ARCCFGEN-2660](https://jira.etas-dev.com/browse/ARCCFGEN-2660) to fix this issue in 12.12.0 release.

[RH-16898](https://rtahotline.etas.com/jira/browse/RH-16898)
12.11.0
&#91;VNCNMS&#93;&#91;BIP&#93; DoIP config-gen issues
!help_16.png!
Wait for Hotline ticket

[RH-16928](https://rtahotline.etas.com/jira/browse/RH-16928)
12.11.0
&#91;VNCNMS&#93;&#91;BIP&#93; DoIP TCP Connection Issue
!help_16.png!
Wait for Hotline ticket

[RH-16963](https://rtahotline.etas.com/jira/browse/RH-16963)
12.11.0
&#91;VNCNMS&#93;&#91;BIP&#93; Tool Issue when using RTA-CAR 12.11.0
!help_16.png!
Wait for Hotline ticket

[RH-16968](https://rtahotline.etas.com/jira/projects/RH/issue/RH-16968)
12.11.0
&#91;VNCNMS&#93;&#91;BIP&#93; File was removed but ECU Navigator still recognize it
!help_16.png!
Wait for Hotline ticket

[RH-16996](https://rtahotline.etas.com/jira/browse/RH-16996)
12.11.0
&#91;VNCNMS&#93;&#91;BIP&#93; Questions for Conf-gen of SD module
!help_16.png!
Wait for Hotline ticket

[RH-16986](https://rtahotline.etas.com/jira/browse/RH-16986)
12.11.0
&#91;VNCNMS&#93;&#91;ANY&#93; ConfigGen not support generate PduRRoutingPath in RTA_BIP_PduR_EcucValues.arxml for multi core
!help_16.png!
Wait for Hotline ticket

[RH-17041](https://rtahotline.etas.com/jira/browse/RH-17041)
12.11.0 
&#91;VNCNMS&#93;&#91;BIP&#93; Issue with Enhancer Mapping syntax
!help_16.png!
Wait for Hotline ticket

## 关联

- relates to: [[LUX-35 [Sunwoda-XIP] Hotline issue list and tracking]]
- relates to: [[RTAXIP-3911 [Foton-bip] Hotline issue list and tracking]]
- relates to: [[RTAXIP-2921 BIP 12.9.0 with check conf-gen and addon & full test]]
- is parent of: [[RTAXIP-2171 [EcarX-BIP] Hotline issue list and tracking]]
- is parent of: [[RTAXIP-2516 [QPP] Hotline issue list and tracking]]
- is parent of: [[RTAXIP-2847 [QC8797-BIP] Hotline issue list and tracking]]
- is parent of: [[RTAXIP-4095 [RBCD-BIP] RTA-CAR Hotline issue list and tracking]]
- is parent of: [[RTAXIP-3371 [Xpeng-bip] Hotline issue list and tracking]]
- is parent of: [[RTAXIP-3870 [Weikeng-BIP] Hotline issue list and tracking]]
- is parent of: [[RTAXIP-2560 [Magna-BIP] Hotline issue list and tracking]]
- is parent of: [[RTAXIP-3850 [WBTL-bip] Hotline issue list and tracking]]
- is parent of: [[RTAXIP-3862 [ECARX-SemiDrive][E3620] Hotline issue list and tracking]]
- tracks: [[RTAXIP-3826 [RTA-BIP-RH] Check the resolution of RH-13209 - Auto Exclusive Area Lock Analysis of RTA-CAR12.7.0 is not easy to use]]
- tracks: [[RTAXIP-3860 [RTA-BIP-RH] Check the resolution of RH-14634 - Gen BSW Code gen get error after generating RTE Code Gen]]
- tracks: [[RTAXIP-3861 [RTA-BIP-RH] Check the resolution of RH-14656 - [Generate ECU Configuration] Issue relates to generate "Dem" elements]]
- tracks: [[RTAXIP-3976 [RTA-BIP-RH] Check the resolution of RH-16617 - IocNeeds.arxml cause RTA-BSW generation error]]
- tracks: [[RTAXIP-3992 [RTA-BIP-RH] Check the resolution of RH-16680 -Intermittent failure to generate RIPS Cssafety source files in RTA-CAR 12.11.0]]
- tracks: [[RTAXIP-3993 [RTA-BIP-RH] Check the resolution of RH-14496 - Issue relates to System Diagnostic for DIAG]]
- tracks: [[RTAXIP-4097 [RTA-BIP-RH] Check the resolution of RH-16671 - RTA-CAR Migration Issue: paramdef files are not updating to version 12.11.0]]
- tracks: [[RTAXIP-2743 [RTA-BIP-RH] Check the resolution of RH-14332 - RTA-RTE gen error with DoIP_BSWMD.arxml]]
- tracks: [[RTAXIP-3829 [RTA-BIP-RH] Check the resolution of RH-13992 - PduR should support tp gateway queued multicast CANTP]]
- tracks: [[RTAXIP-3863 [RTA-BIP-RH] Check the resolution of RH-14510 - Conflict between RTA_BSW and RTA_RTE code gen for ComTimeoutNotification Function name]]
- tracks: [[RTAXIP-3864 [RTA-BIP-RH] Check the resolution of RH-14324 - Rte_Rips_CSSafety_Cfg_IocNeeds.arxml cause RTA-BSW generation error]]
- tracks: [[RTAXIP-3924 [RTA-BIP-RH] Check the resolution of RH-14736 - Issue relates to "NvMSingleBlockCallBack" after RTE-gen]]
- tracks: [[RTAXIP-3929 [RTA-BIP-RH] Check the resolution of RH-14638 - OsNeed.arxml generate duplicate Counter with same OsCounterMaxAllowedValue]]
- tracks: [[RTAXIP-3934 [RTA-BIP-RH] Check the resolution of RH-14638 - OsNeed.arxml generate duplicate Counter with same OsCounterMaxAllowedValue with already counter configuration]]
- tracks: [[RTAXIP-3939 [RTA-BIP-RH] Check the resolution of RH-16603 - Unexpected Changes in ETAS_FlatMap.arxml After Running Generate ECU Configuration Wizard]]

## 评论

> [!note]+ 2026-08-25 14:11 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> [[JI_Jiaqi_(ETAS-ECMXSF-CN)|JI Jiaqi (ETAS-ECM/XSF-CN)]] : Why do you close this ticket?

-------

> [!note]+ 2025-11-04 12:08 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> I created this mother ticket to manage:
>  * China mainstream Hotline issue
>  * Link to seperated project's ticket which manage hotline which is raised by and for project team

-------

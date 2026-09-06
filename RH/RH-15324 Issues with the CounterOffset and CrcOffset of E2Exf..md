---
jira_key: RH-15324
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15324"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: dong.liu5@etas.com
reporter: dong.liu5@etas.com
tags: []
components: [System-InfraLib-Safety]
fix-versions: []
epic: null
parent: null
created: "2026-03-02T06:16:22.000+0100"
updated: "2026-05-12T11:37:45.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-15324 Issues with the CounterOffset and CrcOffset of E2Exf.

> [!jira] Closed · Critical · [[Dong_LIU|Dong LIU]] · 更新于 2026-05-12T11:37:45.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-15324)

> 标签：#jira/comp/system-infralib-safety

## 描述

Hi, 

I encountered an issue while using E2EXf. The RTACAR version I am using is RTA-CAR 12.11.0VCTCESR1pr1. 

Project background:

 The VTCT MQB platform plans to upgrade the project from RTA-CAR 9.1 to RTA-CAR 12.11.0VCTCESR1pr1. During the upgrade process, an issue was encountered with E2EXf. 

Issue description:

 In RTA-CAR 9.1, the customer configured the CounterOffset and CrcOffset as shown in the figure below: 

![[RH-15324-image003.png]] 

After upgrading to RTA-CAR 12.11.0VCTCESR1pr1, with the same configuration, the tool reports the following error: 

![[RH-15324-image001.png]] 

The customer’s DBC requirements for this frame are as shown below: 

![[RH-15324-image004.png]] 

Customer requirement:

 The customer expects that, without changing the input requirements, RTA-CAR 12.11.0VCTCESR1pr1 can be compatible with the configuration of RTA-CAR 9.1 and successfully generate code. 

Thank you ! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 Tel. +86 21 2218-4408 | [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- mentions: [[RH-9550 rba_SysElem validation check implementation is different with Requirements]]

## 评论

> [!note]+ 2026-05-12 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-28 06:39 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi,
>
>     Yes this fix available in the RTA-CAR 12.11.0 also. We done this fixed under below version:
>
> **ALM Version : AR45_6_2_0**
>
> **RTA-CAR version : 12.3.x**
>
> Under "Change Request 648334" we done following changes :-
>
> 1.Change the validation check range for maxdeltacounter parameter for all profiles.
> As per AUTOSAR_CP_TPS_SystemTemplate document AR23-11 [constr_3158], [constr_3195], [constr_3159], [constr_3196], [constr_3197], [constr_3316] requirement IDs the 'rba_SysElem_MaxDeltaCounter' parameter range for validation check should start with 1 to maximum value of counter.
>
> 2.Validation script update based on AUTOSAR_CP_TPS_SystemTemplate document AR23-11 [constr_3165] requirement ID.
> https://rtahotline.etas.com/jira/browse/RH-9550 Validation update for E2E P01 and P11.

-------

> [!note]+ 2026-04-23 12:09 · [[Vihitha_Jain|Vihitha Jain]]
> [[Dong_LIU|Dong LIU]] : Which is the current version used by you?Have you upgraded to an RTA-CAR 12.11.0 preview version?
>
> [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] : Is this fix available in the RTA-CAR 12.11.0? The link shared by you is for the older release right?

-------

> [!note]+ 2026-04-14 14:10 · [[Dong_LIU|Dong LIU]]
> Hi, [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] I can’t access this link: [https://rb-alm-28-p.de.bosch.com/ccm/resource/itemName/com.ibm.team.workitem.WorkItem/648334]. The current Cariad project is blocked at this point. Do you have any suggestions or solutions?

-------

> [!note]+ 2026-04-03 12:58 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi ,
>
> This E2EXF validation issue resolved under the below mentioned CR-648334 in software version AR45_6_2_0.
>
> [648334: [GEN6][E2EServices][E2EXF] Validation Script update|https://rb-alm-28-p.de.bosch.com/ccm/resource/itemName/com.ibm.team.workitem.WorkItem/648334]
>
> Below snap taken from the "AUTOSAR_CP_TPS_SystemTemplate.pdf" document.
>
> ![[RH-15324-image-2026-04-03-16-21-36-044.png]]

-------

> [!note]+ 2026-04-01 08:35 · [[S_P_Deepak|S P Deepak]]
> Hi [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] ,
>
> Could you please check this?
>
> Regards,
>
> Deepak S P

-------

> [!note]+ 2026-03-30 17:18 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[S_P_Deepak|S P Deepak]],
>
> We have a customer upgrading from RTA-CAR **9.1** to {*}12.11.0VCTCESR1pr1{*}. Their **E2EXf** transformer ({*}Profile 1{*}) has the counter at bit 48 and CRC at bit 56 in their DBC -counter comes before CRC. This worked in 9.1 but fails the 12.11 validator.
>
> The validator in 12.11 enforces that **E2EXfRb_CrcOffset** must equal **E2EXfRb_UpperHeaderBitsToShift** and **E2EXfRb_CounterOffset** must equal {*}E2EXfRb_UpperHeaderBitsToShift+8{*}. The customer's values ({*}CounterOffset=48{*}, {*}CrcOffset=56{*}) seem to be mathematically incompatible: satisfying **CrcOffset=56** requires {*}UpperHeaderBitsToShift=56{*}, but then **CounterOffset** would need to be 64, not 48. Additionally, **UpperHeaderBitsToShift** is mandatory (minCount=1) so it cannot be left unset to bypass the check.
>
> Two questions:
>  # Is this CRC-before-Counter constraint new in 12.11 compared to 9.1?
>  # Is there any supported configuration in 12.11 that accommodates a Counter-before-CRC layout (counter at bit 48, CRC at bit 56), or can the validator be extended to support this ordering?
>
> Best regards,
> Hritik

-------

> [!note]+ 2026-03-30 07:26 · [[Dong_LIU|Dong LIU]]
> hi [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]] 
>
> The core issue is that the customer is upgrading from RTACAR 9.1 to RTACAR 12.11 and does not accept modification to this input requirement. thank you!

-------

> [!note]+ 2026-03-30 07:23 · [[Dong_LIU|Dong LIU]]
> Hi [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]] 
>
> When I used Expected case 1, the following error occurred while generating the code.
>
> ![[RH-15324-image-2026-03-30-13-19-49-913.png]]
>
> For the expected Case 2 solution, the customer’s input was modified, which the customer did not accept.

-------

> [!note]+ 2026-03-23 17:46 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-03-02 15:27 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[Dong_LIU|Dong LIU]],
>
> error is returned bc BSW/E2EXF does not expect this configuration for type E2EXF_PROFILE11.
> Expected case: 1
>
> e2EXfRb_CounterOffset unset and
> e2EXfRb_UpperHeaderBitsToShift is unset.
>
> Expected case: 2
>
> e2EXfRb_CounterOffset set to e.g. 8 and
> e2EXfRb_UpperHeaderBitsToShift is to 0.
>
> For Details please refer to: [repos/rta-bsw/browse?at=refsV12.11.0.VCTCESR1pr1](https://bitbucket.etas-dev.com/projects/RTABSW/repos/rta-bsw/browse?at=refs%2Fheads%2Frelease%2F12.11.0.VCTCESR1pr1)
> ```
> Files:
> Source\com.etas.rtabsw.code\gen\E2EServices\E2EXf\scripts\E2EXf_Utilities_Validator.ext
> Source\com.etas.rtabsw.code\gen\E2EServices\E2EXf\scripts\E2EXf_Utilities.ext {code}
> Please tell me in case there are issues with this configuration.
>
> Best
> Shaker

-------

> [!note]+ 2026-03-02 07:35 · [[Dong_LIU|Dong LIU]]
> the RTACAR 12.11pre config project is attached
> [^Config.zip]

-------

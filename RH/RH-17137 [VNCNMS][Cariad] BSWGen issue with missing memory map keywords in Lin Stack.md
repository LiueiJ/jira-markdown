---
jira_key: RH-17137
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17137"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: High
project: RH
assignee: "[[Haneef_Nusrin|Haneef Nusrin]]"
reporter: "[[Cuong_Phan_Manh|Cuong Phan Manh]]"
tags: [jira/comp/communication-can-lin-fr, jira/label/makw, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-09-07T12:32:01.000+0200"
updated: "2026-09-10T05:31:23.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

RTA CAR version: **12.11.0**

I supported the customer in investigating the missing MemMap macro issue for Cariad and found several **Lin Stack functions that are currently defined without being enclosed by the corresponding MemMap section macros**.

In other words, these functions/variables are present in the source code, but their definitions are **not placed between the appropriate**  ** {{***START_SEC*** }}and {{***STOP_SEC*** }}MemMap macros.

The missing MemMap coverage may cause compilation errors when the corresponding MemMap sections are required by the compiler/linker configuration.

This is list of Func/Variable I found:

- LinIf_NoNewScheduleRequestScheduleProc_Inline
- LinTp_BswMRequestMode
- LinIf_ProcessTheFirstFrameFForSF
- LinTp_MRF_TXError
- LinTp_MRF_ProcessContinuousFrame
- LinTp_SRF_UnexpectedSequenceHandling
- LinTp_SRF_ProcessReceivedContinuousFrame
- LinTp_SlaveGetFrameType
- LinTp_SlaveAvailableRxDataGreaterThanSix
- LinTp_SlaveAvailableRxDataLessThanSix
- LinTp_SlaveMRFErrorCase_Inline
- LinTp_SlaveSRF_ProcessSF
- LinTp_SlaveSRF_PrepareSingleFrame
- LinTp_SlaveSRF_ProcessFF
- LinTp_SlaveSRF_PrepareFirstFrame
- LinTp_SlaveSRF_ProcessCF
- LinTp_SlaveSRF_PrepareContinuousFrame
- LinTp_SlaveDiagnosticFrameDispatcher
- LinIf_NCAssignNad
- LinIf_NCSaveConfiguration
- LinIf_NCAssignFrameIdentifierRange
- LinIf_NCReadByIdentifier
- LinIf_NCHandler
- LinTp_SlaveRxIndication

Could you please help confirm whether these functions/variables are expected to be covered by MemMap macros? 

Thank you so much

![[RH-17137-image-2026-09-08-09-31-21-031.png]]

Trân trọng / Best regards,

**Cuong Phan Manh**

RTA CHINA  (MS/ETA-Hub-CN)

Bosch Global Software Technologies Company Limited | 364 Cong Hoa Street | Tan Binh Ward | Ho Chi Minh City | VIETNAM | [www.bosch.com.vn](https://www.bosch.com.vn/) 

[Cuong.PhanManh@vn.bosch.com!mail_small.gif!](mailto:Cuong.PhanManh@vn.bosch.com)

Managing Directors: Sawaiker Girish Vinayak (BGSV/GM)

## 关联

- mentions: [[RH-16705 [VNCNMS] BSWGen issue with missing memory map keywords in Com Stack]]
- is mentioned in: [[RH-16705 [VNCNMS] BSWGen issue with missing memory map keywords in Com Stack]]

## 评论

> [!note]+ 2026-09-08 09:40 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[Muhammed_Anas_K_K|Muhammed Anas K K]] , I updated the Description for more detail, could you analyze the issue again? If you still not clear the information, you can contact me via MS Team or check the ticket **RH-16705** for more information, Thanks

-------

> [!note]+ 2026-09-07 13:35 · [[Muhammed_Anas_K_K|Muhammed Anas K K]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] , The hotline ticket content is not clear. Could you please provide more details on the issue, expected behavior, and the specific analysis/action required?

-------

> [!note]+ 2026-09-07 12:56 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]], I created this ticket to discuss and analyze your question in here. Thank you so much

-------

> [!note]+ 2026-09-07 12:38 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Haneef_Nusrin|Haneef Nusrin]], this Communication-Can-Lin-Fr ticket requires an assignee. As the component lead for Communication-Can-Lin-Fr, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-07 12:32 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Cuong Phan Manh, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

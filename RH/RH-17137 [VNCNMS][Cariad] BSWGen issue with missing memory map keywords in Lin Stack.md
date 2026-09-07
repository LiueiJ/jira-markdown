---
jira_key: RH-17137
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17137"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: High
project: RH
assignee: nusrin.haneef@in.bosch.com
reporter: cuong.phanmanh@vn.bosch.com
tags: [VNCNMS]
components: [Communication-Can-Lin-Fr]
fix-versions: []
epic: null
parent: null
created: "2026-09-07T12:32:01.000+0200"
updated: "2026-09-07T12:56:37.000+0200"
synced-at: "2026-09-07T11:18:36.755Z"
jira-orphaned: false
---

# RH-17137 [VNCNMS][Cariad] BSWGen issue with missing memory map keywords in Lin Stack

> [!jira] Waiting for Level 3 · High · [[Haneef_Nusrin|Haneef Nusrin]] · 更新于 2026-09-07T12:56:37.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17137)

> 标签：#jira/comp/communication-can-lin-fr #jira/label/vncnms

## 描述

RTA CAR version: **12.11.0**

I supported the customer in investigating the missing MemMap macro issue for Cariad and found that several macros in the Lin Stack were not covered by the MemMap macros.

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

Could you please support me analyze this issue? Thank you so much

![[RH-17137-image-2026-09-07-17-27-17-903.png]]

Trân trọng / Best regards,

**Cuong Phan Manh**

RTA CHINA  (MS/ETA-Hub-CN)

Bosch Global Software Technologies Company Limited | 364 Cong Hoa Street | Tan Binh Ward | Ho Chi Minh City | VIETNAM | [www.bosch.com.vn](https://www.bosch.com.vn/) 

[Cuong.PhanManh@vn.bosch.com!mail_small.gif!](mailto:Cuong.PhanManh@vn.bosch.com)

Managing Directors: Sawaiker Girish Vinayak (BGSV/GM)

## 关联

- is mentioned in: [[RH-16705 [VNCNMS] BSWGen issue with missing memory map keywords in Com Stack]]

## 评论

> [!note]+ 2026-09-07 12:56 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]], I created this ticket to discuss and analyze your question in here. Thank you so much

-------

> [!note]+ 2026-09-07 12:38 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Haneef_Nusrin|Haneef Nusrin]], this Communication-Can-Lin-Fr ticket requires an assignee. As the component lead for Communication-Can-Lin-Fr, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-07 12:32 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Cuong Phan Manh, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

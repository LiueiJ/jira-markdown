---
jira_key: RH-16705
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16705"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: High
project: RH
assignee: xiao.bai@cn.bosch.com
reporter: xiao.bai@cn.bosch.com
tags: [VNCNMS]
components: [Drivers/Transceivers for Can-Lin-Fr]
fix-versions: []
epic: null
parent: null
created: "2026-07-20T10:28:37.000+0200"
updated: "2026-09-07T12:35:57.000+0200"
synced-at: "2026-09-07T11:18:36.755Z"
jira-orphaned: false
---

# RH-16705 [VNCNMS] BSWGen issue with missing memory map keywords in Com Stack

> [!jira] Solution Proposed · High · [[Xiao_BAI|Xiao BAI]] · 更新于 2026-09-07T12:35:57.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16705)

> 标签：#jira/comp/drivers/transceivers-for-can-lin-fr #jira/label/vncnms

## 描述

Dear hotline colleagues, 

I have following BSW issue in  **RTA-CAR 12.11.0VCTCESR1pr1:** 

In BSW code, some functions and variables are missing memory map keyword, and it will cause compilation errors. 

For example: 

In the picture,  **LinTrcv_WakeupByBusUsed_au8**  does not have any “*START_SEC*” before it and “_STOP_SEC” after it. This causes it to be unable to compile to the specified region. 

![[RH-16705-image001.png]] 

Attached is the reference file. 

 ** Xiao BAI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Xiao.BAI@cn.bosch.com!mail_small.gif!](mailto:Xiao.BAI@cn.bosch.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- mentions: [[RH-17137 [VNCNMS][Cariad] BSWGen issue with missing memory map keywords in Lin Stack]]
- is mentioned in: [[RH-16775 [VNCNMS][VCTC] Avoid Using Static Variables Inside Functions]]

## 评论

> [!note]+ 2026-09-07 12:35 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] , It seems that this issue is related to the Lin Stack. Therefore, I would like to create a new ticket RH-17137 for this issue and close the current one, which will make it easier for us to provide support and track the issue in the future.

-------

> [!note]+ 2026-09-06 15:05 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Cuong_Phan_Manh|Cuong Phan Manh]] ,
>
> I have checked these codes based on RTA CAR 12.11, but there are still issues that have not been fixed. Could you please provide the specific fix version and the plan/timeline?
>
> For example, the function shown in the picture below does not contain any section-related code at all.
>
> ![[RH-16705-image-2026-09-06-21-04-16-636.png]]

-------

> [!note]+ 2026-08-18 14:27 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-30 09:26 · [[Shekar_H_S_Vijay|Shekar H S Vijay]]
> Hello [[Cuong_Phan_Manh|Cuong Phan Manh]], Team has reviewed the changes and there are no findings/review points, request you to go ahead with the delivery

-------

> [!note]+ 2026-07-29 17:10 · [[Shekar_H_S_Vijay|Shekar H S Vijay]]
> Hello [[Cuong_Phan_Manh|Cuong Phan Manh]], 
>
> I have shared the files with development team for review; I will update the feedback once team completes the review and share the review point with me.
>
> My sincere apologies for the delayed response, as the development is occupied with the critical customer deliveries planned.

-------

> [!note]+ 2026-07-29 11:10 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[Shekar_H_S_Vijay|Shekar H S Vijay]] , 
>
> Due to the urgency of this issue, we had to implement the fix ourselves and complete an internal review. However, to ensure the quality goal standards, we would appreciate it if the L3 development team could review the changes. Would you please review the updated source code?
> [^LinTrcv_beforefixed.zip]

-------

> [!note]+ 2026-07-24 12:41 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Shekar_H_S_Vijay|Shekar H S Vijay]] , Do you confirm that this is the bug? If yes, do you agree to update in product and share your plan?
>
> In parallel, as customer's asking the fix on 31st/July, our team will add memmap for these and provide the preview RTA_CAR plugin for customer. 
> | const LinTrcv_DioArray_tst LinTrcv_DioArrayWup_ast[LINTRCV_CFG_NUMBER_OF_LINTRCV] = |
> | const uint8 LinTrcv_WakeupByBusUsed_au8[LINTRCV_CFG_NUMBER_OF_LINTRCV] = |
> | const Dem_EventIdType LinTrcv_DemEvt_aen[2] = |
>
> After that, We will need your support to provide official fix from your team. Please share your plan for it!

-------

> [!note]+ 2026-07-24 06:54 · [[Shekar_H_S_Vijay|Shekar H S Vijay]]
> [[Phuong_Nguyen_Le|Phuong Nguyen Le]], Request you to find the response from development team in the attached mail
> [^RE_ _RH-16705__ *VNCNMS* BSWGen issue with missing memory map keyword in LinTrcv.msg]

-------

> [!note]+ 2026-07-24 04:35 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Shekar_H_S_Vijay|Shekar H S Vijay]] , [[Joao_Goncalves|Joao Goncalves]] : Can you speed up and share feedback today? 
>
> To catch up with customer timeline (31/7), our team (responsible for provide the RTA-CAR ESR which fixes the issue for COEM) will do the fix ourselves and provide the preview RTA-CAR plugin for customer firstly.
>
> After we will need your support to review ([[Joao_Goncalves|Joao Goncalves]] ) our changes as your code review is required for official the RTA-CAR ESR. Can you help to reserve your time to help us to do this?

-------

> [!note]+ 2026-07-23 11:05 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Joao_Goncalves|Joao Goncalves]] : Please help to confirm this issue soon and share fix plan for this. We need to provide the fix for customer next week (31/7)

-------

> [!note]+ 2026-07-21 05:36 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Shekar_H_S_Vijay|Shekar H S Vijay]], this Drivers/Transceivers for Can-Lin-Fr ticket requires an assignee. As the component lead for Drivers/Transceivers for Can-Lin-Fr, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-21 05:35 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Xiao_BAI|Xiao BAI]] , after checking, I have some findnig:
>
> 1) These below functions are INLINE function whih isn't required MAKW for them. [[Xiao_BAI|Xiao BAI]]  Please check with customer again: How are they define LOCAL_INLINE and ensure that compiler understand "inline" function.
> | CanTp_Prv_CanIfTransmit | LOCAL_INLINE void CanTp_Prv_CanIfTransmit(const CanTp_TxContextType *Context, const PduInfoType *CanIfTxInfoPtr) |
> | LinIf_NoNewScheduleRequestScheduleProc_Inline | LOCAL_INLINE void LinIf_NoNewScheduleRequestScheduleProc_Inline(...) |
> | LinTp_MRF_ProcessContinuousFrame | LOCAL_INLINE void LinTp_MRF_ProcessContinuousFrame(...); |
> | LinTp_SRF_UnexpectedSequenceHandling | LOCAL_INLINE void LinTp_SRF_UnexpectedSequenceHandling(...); |
> | LinTp_SRF_ProcessReceivedContinuousFrame | LOCAL_INLINE void LinTp_SRF_ProcessReceivedContinuousFrame(...); |
>
> 2) **LinTrcv_WakeupByBusUsed_au8:** I think that this is issue of RTA-CAR. [[Shekar_H_S_Vijay|Shekar H S Vijay]] : Please help to check this and confirm this issue! I think that we need to fix this issue. Do you agree? Can you share plan to fix it?

-------

> [!note]+ 2026-07-21 04:10 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Xiao_BAI|Xiao BAI]] : Thanks for your quick response. Can you share more detail about error? What is error description?

-------

> [!note]+ 2026-07-21 04:07 · [[Xiao_BAI|Xiao BAI]]
> Hello [[Phuong_Nguyen_Le|Phuong Nguyen Le]] :
>
> 1) The compiler is Hightec 9.1.1
>
> 2) compile options: [^toolchain-hightec.cmake]
>
> 3) Error log:  ![[RH-16705-image-2026-07-21-10-06-33-983.png]]
>
> ![[RH-16705-image-2026-07-21-10-07-35-721.png]]

-------

> [!note]+ 2026-07-21 03:33 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Xiao_BAI|Xiao BAI]] , [[Jiaqi_JI|Jiaqi JI]] , [[Jie_LIU|Jie LIU]] : Please share some info for better analysis:
>
> 1) Which compiler version?
>
> 2) What is compile/linking options/flags?
>
> 3) Error log.

-------

> [!note]+ 2026-07-21 03:25 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Xiao_BAI|Xiao BAI]] , Can you share Error log with compilation

-------

> [!note]+ 2026-07-20 10:28 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Xiao BAI, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-07-20 10:28 · [[Xiao_BAI|Xiao BAI]]
> [^Com stack.zip] *(168 kB)*

-------

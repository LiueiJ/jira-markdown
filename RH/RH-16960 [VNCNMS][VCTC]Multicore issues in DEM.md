---
jira_key: RH-16960
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16960"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: High
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: [Diagnostic-EventStateMgmt]
fix-versions: []
epic: null
parent: null
created: "2026-08-18T11:40:56.000+0200"
updated: "2026-09-07T16:36:19.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16960 [VNCNMS][VCTC]Multicore issues in DEM

> [!jira] Solution Proposed · High · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-09-07T16:36:19.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16960)

> 标签：#jira/comp/diagnostic-eventstatemgmt #jira/label/vncnms

## 描述

Hi hotline， 

 The customer has raised the following concerns regarding our DEM multicore implementation: 

1. Our DEM is deployed on Core0. If the customer directly calls the DEM API from Core1’s CDD (without going through the RTE), is this allowed?

Because we found that after configuring cross-core, the “from-core” side only wraps the DEM function and does not perform any additional operations, so can the API be called directly? 

![[RH-16960-image003.png]] 

![[RH-16960-image002.png]] 

1. In addition, it seems there may be an issue with DEM’s critical section. In the picture, the critical section is only added inside the red area, but red area is clearly a globally modified variable as well—why isn’t it included in the critical section too? There are still many critical section issues in the Dem functions. Could you please help check whether the DEM critical sections are reasonable?

![[RH-16960-image001.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-07 16:36 · [[Sagar_Subbaramaiah|Sagar Subbaramaiah]]
> Hi [[Jie_LIU|Jie LIU]] 
>
> There is no +explicit+ specification in AR that the API Dem_SetEventAvailable() API can only be called once at the very beginning. We can check with our representiative in the AR-workgroup to see if such a constraint can be added to a future version of AR SWS. In any case, considering that the API itself is intended for variant handling, we did not expect it to be called during normal operation. But if the customer claims that the variant switch can happen at any time, it would be interesting to collect more details of their use-case. So, could you please get some more details on this?
>
> Having said that, please note that updating the function `Dem_RepIUMPRDenRelease()` to include the line `Dem_EvtIsAvailable(rba_DemObdBasic_Ratio_GetEvent(RatioID)` within the critical section makes no difference in the end, as the availability status of the event is accessed **only once** within `Dem_RepIUMPRDenRelease()` and that access is a *read-access*. Only if it were a write-access or if there were multiple read accesses, an exclusive area would have made sense e.g., by ensuring that the different reads do not return different results.
>
> In short, we still do not see any need to include `Dem_EvtIsAvailable(rba_DemObdBasic_Ratio_GetEvent(RatioID)` within the exclusive area. Nevertheless, we understand that the customer has not noticed any data consistency issues in real life but is only concerned due to the theoretical risk. Buf from our perspective, even this theoretical concern is not warranted. However, if the customer has any concrete situation (however theoretical it may be) that we might have missed, where the usage of exclusive area brings any real difference/benefit, please let us know.

-------

> [!note]+ 2026-09-07 09:46 · [[Darren_Buttle|Darren Buttle]]
> [[Gunjan_Pradip_Mantala|Gunjan Pradip Mantala]] - just speaking with the ETCN team and they have a customer meeting on Wednesday and they need to provide some feedback on this issue. Can you make sure that they have something by End of Business on Tuesday 8/Sept/26 Thanks!

-------

> [!note]+ 2026-09-04 10:35 · [[Jie_LIU|Jie LIU]]
> hello, [[Vihitha_Jain_(vihitha.jain@bosch.com)|Vihitha Jain]] 
>
> Customer has some feedback based on the analyzing report for PF. Could you please help to answer it?

-------

> [!note]+ 2026-09-03 10:48 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Removing RTE from components as there is no need.

-------

> [!note]+ 2026-08-31 13:36 · [[Jie_LIU|Jie LIU]]
> Hello, [[Gunjan_Pradip_Mantala|Gunjan Pradip Mantala]] 
>
> Based on the feedback of [https://rtahotline.etas.com/jira/browse/RH-16960?focusedCommentId=722141&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-722141,] customer furtherly asked is there any specification to say **Dem_SetEventAvailable()** API can only be called once at the very beginning? 
>
> Based on customer's use case, the variant may also be changed during the normal execution which is highly depending on customer domain function. Either there are specification which defines this, otherwise, we shall not assume the use case for customer.

-------

> [!note]+ 2026-08-31 04:20 · [[Jie_LIU|Jie LIU]]
> [^Dem_Multicore_Analysis.docx]

-------

> [!note]+ 2026-08-31 04:19 · [[Jie_LIU|Jie LIU]]
> **Uploaded the feedback from PF in email loop as attachment:**
>
> Hi together,
>
> The question was why the red part below is also not enclosed within the lock. The reason is as below.
>
> Please find below the analysis requested:
>
> The function rba_DemObdBasic_Ratio_GetEvent() returns value from a const data structure, so it does not need any lock.
>
> The function Dem_EvtIsAvailable() returns value from a RAM data structure, and one may argue that it needs to be protected by lock. However, this RAM data structure is only updated in two cases:
>  # During initialization
>
>  * This one does not collide with a call to Dem_RepIUMPRDenRelease(), as Dem-init runs before any application  No race condition, no need for lock
>
>  # When the API Dem_SetEventAvailable() is called
>
>  * AR provides the API Dem_SetEventAvailable() for variant handling purposes. Since the variant handling/selection is not something that can change during normal execution, the API Dem_SetEventAvailable() should be called only once, at the very beginning, before any monitors can execute. So, this also cannot collide with a call to Dem_RepIUMPRDenRelease()  No race condition, no need for lock
>
> '''
>
> Std_ReturnType Dem_RepIUMPRDenRelease(Dem_RatioIdType RatioID)
> {
>     Std_ReturnType retValue = E_NOT_OK;
>     uint8 denGroup;
>
>
>
>     if (RatioID < DEM_CFG_NUM_ALL_IUMPR_RATIOS)
>     {
>         denGroup = rba_DemObdBasic_Ratio_GetRatioDenGroup(RatioID);
>         if ( (denGroup == DEM_OBDIUMPR_DENCOND_PHYS_API) || (denGroup == DEM_OBDIUMPR_DENCOND_CSERS_API))
>         {
>             if (Dem_EvtIsAvailable(rba_DemObdBasic_Ratio_GetEvent(RatioID)))
>             {
>                 /* Enter the atomic section */
>                 DEM_ENTERLOCK();
>
>
>
>                 /* Mark the ratio to enable denominator increment, if other necessary conditions are satisfied too */
>                 rba_DiagLib_Bit8SetBitMask(&rba_DemObdBasic_Iumpr_RatioSt((uint16 )RatioID), DEM_RATIO_STSMASK_PHYACT_COND);
>                 /* Exist the atomic section */
>                 DEM_EXITLOCK();
>
>
>
>                 retValue = E_OK;
>             }
>         }
>     }
>
>     return retValue;
> }
>
> '''
>
> Best regards,
>
> **Vihitha Jain**
> **MS/EBD-ETAS-VOS**

-------

> [!note]+ 2026-08-31 04:15 · [[Jie_LIU|Jie LIU]]
> [^RE_ VCTC - DEM Multicore a_lignment.msg]

-------

> [!note]+ 2026-08-20 16:27 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-08-20 16:27 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> ![[RH-16960-screenshot-1.png]]

-------

> [!note]+ 2026-08-19 11:53 · [[Gunjan_Pradip_Mantala|Gunjan Pradip Mantala]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]], Hi [[Jie_LIU|Jie LIU]],
>
> Thank you for reaching out to us.
>
> Q : **Which approach should we recommend to the customer for this kind of communication: the default RTE-generated communication or CSSafety?**
> A : Dem supports multicore implementations. If the communication is not safety-related, the default RTE-generated communication can be used. However, for safety-critical software, we recommend using CSSafety communication to ensure compliance with safety requirements.
>
> Q : **For the first question, customer also wants to know if they use CDD in each partition to call the API listed in the sheets directly without RTE, is it safe for reentrance? The reason is our wrapper function also call the APIs directly.**
> A : In general, we recommend using the RTE for event reporting for non BSW modules. However, if the CDD is implemented alongside BSW modules, direct API calls can also be used. The APIs that support multi-partition operation are designed to be reentrant for different Event IDs.
>
> Q : **Regarding the second question, could you please share some information with the customer about this Dem critical section?**
> A : During implementation, appropriate synchronization and protection mechanisms have been applied wherever required to ensure safe concurrent access. The APIs that support multi-partition operation are designed to be reentrant for different Event IDs, and the implementation is aligned with AUTOSAR requirements. Based on our analysis, we do not anticipate any reentrancy-related issues when these APIs are used as intended.
>
> If the customer has observed a specific issue, particularly involving a variable, code path, or concurrent access scenario, please share additional details. We will review the use case, analyze the implementation, and provide feedback.
>
> Best Regards,
> Gunjan Mantala

-------

> [!note]+ 2026-08-19 06:55 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> As [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]'s comment, please use CSSafety to handle inter core client server communications.
>
> From your image, I assume that you are connecting the C/S ports directly without enabling {{{}CSSafety{}}}, and that RTE is generated with the option {{{}--client-server-global-optimization=1{}}}.

-------

> [!note]+ 2026-08-19 06:18 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hello [[Dang_Ho_Anh|Dang Ho Anh]] , related to RTE: In the given use case, CSSafety has to be used to handle inter core client server communications.

-------

> [!note]+ 2026-08-19 03:46 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-08-19 02:43 · [[Jie_LIU|Jie LIU]]
> Dear experts,
>
> For the first question, customer also wants to know if they use CDD in each partition to call the API listed in the sheets directly without RTE, is it safe for reentrance? The reason is our wrapper function also call the APIs directly.

-------

> [!note]+ 2026-08-19 02:37 · [[JSM_Service_Bot|JSM Service Bot]]
> Reminder for tickets requiring L3 RTE attention:
>
> - Have you attached the configuration?
> - Have you stated which version of RTA-CAR is being used (or, RTA-RTE)?
> - Have you tried the configuration with the latest version of RTA-CAR (or, RTA-RTE)?
> - Have you provided the exact command-line options and exact set of input files fed in to RTA-RTE (this could be the ISOLAR RTE LOG file)?
> - Have you stated the name of the customer?
> - Have you stated the priority / deadline?
> - Have you checked the history of hotline tickets for any relevant keywords?
>
> Not providing this information could delay the solution to the problem.

-------

> [!note]+ 2026-08-19 02:37 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Gunjan_Pradip_Mantala|Gunjan Pradip Mantala]], this Diagnostic-EventStateMgmt ticket requires an assignee. As the component lead for Diagnostic-EventStateMgmt, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-08-19 02:36 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Dear [Mantala Gunjan Pradip (MS/EMS3-ETAS)](https://confluence.etas-dev.com/display/~gct2kor) and [Koduri Vamsi Kiran (ETAS-ECM/XPC-Abt1)](https://confluence.etas-dev.com/display/~kod4abt)
>
> This ticket is related to both Dem and RTE for the Cariad customer.
>
> {*}Regarding the first question{*}, my understanding is that when an SWC calls a Dem service on a different core via a C/S interface, RTE can automatically generate an IOC channel to handle this call. However, RTA-CAR also provides the `CSSafety` feature for this type of use case.
>
> Which approach should we recommend to the customer for this kind of communication: the default RTE-generated communication or {{{}CSSafety{}}}?
>
> Besides that, when we use the default IOC channel generated by RTE together with the RTE option {{{}--client-server-global-optimization=1{}}}, the default generated IOC channel is ignored. Therefore, I think this option should not be used for this type of use case.  Please let me know if you have a different opinion or recommendation.
>
> {*}Regarding the second question{*}, could you please share some information with the customer about this Dem critical section?
> Thank you,

-------

> [!note]+ 2026-08-18 14:32 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> Just to let you know, I am currently analyzing your ticket and will get back to you with more details as soon as possible.

-------

> [!note]+ 2026-08-18 11:50 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

---
jira_key: RH-16490
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16490"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: jiaqi.ji@etas.com
reporter: jiaqi.ji@etas.com
tags: [VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-06-26T03:50:56.000+0200"
updated: "2026-07-28T14:24:22.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16490 [VNCNMS][VCTC] Questions on Ratio Group Configuration

> [!jira] Closed · High · [[Jiaqi_JI|Jiaqi JI]] · 更新于 2026-07-28T14:24:22.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16490)

> 标签：#jira/label/vncnms

## 描述

Hi Team, 

Currently CARIAD encounter 2 questions as follows, could you please help have a check? 

Noted with thanks! 

1. currently, there is ratio group defined as "OTHER" which contains the DTC not in the other group. however, we don't find this group in ETAS stack, please help to figure out how to handle it
2. there is "low temp" defined by us as denominator, however, it is also not defined in current ETAS stack, how to handle it?

 **Best Regards,** 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-07-28 14:24 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-14 12:41 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi all,
>
> Thank you, bro [[Dang_Ho_Anh|Dang Ho Anh]], for your support. After the meeting, we found that all of the customer's new concerns are unrelated to the main topic of this ticket. Therefore, [[Jiaqi_JI|Jiaqi JI]] , could you please create a new ticket to track and address these additional questions? I will move this ticket to the 'Proposed Solution' state.
>
> Thank you! 

-------

> [!note]+ 2026-07-14 09:15 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
>
>
> Have we received any feedback from the customer regarding their new issue 😅?

-------

> [!note]+ 2026-07-13 13:06 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Jiaqi_JI|Jiaqi JI]] ,
>
> 1. I don't know why the customer is encountering this error. Could we obtain the ECUC configuration from their project (at least for the DCM module) for further analysis?
>
> 2. Why do we have a new ServiceTable named "NonOBD"? How does it differ from "OBDClassic" or "DcmDsdServiceTable"?
>
> 3. The current workaround is to keep the previous configuration, which allows the project to pass without this error.

-------

> [!note]+ 2026-07-13 07:10 · [[Jiaqi_JI|Jiaqi JI]]
> Hello [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> Noted with thanks for your feedback.
>
> Customer also want to know: Is it possible to disable the OBD protocol by using a configuration parameter (configuration bit)? **by today**
> Q: If I configured 3 tables: DcmDsdServiceTable/DcmDsdServiceTable_OBDClassic/DcmDsdServiceTable_OBDonUDS， code generation successful. If I add a new table, I configured 4 tables: DcmDsdServiceTable/DcmDsdServiceTable_OBDClassic/DcmDsdServiceTable_OBDonUDS/DcmDsdServiceTable_NonOBD，code generation failed.  The error is as follows: ================================================================================ Build validation is failed with following errors for RTA-BSW and execution is aborted:  ================================================================================ 1. The number of instances of element "DcmDsdSidTabId" in container "/RTA_BIP/EcucModuleConfigurationValuess/Dcm/DcmConfigSet_0/DcmDsd_0/DcmDsdServiceTable_NonOBD" is greater than the upper multiplicity of "1". 2. The number of instances of element "DcmDsdSidTabId" in container "/RTA_BIP/EcucModuleConfigurationValuess/Dcm/DcmConfigSet_0/DcmDsd_0/DcmDsdServiceTable_OBDonUDS" is greater than the upper multiplicity of "1". 3. The number of instances of element "DcmDsdSidTabId" in container "/RTA_BIP/EcucModuleConfigurationValuess/Dcm/DcmConfigSet_0/DcmDsd_0/DcmDsdServiceTable_OBDClassic" is greater than the upper multiplicity of "1".
> ![[RH-16490-image-2026-07-13-13-14-02-731.png]]
> Best Regards,
>
> Jiaqi Ji
> ![[RH-16490-image-2026-07-13-13-14-02-731.png]]

-------

> [!note]+ 2026-07-13 06:07 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
>
> I think the customer has the solution for this case, the configuration **DEM_IUMPR_DEN_NONE** can be used as mentioned in the AUTOSAR
>
> ![[RH-16490-image-2026-07-13-10-50-31-568.png]]
>
> ![[RH-16490-image-2026-07-13-10-51-42-476.png]]

-------

> [!note]+ 2026-07-13 04:33 · [[Jiaqi_JI|Jiaqi JI]]
> Hello [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> Customer added one question based on your reply: 
>
> Please give the reply ASAP by today as it's critical for customer, noted with thanks for your support!
> If the denominator is General, which of the attribute of DemIMUPRGenGroup should be chosen?
> ![[RH-16490-image-2026-07-13-10-32-47-052.png]]

-------

> [!note]+ 2026-07-10 08:13 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Jiaqi_JI|Jiaqi JI]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-07-10 08:13 · [[Jiaqi_JI|Jiaqi JI]]
> Hello [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> Got it. Thanks a lot for your kindly support.

-------

> [!note]+ 2026-07-09 16:00 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Jiaqi_JI|Jiaqi JI]] ,
>
>
> Please help ensure that the customer has reviewed the information below and {color:#de350b}confirm whether the proposed solution addresses their concerns{color}.
>
> I will move this ticket to **"Solution Proposed"** status. Should the customer require further clarification or encounter any issues with the proposed solution, please feel free to reopen the ticket.
>
> Thank you for your support.

-------

> [!note]+ 2026-07-09 15:58 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> I would like to summarize the current information and my understanding of your use case:
> ### Current Situation
>
> You currently have:
>  * Two Events: **Low Temp** and {*}High Temp{*}.
>
>  ** Each Event corresponds to a separate ITC (Internal Trouble Code) and a different DTC related to temperature.
>  * You would like to track these Events using two different metrics with different activation conditions.
>
>  ** Therefore, you intend to use **DemRatio** for this purpose.
>  * You would like to understand:
>
>  ** How to configure it,
>  ** How to implement it in software,
>  ** And how it can be tested.
>
> ----
> ### 1. Understanding DemRatio
>
> First of all, let's look at the concept of {*}DemRatio{*}.
>
> The original purpose of DemRatio is to track standardized OBD monitoring events in order to fulfill emission-related regulations required by different regions.
>
> ![[RH-16490-image-2026-07-09-20-45-26-589.png]]
>
>
> ----
> ### 2. Selecting the Appropriate IUMPR Group
>
> Next, we need to determine the appropriate **IUMPR group** for your two Events.
>  * Since **Low Temp** and **High Temp** are temperature-related Events, among the standard AUTOSAR denominator groups shown below, **DEM_IUMPR_DEN_PHYS_API** appears to be the most suitable from a functional perspective.
>
> ![[RH-16490-image-2026-07-09-20-46-42-208.png]]
>  * However, these Events do not belong to any mandatory OBD monitoring requirement where ratio tracking is legally required. Therefore, you will not find a standard IUMPR group that exactly matches your use case.
>
>  * In addition, the standard groups are defined to be accessible through **SID 0x09** with **ITID 0x08** and **0x0B** according to SAE standards. More information can be found in:
>
>  ** **SAE J1979-2**
>  ** {*}J1979DA{*}, which defines the ITIDs.
>  * Among the available groups, you will not find details regarding {*}DEM_IUMPR_PRIVATE{*}, because this group is reserved by AUTOSAR for non-standardized use cases. ![[RH-16490-image-2026-07-09-20-48-11-378.png]]
>
>  ** This group is intended for manufacturer-specific or private requirements and can be freely adapted by the user.
> ![[RH-16490-image-2026-07-09-20-48-34-401.png]]
>
> #### Recommendations
>  * If your customer {*}does not explicitly require ratio tracking for these Events{*}, no additional configuration is necessary.
>
>  * If there is still a requirement to use these values for internal monitoring or diagnostic purposes, configure them as {*}DEM_IUMPR_PRIVATE{*}.
>
> ----
> ### 3. Configuring the Ratios
>
> In the next step, configure your two **DemRatio** instances.
>
> For each ratio:
>  * Reference the corresponding Event.
>  * Configure:
>  ** **DEM_IUMPR_DEN_PHYS_API** as the {*}DemIUMPRDenGroup{*}.
>  ** **DEM_IUMPR_PRIVATE** as the {*}DemIUMPRGroup{*}.
>
> ----
> ### 4. Important Notes
>
> Although both ratios may reference the same **DemIUMPRDenGroup** and {*}DemIUMPRGroup{*}, they are still completely independent ratios with separate values.
>  * **DemIUMPRDenGroup is not a shared counter.**
>  ** It only defines the rule that controls how the denominator should be incremented.
>  ** The actual denominator value is stored and calculated separately for each individual RatioId, as previously discussed.
>
> ![[RH-16490-image-2026-07-09-20-50-48-253.png]]
>  * As you can see from the definitions, the wording is always:
>
> {quote}"Increment the denominator of the ratio"
> {quote}
> meaning that only the denominator belonging to that specific ratio is incremented.
>  * Furthermore, AUTOSAR requirement **SWS_Dem_00611** explicitly states:
>
> {quote}"One port of this interface type is provided per ratio Id"
> {quote}
> ![[RH-16490-image-2026-07-09-20-51-52-189.png]]
>
> This means each RatioId has its own dedicated interface and storage, completely isolated from other ratios, even if they use the same DemIUMPRDenGroup.
> ----
> ### 5. Triggering the Denominator
>
> To control when the denominator should be incremented for a specific Event, you can use: API {*}Dem_RepIUMPRDenRelease{*}(RatioId);
>
> ![[RH-16490-image-2026-07-09-20-54-30-991.png]]
> ![[RH-16490-image-2026-07-09-20-53-04-582.png]]
> Example:
>
> if (LowTemp_ConditionMet)
> {
>  Dem_RepIUMPRDenRelease(RatioId_LowTemp); // Only LowTemp release
> }
>
> if (HighTemp_ConditionMet)
> {
>  Dem_RepIUMPRDenRelease(RatioId_HighTemp); // Only HighTemp release
> }
>
> ----
> ### 6. Reading the DemRatio Values
> #### {color:#de350b}Recommended Approach{color}
>
> I would recommend using **UDS Service 0x19** and reading the corresponding Extended Data via:
>  * Sub-function **0x04**
>  * Sub-function **0x06**
>
> In this case, you only need the related DTC, please ensure create **DemInternalDataElement** for your event.
>
> ![[RH-16490-image-2026-07-09-20-55-26-439.png]]
> #### {color:#de350b}Alternative Approach{color}
>
> You may also use {*}SID 0x22{*}, as I mentioned during our previous meeting.
>
> ---------------------------------------
>
> Both approaches require:
>  * UDS configuration
>  * OBDonUDS configuration
>
> ----------------------------------------
> #### Internal SW-C Access
>
> If you do not need to expose these values to an external tester and only want to provide them as input to other SW-Cs, you can directly use API :{*}Dem_GetEventExtendedDataRecordEx{*}
>
> ![[RH-16490-image-2026-07-09-20-57-43-798.png]]
>
> ![[RH-16490-image-2026-07-09-20-58-04-509.png]]
> ----
> In summary, for your Low Temp and High Temp use case, the recommended solution is to configure two independent **DemRatio** instances using **DEM_IUMPR_DEN_PHYS_API** and {*}DEM_IUMPR_PRIVATE{*}, then control each denominator independently through `Dem_RepIUMPRDenRelease()` using the corresponding RatioId. Even if both ratios share the same denominator group configuration, their counters and stored values remain completely independent.

-------

> [!note]+ 2026-07-08 07:35 · [[Jiaqi_JI|Jiaqi JI]]
> Hello [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> Customer added one screen shot.
>
> ![[RH-16490-image-2026-07-08-13-35-47-468.png]]

-------

> [!note]+ 2026-07-03 08:38 · [[Jiaqi_JI|Jiaqi JI]]
> |  |
> **
> |  |
> Customer Feedback as follow:
> **Q1:**
>     DEM_IUMPR_PRIVATE: Is the process same as the standard legislated groups?
>
> Although this group still calculates the numerator and denominator, the ratio is not returned via SID 0x09. Instead, you should implement custom handling logic in the application using the **Dem_GetIUMPRRatioData** API.
> {color:#ffab00}Ping[7/3/2026]: i don't find  from ISO standard that IUMPR could be read out by 09 service. can you also can provide handling logic for **Dem_GetIUMPRRatioData** API?{color}
>
> **Q2:**
>     How can multiple groups be referred to DEM_IUMPR_DEM_PHYS_API?
>     Example: two different groups: Low Temp and High Temp
>
> You shall have 2 **DemEventParameter** (one for Low Temp and one for High Temp). Afterwards, please create **2** **DemRatio** for  DEM_IUMPR_DEM_PHYS_API, one maps to Low Temp and the other maps to High Temp.
> You can refer API **Dem_RepIUMPRDenRelease** to release denominator for your {*}DemRatio(s){*}.
> {color:#ffab00}Ping[7/3/2026]: can you show us by picture for the key configurations? {color}
> **Q3:**
>     If multiple ratios have the same IUMPRDenGroup, are the values of their denominators the same ?
>
> No, the values of their denominators are not the same, each **DemRatio** maps directly to one of your {*}EventParameters{*}. Any number of ratios can share the same **DemIUMPRGroup** type, and each ratio will still track its own denominator.
> {color:#ffab00}Ping[7/3/2026]: refer to explanation, why the **DemIUMPRGroup** type is defined? what's usage if denominator is not the same when assigned to same denominator group type? it is better to provide an example to explain it. we think that the same denomiator will be use to calculate Ratio if they are assined to sam denominator group{color}|
> |  |

-------

> [!note]+ 2026-07-03 07:19 · [[extern.ping.wang3@cariad-technology.cn|extern.ping.wang3@cariad-technology.cn]]
> {color:#000000}{color} 
>
> {color:#000000}hello Khoa Phan Huynh Dang{color}  
> {color:#000000} thank for your feedback. please see  below remark.{color}{color:#000000}{color} 
> ----
>
> ![[RH-16490-Outlook-data_image.png]]

-------

> [!note]+ 2026-07-01 13:50 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello XiaoDong,
>
> Hello Ping,
>
> {color:#000000}*Q1:*{color}
> {color:#000000}    {color:#de350b}DEM_IUMPR_PRIVATE: Is the process same as the standard legislated groups?{color}{color}
>
> Although this group still calculates the numerator and denominator, the ratio is not returned via SID 0x09. Instead, you should implement custom handling logic in the application using the **Dem_GetIUMPRRatioData** API.
>
> {color:#000000}*Q2:*
>     {color:#de350b}How can multiple groups be referred to DEM_IUMPR_DEM_PHYS_API?{color}
>     Example: two different groups: Low Temp and High Temp{color}
>
> {color:#000000}You shall have 2 **DemEventParameter** (one for Low Temp and one for High Temp). Afterwards, please create **2** **DemRatio** for  DEM_IUMPR_DEM_PHYS_API, one maps to Low Temp and the other maps to High Temp.{color}
>
> {color:#000000}You can refer API **Dem_RepIUMPRDenRelease** to release denominator for your {*}DemRatio(s){*}.{color}
>
> {color:#000000}*Q3:*
>     {color:#de350b}If multiple ratios have the same IUMPRDenGroup, are the values of their denominators the same ?{color}{color}
>
> {color:#172b4d}No, the values of their denominators are not the same, each **DemRatio** maps directly to one of your {*}EventParameters{*}. Any number of ratios can share the same **DemIUMPRGroup** type, and each ratio will still track its own denominator.{color}

-------

> [!note]+ 2026-07-01 10:09 · [[extern.xiaodong.wang2@cariad-technology.cn|extern.xiaodong.wang2@cariad-technology.cn]]
> {color:#000000}{color} 
>
> {color:#000000} Hi :{color} 
> {color:#000000}     Thanks for your reply.{color} {color:#000000}{color} 
>
> {color:#000000} I have the following questions:{color} 
> {color:#000000}  *Q1:*{color} 
> {color:#000000}     DEM_IUMPR_PRIVATE : Is the process same as the standard legislated groups ?{color} {color:#000000}{color} 
>
> {color:#000000}{color} ![[RH-16490-image.png]]{color:#000000}{color} 
> {color:#000000}  *Q2:*{color} 
> {color:#000000}     How can multiple groups be referred to DEM_IUMPR_DEM_PHYS_API ?{color} 
> {color:#000000}     Example: two different groups: Low Temp and High Temp{color} 
> {color:#000000}{color} ![[RH-16490-image.png]]{color:#000000}{color} {color:#000000}{color} 
>
> {color:#000000}  *Q3:*{color} 
> {color:#000000}     If multiple ratios have the same IUMPRDenGroup, are the values of their denominators the same ?{color} {color:#000000}{color} 
>
>
> {color:#000000} INTERNAL{color} 
> ----
>
> {color:#000000} **From:** Khoa Phan Huynh Dang (Jira) <RTA.Hotline@mailer.rta-hotline.etas.com>
>   **Sent:** Tuesday, June 30, 2026 4:12 PM
>   **To:** Wang, Xiaodong (EXTERN: IAV) <extern.xiaodong.wang2@cariad-technology.cn>
>   **Subject:** [RH-16490] [VNCNMS][VCTC] Questions on Ratio Group Configuration{color}
>
> ![[RH-16490-image-1.png]]

-------

> [!note]+ 2026-06-30 10:10 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> {color:#de350b}there is "low temp" defined by us as denominator, however, it is also not defined in current ETAS stack, how to handle it?{color}
>
> ![[RH-16490-image-2026-06-30-15-03-00-018.png]]
>
> Since this is a team-defined condition (not cold start, not 500-mile, and not standard OBD EVAP), you need to use {*}DEM_IUMPR_DEN_PHYS_API{*}.

-------

> [!note]+ 2026-06-30 09:52 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> {color:#de350b}Currently, there is ratio group defined as "OTHER" which contains the DTC not in the other group. however, we don't find this group in ETAS stack, please help to figure out how to handle it{color}
>
> {color:#172b4d}When configuring a DemRatio (a specific IUMPR ratio) in the ARXML file, you must assign it to a DemIUMPRGroup. If the monitor is proprietary or custom—meaning it does not match any standard legislated groups (such as catalyst, O2 sensor, EGR, etc.)—you should select {*}DEM_IUMPR_PRIVATE{*}. This marks it as a private/manufacturer-specific monitoring group, separate from the public legislated IUMPR groups.{color}
>
> {color:#172b4d}![[RH-16490-image-2026-06-30-14-43-56-703.png]]{color}
>
> {color:#172b4d}![[RH-16490-image-2026-06-30-14-52-23-191.png]]{color}

-------

> [!note]+ 2026-06-30 09:34 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
>
> Sorry for keeping you waiting. Just to let you know, we are currently analyzing the issue and will update you ASAP.

-------

> [!note]+ 2026-06-26 03:59 · [[Jiaqi_JI|Jiaqi JI]]
> Hi Team, 
>
> RTA-CAR version: RTA-CAR 12.11.0VCTCESR1pr1.

-------

> [!note]+ 2026-06-26 03:50 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Jiaqi.JI@bosch.com, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

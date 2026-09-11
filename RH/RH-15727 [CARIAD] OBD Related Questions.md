---
jira_key: RH-15727
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15727"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: "[[Jiaqi_JI|Jiaqi JI]]"
reporter: "[[Jiaqi_JI|Jiaqi JI]]"
tags: [jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-04-10T08:39:43.000+0200"
updated: "2026-05-21T09:56:46.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline,

Please help resolve the questions as Cariad requirement. Thanks a lot!

**1. question1 Background:**

Diagnostic results and learned values are typically stored in non-volatile memory in the ECU post-run (RunOn). Because, in case of an error in the post-run, these data can no longer be stored, an OBD-compliant trip debounce, and other things, are no longer possible. This necessitates a diag-nostic strategy that requires a post-run that is not fully completed.

A special trip debounce mechanism is required for diagnostics. This mechanism is described in this section. Due to the special trip debounce mechanism, the fault must be processed as a zero-trip fault.

 

![[RH-15727-image001.png]]

![[RH-15727-image002.png]]

**2. question2 :** 

Are there any matching configuration items in ETAS tool which are equal to variable"healing_inhibition","healing_inhibition_cnt","healing_TripCounter_cnt" referring to below healing diagram ?{}

ETAS will check these steps exclude step.6/13/15;

**3. Question3**

Refer to E20 figure: It should have two Cycle for Ignition ( Ignition Cycle Counter, Fueled Engine Operation Ignition Cycle Counter), but only one configration in RTA-CAR V9.1. How to configure two Ignition Cycle?

we will verify the ITID 0x12.

provide the information about the configuration.

**4. Question4**

How to configure the "monitor activity data" in RTA-CAR V9.1?

The "monitor activity data" is in RTA-CAR V12.11. See E20 figure.

**ETAS:** It related to the question 11 in this file. Because it’s used for SMAD, and this feature is created from RTA-CAR 12.9.0

=> Hence, RTA-CAR 9.1.x is not supported this element.

**5.Question5**

Is OBD only supported DEM_OBD_PRIMARY_ECU, unsupported DEM_OBD_MASTER_ECU and DEM_OBD_DEP_SEC_ECU in RTA-CAR V12.11? see E21 log.

Notice: We have some ECUs, one is Mil-Master OBD, one is Primary OBD, one is Second OBD. The attribute of DemOBDSupport is not support DEM_OBD_DEP_SEC_ECU, so how to implement the feature of Second OBD?

**ETAS:** This is a deviation from AR which requires Dem_DcmReadDataOfPid21 to be available if DemOBDSupport is not DEM_OBD_NO_OBD_SUPPORT. However, for compatibility with Dem_SetDataOfPID21, which is only supported for Dem_OBD_Primary_ECU. It is decided to remove the scope of “DEM_OBD_DEP_SEC_ECU”, because with this type of ECU, there is no ability to set PID21 calculation of PID21.

**log:**

- rba_DemObdBasic_validator --> Error (Executed for 00:00:00:211 hh:mm:ss:ms)
  Exception: Error during oAW script execution rba_DemObdBasic_Validate.mwe: Execution of rba_DemObdBasic_Validate.mwe reported an error:DemGeneral: For now only DEM_OBD_PRIMARY_ECU is supported for Dem with OBD

**Best Regards,**

 **Jiaqi JI** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

T +86 21 2218-5434 

[Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](http://www.etas.cn/)

 **ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-05-21 09:56 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Jiaqi_JI|Jiaqi JI]] ,
>
> I believe we have resolved all of the customer's concerns for this ticket, so it can be closed now. If there are any new concerns or questions, kindly create a new ticket. Thank you so much!

-------

> [!note]+ 2026-05-21 09:46 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> Can We close this ticket now?

-------

> [!note]+ 2026-05-13 07:22 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
> One question added: Which option to choose about "DemOBDEngineType"? Our car models include "ICE/PHEV/BEV/EREV"? 
>
> Thanks a lot!

-------

> [!note]+ 2026-05-11 11:22 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Jiaqi_JI|Jiaqi JI]] ,  if the customer has any concerns regarding the proposed solutions, please reopen this ticket. However, if they have new questions on this topic, kindly create a new ticket. Thank you.

-------

> [!note]+ 2026-05-04 13:01 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] , since OBDonUDS runs on **UDS (ISO 14229-1)** and the **CAN transport layer** (follow your project), you should use **DCM_UDS_ON_CAN** when configuring it.

-------

> [!note]+ 2026-04-28 08:52 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Jiaqi_JI|Jiaqi JI]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-04-28 08:52 · [[Jiaqi_JI|Jiaqi JI]]
> Hello [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
> could you please check question that Do both RTA-CAR V9.1 and RTA-CAR V12.11 support to implement two UDSonCAN/OBDonCAN protocols ? Two ProtocolRows have same ProtocolType.? Cariad: I configured two different DcmDslProtocolPriority with the same ProtocolType, but it had an error in the generated code. 
> DCM: dcmDslProtocolType should be different for any two DcmDslProtocolRow and DcmDslConnection and should not be repeated between two connection table and two protocol table?  ![[RH-15727-image-2026-04-28-14-53-30-097.png]]![[RH-15727-image-2026-04-28-14-51-59-437.png]]
>
> ![[RH-15727-image-2026-04-28-14-53-30-097.png]]

-------

> [!note]+ 2026-04-20 15:33 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> We provided some hints / solutions for customer via this mail.
>
>
> [^CARIAD_OBD Questions Answering.msg]

-------

> [!note]+ 2026-04-14 08:22 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> Please see the added attachment for Q2 & Q4.
>
> Thanks a lot!

-------

> [!note]+ 2026-04-14 08:22 · [[Jiaqi_JI|Jiaqi JI]]
> [^Q3（ETAS OPL）.docx]

-------

> [!note]+ 2026-04-14 08:21 · [[Jiaqi_JI|Jiaqi JI]]
> ![[RH-15727-Q4.png]]

-------

> [!note]+ 2026-04-14 06:01 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] , 
>
> I believe solutions for Q4 and Q3 have been identified, and we are currently waiting for the customer's response. Meanwhile, we are analyzing the remaining questions.

-------

> [!note]+ 2026-04-10 08:39 · [[Jiaqi_JI|Jiaqi JI]]
> [^ETAS Configuration OPL_4.10.xlsx] *(2.59 MB)*

-------

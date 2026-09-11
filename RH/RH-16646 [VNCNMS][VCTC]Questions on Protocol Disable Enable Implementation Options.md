---
jira_key: RH-16646
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16646"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[Jiaqi_JI|Jiaqi JI]]"
reporter: "[[Jiaqi_JI|Jiaqi JI]]"
tags: [jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-07-15T04:46:34.000+0200"
updated: "2026-08-03T13:42:30.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Team, 

Cariad encountered questions regarding OBD very urgent (which has been discussed on yesterday meeting).  

Please help give us feedback by today. Noted with thanks. 

 **Protocol Disable/Enable via Calibration Variable** 

- Can the protocol enable/disable functionality be implemented through a calibration variable?
- If the protocol is disabled, how should the ECU handle incoming diagnostic requests?
  - Should it  **ignore the request (no response)**, or
  - Should it  **respond with an appropriate NRC (Negative Response Code)**?

 **Service Table Switching** 

- Is it feasible to implement protocol switching by introducing an additional  **ServiceTable** and selecting the active ServiceTable through configuration?
- Would this approach be supported by the current DCM implementation?

 **Best Regards,** 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- is mentioned in: [[RH-16810 [VNCNMS][VCTC] OBD Cross-Core Implementation and NoOBD Configuration]]

## 评论

> [!note]+ 2026-07-29 14:24 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-15 11:04 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
>
> Please check the answer below.
>
> Regarding to **Protocol Disable/Enable via Calibration Variable:**
>  * There is an integration function that allows the user to start or stop a specific protocol based on its protocol type. The function is {*}DcmAppl_DcmStartProtocol(){*}. The protocol type can be DCM_UDS_ON_CAN, DCM_OBD_ON_CAN, etc.
>  * ![[RH-16646-image-2026-07-15-15-46-46-210.png]]*
>  * Based on this function, the user can add a user-defined calibration variable to switch a specific protocol on or off.
>  * When a specific protocol is stopped by using this function, NRC `0x22` ({{{}conditionsNotCorrect{}}}) will be returned.
>
> Regarding to **Service Table Switching:**
>  * The user can configure the parameter *DcmDslProtocolRowUsed* to switch a protocol row on or off. The protocol row has a service table mapped to it. However, this is only supported at pre-compile time through configuration, not through runtime switching. And when a protocol is switched off by this configuration, no response will be returned when the tester sends a diagnostic message to it.
>  * Please note that the protocol should be different for any two DcmDslProtocolRow entries.  For example:
>  ** **DCM_UDS_ON_CAN** for DcmDslProtocolRow 1; **DCM_OBD_ON_CAN** for DcmDslProtocolRow 2: This setup is okay.
>  ** **DCM_UDS_ON_CAN** for DcmDslProtocolRow 1; **DCM_UDS_ON_CAN** for DcmDslProtocolRow 2: This setup is not okay, The BSW will generate an error in this case.

-------

> [!note]+ 2026-07-15 05:47 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
> I have changed the priority of this topic to **_Critical_** because it is {+}currently blocking the customer's progress due to the error discussed in yesterday's meeting{+}. We will prioritize this topic and keep you informed of the solution as soon as possible.

-------

> [!note]+ 2026-07-15 04:50 · [[Jiaqi_JI|Jiaqi JI]]
> The priority is high, as this issue will affect cariad overall strategy, so they request need to align on it before moving forward.

-------

> [!note]+ 2026-07-15 04:46 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Jiaqi.JI@bosch.com, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

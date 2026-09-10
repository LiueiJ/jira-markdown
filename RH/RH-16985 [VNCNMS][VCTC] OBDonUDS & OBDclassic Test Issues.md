---
jira_key: RH-16985
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16985"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: Low
project: RH
assignee: Jiaqi JI
reporter: Jiaqi JI
tags: [jira/comp/diagnostic-communication, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-08-20T10:43:07.000+0200"
updated: "2026-09-03T07:30:21.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Khoa and Team, 

Regarding the table above,  **Cariad has identified several discrepancies between the ETAS protocol stack behavior and the customer's expectations (C6b/C7 regulatory requirements)**. 

ETAS is requested to review how the protocol stack should support these requirements and provide a  **quick assessment/response**. 

 **Scope of review:** 

- Only review the items marked  **“Failed”** in  **Column L** of the Excel file.
- The customer has confirmed that the  **“Expected Result”** can be considered as the  **required result according to the applicable regulations**.

Please give us feedback ASAP as it’s important for their testing now. Thanks a lot for your kindly support!  

 **Best Regards,** 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-03 07:30 · JSM Service Bot
> Jiaqi JI, the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-09-03 07:30 · Jiaqi JI
> Hi Khoa Phan Huynh Dang ,
>
> Big thanks for your kindly support!
>
> BR,
>
> Jiaqi

-------

> [!note]+ 2026-09-03 06:15 · Khoa Phan Huynh Dang
> Hi Raghuram Telagamsetti ,
>
> Thanks for your feedback 😊
>
> Hello Jiaqi JI ,
>
> As confirmation from dev team, our RTA-CAR implementation is designed to comply with ISO 15031-5 for classic OBD and ISO 14229-1 for OBD on UDS. As AUTOSAR does not define a mandatory approach for this test case, we have chosen to follow the ISO specifications in our implementation. This approach allows us to support a wider range of customers.
>
> Kindly share our development team's feedback with the customer. If the customer would like us to perform further analysis, please ask them to provide detailed logs for investigation.

-------

> [!note]+ 2026-09-02 16:38 · Raghuram Telagamsetti
> Hello Khoa Phan Huynh Dang / Jiaqi JI 
>
> Please refer to **Column P** in both the **"OBDClassic"** and **"OBDonUDS"** tabs of the attached **"OBDonUDS & OBDclassic Test_en_Feedback.xlsx"** file for my feedback.
> Thanks, Raghu
> [^OBDonUDS & OBDclassic Test_en_Feedback.xlsx]

-------

> [!note]+ 2026-08-28 09:46 · Khoa Phan Huynh Dang
> Hello Raghuram Telagamsetti ,
>
> I used **SAE J1979** and **SAE J1979/2** to analyze this issue in the previous comment due to this information in our release note:
>
> ![[RH-16985-image-2026-08-28-14-44-32-463.png]]
>
> However, I found that we implement SW adaption with **ISO 15031-5** for OBD (as below) and **ISO 14229-1** for OBDonUDS:
>
> ![[RH-16985-image-2026-08-28-14-40-22-070.png]]
>
> Because AUTOSAR is not mentioned the mandatory approach for this logic, I understand **we decide to return NRC code in case "not supported"** as mentioned in ISO. Kindly let me know whether my understand is correct or not.

-------

> [!note]+ 2026-08-27 11:21 · JSM Service Bot
> Hi Raghuram Telagamsetti, this Diagnostic-Communication ticket requires an assignee. As the component lead for Diagnostic-Communication, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-08-27 11:20 · Khoa Phan Huynh Dang
> Hi Jiaqi JI ,
>
> Sorry to keep you waiting so long,
>
> Hello Raghuram Telagamsetti ,
>
> I see almost test case "Fail" of customer relate to "the ECU shall not respond" are following **ISO 15765-4** for CAN protocol and **SAE J1979** for OBD
>
> ![[RH-16985-image-2026-08-27-16-21-55-600.png]]
>
> ![[RH-16985-image-2026-08-27-16-22-29-134.png]]
>
> As you can see in the screenshot from J1979 above, for the 'unsupported PID requested' case, **the ECU shall not send a response** (NRC is N/A). However, in the current implementation, I can see that NRC 0x12 is returned for this case.
> ==> Could you please help check this issue and provide your feedback? I assume this requirement is not mandatory in AUTOSAR, isn't it?
> ![[RH-16985-image-2026-08-27-16-21-55-600.png]] ![[RH-16985-image-2026-08-27-16-22-29-134.png]]

-------

> [!note]+ 2026-08-21 15:08 · Khoa Phan Huynh Dang
> Hi Jiaqi JI ,
>
> We are analyzing, and will let you know asap

-------

> [!note]+ 2026-08-20 10:43 · JSM Service Bot
> Hi Jiaqi JI, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-08-20 10:43 · Jiaqi JI
> [^OBDonUDS & OBDclassic Test_en.xlsx] *(776 kB)*

-------

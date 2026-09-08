---
jira_key: RH-16912
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16912"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: dong.liu5@etas.com
reporter: dong.liu5@etas.com
tags: [VNCNMS]
components: [Communication-Eth]
fix-versions: []
epic: null
parent: null
created: "2026-08-12T05:45:18.000+0200"
updated: "2026-08-28T14:28:06.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16912 [VNCNMS][VCTC]Macro definition of DOIP_NACK_OUT_OF_MEMORY

> [!jira] Closed · Critical · [[Dong_LIU|Dong LIU]] · 更新于 2026-08-28T14:28:06.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16912)

> 标签：#jira/comp/communication-eth #jira/label/vncnms

## 描述

Hi, 

Cariad has some questions regarding the use of the DoIP module. The versions being used are  **ISOLAR-AB 9.1.0** and  **RTA-CAR 12.11.0VCTCESR1pr1**. 

 **Problem Description:** 

 When the customer uses  **ISOLAR-AB 9.1.0**, the DoIP module provides a negative response macro definition named  **DOIP_NACK_OUT_OF_MEMORY**, as shown in the figure below. 

![[RH-16912-image001.png]] 

 However, in  **RTA-CAR 12.11.0VCTCESR1pr1**, the macro definition  **DOIP_NACK_OUT_OF_MEMORY** is no longer available. 

 **Customer Requirement:** 

 The customer would like to know why the  **DOIP_NACK_OUT_OF_MEMORY** negative response macro definition was removed in* 

 ***RTA-CAR 12.11.0VCTCESR1pr1**. 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-08-28 14:28 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-08-14 08:19 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Thanks [[K_S_Vinay|K S Vinay]] ,
> Hi [[Dong_LIU|Dong LIU]] , please check Vinay's comment.

-------

> [!note]+ 2026-08-14 07:42 · [[K_S_Vinay|K S Vinay]]
> Hello [[Dong_LIU|Dong LIU]] [[Dang_Ho_Anh|Dang Ho Anh]] 
>
> 1. **[SWS_DoIP_00018]** - Does Not Apply to DoIP_SoAdIfRxIndication 
> The requirement **[SWS_DoIP_00018]** pertains to the Transport Protocol (Tp) communication path - specifically the DoIP_SoAdTpStartOfReception() function, which handles TCP-based diagnostic message reception. The file in question, DoIP_SoAdIfRxIndication.c, operates on the Interface (If) communication path, which handles UDP-based message reception. These are two fundamentally different communication mechanisms within the DoIP module.
>
> In the older version (ISOLAR-AB 9.1.0), the NACK 0x03 (DOIP_NACK_OUT_OF_MEMORY) that was sent from DoIP_SoAdIfRxIndication upon UDP queue overflow was not driven by **[SWS_DoIP_00018]** which you've highlighted. 
>
> Instead, it was as per **[SWS_DoIP_00276]** requirement-based implementation where NACK was sent for Buffer overflow where it was clearly mentioned 
> ![[RH-16912-image-2026-08-14-11-07-48-942.png]]
>
> 2. In the current RTA-CAR version, the DoIP module silently discards the incoming message rather than sending a NACK. This behavior is in accordance with the updated **[SWS_DoIP_00276]** requirement 
> ![[RH-16912-image-2026-08-14-11-09-27-543.png]]
> cc [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] 

-------

> [!note]+ 2026-08-14 06:53 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Rajendran_Jothivel|Rajendran Jothivel]],
> Could you please help check this issue? I just noticed that [Dixit Shweta Ganesh (MS/EMS1-ETAS) ](https://confluence.etas-dev.com/display/~seg6kor)will be on leave until 17-Aug.
> Thank you,

-------

> [!note]+ 2026-08-14 04:47 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

> [!note]+ 2026-08-12 12:04 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]], this Communication-Eth ticket requires an assignee. As the component lead for Communication-Eth, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-08-12 12:03 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [Dixit Shweta Ganesh (MS/EMS1-ETAS)](https://confluence.etas-dev.com/display/~seg6kor),
>
> Customer is asking about the missing handling of the generic DoIP header NACK code `0x03` ({{{}Out of memory{}}}) in the new RTA-CAR version ({{{}12.11.0VCTCESR1pr1{}}}) compared to the older version ({{{}9.1.0{}}}).
>
> The macro definition for this NACK in the newer version is:
>
> `DOIP_GA_RESPCODE_EXCEEDS_DOIP_BUFFER`
>
> In the older version, it is:
>
> `DOIP_NACK_OUT_OF_MEMORY`
>
> As I checked in the AUTOSAR DoIP specification 19-11, this NACK code is mentioned in the image below.
> ![[RH-16912-image-2026-08-12-17-04-10-908.png]]
> However, we do not have a function to handle this NACK in the newer RTA-CAR version.
>
> Could you help confirm the reason why this NACK is not handled in the mentioned RTA-CAR version?
>
> Thank you,

-------

> [!note]+ 2026-08-12 10:43 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Dong_LIU|Dong LIU]] , Just to let you know, I will start analyzing this ticket today and get back to you with the results as soon as possible.
> Thank you,

-------

> [!note]+ 2026-08-12 07:55 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

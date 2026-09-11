---
jira_key: RH-16903
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16903"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: "[[Dong_LIU|Dong LIU]]"
reporter: "[[Dong_LIU|Dong LIU]]"
tags: [jira/comp/communication-comservices]
fix-versions: []
epic: null
parent: null
created: "2026-08-11T11:18:14.000+0200"
updated: "2026-09-02T14:28:31.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi， 

Cariad has some questions regarding the use of the XCP module. The RTA-CAR version being used is  **RTA-CAR 12.11.0VCTCESR1pr1**, thank you ! 

 **Problem Description:**

 Cariad would like to have an interface to enable or disable the XCP functionality. After checking the code, I found the Xcp_SetControlMode interface. 

 **Customer Requirement:**

 Can the Xcp_SetControlMode interface be exposed for customer use? If not, is there any other interface that can be used to enable or disable the XCP functionality? 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- mentions: [[RH-10087 Turn XCP on/off during runtime]]

## 评论

> [!note]+ 2026-09-02 14:28 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-08-12 12:58 · [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]]
> Hello [[Lewis_Oxtoby|Lewis Oxtoby]] , Thats correct, these APIs can be used to enable/Disable Calibration, Measurement and Stimulation.

-------

> [!note]+ 2026-08-12 09:46 · [[Lewis_Oxtoby|Lewis Oxtoby]]
> Hi [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]] ,
>
> After a bit of digging I found this response to the same question from a couple of years ago:
>
> [https://rtahotline.etas.com/jira/browse/RH-10087?focusedCommentId=225242&page=com.atlassian.jira.plugin.system.issuetabpanels%3Acomment-tabpanel#comment-225242]
>
> This seems to explain that you can use both Xcp_GetControlMode and Xcp_SetControlMode to enable or disable the Xcp module through Application specific code.
>
> Would you be able to confirm the information from the comment is still correct?
>
> Thanks,
>
> Lewis

-------

> [!note]+ 2026-08-11 17:13 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]], this Communication-ComServices ticket requires an assignee. As the component lead for Communication-ComServices, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-08-11 17:13 · [[Lewis_Oxtoby|Lewis Oxtoby]]
> Hi [[Mohammed_Sameer_Gundloor|Mohammed Sameer Gundloor]] 
>
> The customer would like to be able to dynamically enable and disable XCP. The Xcp_SetControlMode function has been identified as a possible way of doing this, can this be accessible, such as from an application code callback, or is this just a BSW internal function? 
>
> Could another possible way of doing this be to enable and disable the PDU group for XCP as a BswM action?
>
> If none of the above are suitable, how would you suggest we achieve this functionality?
>
> Thanks,
>
> Lewis

-------

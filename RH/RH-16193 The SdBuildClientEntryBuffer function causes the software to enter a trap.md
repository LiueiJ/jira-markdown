---
jira_key: RH-16193
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16193"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: Medium
project: RH
assignee: "[[Dong_LIU|Dong LIU]]"
reporter: "[[Dong_LIU|Dong LIU]]"
tags: [jira/comp/communication-eth]
fix-versions: []
epic: null
parent: null
created: "2026-05-28T12:58:38.000+0200"
updated: "2026-09-09T15:45:46.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi,  

Cariad reported a trap issue caused by an Ethernet protocol stack. The RTACAR version used is RTA-CAR 12.11.0VCTCESR1pr1. The call stack information is shown in the figure below: 

![[RH-16193-image001.png]] 

Problem analysis:  

After investigation, the reason for entering the trap is that when calling the SdBuildClientEntryBuffer function shown in the figure below, the value passed to the uint16 IdxSrv_u16 parameter is 0xFFFF. 

![[RH-16193-image002.png]] 

The SdBuildClientEntryBuffer function is called within the SdBuildClientEntry function, and the parameter passed is lSdEntryInfo_pst->IdxPrvEntry_uo.  There is no critical section protection mechanism in this process. 

![[RH-16193-image003.png]] 

SdBuildClientEntry is called in the Sd_MsgBuilderMainFunction function. 

![[RH-16193-image004.png]] 

The order of the call stack is: 

Sd_MsgBuilderMainFunction->SdBuildClientEntry->SdBuildClientEntryBuffer 

The following analyzes under what circumstances the uint16 IdxSrv_u16 parameter passed to the SdBuildClientEntryBuffer function becomes 0xFFFF. After investigation, in the Sd_PushEntryToFreeStack function shown below, lSdEntryInfo_pst->IdxPrvEntry_uo can be assigned the value 0xFFFF. 

![[RH-16193-image005.png]] 

The call stack of the Sd_PushEntryToFreeStack function is:  

Sd_RxIndication -> Sd_RstSrvEntry -> Sd_DeleteRxdEntryInfo -> Sd_DeleteRxdEntryInfofromList -> Sd_PushEntryToFreeStack  

The place where Sd_RxIndication calls Sd_RstSrvEntry is shown in the figure below. The Sd_RxIndication function is triggered by an Ethernet packet reception interrupt. 

![[RH-16193-image006.png]] 

When the code execution enters Sd_MsgBuilderMainFunction, before calling SdBuildClientEntryBuffer, an Ethernet frame is received, triggering a receive interrupt. The receive interrupt calls Sd_RxIndication, and then calls Sd_PushEntryToFreeStack, which sets lSdEntryInfo_pst->IdxPrvEntry_uo to 0xFFFF. The interrupt execution ends and returns to Sd_MsgBuilderMainFunction. At this point, the lSdEntryInfo_pst->IdxPrvEntry_uo value of 0xFFFF is passed to SdBuildClientEntryBuffer, causing a reset. 

Customer requirements:  

The customer has two requests:  

1. The customer hopes we can resolve this issue.  

2. The customer hopes the product team can investigate the SD module to confirm whether there are other similar cases elsewhere. 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-09-03 11:37 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> the review has been done

-------

> [!note]+ 2026-08-27 08:23 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] . the timeline is fine for our team, thank for your support

-------

> [!note]+ 2026-08-26 12:00 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[Cuong_Phan_Manh|Cuong Phan Manh]] : We currently have several team members out on leave, so the earliest we can pick this unplanned activity would be on **September 2nd.** 
>
> Let me know if this works for you!

-------

> [!note]+ 2026-08-26 10:08 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] ,
>
> Could you please review the ticket within this week's timeline?
>
> For this request, we only need confirmation of the changes specifically related to this ticket.

-------

> [!note]+ 2026-08-26 07:46 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[Cuong_Phan_Manh|Cuong Phan Manh]] : What is the timeline for the review? 
>
> Since we are not aware if the base which is used for this porting has some additional changes other than what was officially delivered from product team, we can only ensure if all the **changes only for this ticket** are correctly ported in your PR. 

-------

> [!note]+ 2026-08-25 12:00 · [[Cuong_Phan_Manh|Cuong Phan Manh]]
> Hello [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] , To ensure that we deliver the correct and final version, I would like to ask the NETCOM team to review the source code and confirm that it is aligned with the latest version intended for delivery.
>
> Could you request your team take a few time to review the source code again?
> This is pull request: https://bitbucket.etas-dev.com/projects/RTABSW/repos/rta-bsw/pull-requests/7915/overview

-------

> [!note]+ 2026-07-27 14:24 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-06-24 08:32 · [[Dong_LIU|Dong LIU]]
> Sorry, I closed it by mistake.

-------

> [!note]+ 2026-06-24 04:14 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Dong_LIU|Dong LIU]] , I see that you close this ticket, does it mean that the shared code drop can solve the issue?

-------

> [!note]+ 2026-06-18 18:50 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-06-04 07:04 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> Code drop including reboot and stop offer use cases shared on RTA-CAR 12.9.0 base of Sd (See attached mail).  Please let us know when we can get a feedback of the testing.
>
> [^RE_ Cariad CEA2_0 SD Model Issue Support.msg]

-------

> [!note]+ 2026-06-02 13:21 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] : 
>
> Attached is the code drop for the server reboot case(Base of RTA-CAR 12.9.0) which is reported by Cariad.
>
> In the process of addressing this, the team conducted a thorough analysis and identified a related scenario that could cause a similar race condition(Stop offer from server would cause the race condition between the main function and an Interrupt Service Routine (ISR) in Sd module)
>
> We are currently checking this on high priority and will be delivering another code drop by the EOB tomorrow that addresses both the reported issue and our internal finding.
>
> Request you to kindly test and give us feedback of your testing.[^Sd_Fix_Reboot_Trap_Issue.zip]

-------

> [!note]+ 2026-06-02 07:04 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> Technical root cause analysis is shared(Attached here)
>
>
> [^TechnicalRootCause_RH-16193.pptx]

-------

> [!note]+ 2026-05-29 09:44 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hi Nandhini,
>
> Customer has confirmed they do not have logs for this issue due to the problem happens not often. But it really happens several times in DV car which causes the ECU in unpredictable stable. Actually, customer has analyzed our code for two weeks, and outcome this diagram for root cause, please provide our analysis report based on the evidence.
>
> ![[RH-16193-image-2026-05-29-15-43-24-340.png]]

-------

> [!note]+ 2026-05-28 15:04 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> The analysis from the description looks clear enough.
> Could you please confirm if this is an issue of Sd module?
>
> Thanks,

-------

> [!note]+ 2026-05-28 15:02 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]], this Communication-Eth ticket requires an assignee. As the component lead for Communication-Eth, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

---
jira_key: RH-16737
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16737"
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
created: "2026-07-23T08:09:46.000+0200"
updated: "2026-09-07T06:14:13.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16737 [VNCNMS]The TCP and UDP Events are configured within the same Event Group.

> [!jira] Closed · Critical · [[Dong_LIU|Dong LIU]] · 更新于 2026-09-07T06:14:13.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16737)

> 标签：#jira/comp/communication-eth #jira/label/vncnms

## 描述

Hello, 

Cariad has two questions regarding the use of SD and SoAd and would like to consult the product group. The RTA-CAR version in use is RTA-CAR 12.11.0VCTCESR1pr1. 

1. **Does the RTA-CAR protocol stack support having both UDP-based Events and TCP-based Events in the same Event Group (i.e., belonging to the same Routing Group)?**
2. If this configuration is supported, after a client subscribes to the Event Group and SoAdIfTriggerTransmit is called, can the stack transmit the TCP-based Event and the UDP-based Event sequentially after the Event Group subscription has been established?

 **Thank you for your support.** 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- is mentioned in: [[RH-17116 [VNCNMS][VCTC]Triggering of TCP messages in the SD module]]

## 评论

> [!note]+ 2026-08-14 14:26 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-30 14:29 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-30 14:29 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Thank you, [[Rajendran_Jothivel|Rajendran Jothivel]] .
>
> Hi [[Dong_LIU|Dong LIU]] , Please check Jothivel's response.

-------

> [!note]+ 2026-07-30 13:21 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[Dong_LIU|Dong LIU]],
>
> The RTA CAR SD module shall support either IPv4 or IPv6 addressing, but not both simultaneously. The selected IP version shall be used consistently across all configured server and client services.
>
> Also, the use case which was described was supported in RTA-CAR 9.1 software. Thanks!

-------

> [!note]+ 2026-07-29 13:18 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 13:18 · [[Dang_Ho_Anh|Dang Ho Anh]]
> [[Dong_LIU|Dong LIU]] , Sorry, there was an issue with my email. I just received your message recently.
>
> I have checked the user guide `RTA-Eth_Stack_Reference_Guide_EN.pdf` for {{{}RTA-CAR 9.1.0{}}}, and it mentions the following:
>
> ![[RH-16737-image-2026-07-29-18-16-22-788.png]]
>
> However, this statement does not clearly show whether our use case is supported by this function.
>
>
> Hi [[Rajendran_Jothivel|Rajendran Jothivel]],
> Could you confirm this point with the customer?
>
> Thank you,

-------

> [!note]+ 2026-07-29 10:27 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Dang Ho Anh, Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 10:27 · [[Dong_LIU|Dong LIU]]
> [[Dang_Ho_Anh|Dang Ho Anh]] [[Rajendran_Jothivel|Rajendran Jothivel]] The customer is currently also using RTA-CAR 9.1. Does RTA-CAR 9.1 support this feature as well? Thank you.

-------

> [!note]+ 2026-07-29 04:17 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Dang Ho Anh, JSM Service Bot, Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 04:17 · [[Dong_LIU|Dong LIU]]
> [[Rajendran_Jothivel|Rajendran Jothivel]] [[Dang_Ho_Anh|Dang Ho Anh]] [[JSM_Service_Bot|JSM Service Bot]] **Thank you very much for the information.** 

-------

> [!note]+ 2026-07-28 14:00 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 14:00 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Dong_LIU|Dong LIU]] ,
>
> Please check the final answer from [[Rajendran_Jothivel|Rajendran Jothivel]] 

-------

> [!note]+ 2026-07-28 13:50 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Dang Ho Anh added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 13:50 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello [[Dang_Ho_Anh|Dang Ho Anh]],
>
> Yes, you are correct. RTA CAR software sends the event data sequentially via both UDP and TCP at the same time. Thanks!

-------

> [!note]+ 2026-07-28 12:39 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Rajendran_Jothivel|Rajendran Jothivel]] ,
>
> Does it support the client subscribing to both UDP and TCP at the same time, and will our software send the event data sequentially via UDP and TCP, as the customer pointed out in Question 2?
>
> This means subscribing to both protocol types at the same time, not subscribing to only one type at a time.

-------

> [!note]+ 2026-07-28 12:22 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Dang Ho Anh added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 12:22 · [[Rajendran_Jothivel|Rajendran Jothivel]]
> Hello Everyone,
>
> Yes, this use case is supported in the RTA-CAR product. This feature primarily involves both the SD and SoAd modules.
>
> As [[Dang_Ho_Anh|Dang Ho Anh]] correctly pointed out, the required configuration is in the SD module, where both UDP and TCP subscriptions are mapped to the same routing group.
>
> When SoAdIfTriggerTransmit is invoked with that routing group, SoAd triggers the events through both the UDP and TCP paths. This behavior is already supported by the module.
>
> Please let me know if you need any additional information. Thank you!

-------

> [!note]+ 2026-07-28 09:12 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi everyone,
>
> One input for this is that the RTA-CAR allows the user to configure and generate code when both `SdEventHandlerUdp` and `SdEventHandlerTcp` are mapped to the same `SdEventHandler,` without reporting any errors.

-------

> [!note]+ 2026-07-28 08:43 · [[Frederik_Heinrich|Frederik Heinrich]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]], I'm not sseing the SoAd relevance currently. Only a question towards SD and general handling in our EthStack.
>
> To my knowledge, mixing UDP and TCP based events in the same event group is not supported from our stack and also not possible from AR side. Therefore also 2nd question is irrelevant as it is not supported. 
>
> [[Rajendran_Jothivel|Rajendran Jothivel]] : Any inputs from your side on this topic?

-------

> [!note]+ 2026-07-28 05:37 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Clement Fokam, Frederik Heinrich, Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 05:37 · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]]
> [[Frederik_Heinrich|Frederik Heinrich]] : Assigning the ticket to you as the questions mentioned in the decription is on SoAd.
>
> [[Clement_Fokam|Clement Fokam]] , [[Rajendran_Jothivel|Rajendran Jothivel]] : FYI

-------

> [!note]+ 2026-07-27 17:31 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]], this Communication-Eth ticket requires an assignee. As the component lead for Communication-Eth, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-27 17:30 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [Shweta.GaneshDixit@in.bosch.com](mailto:Shweta.GaneshDixit@in.bosch.com),
>
> As I checked in {{{}12.11.0VCTCESR1pr1{}}}, which is based on {{{}RTA-CAR 12.9.0{}}}, for the first question, our RTA-CAR supports both UDP and TCP for an event. This can be configured by assigning `SdEventHandlerUdp` and `SdEventHandlerTcp` to the same {{{}SdEventHandler{}}}.
>
> However, I am not sure whether both protocol types can be supported at the same time. For example, during my testing, only one protocol was active at a time.
>
> ![[RH-16737-image-2026-07-27-22-28-39-486.png]]
>
>
>
> Could you confirm these points?
>
> Thank you

-------

> [!note]+ 2026-07-27 03:37 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ,
>
> As customer mentioned at weekend that this issue is as critical one and has effect on current development, could you assign one engineer on this topic to help us solve it?
>
> We need the planning time of fix it to report to Cariad. Noted with thanks for your kindly support!
>
> cc [[Dong_LIU|Dong LIU]] [[Jie_LIU|Jie LIU]] 

-------

> [!note]+ 2026-07-27 03:35 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-07-23 08:14 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

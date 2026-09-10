---
jira_key: RH-16737
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16737"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: Dong LIU
reporter: Dong LIU
tags: [jira/comp/communication-eth, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-07-23T08:09:46.000+0200"
updated: "2026-09-07T06:14:13.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

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

> [!note]+ 2026-08-14 14:26 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-30 14:29 · JSM Service Bot
> Note: Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-30 14:29 · Dang Ho Anh
> Thank you, Rajendran Jothivel .
>
> Hi Dong LIU , Please check Jothivel's response.

-------

> [!note]+ 2026-07-30 13:21 · Rajendran Jothivel
> Hello Dong LIU,
>
> The RTA CAR SD module shall support either IPv4 or IPv6 addressing, but not both simultaneously. The selected IP version shall be used consistently across all configured server and client services.
>
> Also, the use case which was described was supported in RTA-CAR 9.1 software. Thanks!

-------

> [!note]+ 2026-07-29 13:18 · JSM Service Bot
> Note: Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 13:18 · Dang Ho Anh
> Dong LIU , Sorry, there was an issue with my email. I just received your message recently.
>
> I have checked the user guide `RTA-Eth_Stack_Reference_Guide_EN.pdf` for {{{}RTA-CAR 9.1.0{}}}, and it mentions the following:
>
> ![[RH-16737-image-2026-07-29-18-16-22-788.png]]
>
> However, this statement does not clearly show whether our use case is supported by this function.
>
>
> Hi Rajendran Jothivel,
> Could you confirm this point with the customer?
>
> Thank you,

-------

> [!note]+ 2026-07-29 10:27 · JSM Service Bot
> Note: Dang Ho Anh, Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 10:27 · Dong LIU
> Dang Ho Anh Rajendran Jothivel The customer is currently also using RTA-CAR 9.1. Does RTA-CAR 9.1 support this feature as well? Thank you.

-------

> [!note]+ 2026-07-29 04:17 · JSM Service Bot
> Note: Dang Ho Anh, JSM Service Bot, Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-29 04:17 · Dong LIU
> Rajendran Jothivel Dang Ho Anh JSM Service Bot **Thank you very much for the information.** 

-------

> [!note]+ 2026-07-28 14:00 · JSM Service Bot
> Note: Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 14:00 · Dang Ho Anh
> Hi Dong LIU ,
>
> Please check the final answer from Rajendran Jothivel 

-------

> [!note]+ 2026-07-28 13:50 · JSM Service Bot
> Note: Dang Ho Anh added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 13:50 · Rajendran Jothivel
> Hello Dang Ho Anh,
>
> Yes, you are correct. RTA CAR software sends the event data sequentially via both UDP and TCP at the same time. Thanks!

-------

> [!note]+ 2026-07-28 12:39 · Dang Ho Anh
> Hi Rajendran Jothivel ,
>
> Does it support the client subscribing to both UDP and TCP at the same time, and will our software send the event data sequentially via UDP and TCP, as the customer pointed out in Question 2?
>
> This means subscribing to both protocol types at the same time, not subscribing to only one type at a time.

-------

> [!note]+ 2026-07-28 12:22 · JSM Service Bot
> Note: Dang Ho Anh added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 12:22 · Rajendran Jothivel
> Hello Everyone,
>
> Yes, this use case is supported in the RTA-CAR product. This feature primarily involves both the SD and SoAd modules.
>
> As Dang Ho Anh correctly pointed out, the required configuration is in the SD module, where both UDP and TCP subscriptions are mapped to the same routing group.
>
> When SoAdIfTriggerTransmit is invoked with that routing group, SoAd triggers the events through both the UDP and TCP paths. This behavior is already supported by the module.
>
> Please let me know if you need any additional information. Thank you!

-------

> [!note]+ 2026-07-28 09:12 · Dang Ho Anh
> Hi everyone,
>
> One input for this is that the RTA-CAR allows the user to configure and generate code when both `SdEventHandlerUdp` and `SdEventHandlerTcp` are mapped to the same `SdEventHandler,` without reporting any errors.

-------

> [!note]+ 2026-07-28 08:43 · Frederik Heinrich
> Hi Shweta Ganesh Dixit, I'm not sseing the SoAd relevance currently. Only a question towards SD and general handling in our EthStack.
>
> To my knowledge, mixing UDP and TCP based events in the same event group is not supported from our stack and also not possible from AR side. Therefore also 2nd question is irrelevant as it is not supported. 
>
> Rajendran Jothivel : Any inputs from your side on this topic?

-------

> [!note]+ 2026-07-28 05:37 · JSM Service Bot
> Note: Clement Fokam, Frederik Heinrich, Rajendran Jothivel added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 05:37 · Shweta Ganesh Dixit
> Frederik Heinrich : Assigning the ticket to you as the questions mentioned in the decription is on SoAd.
>
> Clement Fokam , Rajendran Jothivel : FYI

-------

> [!note]+ 2026-07-27 17:31 · JSM Service Bot
> Hi Shweta Ganesh Dixit, this Communication-Eth ticket requires an assignee. As the component lead for Communication-Eth, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-27 17:30 · Dang Ho Anh
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

> [!note]+ 2026-07-27 03:37 · Jiaqi JI
> Hi Phuong Nguyen Le ,
>
> As customer mentioned at weekend that this issue is as critical one and has effect on current development, could you assign one engineer on this topic to help us solve it?
>
> We need the planning time of fix it to report to Cariad. Noted with thanks for your kindly support!
>
> cc Dong LIU Jie LIU 

-------

> [!note]+ 2026-07-27 03:35 · JSM Service Bot
> Hi Dong LIU, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-07-23 08:14 · JSM Service Bot
> Hi Dong LIU. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

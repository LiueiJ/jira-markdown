---
jira_key: RH-13029
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13029"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: Sammy Burchmore
reporter: Dong LIU
tags: [jira/comp/communication-can-lin-fr]
fix-versions: []
epic: null
parent: null
created: "2025-05-15T04:42:23.000+0200"
updated: "2026-03-05T06:52:03.000+0100"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

hi, 

I encountered an issues with the CanIf module when using RTA-CAR 12.6.0 in Cariad Project. Below is a detailed description of the problem. 

The data type defined in the red box in the following figure is uint8_least 

![[RH-13029-image001.png]] 

The pdu_uo variable is used at the position shown in the figure below 

![[RH-13029-image004.png]] 

However, in the Cariad project, the value of CanIf-Prv_CnfigSet_tpst ->NumOfTxPdus is 312, which exceeds the range of uint8_least 

![[RH-13029-image003.png]] 

I made a temporary modification, blocking the 47th line of code and adding the 48th line of code 

![[RH-13029-image002.png]] 

Thank you!!! 

Best regards, 

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN) 

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2025-07-09 04:54 · Mingye YUAN
> Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0. Dong LIU :Please verify on 12.8.0 version, thanks.

-------

> [!note]+ 2025-06-25 18:00 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-06-02 11:45 · Muhammed Anas K K
> Hello Sammy Burchmore , Hello, Jira ticket ID is [ARCCOM-7467](https://jira.etas-dev.com/browse/ARCCOM-7467)

-------

> [!note]+ 2025-05-29 15:22 · JSM Service Bot
> Hi Communication Can/Lin/Fr Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-05-29 15:21 · Sammy Burchmore
> Hi Muhammed Anas K K,
>
> Thanks a lot. In order to close this ticket I need an ARC ticket to attach here. Could you please create one?
>
> Thank you,
>
> Sammy

-------

> [!note]+ 2025-05-28 11:13 · Muhammed Anas K K
> Hello Sammy Burchmore , Its a defect in CanIf. DWI details [707345: [CanStack][CanIf]: Wrong declaration of loop control variable pdu_uo leading to endless loop during initializing of Tx PDU|https://rb-alm-28-p.de.bosch.com/ccm/resource/itemName/com.ibm.team.workitem.WorkItem/707345]

-------

> [!note]+ 2025-05-19 08:28 · Haneef Nusrin
> Hi Sammy Burchmore ,
>
> The team is looking into the above topic, we will analyse and give feedback shortly.

-------

> [!note]+ 2025-05-15 14:47 · Sammy Burchmore
> Hi Haneef Nusrin,
>
> Could we please include a validation which prevents a value larger than 256 from being set here or support 16 bit integers?
>
> Thanks,
>
> Sammy

-------

> [!note]+ 2025-05-15 14:45 · JSM Service Bot
> Hi Communication Can/Lin/Fr Support Owner. This ticket requires an assignee.

-------

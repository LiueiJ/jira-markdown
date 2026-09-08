---
jira_key: RH-13248
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13248"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: phong.tangdieu@etas.com
reporter: dong.liu5@etas.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-06-11T09:01:52.000+0200"
updated: "2026-03-05T06:52:05.000+0100"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-13248 Feedback on issues in the SD module of RTA-CAR 12.6.0

> [!jira] Closed · Low · [[Phong_Tang_Dieu|Phong Tang Dieu]] · 更新于 2026-03-05T06:52:05.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-13248)

## 描述

Hello: 

I encountered an issues with the SD module when using RTA-CAR 12.6.0 in Cariad Project. Below is a detailed description of the problem. 

In the SD module, we have configured 14 server services as shown in the following figure： 

![[RH-13248-image001.png]] 

However, in the CANoe log, the offerservice message sent by SD only has the service 0x0052, while the other 13 services are missing，as shown in the following figure： 

![[RH-13248-image002.png]] 

With the same configuration, in ISOLAR9.1, the logs in Canoe are shown in the following figure: 

![[RH-13248-image004.png]] 

Thank you!!! 

Best regards, 

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN) 

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2025-06-24 12:38 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Dong_LIU|Dong LIU]]
> Yeah, I saw this fix in RTA-CAR 12.7.0 also.
> As this problem was fixed. I'd like to close this ticket here.
> Thanks,

-------

> [!note]+ 2025-06-20 11:17 · [[Dong_LIU|Dong LIU]]
> Hi,[[Phong_Tang_Dieu|Phong Tang Dieu]] 
>
> In actual debugging, we found that line 538 returned False
>
> ![[RH-13248-image-2025-06-20-17-08-50-342.png]]
>
> Further debugging revealed that when lModePtr_en is set to SOAD_SOCON-OFFLINE, it results in a return value of False
>
> ![[RH-13248-image-2025-06-20-17-10-21-330.png]]
>
> Later, we modified the source code and added the 418th line of code, as shown in the following figure, and the problem was solved
>
> ![[RH-13248-image-2025-06-20-17-16-51-616.png]]

-------

> [!note]+ 2025-06-12 18:37 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Dong_LIU|Dong LIU]] 
>
> Can you please debug and verify if the cyclic offer messages for other servers services are prepared by SD or not? Below breakpoint in Sd_ServerMainFunction should point out which service is prepared to send. Also, please check inside the Sd_SrvRegSendEntryMulticast to make sure the
> Sd_AddRxdEntryInfoToList() is called. 
> ![[RH-13248-image-2025-06-12-17-33-23-714.png]]
>
> Thanks, 

-------

> [!note]+ 2025-06-11 09:49 · [[Dong_LIU|Dong LIU]]
> here is the project attachment[^20_Software.zip]

-------

> [!note]+ 2025-06-11 09:49 · [[Dong_LIU|Dong LIU]]
> [^20_Software.zip]

-------

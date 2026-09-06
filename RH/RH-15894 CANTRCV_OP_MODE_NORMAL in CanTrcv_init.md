---
jira_key: RH-15894
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15894"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: dong.liu5@etas.com
reporter: dong.liu5@etas.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-04-28T05:03:59.000+0200"
updated: "2026-04-29T07:01:02.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-15894 CANTRCV_OP_MODE_NORMAL in CanTrcv_init

> [!jira] Closed · Critical · [[Dong_LIU|Dong LIU]] · 更新于 2026-04-29T07:01:02.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-15894)

## 描述

Hi,  

The customer encountered some issues while using the CanTrcv module. The RTACAR version is RTA-CAR 12.11.0 VCTCESR1pr1. 

Background:

 In the RTACAR 9.1 version, the CanTrcvInitState can be configured as CANTRCV_OP_MODE_NORMAL, as shown in the figure below. 

![[RH-15894-image001.png]] 

However, in the RTA-CAR 12.11.0 VCTCESR1pr1 version, the CANTRCV_OP_MODE_NORMAL option is no longer available in the CanTrcvInitState configuration list, as shown in the figure below. 

![[RH-15894-image002.png]] 

  

Customer requirement:

 The customer would like the CanTrcv to be set to  **NORMAL** mode during the initialization phase. In the RTA-CAR 12.11.0 VCTCESR1pr1 version, do we have any configuration option to achieve this? Thank you. 

  

  

  

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-04-29 07:00 · [[Dong_LIU|Dong LIU]]
> [[Joshua_Cantwell|Joshua Cantwell]] ok, thank you

-------

> [!note]+ 2026-04-28 11:22 · [[Joshua_Cantwell|Joshua Cantwell]]
> [[Dong_LIU|Dong LIU]] 
>
> Oh and for the customer to change to a normal mode they must use the function CanTrcv_SetOpMode with the following parameters; CANTRCV_TRCVMODE_STANDBY, CANTRCV_TRCVMODE_NORMAL or CANTRCV_TRCVMODE_SLEEP. As shown in the state diagram 
>
> ![[RH-15894-image-2026-04-28-10-22-37-106.png]]
>
>
>
> Kind regards Josh C.

-------

> [!note]+ 2026-04-28 11:09 · [[Joshua_Cantwell|Joshua Cantwell]]
> Hi [[Dong_LIU|Dong LIU]],
>
> The reason for the change is that CANTRCV_OP_MODE_NORMAL was dropped from Autosar. The last version of AR that had the value was 4.4. The very next AR release (19-11) now only support SLEEP and STANDBY.
>
>
>
> ![[RH-15894-image-2026-04-28-10-09-24-064.png]]
>
> ![[RH-15894-image-2026-04-28-10-09-06-665.png]]
>
>
>
> Kind regards Josh C.

-------

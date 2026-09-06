---
jira_key: RH-15866
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15866"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: jie.liu8@etas.com
reporter: jie.liu8@etas.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-04-24T06:05:57.000+0200"
updated: "2026-05-26T11:37:59.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-15866 [VW Cariad CEA2.0] Os task meter for max time will decrease sometimes and then get to normal

> [!jira] Closed · Medium · [[Jie_LIU|Jie LIU]] · 更新于 2026-05-26T11:37:59.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-15866)

## 描述

Dear hotline, 

Background: During the testing of Os feature in VW Caraid CEA2.0 project, the meter for maximum task running time is not increasing continuously, it will sometimes decrease as below: 

![[RH-15866-image001.gif]] 

 **Please check whether it is a bug for OS Porting. This does not happen in CEA1.0 with other OS Porting. Customer currently uses TriCore-TC4xx-HighTec_5.0.4 for TC49xN.** 

 ** Jie LIU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 M +86 138 16227585 

 [Jie.LIU8@etas.com!mail_small.gif!](mailto:Jie.LIU8@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-05-26 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-05-11 18:48 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-04-27 14:11 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[Jie_LIU|Jie LIU]],
>
> the current understanding is that the "max" variable should stay constant or increases continuously.
> Having a look at the address where the variable "max" is stored is not a reliable way to measure it,
> since the compiler may reuse the variable for other purposes.
>
> Your test suite should measure the time with the provided API: _Os_GetTaskMaxExecutionTime(Task...)_ (Please refer to RTA-OS Reference Guide.pdf)
>
> Can you tell me please:
>  # which numbers were returned when using Os_GetTaskMaxExecutionTime?
>  # which RTA-OS version + Target Port version + Controller the CARIAD CEA1.0 Project was using 
>
> Best
> Shaker

-------

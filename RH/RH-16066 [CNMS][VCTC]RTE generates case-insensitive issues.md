---
jira_key: RH-16066
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16066"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: Junsheng ZHANG
reporter: Junsheng ZHANG
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-05-18T09:06:30.000+0200"
updated: "2026-06-08T11:38:08.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline, 

 My client encountered an issue with RTE. The client defined an Application SWC named KEYM, and BSW generated a Service SWC named KeyM. This led to problems during RTE generation, where Rte_KeyM.h only defined the variable types and definitions for KEYM, but did not generate any variables or definitions required by KeyM. 

I suspect this is due to RTE not being case-sensitive. Is this a bug? 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-06-08 11:38 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-05-25 06:01 · Khoa Phan Huynh Dang
> Hello Junsheng ZHANG ,
>
> Do you have any remaining concerns regarding this ticket?

-------

> [!note]+ 2026-05-19 09:58 · Khoa Phan Huynh Dang
> Hello Junsheng ZHANG ,
>
> I don't think this is a good idea when get the same name "KEYM" and "KeyM" in this case. Because you will have 2 file "{*}Rte_KeyM.h{*}" and "{*}Rte_KEYM.h{*}", you will see these lines in 2 files
>
> "
> #ifndef RTE_KEYM_H
> #define RTE_KEYM_H
> "
> ==> During software compilation, the compiler only takes the first header file and ignores the rest. This is why you encountered this error. You can try renaming the file to resolve this issue.

-------

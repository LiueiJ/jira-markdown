---
jira_key: RH-17139
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17139"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Customer
priority: High
project: RH
assignee: Junsheng ZHANG
reporter: Junsheng ZHANG
tags: [jira/comp/system-infralib-infrastructure, jira/label/makw, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-09-07T14:49:47.000+0200"
updated: "2026-09-10T08:54:03.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi hotline， 

 I have following BSW issue in* 

 ***RTA-CAR 12.11.0:**  

In BSW code, some functions and variables are missing memory map keyword, and it will cause compilation errors.  

For example:   

In the picture,  **Mfl** does not have any “ *START_SEC* ” before it and “_STOP_SEC” after it. This causes it to be unable to compile to the specified region.  

![[RH-17139-image001.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-10 08:54 · Phuong Nguyen Le
> Mrinal Kanti Sirkar : I don't know what is "improvement activity" but Cariad need these shall be fix on RTA-CAR 12.11 and provide patch to them. 
>
> And I don't agree that this is just improvement points as this impacts to MPU features. 

-------

> [!note]+ 2026-09-10 08:40 · Mrinal Kanti Sirkar
> Hi Phuong Nguyen Le ,
>
> We analyzed the issue and found that the following four constant tables are not enclosed within MemMap macros:
>  # Mfl_ATanTable_caf32
>  # Mfl_ExpIntegralTable_caf32
>  # Mfl_ExpDecimalTable_caf32
>  # Mfl_LogTable_caf32
>
> Since this does not result in any build failure or functional issue, we propose to handle it as an improvement activity. Such improvements are provided in our forward release versions. Please provide your feedback. 
>
> Fyi Thomas Chippy Vihitha Jain 

-------

> [!note]+ 2026-09-08 11:31 · Phuong Nguyen Le
> Mrinal Kanti Sirkar , Cariad is asking to provide the fix on 25/Sep. Is it possible for you to provide the code drop in advance then our team can integrate to RTA-CAR then provide it to customer?

-------

> [!note]+ 2026-09-08 06:09 · JSM Service Bot
> Hi Mrinal Kanti Sirkar, this System-InfraLib-Infrastructure ticket requires an assignee. As the component lead for System-InfraLib-Infrastructure, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-08 06:09 · Cuong Phan Manh
> Hello Mrinal Kanti Sirkar  L3 Component team, After analyze the customer request, I found some **Constant Variable** {*}are not enclosed by memmap macro{*}.
> Could you help me **analyze and confirm** this issue soon and **share fix plan** for this if it correct. 
>
> you can see on the list below:
>  * Mfl_ATanTable_caf32
>  * Mfl_ExpIntegralTable_caf32
>  * Mfl_ExpDecimalTable_caf32
>  * Mfl_LogTable_caf32
>
> Thank you so much

-------

> [!note]+ 2026-09-08 05:18 · Cuong Phan Manh
> Hello Junsheng ZHANG , We have received the information you provided and are currently investigating the issue. We will keep you updated once we have further findings.
>
> Thank for your report.

-------

> [!note]+ 2026-09-07 14:49 · JSM Service Bot
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

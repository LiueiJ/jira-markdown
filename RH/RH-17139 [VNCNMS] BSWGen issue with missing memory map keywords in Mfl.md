---
jira_key: RH-17139
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17139"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: High
project: RH
assignee: mrinal.kantisirkar@in.bosch.com
reporter: junsheng.zhang@bosch.com
tags: [MAKW, VNCNMS]
components: [System-InfraLib-Infrastructure]
fix-versions: []
epic: null
parent: null
created: "2026-09-07T14:49:47.962+0200"
updated: "2026-09-09T14:44:39.031+0200"
synced-at: "2026-09-09T12:45:06.538Z"
jira-orphaned: false
profile: Cariad
---

# RH-17139 [VNCNMS] BSWGen issue with missing memory map keywords in Mfl

> [!jira] Waiting for Level 3 · High · [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] · 更新于 2026-09-09T14:44:39.031+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17139)

> 标签：#jira/comp/system-infralib-infrastructure #jira/label/makw #jira/label/vncnms

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

> [!note]+ 2026-09-08 11:31 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Phuong Nguyen Le]]
> [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]] , Cariad is asking to provide the fix on 25/Sep. Is it possible for you to provide the code drop in advance then our team can integrate to RTA-CAR then provide it to customer?

-------

> [!note]+ 2026-09-08 06:09 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]], this System-InfraLib-Infrastructure ticket requires an assignee. As the component lead for System-InfraLib-Infrastructure, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-08 06:09 · [[Phan_Manh_Cuong_(MSETA-Hub-CN)|Cuong Phan Manh]]
> Hello [[Kanti_Sirkar_Mrinal_(MSEMT4-ETAS)|Mrinal Kanti Sirkar]]  L3 Component team, After analyze the customer request, I found some **Constant Variable** {*}are not enclosed by memmap macro{*}.
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

> [!note]+ 2026-09-08 05:18 · [[Phan_Manh_Cuong_(MSETA-Hub-CN)|Cuong Phan Manh]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] , We have received the information you provided and are currently investigating the issue. We will keep you updated once we have further findings.
>
> Thank for your report.

-------

> [!note]+ 2026-09-07 14:49 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

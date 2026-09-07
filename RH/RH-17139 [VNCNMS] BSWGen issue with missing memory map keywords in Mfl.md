---
jira_key: RH-17139
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17139"
server: rtahotline
kind: hotline
type: Support
status: Investigation Required
priority: High
project: RH
assignee: ""
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-07T14:49:47.000+0200"
updated: "2026-09-07T14:58:22.000+0200"
synced-at: "2026-09-07T13:18:36.829Z"
jira-orphaned: false
---

# RH-17139 [VNCNMS] BSWGen issue with missing memory map keywords in Mfl

> [!jira] Investigation Required · High ·  · 更新于 2026-09-07T14:58:22.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17139)

> 标签：#jira/label/vncnms

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

> [!note]+ 2026-09-07 14:49 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

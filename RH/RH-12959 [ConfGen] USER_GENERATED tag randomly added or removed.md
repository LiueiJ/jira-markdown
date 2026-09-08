---
jira_key: RH-12959
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12959"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: sisi.tao@bosch.com
reporter: sisi.tao@bosch.com
tags: []
components: [ISOLAR-B]
fix-versions: []
epic: null
parent: null
created: "2025-05-06T11:15:14.000+0200"
updated: "2026-03-08T08:36:35.000+0100"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-12959 [ConfGen] USER_GENERATED tag randomly added or removed

> [!jira] Closed · Low · [[Sisi_TAO|Sisi TAO]] · 更新于 2026-03-08T08:36:35.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12959)

> 标签：#jira/comp/isolar-b

## 描述

Dear hotline colleague, 

I’m working with confgen RTA-CAR12.6.0 and using BSW Enhancer. I set many default value for many module configurations. But every time I confgen, sometimes there’ll be S=”USER_GENERATED” attribute generated, sometimes the attributes are removed. This causes many diffs when user doing version control, but actually the value is not changed. Do you know why this happens? Thank you. 

![[RH-12959-image001.png]] 

 ** Sisi TAO** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 133 81555197 

 [Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.com](http://www.etas.com)  ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-10-10 15:07 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-09-25 18:30 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2025-09-04 08:30 · [[Krishnaswamy_Dharani_Dharan|Krishnaswamy Dharani Dharan]]
> Hello [[Sisi_TAO|Sisi TAO]],
>
> We have tried reproducing this multiple times in reported version, but it is not reproducible.
>
> Please Provides us any details steps to reproduce or we can discuss this issue over teams
>
> Please check and feedback
>
> Thank you!!

-------

> [!note]+ 2025-08-28 07:07 · [[Sisi_TAO|Sisi TAO]]
> [^BasicSoftware.zip]

-------

> [!note]+ 2025-08-20 10:40 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi ISOLAR-B Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-08-20 10:40 · [[Marc_Kaiser|Marc Kaiser]]
> First time we execute confgen, we get UserGenerated in the ecucvalues that BSW Enhancer enhanced. Second time and following UserGenerated is removed.
>
> THis makes comparison in beyond compare diffcult because there are just too many differences. We would like consistent behaviour no matter how often we execute.

-------

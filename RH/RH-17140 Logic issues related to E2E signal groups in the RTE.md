---
jira_key: RH-17140
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17140"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Customer
priority: Critical
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-07T15:16:48.000+0200"
updated: "2026-09-07T18:25:44.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-17140 Logic issues related to E2E signal groups in the RTE

> [!jira] Waiting for Customer · Critical · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-09-07T18:25:44.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17140)

## 描述

Hi Hotline, 

 In the code shown in the image, the initial value of Rte_Rx_000738 is RTE_E_NEVER_RECEIVED (133). However, in the actual execution logic, as long as the error type is not RTE_E_MAX_AGE_EXCEEDED (64), it returns RTE_E_COM_STOPPED (128). This makes it impossible for the upper SWC to determine whether the fault cause is specifically RTE_E_NEVER_RECEIVED or the real reason is RTE_E_COM_STOPPED. 

 This logic is not reasonable. Please fix it. 

![[RH-17140-image001.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-07 18:25 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]]
> Could you please describe more detailed about the use case? 
> And could you share the project as well? It would be helpful to analyze the issue. From my side, I could find any similar generated code even for E2E and E2EXf.
> Thanks,

-------

> [!note]+ 2026-09-07 15:21 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

---
jira_key: RH-15338
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15338"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: [Communication-Can-Lin-Fr]
fix-versions: []
epic: null
parent: null
created: "2026-03-03T08:50:23.000+0100"
updated: "2026-04-21T11:37:33.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-15338 [CNMS][VCTC]LinTp configuration error but no error reported

> [!jira] Closed · Medium · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-04-21T11:37:33.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-15338)

> 标签：#jira/comp/communication-can-lin-fr #jira/label/vncnms

## 描述

Hi Hotline, 

 When using RTA CAR12.11.0VCTCESR1pr1, the customer found that LinTpRxNSdu and LinTpTxNSdu were not configured, but the code was generated normally; The macro definition in the code has a value of 0 for LINTP_MAX_TX_NSDU, which can cause static code to encounter issues when calling related arrays; 

 The following diagram shows the customer's configuration, without configuring LinTpRxNSdu and LinTpTxNSdu 

![[RH-15338-image001.png]] 

 The following arrays are all of size 0; 

![[RH-15338-image002.png]] 

 Code encounters issues when calling arrays; 

 ![[RH-15338-image003.png]] 

 We believe that the lack of inspection mechanisms in RTA CAR during code generation is a contributing factor; I hope you can help solve this problem and check if similar issues still exist; If there are still similar issues, please let me know as well. This can help the client avoid these problems during the development process 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](http://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-04-21 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-06 18:48 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-03-23 07:42 · [[Muhammed_Anas_K_K|Muhammed Anas K K]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]], The use case with LinTp is enabled, but LinTpRxNSdu and LinTpTxNSdu are not configured. This is a invalid configuration. .Currently, the validator reports an error if no LinTpChannelConfig is configured; But, not check for empty LinTpTxNSdu or LinTpRxNSdu configurations. The validation check will be updated as part of the task below
>
> [https://jira.etas-dev.com/browse/ARCCOM-10946]

-------

> [!note]+ 2026-03-20 10:38 · [[Jayashankar_Amritha|Jayashankar Amritha]]
> Hi Khoa Phan Huynh Dang, The ticket is currently pending analysis. As the concerned colleagues are on leave, it will be reviewed on Monday (23/03).

-------

> [!note]+ 2026-03-18 09:22 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Haneef_Nusrin|Haneef Nusrin]], althought AUTOSAR **does not mention** this as a mandatory requirement, I think we should implement **a validation rule** in our tool to avoid this issue. Specifically:
>
> Could we implement **logic handling in code gen** to ensure that Rx/Tx configurations for LIN are configured?

-------

> [!note]+ 2026-03-18 09:14 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] , sorry for keep you waiting, about your concern:
>
> + Firstly, the RTA-CAR version which you used follows the **AUTOSAR standard** for LIN module with version **AR 23-11.**
>
> + In this document, I found these containers ({*}LinTpTxNSdu{*} and {*}LinTpRxNSdu{*}) are the optional configurations. I mean that the multiplicity of these NSdu is usually 0...*
>
> ![[RH-15338-image-2026-03-18-15-07-32-707.png]]
>
> => Therefore, our tool currently implements it as an optional configuration.
>
> => This results in the **output Tx and Rx values** ​​potentially {*}being 0 according to AUTOSAR{*}.
>
> ---------------------
>
> However, if you use LIN protocol but {*}haven't configured LinTpRxNSdu and LinTpTxNSdu{*}, you won't be able to complete the configuration in the PduR module for LIN stack. This will result in data transmission and reception functions from the upper/lower layers not being processed ==> **You cannot use the feature of LinTP.**
>
> ==> Please configure at least one **of** **your LinTpRxNSdus and LinTpTxNSdus** to avoid this issue and use the feature of LinTP.

-------

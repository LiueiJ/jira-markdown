---
jira_key: RH-17140
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17140"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: High
project: RH
assignee: Vamsi Kiran Koduri
reporter: Junsheng ZHANG
tags: [jira/comp/rta-rte, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-09-07T15:16:48.000+0200"
updated: "2026-09-10T10:03:04.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

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

> [!note]+ 2026-09-10 10:03 · Dang Ho Anh
> Hi Junsheng ZHANG ,
> Could you please check whether the customer can accept the current RTE behavior or use `HandleNeverReceived = false` instead?
>
> Hi Vamsi Kiran Koduri ,
>
> Do we have a workaround solution for this case?

-------

> [!note]+ 2026-09-10 09:44 · Vamsi Kiran Koduri
> Hello Junsheng ZHANG ,Dang Ho Anh ,Phong Tang Dieu I confirm the reported issue. RTE shall return RTE_E_NEVER_RECEIVED until first reception when handleneverreceived is set to TRUE.

-------

> [!note]+ 2026-09-09 15:33 · JSM Service Bot
> Reminder for tickets requiring L3 RTE attention:
>
> - Have you attached the configuration?
> - Have you stated which version of RTA-CAR is being used (or, RTA-RTE)?
> - Have you tried the configuration with the latest version of RTA-CAR (or, RTA-RTE)?
> - Have you provided the exact command-line options and exact set of input files fed in to RTA-RTE (this could be the ISOLAR RTE LOG file)?
> - Have you stated the name of the customer?
> - Have you stated the priority / deadline?
> - Have you checked the history of hotline tickets for any relevant keywords?
>
> Not providing this information could delay the solution to the problem.

-------

> [!note]+ 2026-09-09 15:33 · JSM Service Bot
> Hi Vamsi Kiran Koduri, this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-09 15:31 · Dang Ho Anh
> Junsheng ZHANG , After giving it some careful thought, I realized that this could be an issue.
>
> Hi [Koduri Vamsi Kiran (ETAS-ECM/XPC-Abt1)](https://confluence.etas-dev.com/display/~kod4abt),
>
> The behavior of RTE that Junsheng just shared is that when HandleNeverReceived is set to true, but **_initValue_** of an unqueued data element, **invalidValue** and **handleInvalid** are not configured. In this case, Rte_Read() function will return RTE_E_COM_STOPPED instead of RTE_E_NEVER_RECEIVED; which seems not correct. Is this the expected behavior from RTE?
>
> I'm trying to configure the project so that the RTE generates code in accordance with the specification requirement below:
> ![[RH-17140-image-2026-09-09-19-59-01-850.png]]
>
> To demonstrate that the RTE supports the use of HandleNeverReceived.
>
> But the RTE report errors:
> ![[RH-17140-image-2026-09-09-20-03-00-955.png]]
>
> Could you also help check this error?
>
> I have attached the project to this ticket. The password to unzip it is the same as the one I sent you previously.
> The testing port is RPort - SysSigGrp_C1_ADS_MP_EPS_AngCtrl_E2E of component CDD_ComUser.
> I found two related known issues documented in the Release Notes:
> ![[RH-17140-image-2026-09-09-21-29-57-039.png]]
>
> Thank you,
> [^Isolar_RH-17140.zip]

-------

> [!note]+ 2026-09-09 10:58 · Dang Ho Anh
> Hi Junsheng ZHANG,
> The initial value of the global buffer Rte_Rx_* is set to RTE_E_NEVER_RECEIVED because the attribute *HandleNeverReceived* is set to true
> ![[RH-17140-image-2026-09-09-15-20-57-496.png]]
>
> The effect of this attribute is described below:
> ![[RH-17140-image-2026-09-09-15-24-27-092.png]]
>
> If this feature is not required for the use case, please set HandleNeverReceived to false. The initial value of the RTE variable will then be set to RTE_E_OK.
> Or please share the customer’s use case so I can analyze it further, as RTE supports different use cases based on our configuration.
>
> CC: [Koduri Vamsi Kiran (ETAS-ECM/XPC-Abt1)](https://confluence.etas-dev.com/display/~kod4abt)

-------

> [!note]+ 2026-09-08 10:31 · JSM Service Bot
> Junsheng ZHANG, the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-09-08 10:31 · Junsheng ZHANG
> password ： ETAS
>
>
> [^Gen.7z]

-------

> [!note]+ 2026-09-07 18:25 · Phong Tang Dieu
> Hi Junsheng ZHANG
> Could you please describe more detailed about the use case? 
> And could you share the project as well? It would be helpful to analyze the issue. From my side, I could find any similar generated code even for E2E and E2EXf.
> Thanks,

-------

> [!note]+ 2026-09-07 15:21 · JSM Service Bot
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

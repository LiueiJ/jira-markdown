---
jira_key: RH-17085
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17085"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Customer
priority: Critical
project: RH
assignee: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
reporter: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
tags: [jira/comp/rta-rte, jira/label/makw]
fix-versions: []
epic: null
parent: null
created: "2026-09-01T07:12:26.000+0200"
updated: "2026-09-10T05:24:25.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi hotline, 

 The customer found during their review of the RTE code that many variables which are configured/defined with initial values are being placed in the CLEAR section, which is incorrect. Is this caused by configuration, or is it a bug? 

![[RH-17085-image001.png]] 

 ![[RH-17085-image002.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-08 10:27 · [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Ngoc Duong Thi]]
> [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Auges Tchouante]] , It has been planned in RTA-RTE 12.14.0 

-------

> [!note]+ 2026-09-08 10:07 · [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Auges Tchouante]]
> [[Duong_Thi_Ngoc_(ETAS-ECMXPC-Yok1)|Ngoc Duong Thi]] I had a discussion with the reporter and he's asking for  the timeline by when the issue will be fixed.

-------

> [!note]+ 2026-09-04 13:03 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> HI [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]] Can we have call to see how memory sections are handled within this project? please invite me and [[Tchouante_Auges_(ETAS-ECMXPC-Abt1)|Auges Tchouante]].

-------

> [!note]+ 2026-09-04 09:42 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]],
>
> the customer wants this to be treated as a bug and fixed in RTA-CAR 12.11 by a sub-release.
> Please tell how the plan is to continue with it.
> In particular a time line would be important for the customer when the fix would be available as part of a release.
>
>
>
> Best
> Shaker

-------

> [!note]+ 2026-09-03 12:17 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]] , this seems to be a known issue from RTE and will be analyzed using linked ticket.

-------

> [!note]+ 2026-09-02 10:42 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-02 10:42 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-09-02 10:42 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]],
>
> as specified above customer is highlighting that generated section names are not correct.
> When applying Workaround 1/2 the customer is not facing any issues.
>
>
>
> But this is causing a development related pain point of the customer side.
> Since initially the linker script and startup code was handling the sections based on their name SEC_VAR_CLEARED_8.
> And now with this issue they need to manually check every SEC_VAR_CLEARED section and adjust their linker script for it.
>
> Could you then please check:
>  # if this is as a bug and provide a fix for this (customer wants this to be fixed)
>  # If this can be avoided by an RTA Configuration
>
>
>
> Best
> Shaker

-------

> [!note]+ 2026-09-02 08:22 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]] ,
>
> Also, the customer’s project is confidential, and the linker and startup code will not affect the RTE-generated code. Can you tell me exactly what to check to confirm the root cause?

-------

> [!note]+ 2026-09-02 08:19 · [[JSM_Service_Bot|JSM Service Bot]]
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-09-02 08:19 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]] ,
>
> This issue currently impacts the customer’s MPU development. The customer also wants to know whether this is caused by a configuration problem or a tool bug.  If it is configuration-related, I can help the customer modify the configuration. But if it is a tool bug, we should inform the customer about the expected fix timeline and the plan.

-------

> [!note]+ 2026-09-01 14:21 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> agree that global variables/buffers/structures with an init value should be mapped to
> a section  SEC_VAR_INIT_8 instead of ... SEC_VAR_CLEARED_8.
>
>
>
> Can you please:
>  # explain if or how this is currently blocking the customer
>  # Upload the Project with generated Code
>  ## especially with linker script and startup code
>
>
>
> From current understanding it as an issue that should be fixed but can not observe directly a bug here for the ECU.
> Workaround 1: 
> The section name SEC_VAR_CLEARED_8 can be mapped in the linker script to RAM.
>
> Workaround 2:
> In the Startup code the customer should then not Zero/Init the sections.
> Instead Startup code needs to load the initial values of the sections (from C-Flash to the RAM).
> ```
> Draft:
> copy_data(&__app_data_start_ram, &__app_data_start_flash, &__app_data_end_ram - &__app_data_start_ram);{code}
>
>
> The workarounds are is also safe / ensure data consistency for sections containing initialized and not initialized variables.
> Since in all C-Standards a not initialized global variable is per default initialized to zero.
> Means:
> Putting a uninitialized variable in a section SEC_VAR_INIT_8 or
> of SEC_VAR_CLEARED_8 achive the same buffer initialization results (will be Zero).
>
>
>
> Best
> Shaker

-------

> [!note]+ 2026-09-01 07:39 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

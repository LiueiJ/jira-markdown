---
jira_key: RH-12824
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12824"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: yinchuan.xu@etas.com
reporter: yinchuan.xu@etas.com
tags: []
components: [Drivers/Transceivers for Can-Lin-Fr]
fix-versions: []
epic: null
parent: null
created: "2025-04-16T08:52:02.000+0200"
updated: "2026-03-05T06:52:05.000+0100"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-12824 Cantrcv_cfg.h issue

> [!jira] Closed · Medium · [[Yinchuan_XU|Yinchuan XU]] · 更新于 2026-03-05T06:52:05.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12824)

> 标签：#jira/comp/drivers/transceivers-for-can-lin-fr

## 描述

Hello Hotline: 

 In RTA-CAR 12.6.0, I found a problem when I generate Cantrcv code, as below, the Indexes of CanTrcv channels is CANTRCV_(channel name), but the list are all capital code, 

![[RH-12824-image001.png]] 

 I search the generate rule in tool script, and found it really change to upper_case. So I’m curious about why these two are not same? 

![[RH-12824-image002.png]] 

 ** Yinchuan XU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Yinchuan.XU@etas.com!mail_small.gif!](mailto:Yinchuan.XU@etas.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 Room 2601, Baoland Plaza, No.83 Pazhou Avenue, Haizhu District, Guangzhou 510308, P.R. China 

 [www.etas.com](http://www.etas.com)  ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-10-18 15:07 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-07-09 04:58 · [[Mingye_YUAN|Mingye YUAN]]
> Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0.

-------

> [!note]+ 2025-06-25 08:09 · [[Chandran_E_K_Subhash|Chandran E K Subhash]]
> Hello [[Alex_Fargus|Alex Fargus]],
>
> As discussed in the below comments, the update is considered as a minor improvement in the CanTrcv component. Change will be available in RTA-CAR 12.8.0 as part of the EPIC  [ARCMND-5914](https://jira.etas-dev.com/browse/ARCMND-5914) (Story - [ARCMND-6582](https://jira.etas-dev.com/browse/ARCMND-6582)).
>
> Regards,
>
> Subhash

-------

> [!note]+ 2025-06-25 05:53 · [[Alex_Fargus|Alex Fargus]]
> [[Chandran_E_K_Subhash|Chandran E K Subhash]] Please can you share the defect ticket for the fix you reported below?

-------

> [!note]+ 2025-06-23 11:33 · [[Chandran_E_K_Subhash|Chandran E K Subhash]]
> Hello [[Mingye_YUAN|Mingye YUAN]],
>
> This issue is already addressed by the platform and the correction will be available in the next release.
>
> Sorry for the delay in response, ticket went unnoticed.
>
> Regards,
>
> Subhash

-------

> [!note]+ 2025-06-23 10:46 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Sammy_Burchmore|Sammy Burchmore]] this issue requires your attention.

-------

> [!note]+ 2025-04-23 08:07 · [[Mingye_YUAN|Mingye YUAN]]
> Hello [[Chandran_E_K_Subhash|Chandran E K Subhash]] :
>
> Could you please correct it since customer is already not pleased about this error.

-------

> [!note]+ 2025-04-22 12:27 · [[Chandran_E_K_Subhash|Chandran E K Subhash]]
> Hello [[Yinchuan_XU|Yinchuan XU]],
>
> I understand the issue and not denying it. The rationale behind keeping these macros in the Cfg.h was for internal testing purpose and are no longer used within our environment. This is the reason why this issue was not detected from platform.
>
> It is not always advisable to use a non standardized information when there is a standardized information already available (Symbolic Name).
>
> From platform, yes we can either correct or remove these macros in mainline version of the software as an improvement.
>
> To unblock the customer and to have a AR standardized approach, I propose to use the symbolic names instead of the macros which are currently being used in CanTrcv_User.c.
>
>
>
> Regards,
>
> Subhash

-------

> [!note]+ 2025-04-21 03:51 · [[Yinchuan_XU|Yinchuan XU]]
> Hello [[Chandran_E_K_Subhash|Chandran E K Subhash]] 
>
> What is used in CanTrcv_User.c not important, it is really integration code. And I just show you the detail error.
>
> What's important is that the channel name is used error in CanTrcv_Cfg.h, as below:
>
> ![[RH-12824-image-2025-04-21-09-46-51-121.png]]
>
> Customer really can't accept this unbelievable issue.

-------

> [!note]+ 2025-04-18 13:11 · [[Chandran_E_K_Subhash|Chandran E K Subhash]]
> Hello [[Yinchuan_XU|Yinchuan XU]],
>
> I see that the error is thrown from CanTrcv_User.c file which is not delivered as part of CanTrcv component. I assume that it is an integration code.
>
> However, as per AUTOSAR, The type of *CanTrcvChannelId* parameter is defined as "{_}EcucIntegerParamDef (Symbolic Name generated for this parameter){_}" and the components or integration code which needs to use the *CanTrcvChannelId* should use the Symbolic Name generated by Can Transceiver in CanTrcv_Cfg.h file.
>
> ![[RH-12824-image-2025-04-18-16-39-26-395.png]]
> So could you please ask the customer to use the symbolic names instead of the macros which are currently being used in CanTrcv_User.c? This approach aligns with the expectation from AUTOSAR.
>
> Symbolic names are generated in CanTrcv_Cfg.h as {_}CanTrcvConf_CanTrcvChannel{_}<CanTrcvChannel_ShortName>.

-------

> [!note]+ 2025-04-17 04:45 · [[Yinchuan_XU|Yinchuan XU]]
> Hi [[Sammy_Burchmore|Sammy Burchmore]] 
>
> When I build the generate code, it report error, as below:
>
> ![[RH-12824-image-2025-04-17-10-38-36-811.png]]
>
> For currently, I modify it manually, but customer is very unsatisfied with it, they said why our product have such unbelievable issue.

-------

> [!note]+ 2025-04-16 15:50 · [[Sammy_Burchmore|Sammy Burchmore]]
> Hi [[Yinchuan_XU|Yinchuan XU]],
>
> Before I ask the developers, is this causing any issues or are you just interested in understanding the design philosophy?
>
> Thanks,
>
> Sammy

-------

---
jira_key: RH-15158
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15158"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[Dong_LIU|Dong LIU]]"
reporter: "[[Dong_LIU|Dong LIU]]"
tags: [jira/comp/memory-drivers]
fix-versions: [RTA-CAR 12.11.0]
epic: null
parent: null
created: "2026-02-10T10:19:13.000+0100"
updated: "2026-04-04T11:37:01.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi, 

Cariad reported an issue with the MemAcc module.  

The version of RTACAR is RTA-CAR 12.11.0VCTCESR1pr1. 

 **Project Configuration Overview:** 

The customer configured MemAccAddressAreaConfiguration_APP in the MemAcc module, and under this container, four MemAccSubAddressAreaConfiguration were configured, as shown in the following image: 

![[RH-15158-image001.png]] 

These four MemAccSubAddressAreaConfigurations each refer to a MemSectorBatch under four different MemInstances in the Mem module. 

![[RH-15158-image002.png]] 

![[RH-15158-image003.png]] 

 **Problem Description:** 

In actual testing, the customer tested the MemAcc's MemAccAddressAreaConfiguration_APP and found an issue with the idInstance_uo parameter being passed when reading and writing data across MemInstances, as shown in the red box in the image below. 

![[RH-15158-image004.png]] 

After investigation, the DeviceData_pst->idHwCur_o at line 999 was changed to MemJobData_pst->El_MemSectorDescr_pcst->idHw_o at line 1000, and the test passed, as shown in the image below. 

![[RH-15158-image005.png]] 

 **Customer Request:** 

The customer wants to confirm whether it is a software issue. If it is a software issue, the customer hopes that we can release a fix package.  

Thank you. 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 Tel. +86 21 2218-4408 | [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-04-04 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-03-19 17:42 · [[Dong_LIU|Dong LIU]]
> [[Tobias_Ernst|Tobias Ernst]] 
>
> ok, thank you!

-------

> [!note]+ 2026-03-16 21:55 · [[Tobias_Ernst|Tobias Ernst]]
> The issue can be confirmed however the solution shall look differently.
> The change should be made in
>
> line 895 in the same file, function {color:#795e26}MemAcc_Prv_PrepareNewMemJobInit{color}
> {color:#af00db}#if{color}{color:#0000ff} (MEMACC_RB_USE_MULTI_HW {color}{color:#000000}!={color}{color:#0000ff} STD_OFF){color}
> {color:#008000}            /* Update idHwCur_o so that all subsequent callers{color}
> {color:#008000}             * (PrepareTimeHandling, dependency scheduling) see correct HW channel */{color}
> {color:#3b3b3b}            {color}{color:#001080}DeviceData_pst{color}{color:#3b3b3b}->{color}{color:#001080}idHwCur_o{color}{color:#3b3b3b} {color}{color:#000000}={color}{color:#3b3b3b} {color}{color:#001080}MemJobData_pst{color}{color:#3b3b3b}->{color}{color:#001080}El_MemSectorDescr_pcst{color}{color:#3b3b3b}->{color}{color:#001080}idHw_o{color}{color:#3b3b3b};{color}
> {color:#af00db}#endif{color}
> This ensures that {color:#001080}DeviceData_pst{color}{color:#3b3b3b}->{color}{color:#001080}idHwCur_o{color} is updated as needed.
> Please remove also the "const" from the function signature
>
> Related function will be updated in RTA-CAR 12.11.0.
>
> The applied original change is working if not all all features of MemAcc (like timeout monitoring) are activated or parameters are not different dependent on the HW.

-------

> [!note]+ 2026-03-09 09:36 · [[Dong_LIU|Dong LIU]]
> The customer’s actual use case requires configuring **4 MemInstances** in the {*}Mem module{*}. In this scenario, when four instances are configured, the {*}Instance ID passed from MemAcc to the Mem module is always the ID of the first instance{*}, and the IDs of the other three instances cannot be passed to the Mem module.
>
> After the customer modified the code {*}from line 999 to the code at line 1000{*}, the issue was resolved.
>
> The customer would like us to {*}evaluate this issue and implement a fix in the official release of RTACAR 12.11{*}.
>
> thank you !

-------

> [!note]+ 2026-03-02 06:33 · [[Dong_LIU|Dong LIU]]
> [[V_Venkatachalam|V Venkatachalam]]
>
> the customer would like to keep the current configuration and does not want to make any changes to it. 
>
> After manually modifying the code at line 1000, the customer was able to pass the test. They would like to know if this change is reasonable and want the product team to confirm whether a fix package release is needed.

-------

> [!note]+ 2026-02-27 13:17 · [[V_Venkatachalam|V Venkatachalam]]
> Hi Dong,
>
> I noticed that the current configuration has multiple meminstances set up for a single device.
>
> Could you please restructure this so that each device has {*}one meminstance{*}, with **multiple sectorbatches** defined within that single meminstance? The different sectorbatches can then be referenced through separate memAcc address area configurations.
>
> This approach should simplify the overall structure while maintaining the necessary flexibility for addressing.
>
> Please let me know if you need any clarification or have questions about this setup.
>
> Best regards,
> Venki

-------

> [!note]+ 2026-02-12 19:14 · [[Max_Sinclair|Max Sinclair]]
> Hi [[V_Venkatachalam|V Venkatachalam]] ,
>
> I'm not familiar enough with the MemAcc implementation to really analyze this. 
>
> Would you be able to have look at the customer modification and/or suggest a work around.
>
> Many thanks,
> Max

-------

> [!note]+ 2026-02-10 10:39 · [[Dong_LIU|Dong LIU]]
> The project is attached.[^Isolar.zip]

-------

> [!note]+ 2026-02-10 10:39 · [[Dong_LIU|Dong LIU]]
> [^Isolar.zip]

-------

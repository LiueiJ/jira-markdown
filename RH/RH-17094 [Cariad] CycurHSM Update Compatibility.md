---
jira_key: RH-17094
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17094"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[Steven.Tang|Steven.Tang]]"
reporter: "[[Steven.Tang|Steven.Tang]]"
tags: [jira/comp/cycurhsm3]
fix-versions: []
epic: null
parent: null
created: "2026-09-02T04:19:31.000+0200"
updated: "2026-09-07T10:57:44.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Team, 

Cariad Project encountered the following issue, which is of extremely high urgency.  

We need to make every effort to resolve it by September 2, 2026, to avoid causing the customer to disassemble the vehicles again. 

If there is anything inaccurate or imprecise in the description, [@CAI Badun (ETAS-ECM/XSF-CN)!mail_small.gif!](mailto:Badun.CAI@etas.com)[@ZHANG Junsheng (ETAS-ECM/XSF-CN)|mailto:Junsheng.ZHANG@bosch.com]please help review and correct it.  

Thank you all for your support. 

Regarding the upgrade path from  **CycurHSM 3.0.7.b1 to 3.0.7.b3 or a later version**. The customer needs a clear confirmation on whether the existing HSM version can be upgraded directly and whether any additional adaptation or migration steps are required.  

This compatibility question is currently affecting the customer's HSM validation and upgrade activities. 

 **Best Regards,** 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-07 10:53 · [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]]
> Let's update the current situation in this ticket:
>
> 1, CARIAD four-domain ECUs (CCU,LZCU,RZCU&TZCU) software to fix CycurHSM3.0.7.b1 Issue have passed pressure test and be release to their onsite engineer for ECU flash last Friday morning.
>
> 2, Their onsite engineer finished around 80 ECUs flash from 3.0.7.b1 to 3.0.7.b4 regular. They continue the remain around 240  3.0.7.b1 ECUs flash work from this Monday. This work will be done estimate by this Thursday.
>
> 3, CARIAD already update the ECU software with 3.0.7.b4 regular to their factory, then there will no further 3.0.7.b1 ECU be manufactured from last Friday.
>
> So close this ticket now. we will track the situation, any update will let all of you know.
>
> Thanks a lot for your support.

-------

> [!note]+ 2026-09-07 09:14 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Sathish Kumar Madanmohan]]
> The issue is addressed and customer has done the stress testing and the feedback is positive. 
>
> THe next step is ensure the solution is of production quality. 
>
> [[Sandra_Weigl|Sandra Weigl]]  next step is to release this in production quality.  Customer expected date : E.09 / or 1st Week of Oct-2026
>
> [[Steven.Tang|Steven.Tang]] [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]  [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]  fyi

-------

> [!note]+ 2026-09-02 07:36 · [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]]
> we meet the CycurHSM 3.0.7.b1 could not be updated to the new released Hotfix package CycurHSM3.0.7.b3 problem. detail you can see the following: 
>
>
>
> 3.0.7 HSM self update test：
>
> b1 -> b1 : OK
>
> b1 -> b3 : NOTOK (errorCode:0x80008220)
>
> b3 -> b3 : OK
>
> b3 -> b1 : NOTOK (errorCode:0x80008220)
>
>
>
> VCTC customer is very worry about it, because they are just updating the 300 sample ECUs from 3.0.5 to 3.0.7.b1. If the 3.0.7b1 could not be updated problem happen, then it will bring very serious problem to them, it is totally not acceptable.
>
>
>
> **VCTC ask us to find out the root cause and confirm whether it could be updatable from CycurHSM 3.0.7.b1 to the upper version package such as CycurHSM 3.0.7.b3 by today. This is mandatory.**  
>
> **Please help to arrange resource to support on this topic urgently.**

-------

> [!note]+ 2026-09-02 04:23 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Steven.Tang. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

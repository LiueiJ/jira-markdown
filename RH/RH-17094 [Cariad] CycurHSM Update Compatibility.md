---
jira_key: RH-17094
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17094"
server: rtahotline
kind: hotline
type: Support
status: Investigation Required
priority: Critical
project: RH
assignee: lukas.riemenschneider@etas.com
reporter: steven.tang@etas.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-02T04:19:31.000+0200"
updated: "2026-09-02T10:07:00.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-17094 [Cariad] CycurHSM Update Compatibility

> [!jira] Investigation Required · Critical · [[Lukas_Riemenschneider|Lukas Riemenschneider]] · 更新于 2026-09-02T10:07:00.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17094)

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

> [!note]+ 2026-09-02 07:36 · [[Steven_TANG|Steven TANG]]
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

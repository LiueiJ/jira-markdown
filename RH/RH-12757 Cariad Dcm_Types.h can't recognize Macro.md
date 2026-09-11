---
jira_key: RH-12757
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12757"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: "[[Yinchuan_XU|Yinchuan XU]]"
reporter: "[[Yinchuan_XU|Yinchuan XU]]"
tags: [jira/comp/diagnostic-communication]
fix-versions: []
epic: null
parent: null
created: "2025-04-08T07:59:11.000+0200"
updated: "2026-03-05T06:52:02.000+0100"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hello Hotline: 

 In Rta-Car 12.6.0, when I build Dcm module with GHS compiler, it report error as below: 

![[RH-12757-image001.png]] 

 Such as line 472 in Dcm_Types.h is as below: 

![[RH-12757-image002.png]] 

 I found that in Dcm_Types.h, it doesn’t include any head file, so the compiler will not recognize the identifier.  

For currently, I add Dcm.h in Dcm_Types.h, and it can build normal, but I don’t think it is a good way to solve this problem, because I modify static code. So could you help to check is there a better way to solve it? 

![[RH-12757-image003.png]] 

 ** Yinchuan XU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Yinchuan.XU@etas.com!mail_small.gif!](mailto:Yinchuan.XU@etas.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 Room 2601, Baoland Plaza, No.83 Pazhou Avenue, Haizhu District, Guangzhou 510308, P.R. China 

 [www.etas.com](http://www.etas.com)  ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-07-24 18:01 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-07-09 18:25 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2025-06-25 05:59 · [[Alex_Fargus|Alex Fargus]]
> Move the ticket state to "waiting for customer" because the last comment from [[Raghuram_Telagamsetti|Raghuram Telagamsetti]] appears to be asking for more information.

-------

> [!note]+ 2025-06-12 12:17 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Sammy_Burchmore|Sammy Burchmore]] this issue requires your attention.

-------

> [!note]+ 2025-04-08 15:20 · [[Raghuram_Telagamsetti|Raghuram Telagamsetti]]
> [[Yinchuan_XU|Yinchuan XU]]
>
> It is important to note that the `Dcm.h` file should not be included within the `Dcm_Types.h` file, as the `Dcm.h` file already includes {{{}Dcm_Types.h{}}}.
>
> Could you please confirm if you are including `Dcm_Types.h` in your application software? If so please include Dcm.h instead of Dcm_Types.h.

-------

> [!note]+ 2025-04-08 12:20 · [[Sammy_Burchmore|Sammy Burchmore]]
> Hi [[Raghuram_Telagamsetti|Raghuram Telagamsetti]],
>
> Why is Dcm.h not included in Dcm_Types? It seems like it should be and its causing a compilation error in RTA-CAR 12.6.0. Currently the customer is working around this by including the file manually.
>
> Thanks,
>
> Sammy

-------

> [!note]+ 2025-04-08 12:16 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Diagnostic Communication Support Owner. This ticket requires an assignee.

-------

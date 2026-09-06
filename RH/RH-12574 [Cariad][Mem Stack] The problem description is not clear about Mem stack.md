---
jira_key: RH-12574
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12574"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: yinchuan.xu@etas.com
reporter: yinchuan.xu@etas.com
tags: [VNCNMS]
components: [Memory High-Level]
fix-versions: []
epic: null
parent: null
created: "2025-03-18T10:24:27.000+0100"
updated: "2026-06-01T11:38:04.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-12574 [Cariad][Mem Stack] The problem description is not clear about Mem stack

> [!jira] Closed · Medium · [[Yinchuan_XU|Yinchuan XU]] · 更新于 2026-06-01T11:38:04.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12574)

> 标签：#jira/comp/memory-high-level #jira/label/vncnms

## 描述

Hello Marc & Hotline colleagues:

I’m confused by the problem description, the RTA-CAR version is 12.6.0. I think it’s a typical problem of our tool, and many customer had complained about this.

The project report error like below:

![[RH-12574-image001.png]]

But finally the cause is I need configure* 

**{**}NvMRbEaDevices to 1{*}, the problem description has absolute nothing to do with the real cause.

![[RH-12574-image002.png]]

Another problem is if I don’t configure FeemainfunctionPeriod/EaMainfunctionPeriod/EepmainfunctionPeriod, it will report error this element is less than the lower multiplicity

![[RH-12574-image003.png]]

But if I configure it, it report this element is greater than the upper multiplicity.

![[RH-12574-image004.png]]

Actually, the root cause is I don’t have any fee block in NVMBlockDescription, but I still generate Fee module.

So could u help to optimize the problem description, it really takes us too much time to resolve these problem.

**Yinchuan XU** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

[Yinchuan.XU@etas.com!mail_small.gif!](mailto:Yinchuan.XU@etas.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

No.6 Zhujiang East Road, Tianhe District, Guangzhou 510062, P.R. China 

[www.etas.com](http://www.etas.com/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-06-01 11:38 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-05-18 05:53 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Yinchuan_XU|Yinchuan XU]] ,
>
> As confirmation from L3 dev, I'll change the status to "Solution Proposed". If you found any new concerns of this topic, kindly help me re-open this ticket. Thank you.

-------

> [!note]+ 2026-05-07 06:24 · [[M_S_Karthik|M S Karthik]]
> changing the component to Mem-HL, so it can be processed as soon as 12.11.0 is released. 

-------

> [!note]+ 2026-03-02 08:25 · [[Tobias_Ernst|Tobias Ernst]]
> The question behind is then why is the Fee configured as some dummy.
> The reason could be that the Fee always need to be configured if it is available - this I have to check.
>
> For sure the Fee does not need to be configured if it is NOT available.
> That is the typical use-case outside RTA-CAR. 
> But in RTA-CAR, Fee is available but NOT configured.
> This is currently not really working and users might have to work-around by setting up a dummy Fee.
>
> This is not good - addressed in linked problem ARCMND-9917.
> Will be added to RTA-CAR 12.11.0.

-------

> [!note]+ 2026-03-02 07:51 · [[Tobias_Ernst|Tobias Ernst]]
> The error message is only coming if you have something configured for the Fee by the user. Please check your configuration. If there is nothing configured for the Fee and nothing requested to be forwarded from Fee, then this error does not occur.

-------

> [!note]+ 2026-03-02 07:12 · [[Alex_Fargus|Alex Fargus]]
> {quote}Actually, the root cause is I don’t have any fee block in NVMBlockDescription, but I still generate Fee module. 
> {quote}
> This looks to be another case where code is generated despite the validation errors. [[M_S_Karthik|M S Karthik]] [[Sunith_Jayakumar_Rohith|Sunith Jayakumar Rohith]] 

-------

> [!note]+ 2025-07-02 13:07 · [[Alex_Fargus|Alex Fargus]]
> [[M_S_Karthik|M S Karthik]] This looks to be an ISOLAR-B topic, who should it be assigned to?

-------

> [!note]+ 2025-03-27 11:12 · [[Tobias_Ernst|Tobias Ernst]]
> [[V_Venkatachalam|V Venkatachalam]] : The problem is the input validation framework which is making checks before the actual driver-script can work on them and make a more suitable output. So the Mem team is the wrong team to be addressed. It is a limitation of the tooling.
>
> The only point we can influence is to switch off the input validation completely - this is however not wanted.

-------

> [!note]+ 2025-03-18 10:54 · [[Adrian_Funk|Adrian Funk]]
> [[V_Venkatachalam|V Venkatachalam]] : Hi Venki, can you please take over? Thank you!

-------

> [!note]+ 2025-03-18 10:45 · [[Nikesh_Vishak|Nikesh Vishak]]
> [[Adrian_Funk|Adrian Funk]] : can you please get this hotline ticket analyzed? Thank you

-------

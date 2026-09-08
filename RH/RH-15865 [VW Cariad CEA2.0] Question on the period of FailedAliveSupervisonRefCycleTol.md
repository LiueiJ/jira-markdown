---
jira_key: RH-15865
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15865"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: jie.liu8@etas.com
reporter: jie.liu8@etas.com
tags: []
components: [System-InfraLib-Safety]
fix-versions: []
epic: null
parent: null
created: "2026-04-24T05:53:57.000+0200"
updated: "2026-06-15T06:10:33.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-15865 [VW Cariad CEA2.0] Question on the period of FailedAliveSupervisonRefCycleTol

> [!jira] Closed · High · [[Jie_LIU|Jie LIU]] · 更新于 2026-06-15T06:10:33.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-15865)

> 标签：#jira/comp/system-infralib-safety

## 描述

Dear hotline, 

Background: During the integration of Multi-partion WdgM feature on VW Cariad CEA2.0 project, customer found FailedAliveSupervisonRefCycleTol uses the supervision cycle as the period for the counter instead of the period of WdgM_MainFunction. 

Which seems inconsistent with the AUTOSAR following specification: 

![[RH-15865-image001.png]] 

 **Customer needs clarification on the requirements and implementation on the period usage, please help!** 

 ** Jie LIU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 M +86 138 16227585 

 [Jie.LIU8@etas.com!mail_small.gif!](mailto:Jie.LIU8@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- is mentioned in: [[RHK-1338 Watchdog 기반 Alive Supervision 구현 데모 요청]]

## 评论

> [!note]+ 2026-05-28 09:44 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> Hi [[Jie_LIU|Jie LIU]] 
>
> Can you closed this ticket?

-------

> [!note]+ 2026-05-14 11:30 · [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]]
> As per AUTOSAR specifications **[ECUC_WdgM_00310]** and {*}[ECUC_WdgM_00327]{*}, the Alive Supervision calculation is based on the timing derived from the {*}Supervision Reference Cycle{*}, rather than the execution period of {{{}WdgM_MainFunction{}}}. Accordingly, the parameter `WdgMFailedAliveSupervisionRefCycleTol` uses the Supervision Reference Cycle as the reference unit for its counter.
>
> ![[RH-15865-image-2026-05-14-15-01-25-887.png]]
>
>
>   ![[RH-15865-image-2026-05-14-15-02-02-352.png]]
> ![[RH-15865-image-2026-05-14-15-01-25-887.png]] ![[RH-15865-image-2026-05-14-15-02-02-352.png]]

-------

> [!note]+ 2026-05-13 10:54 · [[Jie_LIU|Jie LIU]]
> Dear experts, any feedback on this ticket ?

-------

> [!note]+ 2026-05-07 07:41 · [[S_P_Deepak|S P Deepak]]
> Hi [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] ,
>
> Could you please check this?
>
> It looks to be a bit of inconsistency in the Autosar Spec.
>
> Regards,
>
> Deepak S P

-------

> [!note]+ 2026-05-06 16:20 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[S_P_Deepak|S P Deepak]], this System-InfraLib-Safety ticket requires an assignee. As the component lead for System-InfraLib-Safety, please ensure the 'Level 3 Assignee' field is set the appropriate person that an handle this issue.

-------

> [!note]+ 2026-05-06 16:12 · [[Joshua_Cantwell|Joshua Cantwell]]
> Can someone in L3 give us an answer? My thought is that the current behaviour is the same as what the customer is expecting.

-------

> [!note]+ 2026-05-06 10:15 · [[Jie_LIU|Jie LIU]]
> [[Joshua_Cantwell|Joshua Cantwell]] could you please help to confirm?

-------

> [!note]+ 2026-04-29 04:00 · [[Jie_LIU|Jie LIU]]
> Hello, [[Joshua_Cantwell|Joshua Cantwell]] , the question is on the parameter **WdgMFailedAliveSupervisonRefCycleTol** , could you please confirm which period is used? Customer thinks it shall be the period of WdgM_Mainfunction according to the specification snapshot.

-------

> [!note]+ 2026-04-27 23:44 · [[Joshua_Cantwell|Joshua Cantwell]]
> Hi [[Jie_LIU|Jie LIU]],
>
> I don't understand the issue, my understanding of the behaviour of the watchdog is that it is supposed to use supervision cycle count as the period. This is how it does behave and this is how Autosar specifies it to behave.
>
>
>
> The Alive supervision algorithm is based on supervision cycles for it's timing as specified in AR.
>
> ![[RH-15865-image-2026-04-27-22-45-03-321.png]]
>
> ![[RH-15865-image-2026-04-27-22-47-33-890.png]]
>
> In the above screenshot we can see that the supervision reference cycle is part of alive supervision and alive supervision bases it's timing from the supervision reference cycle.
>
>
>
> Kind regards Josh C.
> ![[RH-15865-image-2026-04-27-22-45-03-321.png]] ![[RH-15865-image-2026-04-27-22-47-33-890.png]]

-------

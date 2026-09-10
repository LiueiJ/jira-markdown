---
jira_key: RH-16704
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16704"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
reporter: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
tags: [jira/comp/rta-rte]
fix-versions: []
epic: null
parent: null
created: "2026-07-20T10:15:37.000+0200"
updated: "2026-09-01T14:28:26.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline, 

 Currently, the customer is using RTA-CAR 12.11.0VCTCESR1pr1. After configuring the KeyM module in the BSW and generating code, they need to map  **KeyM_MainBackgroundFunction** to a Task in the RTE configuration. However, in reality, the customer does not want to use a Task of the Background type. 

Is there a way to avoid mapping this event? If we do not perform the mapping, RTE reports an error: “Target ARObject: <BE_KeyM_MainBackgroundFunction> RTE Event 'BE_KeyM_MainBackgroundFunction' within SW-C instance '/AUTOSAR_KeyM/BswImplementations/KeyM' is not mapped to a task. Ensure that all RTE Events that can activate a runnable entity are individually mapped to a task. - Line: 2301. &#91;Infos&#93; <BE_KeyM_MainBackgroundFunction> : </AUTOSAR_KeyM/BswModuleDescriptions/KeyM/BswInternalBehavior/BE_KeyM_MainBackgroundFunction> 

”.  

On the other hand, in the previous version (RTA-CAR 12.6), it was possible to skip the mapping and no error would be reported. 

 ![[RH-16704-image001.png]] 

![[RH-16704-image002.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-01 14:28 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-08-17 18:56 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-08-03 09:24 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> With this workaround solution, there is currently no way to avoid generating the background task.
>
> Could you share the motivation behind the customer’s request to prevent this function from being generated?

-------

> [!note]+ 2026-08-03 07:57 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]],
>
> I checked the customer's current configuration and found that OsTaskAutostart was not enabled; moreover, this task was also generated in the RTE. The customer's expectation is to no longer generate this task;
>
> ![[RH-16704-image-2026-08-03-13-57-17-456.png]]

-------

> [!note]+ 2026-07-31 13:26 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> You can refer to the workaround solution in the BIP project with RTA-CAR 12.9.0. The approach works as follows:
>  # Create a background task in the OS, but do not enable `OsTaskAutostart` for this task.
>  # Map KeyM_MainBackgroundFunction() to this background task. Since the task is not activated by any function, KeyM_MainBackgroundFunction() will not be called automatically by this background task.
>  # The user can manually call KeyM_MainBackgroundFunction{{{}(){}}} from another task as required.
>
> With this workaround, the RTE can be generated successfully, while the invocation of KeyM_MainBackgroundFunction() remains under user control.
>
> CC: [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]] 

-------

> [!note]+ 2026-07-29 04:53 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi [[Hritik_Mehta|Hritik Mehta]] [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] both, 
>
> Good morning, could you have a check on this issue?
>
> Noted with thanks!

-------

> [!note]+ 2026-07-29 04:53 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

> [!note]+ 2026-07-27 09:25 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Hritik_Mehta|Hritik Mehta]], Whats OS idle callback? I don't think this is as per recommendation from KeyM team i.e. to map either to a background task or low prio periodic task.

-------

> [!note]+ 2026-07-24 17:35 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-07-24 17:35 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]],
>
> A customer on **RTA-CAR 12.11.0.VCTCESR1pr1** calls **KeyM_MainBackgroundFunction** directly from the OS idle callback ({*}Os_Idle_cbk{*} per their description) and does not want any task mapping for the corresponding KeyM background event in the RTE configuration. RTE generation then stops with error 1563 for the unmapped {*}BE_KeyM_MainBackgroundFunction{*}. The KeyM L3 has already confirmed the function itself must run (background task type recommended, low-priority periodic repetitive task acceptable), so this remaining question is purely on the RTE side.
>
> The check implements {*}[SWS_Rte_07516]{*}, and **BswBackgroundEvent** is in the categorical must-map event list (RTEGen/Core/xmlquery.cpp:3065-3078, raise at RTEGen/Core/core.cpp:2692-2696; identical from releases/12.5.0 through 12.11.1). The only suppression mechanism is the deprecated `--error-as-warning=E001563` option which we do not want to offer to the customer. Please provide support with the following questions:
>  # Is there any supported way to have RTE generation succeed while this background event stays unmapped, given the integrator invokes the function manually from the OS idle callback?
>  # If not, is mapping the event to a lowest-priority OsTask that the integrator simply never activates an acceptable way to satisfy the check in this scenario, or does RTE rely on that task actually running?
>  # From the RTE point of view, are there any concerns with a BSW schedulable entity being invoked manually from the OS idle callback instead of an RTE-generated task body?
>
> Thanks,
> Hritik

-------

> [!note]+ 2026-07-23 08:08 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> The customer did not use the Schedule Table generated by RTE, so I have already implemented this function (KeyM_MainBackground Function) in Os_Idle_cbk; But the customer doesn't want to configure this task in RTE anymore;However, this will result in an error, so we need to address this issue

-------

> [!note]+ 2026-07-23 08:03 · [[JSM_Service_Bot|JSM Service Bot]]
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-07-23 08:03 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] ,
>
> Now, if I don't map to the Background Task or put it in a periodic task, RTE will report an error; Do we have a way to prevent RTE from reporting this error again;
>
>  “Target ARObject: <BE_KeyM_MainBackgroundFunction> RTE Event 'BE_KeyM_MainBackgroundFunction' within SW-C instance '/AUTOSAR_KeyM/BswImplementations/KeyM' is not mapped to a task. Ensure that all RTE Events that can activate a runnable entity are individually mapped to a task. - Line: 2301. [Infos] <BE_KeyM_MainBackgroundFunction> : </AUTOSAR_KeyM/BswModuleDescriptions/KeyM/BswInternalBehavior/BE_KeyM_MainBackgroundFunction

-------

> [!note]+ 2026-07-22 15:00 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> L3 has confirmed too:
> {quote}i will always recommend 'KeyM_MainBackgroundFunction must be scheduled only in the background task type'. if background task is not available in customer stand, then they can place KeyM_MainBackgroundFunction in any other low-priority periodic repetitive task of OS.
> {quote}
> Thanks,
>
> Hritik

-------

> [!note]+ 2026-07-22 06:53 · [[Balan_Arumugam|Balan Arumugam]]
> Hello Hritik,
>
> i will always recommend '{*}KeyM_MainBackgroundFunction{*} must be scheduled only in the background task type'. if background task is not available in customer stand, then they can place **KeyM_MainBackgroundFunction** in any other low-priority periodic repetitive task of OS. 
>
>
>
> Thanks,
>
> Arumugam

-------

> [!note]+ 2026-07-21 16:08 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Balan_Arumugam|Balan Arumugam]], this SEC-KeyM ticket requires an assignee. As the component lead for SEC-KeyM, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-21 16:07 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Balan_Arumugam|Balan Arumugam]],
>
> A CNMS/VCTC customer on RTA-CAR 12.11.0.VCTCESR1pr1 has configured KeyM and does not want to schedule **KeyM_MainBackgroundFunction** in a background-type task. The RTE rejects the unmapped background event (error 1563), which we consider correct, and we found no KeyM parameter that removes the event. Functionally the background function looks mandatory whenever KeyM is used, since certificate init completion and the asynchronous certificate and key request processing run only there.
>
> The KeyM documentation seems contradictory about the supported task types for this function. The integration advice says it 'should be scheduled in a background task or any other periodic but repetitive task of OS', while the limitations section says '{*}KeyM_MainBackgroundFunction{*} scheduling only in the chain task type background task is supported'. On the RTE side, AUTOSAR also allows activating a background event periodically via an OS alarm or schedule-table expiry point instead of a real background task.
>
> Could you please confirm the analysis? And if it is correct: is scheduling **KeyM_MainBackgroundFunction** periodically from a normal task (for example via {*}RteBswUsedOsAlarmRef{*} or {*}RteBswUsedOsSchTblExpiryPointRef{*}, or any periodic repetitive task) supported and validated for KeyM, or is the chain-type background task the only supported mode? If periodic scheduling is supported, is there guidance on the minimum frequency, and could the limitations section be aligned with the integration advice so both state the same thing?
>
> Thanks,
> Hritik

-------

> [!note]+ 2026-07-21 16:05 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> From our analysis this is expected behaviour: a background event like the one for **KeyM_MainBackgroundFunction** must always be mapped to a task, and there is no KeyM configuration option that removes the event. Since you prefer not to use a background-type task, I am checking with our KeyM development team what the recommended and officially supported way to schedule this function is in your case, and I will follow up as soon as I have their confirmation.
>
> Regarding RTA-CAR 12.6: we compared both versions and the relevant RTE check as well as the KeyM module description are identical, so the same configuration should have raised the same error in 12.6 too. Could you please share the 12.6 project (or at least its Rte configuration) where no error was reported? That would let us pinpoint the difference; most likely the event was already mapped there.
>
> Best regards,
> Hritik

-------

> [!note]+ 2026-07-20 17:49 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> Apologies for the delay, this is now under investigation.
>
> Thanks,
>
> Hritik

-------

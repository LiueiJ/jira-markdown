---
jira_key: RH-13706
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13706"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: "[[Yuan_ZHANG|Yuan ZHANG]]"
reporter: "[[Yuan_ZHANG|Yuan ZHANG]]"
tags: [jira/comp/rta-rte]
fix-versions: []
epic: null
parent: null
created: "2025-08-13T08:02:57.000+0200"
updated: "2026-03-05T06:52:04.000+0100"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

hi hotline colleagues,

Recently my customer gave the feedback that, the datatype of DcmDspRoutine Signal generated in SWC code frame is inconsistent with that generated in Rte with **Version RTACAR 12.6.0**

As you can see the declaration of input parameter **DataIn_DcmDspStartRoutineInSignal** in function **RoutineServices_DcmDspRoutine_0xC000_Start** is defined as P2CONST. a pointer

![[RH-13706-image-2025-08-13-13-50-18-094.png]]

however in generated code frame, the definition of input parameter **DataIn_DcmDspStartRoutineInSignal** in function **RoutineServices_DcmDspRoutine_0xC000_Start** is defined as VAR, which is inconsistent with its declaration.

![[RH-13706-image-2025-08-13-13-54-59-449.png]]

The related code files are attached in zip file.

Thanks!

[code file.zip!link_attachment_7.gif!](/jira/secure/attachment/169282/169282_code+file.zip)

## 评论

> [!note]+ 2025-10-18 15:07 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-09-19 09:56 · [[James_Butterfield|James Butterfield]]
> Hi [[Yuan_ZHANG|Yuan ZHANG]],
>
> Do you have any updates on this ticket?
>
> Best Regards,
> James

-------

> [!note]+ 2025-09-04 10:02 · [[Yuan_ZHANG|Yuan ZHANG]]
> hi [[James_Butterfield|James Butterfield]] 
>
> Thanks for your reply. Because of data confidentiality rule, customer can't not provide the whole project to me. I will try to regenerate the issue with available project in my hand then contact you. 

-------

> [!note]+ 2025-09-03 10:06 · [[James_Butterfield|James Butterfield]]
> Hi [[Yuan_ZHANG|Yuan ZHANG]],
>
> Did you get this issue resolved in the end?
>
> Best Regards,
> James

-------

> [!note]+ 2025-09-02 18:27 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2025-08-19 12:24 · [[James_Butterfield|James Butterfield]]
> Hi [[Yuan_ZHANG|Yuan ZHANG]],
>
> I believe this could be a bug with the Code Frame Generator however I would like to be able to recreate this issue on my end to confirm this suspicion.
> Could you please ask the customer to provide the full project file?
>
> Best Regards,
> James

-------

> [!note]+ 2025-08-19 11:30 · [[Yuan_ZHANG|Yuan ZHANG]]
> thanks for your explanation from RTE side [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] 
>
> is there any explanation from code frame template design side?[[James_Butterfield|James Butterfield]] 
>
> above situation is not take into consideration or there's some theory behind?

-------

> [!note]+ 2025-08-14 13:34 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> [[Yuan_ZHANG|Yuan ZHANG]],[[James_Butterfield|James Butterfield]] RTE generating P2Const for input argument of array type is as per autosar.
>  ![[RH-13706-screenshot-1.png]] 
>
> By setting <SERVER-ARGUMENT-IMPL-POLICY>USE-ARGUMENT-TYPE</SERVER-ARGUMENT-IMPL-POLICY> for the argument RTE will generate pointer to array type instead of pointer to array base type. But P2Const will always be generated for IN arguments of array type.
>  ![[RH-13706-screenshot-2.png]] 

-------

> [!note]+ 2025-08-14 13:07 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2025-08-14 13:07 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi RTA-RTE Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-08-14 08:52 · [[Yuan_ZHANG|Yuan ZHANG]]
> hi [[James_Butterfield|James Butterfield]] 
>
> Related configuration is attached in the 'configuration.zip'.
> [^configuration.zip]

-------

> [!note]+ 2025-08-13 13:06 · [[James_Butterfield|James Butterfield]]
> Hi [[Yuan_ZHANG|Yuan ZHANG]],
>
> To investigate this issue I will need to see the configuration of the *DiagUT* and _Dcm_, as well as the *Dcm SWCD* file.
>
> Could you please supply the customer's project file so that I can see these configurations?
>
> Best Regards,
> James

-------

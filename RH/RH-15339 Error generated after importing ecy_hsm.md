---
jira_key: RH-15339
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15339"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
reporter: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-03-03T08:56:23.000+0100"
updated: "2026-04-28T10:17:57.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline, 

 When using RTA CAR12.11.0VCTCESR1pr1, Importing the arxml file released by the hsm team and generating bsw code will result in a Java error; But we will use these items in actual development; 

Is this a compatibility issue with the tool? Could you please help investigate and resolve this problem? 

![[RH-15339-image001.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](http://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-04-07 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-03-23 17:46 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-03-05 19:03 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]],
>
> The issue is expected to be patched in the following upcoming releases:
>  * RTA-CAR 12.9.hf due on 13/03.
>  * RTA-CAR 12.10 release due this month.
>
> Can you please confirm if the customer will be able to move to one of these versions? If not, we may need to request a hotfix for RTA CAR12.11.0VCTCES used by Cariad.
>
> Best regards,
>
> Hritik

-------

> [!note]+ 2026-03-04 03:07 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-03-04 03:07 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] ,
>
>     My customer is Cariad；RTA CAR12.11.0VCTCESR1pr1;RTA CAR12.11.0VCTCESR1pr1 is a special version released for customers; If new tools need to be released, they need to be upgraded on this basis;

-------

> [!note]+ 2026-03-03 18:38 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]],
>
> This is a known issue. I know there is a hotfix PR version available for this but I don't think this can be shared with the customer: [https://artifactory.etas-dev.com/artifactory/rtacar-generic-release-local/pre-release/RTA-CAR/RTA-CAR_V12.9.0eng1_EcarX12.9.0hf1_Windows.zip]
>
> I'm checking with L3 if we have an RTA-CAR version which contains the fix and can be used by the customer.
>
> In the meantime, please try and remove the ecucvalues related to the dynamic HSM configuration and the code should then generate successfully. Please let me know if this does not work.
>
> Also, which customer does this ticket pertain to?
>
> Best regards,
>
> Hritik

-------

> [!note]+ 2026-03-03 08:56 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> [^ecy_hsm_EcucParamDef.arxml] *(892 kB)*
>
> [^ecy_hsm_EcucValues.arxml] *(470 kB)*

-------

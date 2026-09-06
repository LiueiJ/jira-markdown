---
jira_key: RH-16553
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16553"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: dong.liu5@etas.com
reporter: dong.liu5@etas.com
tags: [VNCNMS]
components: [Generic-Importers]
fix-versions: []
epic: null
parent: null
created: "2026-07-03T10:20:00.000+0200"
updated: "2026-07-28T14:24:22.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-16553 ConfGen error with Lintp pdu

> [!jira] Closed · Critical · [[Dong_LIU|Dong LIU]] · 更新于 2026-07-28T14:24:22.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16553)

> 标签：#jira/comp/generic-importers #jira/label/vncnms

## 描述

Hi, 

I'm having an issue when using the ConfGen feature in the RTA-CAR tool. Could you please help me take a look? The RTA-CAR version is RTA-CAR 12.11.0pr6. 

 **Issue Description:** 

When I run ConfGen in RTA-CAR, I encounter the error highlighted in the red box in the screenshot below: 

![[RH-16553-image001.png]] 

However, this is a LinTp-related PDU, and it is referenced in LinTp. Why is it reporting a CanTp Connection-related issue? 

Could you please help investigate this issue? Thank you! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- mentions: [[RH-12965 [ConfGen] LinIfRxPdu and LinIfTxPdu for Lin Diag messages and LinIfFrameType]]

## 评论

> [!note]+ 2026-07-28 14:24 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-14 06:45 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Dong_LIU|Dong LIU]] ,
>
> Currently, I got the information from COEM team, the solution has been updated and implemented in the **RTA-CAR 12.11.0VCTCESR1pr4.** Hence, I will change the status to "Solution Proposed"
>
> cc: [[K_Raj_Kumar|K Raj Kumar]] , anh [[Phuong_Nguyen_Le|Phuong Nguyen Le]] , anh [[Cuong_Phan_Manh|Cuong Phan Manh]] 

-------

> [!note]+ 2026-07-09 13:23 · [[K_Raj_Kumar|K Raj Kumar]]
> Please find the attached patch. <<RH-16553.patch.txt>> Please apply this on Custom ConfGen of RTA-CAR 12.11.0
>
> Best Regards, Rajkumar
>
>
> [^RH-16553.patch.txt]

-------

> [!note]+ 2026-07-09 07:25 · [[K_Raj_Kumar|K Raj Kumar]]
> [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] {*}Proposal{*}: We will provide the patch later today. Could you please coordinate with the HUB or FAE for the customer project, generate the Custom ConfGen for version 12.11.0, apply the patch, and provide the updated release to the customer? 
>
> Best Regards, **Rajkumar**

-------

> [!note]+ 2026-07-08 12:05 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[K_Raj_Kumar|K Raj Kumar]] ,
>
> As discussed, please help me check internally with your team about the proposed solution. We just need to make sure that this plugin is compatible with {*}RTA-CAR 12.11.x{*}.
>
> {+}*Note*{+}: Because this issue is currently blocking their progress, if your fix is already available, you can provide the code to our COEM team so they can create a plugin for the customer and allow them to continue their work.
>
> cc: anh [[Phuong_Nguyen_Le|Phuong Nguyen Le]] , anh [[Dang_Ho_Anh|Dang Ho Anh]] , [[Jie_LIU|Jie LIU]] 

-------

> [!note]+ 2026-07-08 07:14 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] and [[K_Raj_Kumar|K Raj Kumar]] 
>
> Cariad, our customer, they will take 12.11 as the final version. If confgen miss generating something or generates something wrong, our local team can used post hook to fix it. But this issue \{*}STOPs Confgen and generate nothing{*}. This is unacceptable by customer. With same ecu extract, confgen has been working in previous RTA-CAR version for a long time, we also negotiated with customer E/E department to frozen the format of ecu extract they release with a lot of effort.
> Is it possible to give us a ConfGen installer / patch on RTA-CAR 12.11 final release to fix this issue?
> [[Jiaqi_JI|Jiaqi JI]] This could be a high risk for Cariad project.

-------

> [!note]+ 2026-07-08 06:23 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Dong_LIU|Dong LIU]] ,
> Could you check with the customer about the proposed bug-fix plan? According to [[K_Raj_Kumar|K Raj Kumar]] , this issue will be resolved in {*}RTA-CAR 12.12.0{*}.

-------

> [!note]+ 2026-07-08 06:10 · [[K_Raj_Kumar|K Raj Kumar]]
> the fix will be planned to implement in RTA-CAR 12.12.0 release.

-------

> [!note]+ 2026-07-07 18:00 · [[K_Raj_Kumar|K Raj Kumar]]
> [[Dang_Ho_Anh|Dang Ho Anh]] 
>
> This issue was introduced during the centralized PDU implementation for CanTp, where a condition check to verify that the creator module is
>
> CAN was inadvertently missed. We have created an issue [ARCCFGEN-2508](https://jira.etas-dev.com/browse/ARCCFGEN-2508)  to address this problem.
>
> We will provide an update on the which RTA-CAR release the fix will be available.

-------

> [!note]+ 2026-07-07 15:21 · [[K_Raj_Kumar|K Raj Kumar]]
> Yesterday the hotline was completely down.
>
> ![[RH-16553-image-2026-07-07-18-49-34-176.png]]
>
> Team has started analyzing this issue today. we will provide the feedback once the analysis is completed.
>
> Best Regards, **Rajkumar**

-------

> [!note]+ 2026-07-07 12:17 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [Raj Kumar K (MS/EMT2-ETAS),](https://confluence.etas-dev.com/display/~rka4kor)
>
> Do we have any updates on this ticket? It is currently blocking the development team and the customer as we begin migrating the project to RTA-CAR 12.11.

-------

> [!note]+ 2026-07-06 04:32 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Dong_LIU|Dong LIU]] ,
>
> I believe this is an issue with {*}conf-gen{*}, so I am forwarding it to our L3 experts for further review.
>
> Hi [Raj Kumar K (MS/EMT2-ETAS),](https://confluence.etas-dev.com/display/~rka4kor)
>
> Could you please look into this reported issue from the customer?

-------

> [!note]+ 2026-07-03 10:54 · [[FAE_Technical|FAE Technical]]
> {panel:bgColor=#ffffce}
> **AI-Generated Investigation**
> *This is experimental. Do not treat the findings as certain. Please do not reply to this comment; your assigned FAE will follow up separately.*
> {panel}
>
> Full investigation details, code trace, and draft replies are in the attached dashboard.
>
>
> [^RH-16553_investigation.html] *(54 kB)*

-------

> [!note]+ 2026-07-03 10:28 · [[Dong_LIU|Dong LIU]]
> There are two related hotlines：[RH-12965] [ConfGen] LinIfRxPdu and LinIfTxPdu for Lin Diag messages and LinIfFrameType - RTA Hotli…
>
> [[ARCCFGEN-1998] [RH-12965] LinIfRxPdu and LinIfTxPdu for Lin Diag messages and LinIfFrameType - Jir…|https://jira.etas-dev.com/browse/ARCCFGEN-1998]

-------

> [!note]+ 2026-07-03 10:25 · [[Dong_LIU|Dong LIU]]
> The related project is attached.
> [^Isolar.zip]

-------

> [!note]+ 2026-07-03 10:20 · [[FAE_Technical|FAE Technical]]
> AI Investigation automatically started due to ticket creation by trusted agent Dong LIU.
> Progress can be tracked on [Jenkins](https://rta-fae.jenkins.etas-dev.com/job/Hotline%20Automation%20-%20Agentic/job/main)
>
> (Return code: 201)

-------

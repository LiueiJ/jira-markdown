---
jira_key: RH-16478
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16478"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: Critical
project: RH
assignee: Jiaqi.JI@bosch.com
reporter: Jiaqi.JI@bosch.com
tags: [Cariad, VNCNMS]
components: [RTA-RTE]
fix-versions: []
epic: null
parent: null
created: "2026-06-25T11:56:56.000+0200"
updated: "2026-08-28T09:00:51.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16478 [VNCNMS][VCTC] E2E Signalgroup Issue

> [!jira] Solution Proposed · Critical · [[Jiaqi.JI@bosch.com|Jiaqi.JI@bosch.com]] · 更新于 2026-08-28T09:00:51.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16478)

> 标签：#jira/comp/rta-rte #jira/label/cariad #jira/label/vncnms

## 描述

Hello 

There is an urgent issue from customer (Cariad) . 

Background: In RTA-CAR 12.11.0VCTCESR1pr1, The RTA-RTE can not generate the data conversion for Isignal in IsignalGroups with ComBased transformer. 

Impact: Customer want to use this feature in this RTA-CAR version end of today as it blocks their one internal milestone. 

Hint: Cariad also required it can be solved on RTA-CAR 9.1.0 as one old SOP project use this RTA-CAR Version also need this feature. 

Noted with thanks for you all kindly support! 

 **Best Regards,** 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- mentions: [[RH-16347 RTE code gen Error parsing input file ]]
- mentions: [[RH-16581 ComXf Issue with Parsing float32 Data Type]]
- is mentioned in: [[RH-16581 ComXf Issue with Parsing float32 Data Type]]

## 评论

> [!note]+ 2026-08-27 09:48 · [[Su_Nguyen_Quoc|Su Nguyen Quoc]]
> Meeting Minutes **Date:** 27-Aug-2026
> ### **Participants:**  [[Jie_LIU|Jie LIU]] , [[Phuong_Nguyen_Le|Phuong Nguyen Le]] , Nguyen Quoc Su.
> #### Discussion
>  * **RH-16478** was classified as a **feature misuse** rather than a product issue. The issue should not be claimed as a product defect requiring a fix.
>  * Guidance on the correct usage has been provided in the RH ticket.
>  * The **project team** (not the end customer) is responsible for performing verification testing and providing feedback through the **Hotline** and Customer channels.
>  * If additional testing is required under a {*}COEM ESR{*}, the confirmed RH issue should be evaluated and planned as part of the **China ESR release backlog** under [China - Delivery requests](https://confluence.etas-dev.com/spaces/RTAC/pages/501715509/China+-+Delivery+requests?src=contextnavpagetreemode)
>  * For testing-related requests, a **BIP reference test plan** may be shared through the RH Hotline ticket when applicable.
>
> #### Decision
>
> **Q:** Do we need to create a **BIP Need** for this testing use case?
> **A:** **No.** This is not considered a common use case; therefore, {*}no BIP Need will be created{*}.
> #### Consideration
>  * **Liu Jie (PO)** will consider handling similar requests through a future **RH Hotline ticket** process if needed.

-------

> [!note]+ 2026-08-26 00:31 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> For the two projects you sent, I was able to generate BSW and RTE for the LZCU project.
>
> I found that the issue is caused by the incorrect data type policy of all `ISignals` belonging to the signal group. The data type policy should be configured as {{{}TRANSFORMING-I-SIGNAL{}}}, as shown in the comment of ticket [RH-16581] ComXf Issue with Parsing float32 Data Type - RTA Hotline
>
> ![[RH-16478-image-2026-08-26-05-27-16-082.png]]
>
> I tried to test it with the signal group {{{}SysSigGrp_B2_EPB_03_E2E{}}}, and the data conversion was generated as below (compuMethod for ISignal B2_EPB_03_Counter_B2_EPB_03 has been updated for testing purpose):
>
> ![[RH-16478-image-2026-08-26-05-29-33-379.png]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] , Please add your points if I am missing anything in this case.
>
> CC: [[Sathish_Kumar_Madanmohan|Sathish Kumar Madanmohan]] [[Phuong_Nguyen_Le|Phuong Nguyen Le]] [[Jiaqi_JI|Jiaqi JI]] 

-------

> [!note]+ 2026-08-25 20:11 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
>    I have send you the project yesterday; The RTA-RTE did not generate the data conversion  of E2E SignalGroup;

-------

> [!note]+ 2026-08-25 09:04 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Jiaqi_JI|Jiaqi JI]] and [[Junsheng_ZHANG|Junsheng ZHANG]]
>
> Could you please provide a snapshot of the issue and a reference project that can reproduce it?
>
> Based on the analysis so far, the mentioned feature appears to already be supported in RTA-CAR 12.11.0.

-------

> [!note]+ 2026-08-25 03:19 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-08-25 03:19 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-08-25 03:19 · [[Jiaqi_JI|Jiaqi JI]]
> After checked with customer, this issue has not been fixed, need PF Team re-investigate it. Thanks

-------

> [!note]+ 2026-08-24 14:10 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Jiaqi.JI@bosch.com|Jiaqi.JI@bosch.com]] ,
>
> Do we have any feedback or reports related to this issue after the customer migrated their project to RTA-CAR 12.11.0?

-------

> [!note]+ 2026-08-24 14:03 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]]  Do we have feedback from customer after porting project to RTA-CAR 12.11.0?

-------

> [!note]+ 2026-08-24 13:41 · [[Simon_Wadsworth|Simon Wadsworth]]
> Can we please confirm with the customer is this still an issue ?

-------

> [!note]+ 2026-07-23 14:23 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-06-30 11:49 · [[Dang_Ho_Anh|Dang Ho Anh]]
> As noted, this use case has been supported since RTA-CAR 12.10.0.
> The customer will verify it after porting the project to RTA-CAR 12.11.0.

-------

> [!note]+ 2026-06-30 08:58 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] 
>
> Great to see this result. Then you verify that this issue has been resolved in the later RTA-CAR project. It give us much confidence to promise customer coming RTA-CAR doesn't have this issue.
> Next month we will start migrating customer projects (they have 4 zone controllers) to official 12.11.0, till then we will check again the result. Thank you again for your dedicated support !

-------

> [!note]+ 2026-06-30 08:50 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Sisi_TAO|Sisi TAO]] ,
>
> I just verified support for this feature in RTA-CAR 12.10.0 by migrating the project you sent to this version.
>
> The RTE can generate data conversion for dedicated signals, for example: 
> ![[RH-16478-image-2026-06-30-13-44-47-784.png]]
>
> If you need this project for reference, I can send it to you.

-------

> [!note]+ 2026-06-29 09:27 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Ryan_Dixon|Ryan Dixon]] and [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
> Thank you very much for your information and support.
>
> We have developed a post-processing script that runs after RTE generation. This script parses the project to identify Signal Groups that require data conversion, and then modifies the generated RTE code accordingly to implement the data conversion functionality.
>
> This script will be provided to the customer as a transitional solution, and is expected to be used for approximately one month. During this period, we will work with the customer to facilitate the upgrade of RTA-CAR to the official 12.11 release. Once the upgrade is complete, we will verify whether the data conversion feature is natively supported in that version, and subsequently phase out the temporary script.

-------

> [!note]+ 2026-06-26 09:51 · [[Ryan_Dixon|Ryan Dixon]]
> Please see https://rtahotline.etas.com/jira/browse/RH-16347?focusedCommentId=698428&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-698428
>
> That was originally meant for this ticket.

-------

> [!note]+ 2026-06-26 09:22 · [[Ryan_Dixon|Ryan Dixon]]
> From what I know - the issue is that *data conversion* is not being applied to the _signal group_. This is because RTA-CAR 12.9.0 still applies the *RTE PreProcessorPlugin* which was a long standing hack to get *ComXf data transformation* to work. The plugin would silently converts *signal groups* to primitive signals; that is, the `ISignalGroup` would be effectively replaced with an `ISignal`. This means that *data conversion* will never work.
>
> I am not sure if there is a way to **not** apply the _Rte PreProcessorPlugin_.
>
> I believe that an RTA-CAR based on version 12.10.0 should be okay because the plugin was removed.
>
> [[Oliver_Taylor|Oliver Taylor]]
> [[Ngoc_Duong_Thi|Ngoc Duong Thi]]
>
> If there is no way to not apply the plugin, we may need to look into the logic of the plugin, make a change so that the plugin does not molest the *signal group* and perhaps fix anything up *just before* feeding it through to RTEGen.
>
> Without a workaround, *data conversion* for *ComXf* is just not supported with this version.
>
> Furthermore, some of the things that the plugin does do is needed. So, somehow, just the *ComXf* translation needs to be disabled or a lot of file diffing and merging.

-------

> [!note]+ 2026-06-25 14:58 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Dang_Ho_Anh|Dang Ho Anh]] ,
>
> Noted with thanks for your confirmation. I will check and asked for the issue screenshots~ :)

-------

> [!note]+ 2026-06-25 14:53 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Jiaqi.JI@bosch.com, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-06-25 13:21 · [[Dang_Ho_Anh|Dang Ho Anh]]
> Hi [[Jiaqi.JI@bosch.com|Jiaqi.JI@bosch.com]] ,
>
> After checking with the team, we confirmed that this use case is supported in the RTA-CAR 12.9.0 official release, which RTA-CAR 12.11.0VCTCESR1pr1 is based on.
> Could you please share the affected project with us, along with a description and any screenshots showing where the issue occurs? We suspect that there may be a configuration issue in the project.

-------

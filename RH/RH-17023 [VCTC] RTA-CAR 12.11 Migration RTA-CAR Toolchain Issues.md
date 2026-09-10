---
jira_key: RH-17023
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17023"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Customer
priority: Critical
project: RH
assignee: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]"
reporter: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]"
tags: [jira/comp/generic-importers, jira/comp/isolar-a/b, jira/label/isolar-ab, jira/label/isolar-b, jira/label/regional, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-08-25T11:22:50.000+0200"
updated: "2026-09-10T05:04:45.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi [@Karthi Krishna Shekaar (MS/EMT-ETAS)!mail_small.gif!](mailto:Karthi.Krishna@etas.com)

When we are migrating VCTC (Cariad) projects from RTA-CAR 12.11.0VCTCESR1pr1 to RTA-CAR 12.11.0, we had following issues:

1. Split this issue to [https://rtahotline.etas.com/jira/browse/RH-17174](https://rtahotline.etas.com/jira/browse/RH-17174)

2. Split this issue to [https://rtahotline.etas.com/jira/browse/RH-17171](https://rtahotline.etas.com/jira/browse/RH-17171)

3. Split this issue to [https://rtahotline.etas.com/jira/browse/RH-17175](https://rtahotline.etas.com/jira/browse/RH-17175)

4. Split this issue to [https://rtahotline.etas.com/jira/browse/RH-17176](https://rtahotline.etas.com/jira/browse/RH-17176)

5. Split this issue to [https://rtahotline.etas.com/jira/browse/RH-16347](https://rtahotline.etas.com/jira/browse/RH-16347)

6. ConfGen failed without any problems. Screenshot not available. Info like: Internal Error:Sd. Reopen RTA-CAR can fix this issue.

7. Split this issue to [https://rtahotline.etas.com/jira/browse/RH-17173](https://rtahotline.etas.com/jira/browse/RH-17173)

8.Sometimes the first generation fails with a BFX generator error. Switching to a different workspace and generating again resolves the issue.

**Sisi TAO** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 133 81555197 

[Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

**ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- relates to: [[RH-16963 [VNCNMS][BIP] Tool Issue when using RTA-CAR 12.11.0]]
- split to: [[RH-17173 Whole BSW becomes invalid in Code Gen UI]]
- split to: [[RH-17174 Exception during Execution of JavaAction for Com]]
- split to: [[RH-17175 0_CheckLiceses Error during Code Gen]]
- split to: [[RH-17176 Resources Could Not Be Found Exception during Code Gen]]
- split to: [[RH-17171 Error Report During LDF File Importing by CLI]]
- split to: [[RH-16347 RTE code gen Error parsing input file ]]
- mentions: [[RH-17070 RTA CAR file parsing error]]

## 评论

> [!note]+ 2026-09-10 05:04 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]] To avoid mixing all the issues, the issues with evidence are split into separate tickets. Please help to check whether all these issues can be solved with the patch to be delivered.

-------

> [!note]+ 2026-09-08 09:11 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[M_S_Karthik|M S Karthik]] : Which issues will be included in the patch?
>
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]] , as info from [[M_S_Karthik|M S Karthik]] , it's a standalone installation package so that it will be not integrated into VCTCPR7 plugin. Please note that next delivery will be VCTCPR7 plugin + ISOLAR-A/B installation package
>
> CC: a [[Lan_Tran|Lan Tran]] 

-------

> [!note]+ 2026-09-08 05:33 · [[Duy_Pham|Duy Pham]]
> Hi [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]], would you please provide us log errors for ConfGen and project to preproduce the problems ?

-------

> [!note]+ 2026-09-07 08:55 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> [[M_S_Karthik|M S Karthik]] , thanks for the feedback. 
>
> Yes, it is required in CW38 to have one version for our ETAS internal testing.
>
> And in CW39, we need one version to deliver to customer as VCTC PR7 release with other bugfix as a whole.
>
> cc. [[Phuong_Nguyen_Le|Phuong Nguyen Le]]  [[Lan_Tran|Lan Tran]] 

-------

> [!note]+ 2026-09-04 13:24 · [[M_S_Karthik|M S Karthik]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]], Thanks for asking.
>
> This delivery from ISOLAR-A/B would be a standalone installation package which user must perform installation on top of RTA-CAR to patch it. No integration with VCTC RTA-BSW plugin necessary. Do you still see a need for it to be delivered by CW 38? If this is required in CW 38 only for our ETAS internal testing, we could provide an unofficial delivery package ({_}not QG'ed one{_}) for the same.
>
> Looking forward for your feedback on the same. Thanks. 
>
> [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]] - FYI

-------

> [!note]+ 2026-09-04 10:31 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hello, [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]], is it possible to provide a patch delivery by CW 38, so that we can integrate it into VCTC PR7 plugin by CW 39?

-------

> [!note]+ 2026-09-03 14:32 · [[Duy_Pham|Duy Pham]]
> Hi all, ticket https://jira.etas-dev.com/browse/ARCCFGEN-2714 create to analysis for Confgen issue #6

-------

> [!note]+ 2026-09-03 11:04 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]]
> Hello [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> Team is working on the fix and plan is to provide a patch delivery by CW 39 and then we will plan for an official bug fix release later.

-------

> [!note]+ 2026-09-02 10:58 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Hello, [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]] 
>
> Do we have the timing plan for back porting to V12.11? We needs to share it also with customer

-------

> [!note]+ 2026-09-01 06:54 · [[Karthi_Krishna_Shekaar_(MSEMT-ETAS)|Shekaar Karthi Krishna]]
> **#2** 
>  * .LDF(in uppercase) is not getting imported, this is a issue in CLI 
>  * Workaround:
>  ** Rename extension as .ldf (lower case) or
>  ** Use ldf import in GUI
>  * Solution: This will be fixed as part of [ARCTOOLS-23474](https://jira.etas-dev.com/browse/ARCTOOLS-23474) in V12.12 and same would be back ported to V12.11
>
> **#5** - handled via [https://rtahotline.etas.com/jira/browse/RH-16347] 
>
> **#6:  [[K_Raj_Kumar|K Raj Kumar]]** This is confgen related issue, can you please check and create necessary ticket to take forward

-------

> [!note]+ 2026-08-31 18:03 · [[M_S_Karthik|M S Karthik]]
> Please find the latest status on above reports: 
>  * **#1**
>  ** ISOLAR team is able to reproduce the issue, however, root cause is not yet identified and Its challenging. Analysis is in progress
>  ** Workaround of clearing the output files and reopen workspace works in our environment too. Suspecting script implementation contains random behavior during Incremental build case. investigation in progress...
>  ** [ARCTOOLS-23630](https://jira.etas-dev.com/browse/ARCTOOLS-23630) created to resolve this issue
>  * **#3. & #4**
>  ** "\.buildframework" folder is not delivered to SCM (like GIT).
>  ** {*}General Instruction{*}: When user store the generated output in SCM, then it is mandatory to deliver also the "\.buildframework" folder into SCM in order to automatically clean the generated artifact during previous run or to detect the configuration changes and automatically regenerate the output to keep artifacts in sync. 
>  * **#7**
>  ** This is caused by the way how RTA-BSW VCTC ESR update site package is prepared. Looks like it is prepared as release package but not as custom package due to tool randomly detecting it as its own standalone RTA-BSW and internal validation in RTA Code Generator window throws false positive errors. 
>  ** This is the tooling issue and will be fixed as part of [ARCTOOLS-23627](https://jira.etas-dev.com/browse/ARCTOOLS-23627)
>  * **#2** - we will feedback in our next post.
>  * **#5** - handled via separate ticket
>  * **#6** - Not an issue with ISOLAR. Separate ticket must be created for Conf Gen. 

-------

> [!note]+ 2026-08-30 08:29 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> The file not recognized issue also affects the customer’s use of Git for synchronized development. After downloading the code from Git, it may fail to recognize the ARXML files in the bswmd and swcd folders, causing the RTE code generation to lack links for ports related to BSW modules. RTE code can still be generated without errors, but the actual functionality is missing.You can ref https://rtahotline.etas.com/jira/projects/RH/queues/custom/470/RH-17070；

-------

> [!note]+ 2026-08-27 12:03 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> Patch used basing on RTA-CAR 12.11.0 official release
> [^RTA-CAR_12.11.0.VCTCESR1pr5_UpdateSite-SNAPSHOT.zip] [^RTA-CAR_CORE_BUNDLES_UpdateSite-12.11.0.VCTCESR1pr4-SNAPSHOT.zip]

-------

> [!note]+ 2026-08-27 11:48 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> It could happen when changing folder structure of ecucvalues or paramdefs, adding new modules, ECUC extract, etc.

-------

> [!note]+ 2026-08-27 07:10 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Sisi TAO. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

> [!note]+ 2026-08-27 04:51 · [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]
> The work around is to delete all these things:
>
> ![[RH-17023-image-2026-08-27-10-52-24-135.png]]

-------

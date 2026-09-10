---
jira_key: RH-16462
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16462"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: Junsheng ZHANG
reporter: Junsheng ZHANG
tags: [jira/comp/cycurhsm3, jira/comp/sec-cryptoauhsm3, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-06-24T12:02:55.000+0200"
updated: "2026-08-11T16:44:21.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi hotline，

I received the latest HSM package from the HSM team yesterday (SEC_ONS_HSM3_VW_TC4HR_015_PPR_784cb3424c_V3.0.6.a0). During the integration process, I found that the data types(ecy_hsm_Csai_HwCsp_ReleaseKey_ParamSetAndVersionT ) and interface definitions in the package have changed again and do not match the current Crypto interfaces in RTA CAR, making integration impossible and preventing fully-fail-safe testing. Additionally, Boehm Volker reported that the current RTA CAR 12.11 version was developed based on 3.0.5, which will prevent Crypto and HSM from being integrated. All of our current projects are developed based on RTA-CAR 12.11.0pr3, which is a significant problem. We need to know how to match the versions of both sides.

 **Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- relates to: [[RH-16888 [Crypto Stack] [RTA-CAR 12.11.0 Patch 1] [SecServices 14.2.0-alpha.1] BSW Generation Fails with Java Error]]
- is mentioned in: [[RH-16888 [Crypto Stack] [RTA-CAR 12.11.0 Patch 1] [SecServices 14.2.0-alpha.1] BSW Generation Fails with Java Error]]

## 评论

> [!note]+ 2026-07-29 13:50 · Junsheng ZHANG
> Hi Khoa Phan Huynh Dang ,  
>
> The issue code has already been fixed in the pr4 version.We can close the ticket now;Thank you very much for your support;

-------

> [!note]+ 2026-07-29 05:37 · Khoa Phan Huynh Dang
> Hi Junsheng ZHANG ,
>
>
> I would like to summarize this ticket. The issue **identified in RTA-CAR 12.11.0.VCTCESR1pr3** has been resolved in the subsequent release, {*}RTA-CAR 12.11.0.VCTCESR1pr4{*}.
>
> However, due to {*}some stability concerns with version 12.11.0.VCTCESR1pr4{*}, we plan to provide an updated plugin **in the upcoming pr5 release** to resolve the tool issue.
>
> Therefore, this ticket can be closed as "Solution Proposed", please let me know if you have any concerns about it.

-------

> [!note]+ 2026-07-28 06:48 · Khoa Phan Huynh Dang
> Hi all,
> After reviewing version **12.11.0.VCTCESR1pr4** with Junsheng ZHANG, I confirmed that this issue is valid and requires support from the development team. The following errors were identified:
>  * An error related to {*}`CryptoPrimitiveConfiguration`{*}, which does not contain the member field (mentioned by the customer).
>  * An error related to the AUTOSAR (AR) compatibility version.  ![[RH-16462-image-2026-07-28-11-14-47-414.png]]
>  * Some updates have been released for other modules, but the plugin does not include the corresponding updated versions. For example, the HSM3 module was updated to version 6.2.0 in this release; however, after integrating the pr4 plugin, we are still unable to update it.  ![[RH-16462-image-2026-07-28-11-19-34-701.png]]   
>
> Please correct me if I missed any points, Junsheng ZHANG 
>
> -------------------------------------------------------------------
>
> Junsheng ZHANG , for the workaround solution to pass the error of BSW gen, you can refer:
>  # After update Crypto to the upgraded version in pr4, choose "import source code" to generate this module in your project
>  # Revert the change in "{*}Crypto_Cfg_h.ftl{*}" ![[RH-16462-image-2026-07-28-11-47-24-342.png]]
>  # Rebuild BSW again and it will pass as below:
>
> ![[RH-16462-image-2026-07-28-11-28-13-802.png]]
>
> ---------------------
>
> Junsheng ZHANG , I'm checking with dev team to analyze the plugin pr4 and will let you know details asap

-------

> [!note]+ 2026-07-27 15:20 · Junsheng ZHANG
> Hi Khoa Phan Huynh Dang ,
>
> After I installed PR4, I regenerated the BSW code, but I got this error. It’s possible this is a tool issue.
>
> ![[RH-16462-image-2026-07-27-21-19-22-968.png]]
> [^Isolar.zip]

-------

> [!note]+ 2026-07-24 10:41 · Khoa Phan Huynh Dang
> Hi all,
>
> After checking with the customer, we confirmed that the fix for this issue has already been implemented in {*}RTA-CAR 12.11.0.VCTCESR1pr4{*}. I have provided the plugin for this version.
>
> Junsheng ZHANG , could you please verify the solution and close the ticket if the issue has been resolved? Otherwise, please let us know if you have any further concerns. Thank you!

-------

> [!note]+ 2026-07-24 09:50 · JSM Service Bot
> Hi Junsheng ZHANG, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-07-24 09:21 · JSM Service Bot
> Junsheng ZHANG, the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-07-24 09:21 · Junsheng ZHANG
> Hi Phong Tang Dieu ,Volker Boehm 
>
> I have check the code of RTA-CAR 12.11.0.VCTCESR1pr4,I also have the type(ecy_hsm_Csai_HwCsp_ReleaseKey_ParamSetAndVersionT),but 3.0.6 do not define it;
>
> ![[RH-16462-image-2026-07-24-15-20-03-738.png]]

-------

> [!note]+ 2026-07-09 14:22 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-06-24 15:06 · Volker Boehm
> Should be resolved by
>
> !https://jira.etas-dev.com/images/icons/issuetypes/epic.svg|width=16,height=16!  [ARCSEC-6975](https://jira.etas-dev.com/browse/ARCSEC-6975) [CryptoAuHSM3] Update to support HSM 3.0.6 instead of 3.0.5 beta (fwd path)
>
> via
> !https://jira.etas-dev.com/images/icons/issuetypes/epic.svg|width=16,height=16! [ARCSEC-6952](https://jira.etas-dev.com/browse/ARCSEC-6952) [Crypto][CryptoAuHSM3] Port forward path features to 14.2.0 branch - Alpha 

-------

> [!note]+ 2026-06-24 12:45 · Phong Tang Dieu
> Hi Alexander Wegmann
> Could you please take a look at this issue?
> Thanks,

-------

> [!note]+ 2026-06-24 12:44 · JSM Service Bot
> Hi Alexander Wegmann, this CycurHSM3 ticket requires an assignee. As the component lead for CycurHSM3, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-06-24 12:21 · FAE Technical
> {panel:bgColor=#ffffce}
> **AI-Generated Investigation**
> *This is experimental. Do not treat the findings as certain. Please do not reply to this comment; your assigned FAE will follow up separately.*
> {panel}
>
> Full investigation details, code trace, and draft replies are in the attached dashboard.
>
>
> [^RH-16462_investigation.html] *(52 kB)*

-------

> [!note]+ 2026-06-24 12:02 · FAE Technical
> AI Investigation automatically started due to ticket creation by trusted agent Junsheng ZHANG.
> Progress can be tracked on [Jenkins](https://rta-fae.jenkins.etas-dev.com/job/Hotline%20Automation%20-%20Agentic/job/main)
>
> (Return code: 201)

-------

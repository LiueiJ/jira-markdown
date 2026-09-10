---
jira_key: RH-17005
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17005"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-23T14:02:22.000+0200"
updated: "2026-09-10T01:51:03.000+0200"
synced-at: "2026-09-10T00:24:38.390Z"
jira-orphaned: false
profile: Cariad
---

# RH-17005 Issues caused by the HSM version update to 3.0.7

> [!jira] Closed · Critical · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] · 更新于 2026-09-10T01:51:03.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17005)

## 描述

Hi Hotline, 

 After upgrading from 3.0.5 to 3.0.7, it is necessary to modify the HSM’s UCB1 and erase the HSM’s DFLASH. However, the existing customer code does not implement these steps, so customer OTA cannot directly upgrade the HSM (the upgrade will prevent the HSM from being upgraded again). We need to justify the proposed solution and define the specific implementation steps. 

 Additionally, if the Secure Boot verification fails on 3.0.7, it takes about 3 seconds; this is also a serious issue for customers. 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- relates to: [[RH-17004 [CNMS][VCTC]CycurHSM v3.0.7.b0 performance issue about ecy_hsm_Mgmt_WaitForMode]]

## 评论

> [!note]+ 2026-09-10 01:50 · [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]]
> this proposal already verified at CARIAD side. it works well, we can close this ticket.

-------

> [!note]+ 2026-09-09 18:57 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-08-26 13:31 · [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Sandra Weigl]]
> Hi [[Christian_Fuerst|Christian Fuerst]] ,
>
> product team is already heavily involved and provided already a POC how to solve the situaiton on customer side.
>
> The update issue described is based to a change to a new update concept requested by VCTC, which is implemented in 3.0.7.b0.  

-------

> [!note]+ 2026-08-24 15:39 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> normally it is not needed to change the UCB settings when you upgrade the CycurHSM to a newer version.
>
> And if you do not made any special layout changes from the DFlash, then there is no need to reinit the HSM DFlash part.
>
> Did you changed some features which needs to set UCBs again?
>
> Also keep in mind that:
> "TargetportGuide-TC4XX-CycurHSM_V3.0.7.b0.pdf" out of the doc folder of the provided delivery:
> {quote}CycurHSM v3.0.7.b0 is in beta quality and hence not fully qualified. Please
> note that if device protections are enabled (i.e., APUBYPASS is disabled and
> the protections are confirmed), ETAS cannot guarantee a successful
> future update to a newer, qualified CycurHSM version. ETAS recommends
> that device protections should not be enabled with this beta release.
> {quote}
>
>
> Can you provide more information about this, please?
> This would be helpful to analyze the issue.
>
> thx
>
> BR
> Christian

-------

> [!note]+ 2026-08-24 10:34 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> can you provide in which phase of development this issue shows up, please?
>
> This will help us to provide the required support.
>
> thx
>
> BR
> Christian

-------

> [!note]+ 2026-08-23 14:11 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

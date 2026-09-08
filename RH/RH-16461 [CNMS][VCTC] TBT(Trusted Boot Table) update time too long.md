---
jira_key: RH-16461
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16461"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: []
components: [CycurHSM2]
fix-versions: []
epic: null
parent: null
created: "2026-06-24T11:58:55.000+0200"
updated: "2026-09-01T08:42:35.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16461 [CNMS][VCTC] TBT(Trusted Boot Table) update time too long

> [!jira] Closed · Critical · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-09-01T08:42:35.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16461)

> 标签：#jira/comp/cycurhsm2

## 描述

Hi hotline, 

We tested the TBT(Trusted Boot Table) update times (2k &#8211; 6.88ms, 4k &#8211; 6.44ms, 8k &#8212; 7.37ms, 16k &#8212; 8.4ms, 64k &#8212; 16ms). Currently, the customer is placing these updates within a 10ms task. Even if the data is sliced into 2k chunks, the remaining time is insufficient for other tasks. Moreover, after slicing into 2k chunks, the total time for the APP(6950k) to update the TBT will be as long as 35 seconds (6950k / 2k * 0.01s = 34.75s). 

 HSM Version: ** SEC_ESS_HSM2_SFP_U2A16_DM_211_NewKeyCEAICE_V2.7.31.r0** 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-07-14 12:29 · [[Alexander_Wegmann|Alexander Wegmann]]
> This request is being worked on by RT-SEC here: [https://jira.etas-dev.com/browse/DE_1901025HSM-105160]

-------

> [!note]+ 2026-06-24 12:46 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Alexander_Wegmann|Alexander Wegmann]]
> Could you please take a look at this issue?
> Thanks,

-------

> [!note]+ 2026-06-24 12:46 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Alexander_Wegmann|Alexander Wegmann]], this CycurHSM2 ticket requires an assignee. As the component lead for CycurHSM2, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-06-24 11:58 · [[FAE_Technical|FAE Technical]]
> AI Investigation automatically started due to ticket creation by trusted agent Junsheng ZHANG.
> Progress can be tracked on [Jenkins](https://rta-fae.jenkins.etas-dev.com/job/Hotline%20Automation%20-%20Agentic/job/main)
>
> (Return code: 201)

-------

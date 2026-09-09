---
jira_key: RH-17113
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17113"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Customer
priority: Medium
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-03T06:11:36.000+0200"
updated: "2026-09-09T16:28:53.000+0200"
synced-at: "2026-09-09T14:34:18.809Z"
jira-orphaned: false
profile: Cariad
---

# RH-17113 Lin’s E2E issue

> [!jira] Waiting for Customer · Medium · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] · 更新于 2026-09-09T16:28:53.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17113)

> 标签：#jira/label/vncnms

## 描述

Hi hotline, 

 When configuring Lin-related E2E frames, the customer encountered tool rule error messages, but these limitations do not meet the customer’s requirements. 

 When the customer configured Lin E2E parameters, 

they set:Counter start bit = 48, length = 4 CRC start bit = 56, length = 8 No header is usedTherefore；  

the customer set:E2EXfRb_UpperHeaderBitsToShift = 0E2EXfRb_CounterOffset = 48E2EXfRb_CRCOffset = 56； 

However, our tool reports that: 

E2EXfRb_UpperHeaderBitsToShift must equal E2EXfRb_CounterOffset,  

E2EXfRb_CRCOffset must equal E2EXfRb_CounterOffset + 8. 

The customer cannot change this accordingly. They can only configure it as follows, but this configuration is actually incorrect in practice. 

May I ask why we have such restrictions? Is there a way to help the customer achieve the required functionality? 

![[RH-17113-image001.png]] 

![[RH-17113-image002.png]] 

![[RH-17113-image003.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-03 10:32 · [[JSM_Service_Bot|JSM Service Bot]]
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-09-03 10:32 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]] ,
>
> The customer hasn’t synced the project to us yet, but previously in the 9.1 version, the RTA CAR was configurable. After the customer synced to 12.11, it no longer works.

-------

> [!note]+ 2026-09-03 08:47 · [[Ho_Anh_Dang_(MSETA-Hub-CN)|Dang Ho Anh]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] 
>
> Could you share the project in the ticket or directly with me?
>
> Regarding the statement “our tool reports that ...”, could you confirm whether this error is reported by BSW Gen?

-------

> [!note]+ 2026-09-03 06:19 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

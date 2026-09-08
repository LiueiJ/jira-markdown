---
jira_key: RH-15399
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15399"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: yinchuan.xu@etas.com
reporter: yinchuan.xu@etas.com
tags: []
components: [RTA-OS]
fix-versions: []
epic: null
parent: null
created: "2026-03-09T13:17:27.000+0100"
updated: "2026-06-01T10:06:43.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-15399 [Cariad] BSW can't be implemented by untrusted application

> [!jira] Closed · Critical · [[Yinchuan_XU|Yinchuan XU]] · 更新于 2026-06-01T10:06:43.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-15399)

> 标签：#jira/comp/rta-os

## 描述

Dear hotline:

Our customer Cariad meet an issue in **RTA-CAR 12.11.0VCTCESR1pr1**,  os port **TriCore-TC4xx-HighTec_5.0.4**

**Background**: Customer only need ASILB(trusted with protection) and QM(untrusted) application in a core, and they hope to allocate BSW into QM application, because in customer’s architecture, a lot of QM swcs need to invoke BSW code, they must set BSW in QM application, so that it can access normally.

**Issue1**: For currently, our tool don’t support set BSW into QM application, it forced to implement to trusted application, as below screenshot:

![[RH-15399-image001.png]]

**Workaround**: Customer config two trusted with protection applications, then set one application as QM, another one as ASILB. 

**Issue2**: In this case, both two applications belong to set2(we config TWP is set2), our OS can't distinguish which application should use set2, and another use set1 or the other set. 

To these issues, customer have two **options**:

1. Can we set BSW into untrusted application?
2. Can our OS provide callback function which we can add manual code to distinguish different set?

**Yinchuan XU** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

T +86 21 2218-5944 

M +86 159 02128410 

[Yinchuan.XU@etas.com!mail_small.gif!](mailto:Yinchuan.XU@etas.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

Room 2601, Baoland Plaza, No.83 Pazhou Avenue, Haizhu District, Guangzhou 510308, P.R. China 

[www.etas.cn](http://www.etas.cn/) **

ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- is mentioned in: [[RH-16055 Partitioning Concept]]

## 评论

> [!note]+ 2026-05-13 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-11 08:08 · [[Yinchuan_XU|Yinchuan XU]]
> Ok, got it, thanks for your response, I will synchronize this information with customer 

-------

> [!note]+ 2026-04-10 23:03 · [[Benedikt_Bauer|Benedikt Bauer]]
> [[Yinchuan_XU|Yinchuan XU]] 
> I think issue 1 is caused by a check of RTE, is that assumption correct?
> If so, this behaviour is changed in a version of RTE which is not integrated in the mentioned RTA-CAR version.
> ![[RH-15399-image-2026-04-10-23-02-45-447.png]]

-------

> [!note]+ 2026-03-31 04:06 · [[Yinchuan_XU|Yinchuan XU]]
> For issue1, in {*}RTA-CAR 12.11.0VCTCESR1pr1{*}, customer tested, still can't set BSW into untrusted application;
>
> For issue2, it really works, many thanks for all your support.

-------

> [!note]+ 2026-03-26 17:46 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-03-12 16:09 · [[Girish_Chandran|Girish Chandran]]
> thanks [[Benedikt_Bauer|Benedikt Bauer]] :) Much appreciate your help. 
>
> [[Yinchuan_XU|Yinchuan XU]] Please check the feedback from Benedikt. It seems like, your osPort already supports what's been requested by the customer. We didn't see it during the meeting, as I assume you were using the old version of Os. Can you check if customer has TriCore-TC4xx-HighTec_5.0.4 and see if the proposal from Benedikt works for you.
>
> Thanks!

-------

> [!note]+ 2026-03-12 13:41 · [[Benedikt_Bauer|Benedikt Bauer]]
> [[Yinchuan_XU|Yinchuan XU]] 
> TriCore-TC4xx-HighTec_5.0.4 added a new feature "ExtendedPermissions".
> I think this should cover your use-case, as each OsApplication can be assigned individual PSW PRS, IO and S bits once during StartOs. This probably will also reduce re-programming time at context switches.
>
> Or did I misinterpret your intention for issue2?

-------

> [!note]+ 2026-03-12 13:29 · [[Benedikt_Bauer|Benedikt Bauer]]
> Fastforward to L3

-------

> [!note]+ 2026-03-12 13:29 · [[Benedikt_Bauer|Benedikt Bauer]]
> Fastforward to L3

-------

> [!note]+ 2026-03-12 12:41 · [[Yinchuan_XU|Yinchuan XU]]
> Hi [[Girish_Chandran|Girish Chandran]] 
>
> For issue1:
>
> I will recommend customer to have a try.
>
> For issue2:
>
> Please help to connect OS team, and give customer feedback as soon as possible.
>
> Many thanks for your support.

-------

> [!note]+ 2026-03-12 10:33 · [[Girish_Chandran|Girish Chandran]]
> hi [[Yinchuan_XU|Yinchuan XU]], Please feel free to add a calendar blocker and let's get into a discussion. 

-------

> [!note]+ 2026-03-12 03:50 · [[Yinchuan_XU|Yinchuan XU]]
> Hello [[Girish_Chandran|Girish Chandran]] 
>
> When you are free, please tell me, I will book a meeting, and show you the detail issue, thanks for your support

-------

> [!note]+ 2026-03-12 00:12 · [[Sathish_Kumar_Madanmohan|Sathish Kumar Madanmohan]]
> [^Re_ *Cariad* BSW can't be implemented by untrusted application.msg]
>
> ^Customer escalation for immediate support as it blocks their release^
>
> to avoid losing time. [[Yinchuan_XU|Yinchuan XU]] please book a meeting with [[Girish_Chandran|Girish Chandran]]  and explain - if possible, show the issue so the product team can understand the problem clearly . 
>
> thanks [[Alex_Fargus|Alex Fargus]]  for your imm. support.

-------

> [!note]+ 2026-03-11 14:27 · [[Girish_Chandran|Girish Chandran]]
> hi [[Yinchuan_XU|Yinchuan XU]] Could you please provide more insights on the error you are getting in issue1,. It's not clear who reports it and the context. 

-------

> [!note]+ 2026-03-11 14:19 · [[Alex_Fargus|Alex Fargus]]
> [[Su_Nguyen_Quoc|Su Nguyen Quoc]] Please can the support team start looking at this it has high priority, I will try to pull support from the global team.
>
> [[Girish_Chandran|Girish Chandran]] Please can AAA team take a quick look and advise?

-------

> [!note]+ 2026-03-10 02:16 · [[Jie_LIU|Jie LIU]]
> [[Yinchuan_XU|Yinchuan XU]]  Please always add ETAS Project Manager so that the ticket can be seen

-------

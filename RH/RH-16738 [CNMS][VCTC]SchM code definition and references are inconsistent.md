---
jira_key: RH-16738
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16738"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: [RTA-RTE]
fix-versions: []
epic: null
parent: null
created: "2026-07-23T08:23:46.000+0200"
updated: "2026-09-03T14:28:36.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-16738 [CNMS][VCTC]SchM code definition and references are inconsistent

> [!jira] Closed · High · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-09-03T14:28:36.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16738)

> 标签：#jira/comp/rta-rte #jira/label/vncnms

## 描述

Hi Hotline, 

 The customer found that our ETH_TCP SchM code calls and definitions are inconsistent, which leads to compilation issues; 

 As shown in the example of the attached image: the SchM_Enter_rba_EthTcp_TxBuf function has input parameters when it is called, but the corresponding RTE interface has no input parameters. This is an issue.  

If this problem is caused by configuration, please provide a solution.

 If it is caused by a tooling issue, please let us know a repair plan; 

 ![[RH-16738-image001.png]] 

 ![[RH-16738-image002.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- mentions: [[RH-13777 [rba_EthTcp] remove argument from exclusive area function]]

## 评论

> [!note]+ 2026-09-03 14:28 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-08-20 03:58 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Junsheng_ZHANG|Junsheng ZHANG]] , do you have any feedback for this ticket? 

-------

> [!note]+ 2026-08-19 18:56 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-08-04 15:46 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Junsheng_ZHANG|Junsheng ZHANG]] :
>
> These integration code will map input parameter to SchM_Enter_rba_EthTcp_...[] array then it will be mapped to rte schm function
>
> ![[RH-16738-image-2026-08-04-20-45-13-216.png]]
>
> ![[RH-16738-image-2026-08-04-20-45-48-263.png]]

-------

> [!note]+ 2026-08-04 14:47 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ,
> I’m not fully understanding your response. In the picture you provided, the issue was not fixed—the function still has parameters. I checked in PR4 the call sites of {{{}SchM_Enter_rba_EthTcp_TxBuf{}}}, and they are still made with parameters.
>
> So did the RTE segment modify the code and add parameters to these interfaces?

-------

> [!note]+ 2026-07-27 08:56 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ,
>
> Big thanks for your feedback.
>
> In this week, [[Dong_LIU|Dong LIU]] is the proxy of Zhang Junsheng.
>
> Thanks a lot!

-------

> [!note]+ 2026-07-27 08:50 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] , [[Junsheng_ZHANG|Junsheng ZHANG]] , [[Dong_LIU|Dong LIU]] , [[Jiaqi_JI|Jiaqi JI]] : We check and this issue was fixed in RTA-CAR 12.11 and it's been in RTA-CAR 12.11.0.VCTCESR1pr4.
>
> Note: please generate integration code (rba_EthTcp_Cfg_SchM.h) again then SchM function will be defined like below:
>
> ![[RH-16738-image-2026-07-27-13-49-40-090.png]]
>
> Please check again with RTA-CAR 12.11.0.VCTCESR1pr4!

-------

> [!note]+ 2026-07-26 05:42 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-07-26 05:42 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> Could you please help confirm the specific fix version and timing?

-------

> [!note]+ 2026-07-24 14:58 · [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]],  There is no fix required from RTE. EthTcp module should change the way Schm APIs are called i.e. those API's should not have an argument. In  RH-13777 , issue was resolved by change in https://jira.etas-dev.com/browse/ARCCOM-9772

-------

> [!note]+ 2026-07-24 11:22 · [[JSM_Service_Bot|JSM Service Bot]]
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

> [!note]+ 2026-07-24 11:22 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]], this RTA-RTE ticket requires an assignee. As the component lead for RTA-RTE, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-24 11:20 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Vamsi_Kiran_Koduri|Vamsi Kiran Koduri]] ,
> As I understand it, this issue was already identified in RH-13777 and was resolved in RTA-CAR by the {*}RTA-RTE team{*}. However, I cannot see any related updates or changes. Could you kindly help me confirm the following: 
>  # Is my understanding of this issue correct?
>  # If so, do we have any plans to provide a fix for it?
>
> As a workaround, I believe we should keep the APIs with parameters in **`rba_EthTcp_Cfg_SchM.h`** from RTA-BSW. Could you please confirm whether this approach is correct? 

-------

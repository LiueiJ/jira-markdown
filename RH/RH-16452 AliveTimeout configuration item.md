---
jira_key: RH-16452
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16452"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: dong.liu5@etas.com
reporter: dong.liu5@etas.com
tags: [Regional, VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-06-23T19:07:55.000+0200"
updated: "2026-08-06T05:57:30.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-16452 AliveTimeout configuration item

> [!jira] Closed · High · [[Dong_LIU|Dong LIU]] · 更新于 2026-08-06T05:57:30.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16452)

> 标签：#jira/label/regional #jira/label/vncnms

## 描述

Hi, 

The customer has some questions regarding the usage of the  **AliveTimeout configuration parameter**. The RTA-CAR version being used is* 

 ***RTA-CAR 12.9.0**. Could you please help check this issue? Thank you. 

 **Issue background:**

 The customer has configured the  **AliveTimeout** parameter, as shown in the figure below. However, after the configuration, they found that the  **AliveTimeout** setting has no impact on the generated configuration files and code after running  **ConfGen** and  **CodeGen**. 

![[RH-16452-image001.png]] 

The customer would like to confirm the purpose of the  **AliveTimeout** parameter and how to make it take effect. 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- duplicates: [[RH-16863 [VNCNMS][VCTC]AliveTimeout configuration is not taking effect]]
- mentions: [[RH-14775 [VNCNMS][ANY] Issue relates to generate "ComTimeOutNotification" using conf-gen of RTA-CAR 12.9.0]]

## 评论

> [!note]+ 2026-06-24 14:18 · [[Dong_LIU|Dong LIU]]
> [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]   ok, thank you

-------

> [!note]+ 2026-06-24 11:21 · [[Shaker_Abdolrahman_Saleh|Shaker Abdolrahman Saleh]]
> Hi [[Dong_LIU|Dong LIU]],
>
> the AliveTimout value can be configured as suggested in this [RH-14775?focusedCommentId=637383](https://rtahotline.etas.com/jira/browse/RH-14775?focusedCommentId=637383&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-637383) therefore either:
>  # Change the <TIMEOUT> value on ISignalPort ETAS01_Sig01_ETAS_IN to be 3.0 and rerunning ConfGen (Generate ECU Configuration) or
>  # Change the DataTypePolicy of the ISignal from LEGACY to NETWORK-REPRESENTATION-FROM-COM-SPEC, which makes ConfGen derive ComTimeout directly from the AliveTimeout on the SWC RPort. (See attached picture)
>
> Additionally it is recommended to use git for versioning project changes instead of creating multiple copies of the project.
>
>
>
> Best
> Shaker
> ![[RH-16452-2026-06-24_11h18_01.png]]

-------

> [!note]+ 2026-06-24 04:37 · [[Dong_LIU|Dong LIU]]
> I have attached the project in the attachment.

-------

> [!note]+ 2026-06-24 04:37 · [[Dong_LIU|Dong LIU]]
> [^autosar_rta_xip_1290.zip]

-------

> [!note]+ 2026-06-23 19:07 · [[FAE_Technical|FAE Technical]]
> AI Investigation automatically started due to ticket creation by trusted agent Dong LIU.
> Progress can be tracked on [Jenkins](https://rta-fae.jenkins.etas-dev.com/job/Hotline%20Automation%20-%20Agentic/job/main)
>
> (Return code: 201)

-------

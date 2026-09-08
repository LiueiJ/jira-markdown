---
jira_key: RH-17116
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17116"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: Medium
project: RH
assignee: shweta.ganeshdixit@in.bosch.com
reporter: dong.liu5@etas.com
tags: [VNCNMS]
components: [Communication-Eth]
fix-versions: []
epic: null
parent: null
created: "2026-09-03T08:18:36.000+0200"
updated: "2026-09-07T07:19:30.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-17116 [VNCNMS][VCTC]Triggering of TCP messages in the SD module

> [!jira] Waiting for Level 3 · Medium · [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] · 更新于 2026-09-07T07:19:30.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17116)

> 标签：#jira/comp/communication-eth #jira/label/vncnms

## 描述

hi, 

 CARIAD has reported an issue with the SD module. The RTA-CAR version being used is RTA-CAR 9.1. 

 **Issue Description:** 

The subscription event group on the SD server side is configured with both UDP and TCP messages. However, when the customer subscribes to the relevant event group, only the UDP message is transmitted, while the TCP message is not transmitted. 

After investigation, it was found that in the code shown in the figure below, only the Routing Group corresponding to UDP is triggered for transmission. There is no corresponding trigger logic to initiate transmission for the Routing Group corresponding to TCP. 

![[RH-17116-image001.png]] 

I further checked the corresponding code in RTA-CAR 12.11 and found that the Routing Group corresponding to TCP can be triggered, as shown in the figure below: 

![[RH-17116-image002.png]] 

 **Customer Request:** 

The customer would like us to provide a suitable solution to resolve this issue. Thank you! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 关联

- mentions: [[RH-16737 [VNCNMS]The TCP and UDP Events are configured within the same Event Group.]]

## 评论

> [!note]+ 2026-09-07 06:14 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]], this Communication-Eth ticket requires an assignee. As the component lead for Communication-Eth, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-09-07 06:13 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Shweta_Ganesh_Dixit|Shweta Ganesh Dixit]] ,
>
> I got the confirmation in RH-16737 that **UDP and TCP has been supported** and it can be configured together {*}in the project for RTA-CAR 9.1{*}.
>
> ![[RH-17116-image-2026-09-07-11-14-10-110.png]]
>
> Hence, I checked the customer project and see **the configuration for TCP of SD module have been created** as below:
>
> ![[RH-17116-image-2026-09-07-11-14-31-167.png]]
>
> Therefore, I checked the code in this version (RTA-CAR 9.1), I only see UDP messages being transmitted, as TCP is not supported, which matches the customer's report.
>
> ![[RH-17116-image-2026-09-07-11-15-00-004.png]]
>
> I checked the higher release ({*}RTA-CAR 12.1.0{*}) and see UDP has been updated as below:
>
> ![[RH-17116-image-2026-09-07-11-15-19-965.png]]
>
> -------------
>
> ==> Could you please help check this issue and provide feedback to the customer?
> To summarize, the customer has already performed the necessary TCP-related configurations in the SD module. However, they are observing that TCP message is not transmitted.
> Thank you. 
> ![[RH-17116-image-2026-09-07-11-14-10-110.png]] ![[RH-17116-image-2026-09-07-11-14-31-167.png]] ![[RH-17116-image-2026-09-07-11-15-00-004.png]] ![[RH-17116-image-2026-09-07-11-15-19-965.png]]

-------

> [!note]+ 2026-09-03 13:16 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
> We will begin analyzing this ticket tomorrow and will share further details asap.

-------

> [!note]+ 2026-09-03 10:38 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Phuong_Nguyen_Le|Phuong Nguyen Le]] Phuong,
>
> Could you support arrange one of your colleague to help take a look into this issue?
>
> Thanks a lot!
>
> Best Regards,
>
> Jiaqi Ji

-------

> [!note]+ 2026-09-03 10:37 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Dong LIU, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

---
jira_key: RH-17116
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17116"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 2
priority: Medium
project: RH
assignee: khoa.phanhuynhdang@vn.bosch.com
reporter: dong.liu5@etas.com
tags: [VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-03T08:18:36.000+0200"
updated: "2026-09-03T13:17:08.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-17116 [VNCNMS][VCTC]Triggering of TCP messages in the SD module

> [!jira] Waiting for Level 2 · Medium · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] · 更新于 2026-09-03T13:17:08.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17116)

> 标签：#jira/label/vncnms

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

## 评论

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

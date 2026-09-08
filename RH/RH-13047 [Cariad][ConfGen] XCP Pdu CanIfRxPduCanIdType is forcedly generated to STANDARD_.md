---
jira_key: RH-13047
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13047"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: marc.kaiser2@etas.com
reporter: sisi.tao@bosch.com
tags: []
components: [Communication-Can-Lin-Fr]
fix-versions: []
epic: null
parent: null
created: "2025-05-16T09:10:24.000+0200"
updated: "2026-06-11T10:35:11.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-13047 [Cariad][ConfGen] XCP Pdu CanIfRxPduCanIdType is forcedly generated to STANDARD_NO_FD_CAN

> [!jira] Closed · Low · [[Marc_Kaiser|Marc Kaiser]] · 更新于 2026-06-11T10:35:11.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-13047)

> 标签：#jira/comp/communication-can-lin-fr

## 描述

Dear Marc and hotline colleague, 

I’m using RTA-CAR 12.6 ConfGen. XCP message is forcedly generated to STANDARD_NO_FD_CAN even though the can frame RX behavior is ANY 

<CAN-FRAME-RX-BEHAVIOR>ANY</CAN-FRAME-RX-BEHAVIOR> 

![[RH-13047-image001.png]] 

Following is the confgen script where overwrite the GI value: 

![[RH-13047-image002.png]] 

I remember I discussed with [@Kaiser Marc (ETAS-ECM/XPC-Fe5)!mail_small.gif!](mailto:Marc.Kaiser2@etas.com) about this but cannot find the record. And also [https://rtahotline.etas.com/jira/browse/RH-2907](https://rtahotline.etas.com/jira/browse/RH-2907) mentioned this issue. Apparently XCP on FD is supported. Cariad also uses XCP on CanFD. So I’d like to know the intention of this line and whether RTA-BSW can make the change. Thank you very much. 

 ** Sisi TAO** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 133 81555197 

 [Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](http://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-08-14 18:02 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-07-09 04:53 · [[Mingye_YUAN|Mingye YUAN]]
> Confirmed from Mr. Fargus Alex, this issue will be solved in CAR 12.8.0.

-------

> [!note]+ 2025-05-16 09:45 · [[Marc_Kaiser|Marc Kaiser]]
> Hello [[Sisi_TAO|Sisi TAO]], 
>
>
>
> thank you for reporting this again. 
>
> The line is removed in RTA-CAR 12.8.0. This is the ticket for tracking removal of the line: [https://jira.etas-dev.com/browse/ARC-9353](https://jira.etas-dev.com/browse/ARC-9353) 
>
>
>
> I just checked with [[K_Raj_Kumar|K Raj Kumar]] to make sure that it is not missed. 
>
> Until that release, we will bridge gap by providing ConfGen Plugins with hotfixes. 
>
>
>
> We will send Plugin by EOD. 
>
>
>
>  *{color:black} *Marc Kaiser*{color}*{color:black} 
>  Cross-Functional People and Competence- People Lead Feuerbach 5 
>
>  T +49 7062 911-5130{color}{color:black}{color} 
>  [{color:black}{color}{color:#164293}Marc.Kaiser2@etas.com{color}{color:black}{color}](mailto:Marc.Kaiser2@etas.com){color:black}{color}{color:black} 
>
>  ETAS GmbH, ETAS-ECM/XPC-Fe5 
>  Robert-Bosch-Allee 1, 74232 Abstatt, Germany{color}{color:black}{color} 
>  [{color:black}{color}{color:#164293}www.etas.com{color}{color:black}{color}](http://www.etas.com){color:black}{color}{color:black}{color}  *{color:#164293} 
>
>  *ETAS – Empowering Tomorrow’s Automotive Software*{color}*{color:black} 
>
>  Managing Directors: Dr. Thomas Irawan, Nicolet Eglseder, Mariella Minutolo
>  Chairman of the Supervisory Board: Dr. Walter Schirm
>  Registered Office: Stuttgart, Registration Court: Amtsgericht Stuttgart, HRB: 19033{color} 
>
>
>
>
>
>
>
>
>
>
>
>
>
>
>
>
>
>
>
> ![[RH-13047-image001.png]]
>
>
>
>
>
>
>
> ![[RH-13047-image002.png]]

-------

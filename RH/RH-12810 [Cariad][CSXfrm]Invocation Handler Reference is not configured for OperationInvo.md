---
jira_key: RH-12810
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12810"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: yinchuan.xu@etas.com
reporter: yinchuan.xu@etas.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-04-15T10:56:01.000+0200"
updated: "2026-03-12T07:39:53.000+0100"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-12810 [Cariad][CSXfrm]Invocation Handler Reference is not configured for OperationInvokedEvent *** in Rte Ecuc value

> [!jira] Closed · High · [[Yinchuan_XU|Yinchuan XU]] · 更新于 2026-03-12T07:39:53.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12810)

## 描述

Hello Hotline & Marc: 

 I’m integrating customer’s project base on RTA-CAR 12.6.0, and add  **Rte_Rips_CSXfrm** this module, then I meet a problem when I generate BSW code, the detail error as below: 

![[RH-12810-image001.png]] 

 Customer really has SWC with OperationInvokedEvent, and I map this event(runable) to an empty task, also I configure RteRipsInvocationHandler in  **Rte_Rips_CSXfrm** module. 

![[RH-12810-image002.png]] 

![[RH-12810-image003.png]] 

 All of these configuration have been done, but it still report error, so I’m confused about what else should I do for this error? 

 Thanks a lot for your support. 

 ** Yinchuan XU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Yinchuan.XU@etas.com!mail_small.gif!](mailto:Yinchuan.XU@etas.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 Room 2601, Baoland Plaza, No.83 Pazhou Avenue, Haizhu District, Guangzhou 510308, P.R. China 

 [www.etas.com](http://www.etas.com)  ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-08-07 18:01 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-07-21 11:19 · [[Yinchuan_XU|Yinchuan XU]]
> Hi [[Alex_Fargus|Alex Fargus]] ,
>
> I just use RTA CAR generate it. Drop the OIE event runnable to task, then it generate automatically.

-------

> [!note]+ 2025-06-26 08:17 · [[Alex_Fargus|Alex Fargus]]
> [[Yinchuan_XU|Yinchuan XU]] you say below that the CSXfrm ecucvalues are automatically generated. Which tool is automatically generating these ecucvalues?

-------

> [!note]+ 2025-06-25 09:30 · [[Mingye_YUAN|Mingye YUAN]]
> Can anybody answer this question? Thanks.

-------

> [!note]+ 2025-04-18 09:01 · [[Yinchuan_XU|Yinchuan XU]]
> Hello Marc: 
>
>
>
>  Thanks a lot for your support, it really works when I change CSSafety to CSXfrm. 
>
>
>
>  But I don’t know if we have gap between our understanding to this issue. Actually in my CSXfrm EcuCValues, it include CSSafety, it’s really strange, but I’m sure it is not my copy paste, because it is generated automatic, the original name is  **/AUTOSAR/EcucDestinationUriDefSets/RteRipsUriDefSet**  or **/AUTOSAR_Rte_Rips_CSSafety/EcucModuleDefs/Rte_Rips_CSSafety (I don’t know when generate uri, and when generate CSSafety, I just really found these two path)** 
>
> ![[RH-12810-image001.png]] 
>
>
>
>  How the InvocationHandler generated: 
>
>  Drop the OIE event runnable to task, then the InvocationHandler in Rte_Rip_CSXfrm will be generated automatically. 
>
> ![[RH-12810-image002.png]] 
>
> ![[RH-12810-image003.png]] 
>
>
>
> I think this generated path is also wrong, I don’t know if this is same with your mentioned “This is bug in ISOLAR-B“.  
>
>
>
> Another issue I think you had known is that RteRipsInvocationHandlerRef only can ref to  **InvocationHandler** but not  **InvocationHandlerFnc.** 
>
> ![[RH-12810-image005.png]] 
>
>
>
>  *{color:black} *Yinchuan XU*{color}*{color:black} 
>  Cross Functional Regional Solution Field Management - Regional Solution Field Manager China{color} 
>
>  [{color:black}{color}{color:#164293}Yinchuan.XU@etas.com{color}{color:black}{color}](mailto:Yinchuan.XU@etas.com){color:black} 
>
>  ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 
>  Room 2601, Baoland Plaza, No.83 Pazhou Avenue, Haizhu District, Guangzhou 510308, P.R. China{color} 
>  [{color:black}{color}{color:#164293}www.etas.com{color}{color:black}{color}](http://www.etas.com){color:black}{color}  *{color:#164293} 
>
>  *ETAS – Empowering Tomorrow’s Automotive Software*{color}*{color:black}{color} 
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
> ![[RH-12810-image004.png]]
>
>
>
>
>
>
>
> !image008.png|thumbnail!
>
>
>
>
>
>
>
> !image009.png|thumbnail!
>
>
>
>
>
>
>
> !image010.png|thumbnail!
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
>
>
> !image011.png|thumbnail!
>
>
>
>
>
> !image012.png|thumbnail!
>
> !image013.png|thumbnail!
>
> ![[RH-12810-image001-2.png]]
>
> ![[RH-12810-image002-2.png]]
>
> ![[RH-12810-image003-2.png]]
>
> ![[RH-12810-image001-1.png]]
>
> ![[RH-12810-image002-1.png]]
>
> ![[RH-12810-image003-1.png]]

-------

> [!note]+ 2025-04-17 10:23 · [[Marc_Kaiser|Marc Kaiser]]
> Hello Yinchuan, 
>
>
>
> you have created a sneaky bug that was a bit hard to find 😝. But it was great fun to hunt for it xD… 
>
>
>
> Let me show you. In your CSXfrm EcuCValues, you have done a bad copy paste from CSSafety EcuCValues and you seem to have missed to update the Definition-Ref, so the values were still contributing to Parameters from CSSafety Paramef. 
>
>
>
> ![[RH-12810-image004.png]] 
>
>
>
> ISOLAR-B was not smart enough to catch this and it has actually merged the Parameters into the CSXfrm Values, which is incorrect. This is bug in ISOLAR-B. 
>
>
>
> ![[RH-12810-image001.png]] 
>
>
>
> However, ARTOP was smart enough to catch it and did not do the same mistake as ISOLAR-B. I only found out by debugging… 
>
>
>
> ![[RH-12810-image002.png]] 
>
>
>
> See when Jacop code, asks to get getRteRipsInvocationHandlerFncs() from rteRipsInvocationHandler, ARTOP correctly says that there are no such Containers in the EcuCValues. 
>
>
>
> ![[RH-12810-image003.png]] 
>
>
>
> I hope this helps! 
>
>
>
> If you get any other RTE issues you can always ping me to debug. 
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
> ![[RH-12810-image005.png]]
>
>
>
>
>
> !image006.png|thumbnail!
>
> !image007.png|thumbnail!
>
> ![[RH-12810-image001-1.png]]
>
> ![[RH-12810-image002-1.png]]
>
> ![[RH-12810-image003-1.png]]

-------

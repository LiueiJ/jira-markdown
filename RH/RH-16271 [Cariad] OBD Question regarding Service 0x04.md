---
jira_key: RH-16271
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16271"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: Jiaqi JI
reporter: Jiaqi JI
tags: [jira/label/cnms, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-06-05T04:49:43.000+0200"
updated: "2026-06-25T11:39:13.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Team, 

Cariad now has question that: 

Currently, Service 0x04 can only clear EmissionRelated DTCs. If all DTCs (include EmissionRelated and Non-EmissionRelated DTCs) can be cleared by service 0x04, how to implement it? 

Which option to choose about "DemOBDEngineType"? Our car models include "ICE/PHEV/BEV/EREV". 

Does ETAS lin stack support lin busoff? As they don't read any requirement in lin2.0 and IS017987-1/-2/-3/-4 related lin busoff 

Noted with thanks for your kindly support! 

 **Best Regards,** 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-06-25 11:39 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-06-10 11:42 · JSM Service Bot
> Jiaqi JI, the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-06-10 11:42 · Jiaqi JI
> Hi Khoa Phan Huynh Dang ,
>
> I have forwarded to customer. Noted with thanks for your kindly support!

-------

> [!note]+ 2026-06-09 13:10 · Khoa Phan Huynh Dang
> Hi Jiaqi JI ,
> Can you help me forward the analyzed information to the customer ☺️?

-------

> [!note]+ 2026-06-09 12:56 · Khoa Phan Huynh Dang
> **3. Does** **ETAS lin stack support lin busoff? As they don't read any requirement in lin2.0 and IS017987-1/-2/-3/-4 related lin busoff**
>
> In AUTOSAR, LIN is a simple master-slave (single-master) protocol based on UART, and it does not provide complex error management mechanisms like CAN (which includes error counters and error states such as error active, error passive, and bus-off). Therefore, there is no API or callback named `Lin_BusOff` or `LinIf_BusOff` in AUTOSAR.
>
>
>
> Additionally, if you want to process error in LIN driver, you can refer Fault Operation in "AUTOSAR_SRS_LIN.pdf" and "AUTOSAR_CP_SWS_LINDriver.pdf" for using the APIs
>
> ![[RH-16271-image-2026-06-09-18-07-04-315.png]]
>
> ![[RH-16271-image-2026-06-09-18-06-46-196.png]]
> ![[RH-16271-image-2026-06-09-18-06-46-196.png]] ![[RH-16271-image-2026-06-09-18-07-04-315.png]]

-------

> [!note]+ 2026-06-09 11:16 · Khoa Phan Huynh Dang
> **2. Which option to choose about "DemOBDEngineType"? Our car models include "ICE/PHEV/BEV/EREV".**
>  * Please specify the **EngineType** for **ICE** vehicles. Select **"Spark Ignition"** if the car runs on petrol, or **"Compression Ignition"** for diesel cars.
>
>  * **PHEV** and **EREV** vehicles also require this parameter because they still feature an internal combustion engine.
>
>  * For **BEV** vehicles, configuring this parameter is not required.

-------

> [!note]+ 2026-06-09 08:33 · Khoa Phan Huynh Dang
> 1. **Currently, Service 0x04 can only clear EmissionRelated DTCs. If all DTCs (include EmissionRelated and Non-EmissionRelated DTCs) can be cleared by service 0x04, how to implement it?**
>
> ==> SID 0x04 is used for Classic OBD, so this service can only clear EmissionRelated DTCs. If you want to clear all DTCs (OBD and non-OBD), please use SID 0x14.

-------

> [!note]+ 2026-06-09 08:12 · Jiaqi JI
> Hello Khoa Phan Huynh Dang ,
>
> Yes, customer use this version.

-------

> [!note]+ 2026-06-09 08:08 · Khoa Phan Huynh Dang
> Hello Jiaqi JI ,
>
>
> Could you please confirm whether our customer is still using 12.11.0VCTCESR1pr1 for their project?

-------

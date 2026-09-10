---
jira_key: RH-16304
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16304"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]"
reporter: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]"
tags: [jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-06-10T05:27:47.000+0200"
updated: "2026-06-10T11:49:50.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Dear hotline colleague, 

I’m migrating customer(CARIAD) project from  **RTA-CAR 12.11.0VCTCESR1pr1** to  **RTA-CAR 12.11.0pr3** 

Currently I can’t generate BSW properly. I did the migration in two ways, now I need dedicated support to generate BSW:

 **First way:**

 1. Create a new RTA-CAR project in new version 

2. Copy EcuC value arxml files into the project

 3. Select BSW modules and run generator 

4. But I got the following error: 

![[RH-16304-image001.png]] 

 **Second way:** 

1. Import old version project in the new RTA-CAR
2. Run:  **Convert to RTA-CAR project**
3. In the generated new converted project, configure Project Configuration, select all BSW modules
4. Replace ParamDef with new one
5. But I cannot find the  **Generate RTA-BSW Button**
6. ![[RH-16304-image002.png]]

 ** Sisi TAO** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 M +86 133 81555197 

 [Sisi.TAO@bosch.com!mail_small.gif!](mailto:Sisi.TAO@bosch.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-06-10 11:49 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]]
> I tested [^CEA2_0_RDCU_converted.zip] and it can generate BSW Code. 
>
> But when I copied this project into my repository (exactly the same files), It will report error in  ![[RH-16304-image001.png]]
>
>
> So I follow the error instruction (convert BCT to ISOLAR-B), and then BSW can gen.
>
> I close this ticket.

-------

> [!note]+ 2026-06-10 10:55 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> As offline support, [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] can generated with attachment project.
> [^CEA2_0_RDCU_converted.zip]

-------

> [!note]+ 2026-06-10 08:22 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] , I do a quick check. Can you try to add this line in buildSettings.properties then try it again
>
> ![[RH-16304-image-2026-06-10-13-21-17-639.png]]

-------

> [!note]+ 2026-06-10 06:13 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|Sisi TAO]] ,
>
> Could you attach the corresponding project for analyzing ☺️?

-------

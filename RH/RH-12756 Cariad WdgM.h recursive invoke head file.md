---
jira_key: RH-12756
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12756"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: yinchuan.xu@etas.com
reporter: yinchuan.xu@etas.com
tags: []
components: [System-InfraLib-Safety]
fix-versions: []
epic: null
parent: null
created: "2025-04-08T07:45:11.000+0200"
updated: "2026-03-05T06:52:04.000+0100"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-12756 Cariad: WdgM.h recursive invoke head file

> [!jira] Closed · Medium · [[Yinchuan_XU|Yinchuan XU]] · 更新于 2026-03-05T06:52:04.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12756)

> 标签：#jira/comp/system-infralib-safety

## 描述

Hello Hotline : 

 In Rta-Car 12.6.0, when I build WdgM module with GHS compiler, it report error as below: 

![[RH-12756-image001.png]] 

 Finally, I found the issue is because WdgM.h invoke WdgM_Cfg.h, and also WdgM_Cfg.h invoke WdgM.h, in this case, all the Marcs in WdgM_Cfg.h will be ignore. 

![[RH-12756-image002.png]] ![[RH-12756-image003.png]] 

 So I wanna why should we need to invoke these head file repetitive? 

 ** Yinchuan XU** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Yinchuan.XU@etas.com!mail_small.gif!](mailto:Yinchuan.XU@etas.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 Room 2601, Baoland Plaza, No.83 Pazhou Avenue, Haizhu District, Guangzhou 510308, P.R. China 

 [www.etas.com](http://www.etas.com)  ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2025-06-20 08:26 · [[Mingye_YUAN|Mingye YUAN]]
> Hello Hritik Meha:
>
> Please let me know what specific version will remove this circular, thanks a lot.

-------

> [!note]+ 2025-06-10 18:25 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Sisi_TAO|Sisi TAO]],
>
> That's a fair concern. Here's the comment by the developers:
>
> "Agreed on this. For now, I have linked a story([https://jira.etas-dev.com/browse/ARCSMIL-1371]) for further analysis or changes. Regarding the cyclic inclusion of WdgM, there seems to be a dependency between the macros/functions in WdgM.h and WdgM_cfg.h within the initial Multi-Partition Design. In my opinion, this dependency may no longer be necessary."
>
> This comments points at removing the circular includes in the future versions if possible! 
>
> Hope this helps.
>
> Best regards,
>
> Hritik

-------

> [!note]+ 2025-06-10 12:52 · [[K_Prathap_Kumar|K Prathap Kumar]]
> Hi [[Yinchuan_XU|Yinchuan XU]] [[Sisi_TAO|Sisi TAO]] ,
>
> Agreed on this. For now, I have linked a story([https://jira.etas-dev.com/browse/ARCSMIL-1371]) for further analysis or changes. Regarding the cyclic inclusion of WdgM, there seems to be a dependency between the macros/functions in WdgM.h and WdgM_cfg.h within the initial Multi-Partition Design. In my opinion, this dependency may no longer be necessary.

-------

> [!note]+ 2025-06-10 12:22 · [[Sisi_TAO|Sisi TAO]]
> Hi [[Hritik_Mehta|Hritik Mehta]] , is there any specific reason for such circular includes?  If there’s no need to do so, will it be improved in future release version? Since our customer met this issue, they have concern about the code quality and it’s hard for them to resolve such undirect compiler error. This information will be important for them.

-------

> [!note]+ 2025-06-10 12:19 · [[Yinchuan_XU|Yinchuan XU]]
> Hi [[Hritik_Mehta|Hritik Mehta]], [[K_Prathap_Kumar|K Prathap Kumar]] 
>
> Thanks a lot for your reply of this issue. I had checked my project, and really found **WdgM_Cfg.h** is directly included in a user.c, and I had modified it. It's a minor issue during my compilation process, and it's easy to solve.
>
> Actually my aim of this ticket is not how to solve this problem, but both customer and myself are all confused about why WdgM.h invoke WdgM_Cfg.h, and then WdgM_Cfg.h invoke WdgM.h again, we think it makes no sense, we can totally delete < #include "WdgM.h"> in WdgM_Cfg.h. How do you think?
>
> Compiler is GreenHill_201815

-------

> [!note]+ 2025-06-10 11:55 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Sisi_TAO|Sisi TAO]], [[Yinchuan_XU|Yinchuan XU]],
>
> The compiler error might occur if **WdgM_Cfg.h** is directly included in any of the {*}<(Application/Bsw)-Sw>_Header.h{*}. Could you check if that's the case? If it is, please include **WdgM.h** in the **<(Application/Bsw)-Sw>_Header.h** instead of {*}WdgM_Cfg.h{*}.
>
> Additionally, could you share the compiler details (architecture and version) as well?
>
> Thanks,
>
> Hritik

-------

> [!note]+ 2025-06-10 09:30 · [[K_Prathap_Kumar|K Prathap Kumar]]
> Hi [[Hritik_Mehta|Hritik Mehta]] ,
>
> AFAIK, above mentioned compiler error may occur If WdgM_Cfg.h is directly included in any of the <(Application/Bsw)-Sw>_Header.h, can you check this ?? If so, then include WdgM.h in the <(Application/Bsw)-Sw>_Header.h, not the WdgM_Cfg.h
>
> Can you share the Compiler details(arch, version) as well ??

-------

> [!note]+ 2025-06-09 15:47 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi System Safety developer. This ticket requires your attention.

-------

> [!note]+ 2025-06-09 15:47 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[K_Prathap_Kumar|K Prathap Kumar]],
>
> What do you mean by "include WdgM.h"? The issue arose because it is already included in WdgM_Cfg.h. Please clarify! :) 
>
> Thanks,
>
> Hritik

-------

> [!note]+ 2025-06-02 17:58 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-05-18 18:23 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2025-04-22 08:13 · [[K_Prathap_Kumar|K Prathap Kumar]]
> Hi [[Hritik_Mehta|Hritik Mehta]],[[Yinchuan_XU|Yinchuan XU]] 
>
> As you mentioned cyclic inclusion of WdgM headers shouldn't throw a compiler errors unless we include a wrong header. In this case i guess WdgM_Cfg.h is included directly somewhere in the src/header, if so then this such compiler error/warning will pop up. As a matter of fact, we use GHS compiler as part of our development chain.
>
> Kindly include WdgM.h (since its a public header) and let me know if it helps
>
> On my end i have to look back on any design decisions available to reason this cyclic dependency, but on a first look i don't think there is a need for such recursive inclusion.
>
> [[Mrinal_Kanti_Sirkar|Mrinal Kanti Sirkar]] : Share your thoughts if any

-------

> [!note]+ 2025-04-08 12:31 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Yinchuan_XU|Yinchuan XU]],
>
> I have raised this with L3.
>
> Best regards,
>
> Hritik

-------

> [!note]+ 2025-04-08 12:30 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi System Safety developer. This ticket requires your attention.

-------

> [!note]+ 2025-04-08 12:29 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Thomas_Chippy|Thomas Chippy]],
>
> I can see that circular includes were introduced to the WdgM suite from **12.4.0** onwards, specifically, WdgM.h includes WdgM_Cfg.h and vice versa.
>
> While this should generally work on most compilers due to include guards, it’s causing issues with the {*}GHS compiler{*}. Macros defined in WdgM_Cfg.h are not visible in WdgM.h. Has anyone run into this before, or is there a specific reason for the circular dependency? It may need to be refactored for GHS compatibility.
>
> Please confirm if this needs to be fixed or if there is a workaround.
>
> Thanks,
>
> Hritik

-------

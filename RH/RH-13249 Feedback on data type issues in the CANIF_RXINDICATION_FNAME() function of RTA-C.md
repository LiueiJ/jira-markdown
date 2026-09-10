---
jira_key: RH-13249
jira_url: "https://rtahotline.etas.com/jira/browse/RH-13249"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: Dong LIU
reporter: Dong LIU
tags: []
fix-versions: []
epic: null
parent: null
created: "2025-06-11T09:29:52.000+0200"
updated: "2026-03-05T06:52:02.000+0100"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

hi, 

I encountered an issues with the CANIF_RXINDICATION_FNAME() function when using RTA-CAR 12.6.0 in Cariad Project. Below is a detailed description of the problem. 

The data type defined in the red box in the following figure is uint8_least 

![[RH-13249-image005.png]] 

The RngLstPduId_qu8 variable is used at the position shown in the figure below 

![[RH-13249-image006.png]] 

However, in the Cariad project, the value of HrhCfg_pcst->pduIdx_t is greater than 255, which exceeds the range of uint8_least, As shown in the following figure: 

![[RH-13249-image001.png]] 

Thank you!!! 

Best regards, 

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN) 

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2025-07-24 18:01 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-07-09 18:25 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2025-06-25 12:09 · Phong Tang Dieu
> Hi Dong LIU 
>
> Yes, the uint32_least can be defined as same as uint8_least or you can define it even more.
>
> The meaning of uintx_least types according to Autosar are to define a type with **at least x bits unsigned.** So uint8_least means at least 8 bits unsigned. User can redefine it with a larger range based on the specific use case/system. That is the different between uint8 and uint8_least. The purpose of uintx_least types is to optimize and give better performance and flexibility on different hardware architecture.
>
> So in your case, uint8 is not enough to store all PduIndex as you have more than 255, then you have to redefine the uint8_least by a larger range, unsigned int or unsigned long are still fine. It's not relevant to the uint32_least. 
>
> Thanks, 

-------

> [!note]+ 2025-06-25 11:46 · Dong LIU
> Hi, Phong Tang Dieu 
>
> In our project, uint32_least has already been defined as an unsigned long, and uint8_least is also defined as  unsigned long. So why are uint32_least and uint8_least defined separately in the project, thank you!!!
>
> ![[RH-13249-image-2025-06-25-17-41-48-147.png]]

-------

> [!note]+ 2025-06-24 10:05 · Phong Tang Dieu
> Hi Dong LIU 
>
> This is an Autosar approach to define data type depend on CPU type. So, it would not have any bad impact to your project. In fact, in order projects, the uint8_least type is defined as unsigned long when the PlatformRbCpuType is CPU_TYPE_32. And it works well,
>
> Thanks,

-------

> [!note]+ 2025-06-23 09:11 · Dong LIU
> Hi,Phong Tang Dieu 
>
> In our project, there are over 100 places that use the uint8_least type. If we change the definition of uint8_least, will there be an evaluation of its impact on other places? What if it affects the address alignment in other places
>
> ![[RH-13249-image-2025-06-23-15-11-24-774.png]]

-------

> [!note]+ 2025-06-20 17:28 · Phong Tang Dieu
> Hi Dong LIU 
>
> actually the uint8_least type should be defined depend on your CPU type. You can see below configuration in the Platform module. The PlatformRbCpuType was configured to CPU_TYPE_32, then the PlatformRbNativeUint8Least should be unsigned long.
>
> ![[RH-13249-image-2025-06-20-16-18-45-819.png]]
>
> Thanks,

-------

> [!note]+ 2025-06-20 11:03 · Dong LIU
> Hi, Phong Tang Dieu 
>
> In actual debugging, at line 433 of the code, RngLstPduId_qu8 is assigned a value of 240. At line 460 of the while () loop, RngLstPduId_qu8 accumulates continuously and eventually exceeds 255, causing data overflow.
>
> ![[RH-13249-image-2025-06-20-16-58-03-328.png]]
>
> I have attached the project in the attachment
>
> [^20_Software.zip]

-------

> [!note]+ 2025-06-20 11:03 · Dong LIU
> [^20_Software.zip]

-------

> [!note]+ 2025-06-11 17:38 · Phong Tang Dieu
> Hi Dong LIU 
>
> Actually, the value of HrhCfg_pcst->pduIdx_t is NOT the PduIdx as in your showing figure.
>
> Your showing figure with red rectangles is **CanIf_CanIdListConfig_tacst** in CanIf_PBcfg.c. The PduIdx_t in this table is defined by type PduIdType which is configurable to be uint8/uint16/uint32.
>
> The HrhCfg_pcst->pduIdx_t is the index to get the target element from **CanIf_CanIdListConfig_tacst**  table.
>
> ![[RH-13249-image-2025-06-11-16-29-18-660.png]]
>
> Base on this screenshot of code, the RngLstPduId_qu8 should be 29, 30, 31, 32 for Pdus in your screenshot.
>
> If that is not the case, please share your project or at least the configuration and generated code of CanIf for further analysis.
>
> Thanks,

-------

---
jira_key: RH-15475
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15475"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: "[[Dong_LIU|Dong LIU]]"
reporter: "[[Dong_LIU|Dong LIU]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-03-16T04:15:21.000+0100"
updated: "2026-04-19T11:37:33.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi 

Project Background: 

We are currently working on a Cariad project, using RTACAR version 12.11.0VCTCESR1pr1. 

Problem Description: 

The customer found a memory section in the Fee module that needs to be placed in the Cache region. The section name is BSW_START_SEC_VAR_SECURED_CACHED_RAM_ALIGNED_CLEARED_UNSPECIFIED. In the entire project, this is the only section explicitly required to be placed in the Cache region. 

The customer would like to confirm whether it is mandatory to place this section in the Cache region. If it is not placed in the Cache region, what impact might it have? 

![[RH-15475-image001.png]] 

Thank you ! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 Tel. +86 21 2218-4408 | [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-04-19 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-04 18:48 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-03-19 17:42 · [[Dong_LIU|Dong LIU]]
> Hi, [[Hritik_Mehta|Hritik Mehta]] 
>
> I’ve replied to the customer. Their original understanding was that when using DMA, memory regions with cache cannot be used due to potential cache coherency issues, while without DMA, the data can be placed in any memory region. The customer will need to reconfirm this point.
>
> thank you!

-------

> [!note]+ 2026-03-17 17:21 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Dong_LIU|Dong LIU]],
>  # Yes, placement in cached RAM is mandatory for data integrity when DMA is used by the Fls/MemAcc driver. The section **BSW_START_SEC_VAR_SECURED_CACHED_RAM_ALIGNED_CLEARED_UNSPECIFIED** contains a single variable, {*}Fee_Prv_Cfg_MediumBuffer_un{*}, which is the sole DMA transfer buffer used for all Fee flash read and write operations. 
>  # The reason cached RAM is required is that DMA transfers bypass the CPU cache controller. If the DMA engine writes new data into this buffer while the CPU cache still holds a stale copy, the CPU will read the old (incorrect) data resulting in silent data corruption. 
>  # If DMA is **not** used by the Fls/MemAcc driver (CPU-copy mode only), placing this section in non-cached RAM is safe from a data-integrity perspective, though it incurs a performance cost. 
>
> Please confirm whether your Fls or MemAcc driver is configured to use DMA for flash transfers. If DMA is active, the buffer must be mapped to cacheable RAM.
>
> Best regards,
>
> Hritik

-------

> [!note]+ 2026-03-16 19:25 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Dong_LIU|Dong LIU]],
>
> Apologies for the delay, this is currently in investigation. You will get a response by tomorrow.
>
> Thanks,
>
> Hritik

-------

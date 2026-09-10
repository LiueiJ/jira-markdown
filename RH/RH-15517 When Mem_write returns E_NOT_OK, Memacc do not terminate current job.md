---
jira_key: RH-15517
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15517"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: Dong LIU
reporter: Dong LIU
tags: [jira/comp/memory-high-level]
fix-versions: []
epic: null
parent: null
created: "2026-03-19T18:09:23.000+0100"
updated: "2026-04-23T11:37:35.000+0200"
synced-at: "2026-09-10T08:07:25.599Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi, 

Project Background: 

We are currently working on a Cariad project, using RTACAR version 12.11.0VCTCESR1pr1. 

Problem Description: 

If the current MemAcc job requests MCAL’s mem_write and the mem_write interface returns E_NOT_OK, the MemAcc job will keep requesting mem_write, and the job status will remain in the REQ state, which will affect subsequent job requests. 

![[RH-15517-image001.png]] 

As shown in the figure below, the current job is terminated only when E_MEM_SERVICE_NOT_AVAIL is returned. If E_NOT_OK is returned, the job will not be terminated. 

![[RH-15517-image002.png]] 

The customer would like the current job to be terminated when MCAL’s mem_write returns E_NOT_OK. Please evaluate this request.  

Thank you! 

Best regards,

 

  **Dong LIU** 

 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China (ETAS-ECM/XSF-CN)

 Bosch (China) Investment Ltd. | 333 Fuquan (N.) Road | Shanghai 200335 |  P.R. CHINA 

 Tel. +86 21 2218-4408 | [Dong.LIU5@etas.com!mail_small.gif!](mailto:Dong.LIU5@etas.com)

## 评论

> [!note]+ 2026-04-23 11:37 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-08 18:48 · JSM Service Bot
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-03-24 11:51 · V Venkatachalam
> Hi Hritik Mehta ,
>
> If the parameter **MemAccTimeoutSupervisionEnabled** is set to {*}True{*}, any request will be aborted if a timeout occurs in the `MemAcc_Prv_CheckTimeout` function.
>
>
>
> Regards,
>
> Venki

-------

> [!note]+ 2026-03-20 20:20 · Hritik Mehta
> Hi V Venkatachalam,
>
> A customer using **RTA-CAR 12.11.0VCTCESR1pr1** reports that when **Mem_Write** returns {*}E_NOT_OK{*}, the **MemAcc** job does not terminate, it stays in the **REQ** state and the write is retried on every **MemAcc_MainFunction** call, blocking all subsequent requests.
>
> We traced the issue to {*}MemAcc_Prv_MemRequestJob(){*}: the **else** branch that's reached when **Mem_Write** returns **E_NOT_OK** only re-assigns **result_en = E_NOT_OK** without changing {*}stMemJob_en{*}. Only **E_MEM_SERVICE_NOT_AVAIL** triggers job termination. This is inconsistent with the **FlsLld** path ({*}MemAcc_Prv_FlsLld.c:268-271{*}), which terminates the job for any non-busy result.
>
> Please confirm if this is a bug, if so, are there any existing workarounds?
>
> Thanks,
>
> Hritik

-------

---
jira_key: RH-12910
jira_url: "https://rtahotline.etas.com/jira/browse/RH-12910"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: sammy.burchmore@etas.com
reporter: cong.zhang@etas.com
tags: [Cariad]
components: [Memory High-Level]
fix-versions: []
epic: null
parent: null
created: "2025-04-28T07:30:07.000+0200"
updated: "2026-03-08T08:36:35.000+0100"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-12910 [CNMS][Cariad]FEE/NvM (RTA_CAR 12.3.2) issues with Infenion TC49xN MemAcc ------ VM/Cariad related

> [!jira] Closed · Low · [[Sammy_Burchmore|Sammy Burchmore]] · 更新于 2026-03-08T08:36:35.000+0100
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-12910)

> 标签：#jira/comp/memory-high-level #jira/label/cariad

## 描述

Hi Tao Hao, 

RTA hotline is better to trace this issue with label  **&#91;CNMS&#93;&#91;Cariad&#93;.**  

 **From:** TAO Hao (ETAS-ECM/XSF-CN) <Hao.TAO2@etas.com> 

  **Sent:** Monday, April 28, 2025 1:25 PM

  **To:** Kaiser Marc (ETAS-ECM/XPC-Fe5) <Marc.Kaiser2@etas.com>; Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN) <Sathish.Madanmohan@etas.com>

  **Cc:** ZHANG Cong (ETAS-ECM/XSF-CN) <Cong.ZHANG@etas.com>; TAN Yang (ETAS-ECM/XSF-CN) <Yang.Tan@bosch.com>; TANG Yi (ETAS-ECM/XSF-CN) <Yi.Tang2@etas.com>

  **Subject:** FEE/NvM (RTA_CAR 12.3.2) issues with Infenion TC49xN MemAcc ------ VM/Cariad related   

Hi, Marc, 

When developing RTA-CAR project on TC499N, I found out that ETAS Mem Stack can not work correctly with Infineon MemAcc. Although temp solution had been figured out to solve the problem, I still need your and the production team’s support to analyze the issues further and release a final solution soon. The detailed issues are listed below: 

1. For TC49xN, there is special requirement when using MemAcc from Infineon MCAL: the main function Mem_17_Nvm_MainFunction() should be also called periodically after MemAcc_MainFunction().

![[RH-12910-image001.png]]![[RH-12910-image002.png]]![[RH-12910-image003.png]] 

1. For TC49xN, there is a special requirement when using MemAcc API (DFlash operation API): every time a flash operation finished, MemAcc_MainFunction() and

Mem_17_Nvm_MainFunction() should be called before calling next flash operation API. For satisfying this requirement, I modified the static codes a little like below and proved working. I could explain to you the detailed reason behind later. 

![[RH-12910-image004.png]] 

1. The MemAcc_BlankCheck() from Infenion strictly requires that the length of going to be written data is 8 bytes aligned. A temp solution from my side is setting the NvM block length to be (8n+2) bytes and proved working too.

![[RH-12910-image007.png]] 

1. After codes/config modification mentioned above, the data could be written into DFlash correctly, but reading data still failed. After debugging this issue further, a temp solution like below will help to read the NvM data correctly. For this one I could also explain to you the details later.

![[RH-12910-image008.png]] 

The MCAL package: AURIX_TC4x_MC-ISAR_2.20.0-EIR3 

The RTA_CAR version: 12.3.2 

The BSW version: 12.3.2 

The testing EVB: 

![[RH-12910-image009.jpg]] 

If you have the environment from your side, you can try to replicate the issues easily. Please try to reach me for the project if you need. 

If you don’t have the environment from your side, I could set a remote one for you and we can check the issues together.  

 ** Hao TAO** 

 ETAS-ECM/XSF-CN 

 

 M +86 199 72114034

## 评论

> [!note]+ 2025-09-10 18:03 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-07-16 15:26 · [[V_Venkatachalam|V Venkatachalam]]
> Hello [[Alex_Fargus|Alex Fargus]] ,
>
> [RTA-CAR 12.6.0](https://jira.etas-dev.com/issues/?jql=project+%3D+ARC+AND+fixVersion+%3D+%22RTA-CAR+12.6.0%22) is having the page alignment fix in Fee.
>
> Refer [[ARCMND-3761] [Mem][Fee] Follow-up: Optimize write of unaligned jobs when buffer is bypassed - Jira (etas-dev.com)|https://jira.etas-dev.com/browse/ARCMND-3761]
>
>
>
> Regards,
>
> Venki

-------

> [!note]+ 2025-06-27 04:28 · [[Alex_Fargus|Alex Fargus]]
> If these features are already supported in later versions, please let me know from which version the issues are fixed.

-------

> [!note]+ 2025-06-26 14:47 · [[Adrian_Funk|Adrian Funk]]
> [[Sammy_Burchmore|Sammy Burchmore]] :
>
> - What is Mem_17_Nvm_MainFunction doing?
> The intentended mechanism for scheduling something in the synchronnous init phase is to configure the parameter FeeRbSyncFlsMainLoopHook.
>
> - Later Fee versions already align blank checks to 8 bytes sizes
> - I understood the patch with calling the function rba_FeeFs1x_BC_initCopyDo_extractHdr is fixing an issue. But that modification should of course not be necessary and it should be understood why this patch is necessary. This might be fixed already be configuring FeeRbSyncFlsMainLoopHook to Mem_17_Nvm_MainFunction
>
> [[V_Venkatachalam|V Venkatachalam]] : Handing over this ticket to you as owner. Can you please further support if additional questions comes up?

-------

> [!note]+ 2025-06-25 11:45 · [[Sammy_Burchmore|Sammy Burchmore]]
> Hi [[Adrian_Funk|Adrian Funk]],
>
> This issues been in limbo for a while now. Could we please make some ARC tickets to track the defects and changes?
>
> Thanks,
>
> Sammy

-------

> [!note]+ 2025-06-25 11:43 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Memory Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-06-25 09:10 · [[Mingye_YUAN|Mingye YUAN]]
> After confirmation with Taohao, this issue can be temporarily avoided by either configuration or changing the integrated codes. So I lower the priority of this ticket. But it still should be solved for the coming 2.0 project. Thanks

-------

> [!note]+ 2025-06-25 05:46 · [[Alex_Fargus|Alex Fargus]]
> [[Manuel_Koehler|Manuel Koehler]] Is there any update on this? From reading your comment below it suggests that we have 2 defects and 2 new features required. Ideally we should have tickets for this ready for the upcoming PI planning if there is work to be planned within MEM RT.

-------

> [!note]+ 2025-04-29 12:33 · [[Manuel_Koehler|Manuel Koehler]]
> [^CARRIAD_TC4_DEMO.7z]

-------

> [!note]+ 2025-04-29 12:21 · [[Manuel_Koehler|Manuel Koehler]]
> [^src.7z]

-------

> [!note]+ 2025-04-29 12:14 · [[Manuel_Koehler|Manuel Koehler]]
> Notes from call with TAO Hao
>
> First Issue (Mem_17_Nvm_MainFunction needs to be called in MemIf main function):
> This fix has been applied based on an example project from Infineon. 
> We might need to incorporate this into the MemAcc main function for this platform. 
>
> Second Issue (Mem_17_Nvm_MainFunction needs to be called after flash operation):
> We need to take a closer look at this change. Probably this has to be handled the same way as the fix for the first issue. 
>
> Third issue (byte alignment): 
> The originally generated value for the data size was 384, which actually is a multiple of 8. 
> The problem is that the Fee header here has 14 bytes and this header is added to the memory block. 
> Therefore, by adding 2 bytes of data, we get (data + header) to be 8-byte-aligned. 
> Bswgen probably needs to add some padding to the header to make it 8-byte-aligned. 
>
> Fourth issue (reading not working properly): 
> Actually, fetching data from memory (case rba_FeeFs1x_BC_initCopy_stm_extract_e) works fine but validation fails. 
> Validation fails because according to Tao Hao, in case rba_FeeFs1x_BC_initCopy_stm_validate_e, we might be looking at outdated data (i.e. a different NvM block). If this is true then this seems like a bug in the generated code. 
>
> Tao Hao will share the RTA-CAR project and the modified sources for further investiagtion. 

-------

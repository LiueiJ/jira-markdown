---
jira_key: RH-16658
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16658"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: Medium
project: RH
assignee: alexander.wegmann2@etas.com
reporter: junsheng.zhang@bosch.com
tags: []
components: [CycurHSM3]
fix-versions: []
epic: null
parent: null
created: "2026-07-16T09:55:40.000+0200"
updated: "2026-08-12T07:12:30.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-16658 [CNMS][VCTC]Some host code sections for HSM are missing the memory section

> [!jira] Waiting for Level 3 · Medium · [[Alexander_Wegmann|Alexander Wegmann]] · 更新于 2026-08-12T07:12:30.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16658)

> 标签：#jira/comp/cycurhsm3

## 描述

Hi Hotline, 

 I found that in the HSM host code (CycurHSM_CariadCN_CEA2_configuration_TC4HFx_GHS_V3.0.5.b1_288KB), some functions are not included in the memory section. This will prevent these functions from being linked/compiled to the specified memory addresses, thereby impacting the development of the customer MPU functionality. 

For example, for the functions below, I summarized a table. All the functions of type “text” show similar issues. I believe these missing problems should be fixed. 

![[RH-16658-image001.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-08-10 06:44 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Alexander_Wegmann|Alexander Wegmann]] / [[Lukas_Riemenschneider|Lukas Riemenschneider]] ,
>
> can you help out here, please?
>
> Thx
>
> BR
> Christian

-------

> [!note]+ 2026-08-08 11:39 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Lukas_Riemenschneider|Lukas Riemenschneider]] ,
>
> The customer does not agree with changing the method in the link file, and this issue may potentially affect the customer’s MPU functionality.
>
> My suggestion has always been to provide a fix timeline.

-------

> [!note]+ 2026-08-04 09:04 · [[Alexander_Wegmann|Alexander Wegmann]]
> As per Lukas' comment, we consider this to be a future product improvement. This is not considered a bug. A customer workaround is available to the respective people.

-------

> [!note]+ 2026-07-27 15:00 · [[Lukas_Riemenschneider|Lukas Riemenschneider]]
> We already communicated to the project that there are trivial workarounds (e.g. can be solved by 1 line of code on customer side) to achieve this and asked the project to solve it on their side.
> Also, there are no product requirements for the expected behavior
> => this is not an issue and especially not a bug, but something nice to have, please be sensible about the communication
>
> we might consider this as a nice to have addition for the future.

-------

> [!note]+ 2026-07-20 08:01 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Alexander_Wegmann|Alexander Wegmann]], this CycurHSM3 ticket requires an assignee. As the component lead for CycurHSM3, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-07-20 08:00 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Alexander_Wegmann|Alexander Wegmann]] ,
>
> it seems that the "CycurHSM_CariadCN_CEA2_configuration_TC4HFx_GHS_V3.0.5.b1_288KB" have a issue with the memory section.
>
> Many host driver functions land in the default .text section and cannot be placed into MPU-controlled memory regions via ecy_hsm_MemMap.h.
>
> The customer reports that functions in the HSM host driver land in the default .text section instead of a named memory section. The attached map file (ecy_hsm_sections.xlsx) and screenshot (ecy_hsm_proxy_hwcsp.c in editor) confirm the symptom: 60+ functions shown in the map file with type 'text', all in default section. 
>
> Files MISSING ECY_HSM_START_SEC_CODE / STOP_SEC_CODE (11 files):
>
> - ecy_hsm_proxy_hwcsp.c — only has VAR section wrapping (ECY_HSM_START_SEC_VAR_HWCSP_TABLE_UNSPECIFIED), not CODE wrapping 
> - ecy_hsm_proxy.c 
> - ecy_hsm_proxy_trusted_boot.c 
> - ecy_hsm_ipcdrv.c 
> - ecy_hsm_host_hwcsp_drv.c 
> - ecy_hsm_mgmt_hwcsp.c 
> - ecy_hsm_srv_host_hwcsp_mac.c 
> - ecy_hsm_applet_host_hwcsp_mac_generate.c 
> - ecy_hsm_applet_host_hwcsp_mac_verify.c 
> - ecy_hsm_csai_mac_extended.c 
> - ecy_hsm_applet_cfg.c 
> - (TC4x-specific): ecy_hsm_css_drv.c, ecy_hsm_ipcmcal.c, ecy_hsm_prot_apu.c, ecy_hsm_runtime_detection.c, ecy_hsm_target_mcal.c, ecy_hsm_css_drv_mac.c, ecy_hsm_css_drv_sym_crypt.c, ecy_hsm_host_hwcsp_mac_mcal.c, ecy_hsm_host_hwcsp_mcal.c
>
> Files correctly using ECY_HSM_START_SEC_CODE (examples): 
> - ecy_hsm_mgmt_job.c:24 — uses ECY_HSM_START_SEC_CODE / :210 STOP_SEC_CODE 
> - ecy_hsm_basicsrvs.c:24 — same pattern 
> - ecy_hsm_she_session.c:26 — same 
> - ecy_hsm_csai_seclog.c:22 — same
>
> ecy_hsm_MemMap.h:582-586 defines handlers for ECY_HSM_START_SEC_CODE and STOP_SEC_CODE that are empty by default (user must add compiler pragmas). Even if filled in, the 11 affected files do not call them.
>
> Can you double check an confirm if it is a bug or different issue, please?
>
> thx
>
> BR
> Christian

-------

> [!note]+ 2026-07-20 07:54 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> it seems that I have understood your topic little wrong and checked again.
>
> After the re-checking it seems that you are right, that here something is missing.
>
> I will forward this issue to L3. - thx for pointing out again.
>
> BR
> Christian

-------

> [!note]+ 2026-07-19 12:56 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-07-19 12:56 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Christian_Fuerst|Christian Fuerst]] ,
>
>     You may not have understood my question. In the HSM host code, there are many functions that are not placed in the sections defined in the `ecy_hsm_MemMap` file. This is a missing definition—so the issue needs to be completed and fixed.
>
>     The functions are not located in the sections defined in {{{}ecy_hsm_MemMap.h{}}}. No matter how I modify {{{}ecy_hsm_MemMap{}}}, it doesn’t make any difference. Please refer to the images and the Excel file I shared for more details—these are the problematic functions.

-------

> [!note]+ 2026-07-17 08:10 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> found in the Section "4.10.2 Shared Memory Areas" of "UserGuide-CycurHSM_V3.0.5.b1.pdf" (can be found in the doc-folder of your delivery) (page 60) this part:
>
> [---snip---] 
>
> `The session status array and mailbox are static members of the hsm_proxy driver,`
> `but are located in a special section called “.hsm_shared” for convenience of`
> `system configuration. The user’s linker must support these sections.`
>
> `The following has to be considered:`
>
> `- The memory mapping has to be done as shown in ecy_hsm_MemMap.h,`
> `which is part of the delivery.`
> `- ``Host driver complies to the AUTOSAR memory mapping specification where`
> `definitions and declarations of variables, constants and code wrapped with`
> `memory allocation keywords.`
> `- ``All the memory allocation keywords are empty by default and hence are`
> `mapped to the default section. The user shall modify the ecy_hsm_MemM`
> `ap.h to assign the desired memory sections as per the project`
> `requirements.`
>
> [/---snip---]
>
> the mentioned file "ecy_hms_MemMap.h" can be found in the following folder of your delivery:
> [delivery-folder]\host_driver\internals\common
>
>
> you should take care about the memmap for your project needs.
>
>
>
> Hope that helps.
>
> BR
> Christian

-------

> [!note]+ 2026-07-16 09:55 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> [^ecy_hsm_sections.xlsx] *(12 kB)*

-------

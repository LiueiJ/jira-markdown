---
jira_key: RH-16780
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16780"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: "[[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]"
reporter: "[[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]"
tags: [jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-07-28T09:18:13.000+0200"
updated: "2026-08-21T15:05:34.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi team, 

Cariad raised one question that:  Is there any API from DEM module to erase/reinitialize the DEM Nvm block ? you can get these blocks from attachment. 

Noted with thanks! 

Best Regards, 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- is mentioned in: [[RH-16976 [VNCNMS][VCTC] OBD Cross-Core Implementation and NoOBD Configuration Follow-Up Issues]]

## 评论

> [!note]+ 2026-08-13 14:26 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-30 06:32 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> No, the Dem module does not provide a dedicated API to directly erase or reinitialize an NvM block. According to the mandatory interface table in "{*}8.4 Expected Interfaces{*}" and requirement **SWS_Dem_00164** in "AUTOSAR_SWS_DiagnosticEventManager.pdf", Dem interacts with NvM only through the following four APIs: {*}NvM_ReadBlock{*}, {*}NvM_WriteBlock{*}, {*}NvM_SetRamBlockStatus{*}, and {*}NvM_GetErrorStatus{*}. APIs such as **NvM_EraseNvBlock** and **NvM_InvalidateNvBlock** are not used by Dem.
>
> ![[RH-16780-image-2026-07-30-11-30-36-610.png]]
>
> If the customer requires a literal "erase" or "reinitialize" operation on an NvM block, this must be performed by directly calling the appropriate NvM APIs, such as **NvM_EraseNvBlock** or {*}NvM_InvalidateNvBlock{*}, from the application.
>
> ![[RH-16780-image-2026-07-30-11-31-35-174.png]]

-------

> [!note]+ 2026-07-28 09:19 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Khoa Phan Huynh Dang added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

> [!note]+ 2026-07-28 09:19 · [[JI_Jiaqi_(ETAS-ECMXSF-CN)|Jiaqi JI]]
> Hi team, 
>
>
>
> Cariad raised one question that: {color:black} Is there any API from DEM module to erase/reinitialize the DEM Nvm block ? you can get these blocks from attachment.{color} 
>
> Noted with thanks! 
>
>
>
> Best Regards, 
>
>
>
>  *{color:black} *Jiaqi JI*{color}*{color:black} 
>  Cross Functional Regional Solution Field Management - Regional Solution Field Manager China{color} 
>
>  [{color:black}{color}{color:#164293}Jiaqi.JI@etas.com{color}{color:black}{color}](mailto:Jiaqi.JI@etas.com){color:black} 
>
>  ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 
>  333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China{color} 
>  [{color:black}{color}{color:#164293}www.etas.cn{color}{color:black}{color}](https://www.etas.cn){color:black}{color}   *{color:#164293} 
>
>  *ETAS – Empowering Tomorrow’s Automotive Software*{color}*{color:black}{color}
>
> [^DEM_NVM.xlsx] *(11 kB)*

-------

> [!note]+ 2026-07-28 09:18 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Jiaqi.JI@bosch.com, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

> [!note]+ 2026-07-28 09:18 · [[Jiaqi.JI@bosch.com|Jiaqi.JI@bosch.com]]
> [^DEM_NVM.xlsx] *(11 kB)*

-------

> [!note]+ 2026-07-28 09:18 · [[JSM_Service_Bot|JSM Service Bot]]
> Note: Khoa Phan Huynh Dang added as watcher to the issue. Internal support agents cannot be added as Request Participants, so they have been automatically joined as Watchers instead.

-------

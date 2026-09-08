---
jira_key: RH-16976
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16976"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: jiaqi.ji@etas.com
reporter: jiaqi.ji@etas.com
tags: [VNCNMS]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-19T12:28:01.000+0200"
updated: "2026-09-05T14:28:42.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16976 [VNCNMS][VCTC] OBD Cross-Core Implementation and NoOBD Configuration Follow-Up Issues

> [!jira] Closed · Low · [[Jiaqi_JI|Jiaqi JI]] · 更新于 2026-09-05T14:28:42.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16976)

> 标签：#jira/label/vncnms

## 描述

Hi Team,

 

Regarding the following issue, Cariad was advised to use NvM APIs. I found that the

```

Dem_NvMClearBlockByWrite
```

 API can be used to clear the NvM block.

 **Cariad** **'d like to know if the**

```

Dem_NvMClearBlockByWrite
```

 **and**

```

NvM_EraseNvBlock
```

 **interfaces are the same, and what the differences are between them** **？**

![[RH-16976-image001.png]]

 

 **The following issue** **：**

 **Q1** **：** **Is there any API from DEM module to erase/reinitialize the DEM Nvm block ?**

 

![[RH-16976-image002.png]]

 

Big thanks for support!

 

Best Regards,

 **Jiaqi JI** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

[Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

 **ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- mentions: [[RH-16780 [VNCNMS][Cariad] Erase/reinitialization for DEM NVM block]]

## 评论

> [!note]+ 2026-09-05 14:28 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-08-21 15:05 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
>
> As I mentioned in [https://rtahotline.etas.com/jira/browse/RH-16780?focusedCommentId=711171&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-711171] of RH-16780, the DEM module does not provide a dedicated API to directly erase or reinitialize an NvM block.
>
> Regarding the concern point of **Dem_NvMClearBlockByWrite** and **NvM_EraseNvBlock** (Sorry for my mistake in the previous ticket, this is the correct name of this function):
>
> + {*}Dem_NvMClearBlockByWrite{*}: This API only marks the specific NvM blocks that need to be cleared by setting the corresponding flag bits. During the execution of {*}`Dem_MainFunction`{*}, the DEM module checks these flags and triggers the corresponding NvM write operations. Therefore, when operations such as {*}ClearDTC{*}, clearing event memory entries, or handling DTC memory overflow are performed, the associated data stored in the relevant NvM blocks will be cleared automatically by the DEM module.
>
>
> As a result, this API cannot be used by the application to erase or reinitialize DEM NvM blocks directly from Application layer, this API is only the internal helper function for DEM module to manage the above process.
>
> + **NvM_EraseNvBlock:** This API is used to erase NVM block directly as mentioned in RH-16780, 

-------

> [!note]+ 2026-08-20 09:41 · [[Jiaqi_JI|Jiaqi JI]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> Thanks for your feedback. Please give them feedback by tomorrow as customer requirement.
>
> Big thanks again!

-------

> [!note]+ 2026-08-20 05:53 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Jiaqi_JI|Jiaqi JI]] ,
> Let's we analyze the customer's concerns and get back to them with detailed feedback as soon as possible.

-------

> [!note]+ 2026-08-19 12:28 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Jiaqi JI, please note that this issue was made with VNCNMS in the summary and has been sent to the relevant queue by adding the VNCNMS label.

-------

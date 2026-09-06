---
jira_key: RH-17095
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17095"
server: rtahotline
kind: hotline
type: Support
status: Investigation Required
priority: High
project: RH
assignee: rohansatish.pandit@etas.com
reporter: steven.tang@etas.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-02T04:20:30.000+0200"
updated: "2026-09-02T10:14:51.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-17095 [Cariad] HWCSP Function Failure After HSM Reboot

> [!jira] Investigation Required · High · [[Rohan_Pandit|Rohan Pandit]] · 更新于 2026-09-02T10:14:51.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17095)

## 描述

Hi Team, 

Cariad encountered one issue that The HWCSP function does not work properly after an HSM reboot or power cycle. Before key injection, Hwcsp_LoadKey returns  **0x8000130D (EEPROM_TAG_NOT_FOUND)**, which is expected when no key has been injected. After key injection without power cycling,  **MacGen/MacVerify work normally**. However, after an HSM reboot/power cycle, Hwcsp_LoadKey returns  **0x80002211 (KEY_ALREADY_LOADED)**, while direct MacGen/MacVerify calls return  **0x80001208 (NOT_SUPPORTED)**. 

Thanks a lot for your support! 

Best Regards, 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

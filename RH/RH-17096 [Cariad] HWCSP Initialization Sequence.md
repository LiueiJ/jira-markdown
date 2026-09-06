---
jira_key: RH-17096
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17096"
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
created: "2026-09-02T04:21:30.000+0200"
updated: "2026-09-02T10:18:03.000+0200"
synced-at: "2026-09-06T06:58:38.472Z"
jira-orphaned: false
---

# RH-17096 [Cariad] HWCSP Initialization Sequence

> [!jira] Investigation Required · High · [[Rohan_Pandit|Rohan Pandit]] · 更新于 2026-09-02T10:18:03.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17096)

## 描述

Hi Team, 

Cariad encountered one issue that The initial analysis from the product team indicates that  **ecy_hsm_Csai_HwCsp_Init must be called after every HSM power cycle** to reinitialize the HwCsp software modules before performing LoadKey or MAC operations. However,  **Crypto already calls this initialization function**, so the current behavior cannot yet be fully explained by a missing initialization. The exact initialization sequence and HWCSP state after HSM reboot therefore require further investigation. 

Noted with thanks for your support! 

 **Best Regards,** 

 ** Jiaqi JI** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 [Jiaqi.JI@etas.com!mail_small.gif!](mailto:Jiaqi.JI@etas.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

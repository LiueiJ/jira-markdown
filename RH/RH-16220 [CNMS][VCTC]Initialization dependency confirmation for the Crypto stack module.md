---
jira_key: RH-16220
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16220"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Medium
project: RH
assignee: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
reporter: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-06-02T04:09:41.000+0200"
updated: "2026-06-12T09:51:24.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline，

Please confirm whether CryIf_Init, Csm_Init, KeyM_Init, and SecOC_Init depend on the initialization of HSM and Crypto_Init.

The customer wants to initialize HSM and Crypto after the initializations of CryIf_Init, Csm_Init, KeyM_Init, and SecOC_Init.

In Crypto, Hsm's opensession is called, so HSM must be initialized first before initializing Crypto. However, we are not sure if there are any logical or interface dependencies on other modules；

 **Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

 **ETAS – Empowering Tomorrow’s Automotive Software**

**From:** Xiao, Guosheng (C|GX-3) <guosheng.xiao@cariad-technology.cn> 

**Sent:** Monday, June 1, 2026 5:25 PM

**To:** ZHANG Junsheng (ETAS-ECM/XSF-CN) <junsheng.zhang@bosch.com>

**Cc:** JI Jiaqi (ETAS-ECM/XSF-CN) <jiaqi.ji@etas.com>

**Subject:** W: 加密栈模块初始化依赖确认加密栈模块初始化依赖确认

Hi，钧升：

 

    请帮忙确认下CryIf_Init，Csm_Init，KeyM_Init，SecOC_Init对HSM和Crypto_Init的初始化有依赖吗。

 

    我想在CryIf_Init，Csm_Init，KeyM_Init，SecOC_Init初始化之后初始化HSM和Crypto。

 

 

INTERNAL

## 评论

> [!note]+ 2026-06-04 12:28 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> {quote}Why the ideal order of the crypto stack is from top to bottom?
> {quote}
> To make it clear this is for the mainfunction background tasks not the init
>
> Its due to the way the cryptostack is designed: the CSM, cryptodriver and HSM/software lib are all state machines with jobs queues. If they are ordered top to bottom it means when new requests go through they will be processed the same tick/iteration . Otherwise if for example you do the cryptodriver malfunction first its actually dealing with the last iterations round of requests and to an end user this can look like lag and/or poor performance.
> {quote}Do we have any documentation to explain these？
> {quote}
> Yes this information is captured in the manual for the bsw modules in "RTA-Sec_Stack_Reference_Guide_EN.pdf" . There is alot of unhelpful information in the manual but if you look at the "Configuration Advice" and "Integration Advice" sections for each module there is a lot of useful information. Quick example from the CSM integration advice:
> ![[RH-16220-image-2026-06-04-11-28-05-466.png]]
> Example Path:
>
> C:\ETAS\RTA-CAR_12.11.0VCTCESR1pr1\Documents\RTA-BSW_12.11.0VCTCESR1pr1\RTA-Sec_Stack_Reference_Guide_EN.pdf
>
> Many thanks,
> Max

-------

> [!note]+ 2026-06-04 03:37 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-06-04 03:37 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Max_Sinclair|Max Sinclair]] ,
>
>     Why the ideal order of the crypto stack is from top to bottom?Do we have any documentation to explain these？For Crypto and HSM, it is necessary to initialize HSM before initializing Crypto, which is obviously a bottom-up approach；

-------

> [!note]+ 2026-06-03 13:27 · [[Max_Sinclair|Max Sinclair]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
> {quote}Please confirm whether CryIf_Init, Csm_Init, KeyM_Init, and SecOC_Init depend on the initialization of HSM and Crypto_Init.
> {quote}
> You can init the cryptostack in any order, as long as no requests go to SecOC or CSM e.g. crypto tasks, as that will cause errors until the full stack is init'd.
>
> It is worth mentioning that the main functions for the crypto stack should ideally be ordered from top to bottom i.e. SecOC, Csm, ... Cryptodriver. They cannot be run parallel must be run sequentially.
>
> Many thanks,
> Max

-------

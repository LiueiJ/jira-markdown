---
jira_key: RH-15993
jira_url: "https://rtahotline.etas.com/jira/browse/RH-15993"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
reporter: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
tags: [jira/comp/sec-cryptoauhsm3, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-05-09T11:05:09.000+0200"
updated: "2026-07-28T14:24:23.000+0200"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline,

I am working on RTA-CAR 12.11.0VCTCESR1pr3, I encountered the following error message;

![[RH-15993-image001.png]]

I have no problem with the same configuration on RTA-CAR 12.11.0VCTCESR1pr1;

SecOC_Tx and AES128_MacGen is MacGenerate;SecOC_Rx is Macerify;

They did use the same key, but why not? If it is necessary to re validate and redesign the implementation plan of the customer's project, please explain the necessity of this;

**Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

**ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-07-14 08:59 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
>
> Just to let you know, the solution for your request has been implemented and is now available in {*}RTA-CAR 12.11.0.VCTCESR1pr4{*}. Therefore, I will move this ticket to the 'Proposed Solution' state. If you have any further concerns or if the issue persists, please do not hesitate to reopen the ticket. Thank you!
> cc: [[Volker_Boehm|Volker Boehm]] , anh [[Phuong_Nguyen_Le|Phuong Nguyen Le]] , anh [[Cuong_Phan_Manh|Cuong Phan Manh]] 

-------

> [!note]+ 2026-06-24 12:25 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> As my understanding, planning for the updated version is 30/6 --> 1/7
>
> ![[RH-15993-image-2026-06-24-17-24-55-507.png]]
>
> ![[RH-15993-image-2026-06-24-17-25-36-143.png]]

-------

> [!note]+ 2026-06-17 11:39 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-06-02 13:21 · [[Volker_Boehm|Volker Boehm]]
> Planning etc. see linked ticket [ARCSEC-6940](https://jira.etas-dev.com/browse/ARCSEC-6940).

-------

> [!note]+ 2026-05-28 05:34 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Volker_Boehm|Volker Boehm]] , 
> Thank you for mapping your fix tickets. Could you share the timeline for this modification with the customer?

-------

> [!note]+ 2026-05-26 11:38 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Is there currently a timeline and plan for fixing this issue?

-------

> [!note]+ 2026-05-20 10:00 · [[Alex_Fargus|Alex Fargus]]
> Working:
> - RTA-CAR 12.11.0.VCTCESR1pr1
> - SecServices.CryptoStack.Crypto.rba_CryptoAuHSM3 4.4.0.alpha.2
>
> Not working 
> - RTA-CAR 12.11.0.VCTCESR1pr3
> - SecServices.CryptoStack.Crypto.rba_CryptoAuHSM3 6.0.0.pre.4
>
> - RTA-CAR 12.11.0.pr2
> - SecServices.CryptoStack.Crypto.rba_CryptoAuHSM3 6.0.0

-------

> [!note]+ 2026-05-20 09:32 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Volker_Boehm|Volker Boehm]] , Is there any update from your side?

-------

> [!note]+ 2026-05-19 07:40 · [[Steven_TANG|Steven TANG]]
> Hello [[Elvan_Caliskan|Elvan Caliskan]] , [[Jozsef_Fischer|Jozsef Fischer]] ,
>
> This feature is needed in VCTC project. Please help to implement and let us know the Alpha function ready time line.

-------

> [!note]+ 2026-05-18 08:35 · [[Jie_LIU|Jie LIU]]
> Dear level 3 experts,
>
> Since the customer timeline is very urgent, we need to raise this priority of this ticket. One crypto driver for different jobs with the same key may cause concurrent problem especially for SecOC, Tx and Rx may happen at the same time; Each job uses a separate key with the same value is also not a good solution because the key injection may lead to inconvenience and inconsistent problem. 
>
> After checking with customer, they refuse to accept the walk around as final solution.
>
> So please help to fix it to accept split crypto drivers using the same key.

-------

> [!note]+ 2026-05-18 08:34 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Elvan_Caliskan|Elvan Caliskan]] , [[Jozsef_Fischer|Jozsef Fischer]] ,
>
> Based on [[Junsheng_ZHANG|Junsheng ZHANG]] 's confirmation, I think we should implement the updated version of this feature.

-------

> [!note]+ 2026-05-18 04:23 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Elvan_Caliskan|Elvan Caliskan]], this SEC-CryptoAuHSM3 ticket requires an assignee. As the component lead for SEC-CryptoAuHSM3, please ensure the 'Level 3 Assignee' field is set the appropriate person that an handle this issue.

-------

> [!note]+ 2026-05-15 06:47 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
>     The customer currently believes that the HwCsp functionality should not affect the implementation of the normal solution, especially since we have already completed verification in the HSM without HwCsp functionality.
>
>     If we split it into multiple KeySlots, it will introduce more key injection steps and consistency risks. Unless there's a hardware limitation, it would be difficult for me to convince the customer.

-------

> [!note]+ 2026-05-13 05:59 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> Could you please confirm if your project requires this feature (using the same key across different HwCsp keystores)? If you consider this feature important, we can request an update from the development team.

-------

> [!note]+ 2026-05-13 05:46 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello anh [[Phuong_Nguyen_Le|Phuong Nguyen Le]] ,
>
> After discussed with HSM3 expert and [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> {*}New change{*}:
>
> + {+}Old version{+}: The ecy_hsm_Csai_HwCsp_LoadKey API supported bit masks, allowing a key to be loaded into multiple keystores simultaneously.
>
> + {+}New version{+}: The API has been changed; now each API call can only load a single keystore at a time.
>
> {*}Root cause{*}: [[Jozsef_Fischer|Jozsef Fischer]]: Due to {*}_the capacity limitations and deadlines_{*}, the development team has not yet been able to redesign the HwCsp manager in the Crypto module to support multiple API calls (N times) for all workspaces. if this is an important feature, and really needed to use the same key in different hwcsp key stores (again this will create separate RAM copy of the same key, so quite wastefull) then it can be requested from PO to be implemented
>
> {*}Solution{*}: there is 2 options, use 2 different keys, or use only a single driverOBject for both MacVerify and MacGenerate

-------

> [!note]+ 2026-05-12 16:05 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] :
>
> Can you help to summary what you discussed and agreed?
>
> This will help to avoid and reduce effort if the similar issue happen in future.

-------

> [!note]+ 2026-05-12 10:46 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> As discussed, you can follow the proposed solution and try to solve this problem. If you have any further questions, feel free to reopen it.

-------

> [!note]+ 2026-05-12 09:32 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-05-12 09:32 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
>     Does this mean that I cannot use the same key for MacGen and MacVerify?Why didn't PR1 have this restriction before?

-------

> [!note]+ 2026-05-12 09:22 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] , 
>
> We have some updated logic handling of this module (validation step) in **RTA-CAR 12.11.0VCTCESR1pr3**
>
> A job can only be routed to \{*}a single HwCsp driver object{*}. In your case, the SecOC Tx, SecOC Rx, and AES128 MacGen jobs are sharing the same key, causing a single key element to be associated with 3 driver objects simultaneously — which directly violates this principle.
>
> ![[RH-15993-image-2026-05-12-14-19-12-642.png]]
>
> ==> Each CryptoDriverObject using HwCsp must have its own dedicated HwCsp key element. Additional separate key elements must be created and each driver object must be assigned a distinct key element.

-------

> [!note]+ 2026-05-09 11:32 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> As shown in the figure below, the customer's configuration from CSM to Crypto is roughly as follows；The customer uses the same key for receiving and sending SecOC, and has also configured an AES128_MacGen as a verification for key injection；
>
> ![[RH-15993-image-2026-05-09-18-55-22-058.png]]
>
> I understand that this configuration may have some redundancy, but it does not affect normal use. Is it because CSS hardware properties require different keys to be used？

-------

---
jira_key: RH-16053
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16053"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
reporter: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
tags: [jira/comp/cycurhsm3, jira/comp/sec-cryptoauhsm3, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-05-15T06:43:11.000+0200"
updated: "2026-08-28T14:28:06.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline,

When the HSM is flashed, executing ecy_hsm_Mgmt_Reset and ecy_hsm_Mgmt_Configure will cause the HSM core to restart. This will invalidate all open sessions on the Host side, which in turn causes all DriverObjects in the rba_CryptoAuHSM3 protocol stack to become invalid.

**Fault Logic:**

In EcuM, the following functions are executed: Hsm_Init, OpenSessionForHsmFlash, and Crypto_Init.

- Hsm_Init: The standard initialization process for the HSM.
- OpenSessionForHsmFlash: Reserves a session for HSM self-update (Session/Job: 0).
- Crypto_Init: Performs OpenSession for the DriverObjects configured in rba_CryptoAuHSM3 (Session/Job: 1-7), along with the initialization of some variables and states.

In MainFunction, HSM self-update and Crypto functionalities are executed. When HSM self-update is performed:

1. The HSM uses Session 0 for self-update.
2. After the update is complete, ecy_hsm_Mgmt_Reset and ecy_hsm_Mgmt_Configure are executed to restart the HSM.
3. The Crypto protocol stack calls HSM services. Since all open sessions become invalid after the HSM restarts, an errorCode 0x80002C05 ecy_hsm_CSAI_ERR_SESSION_CLOSED is returned.

The current solution involves re-calling rba_CryptoAuHSM3_Prv_Session_Init (with no HwCSP functions currently enabled) before steps 2 and 3. This re-opens sessions for Crypto (Session/Job: 0-6).

I have some questions about this:

1. **Without HwCSP enabled:** Before the HSM upgrade, the session IDs stored in rba_CryptoAuHSM3_Prv_Session_ast are 1-7. After the upgrade, since no session is requested for the HSM upgrade anymore, the session IDs stored in rba_CryptoAuHSM3_Prv_Session_ast become 0-6. Could this cause misalignment for some variables corresponding to the Csm or Crypto protocol stack?
2. **With HwCSP enabled:**
  2.1. Since HwCSP sessions and regular sessions are handled in different functions, is it still necessary to call rba_CryptoAuHSM3_Prv_HwCsp_Init again to re-initialize HwCSP (ecy_hsm_Csai_HwCsp_Init + OpenSessionForHwCsp)? Also, please note that rba_CryptoAuHSM3_Prv_Session_Init will set all HwCSP sessions to 0xFFFFFFFF.
  2.2. If HwCSP sessions are re-opened, will it affect the current operation of CSS? Will there be an impact if the Session IDs do not correspond?

Additionally, Customer hopes that we can solve this problem within the Crypto protocol stack, for example, by adding configuration and callbacks to execute upgrades or session restarts.

**Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

**ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-08-28 14:28 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-07-27 08:12 · [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]]
> Just checked with Junsheng, this work around solution will be checked in next week. then we will feedback whether Lukas proposed work around solution could work and accepted by VCTC. 

-------

> [!note]+ 2026-07-26 18:53 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-07-03 10:31 · [[Lan_Tran|Lan Tran]]
> From [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]] : Currently the test work blocked by the RTA-SEC mismatch problem. so we can not try it and could not get the solution confirm from VCTC.

-------

> [!note]+ 2026-07-03 05:13 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] , [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]] 
>
> Are there any new updates from the customer?
>
> ![[RH-16053-image-2026-07-03-10-14-02-054.png]]
> ![[RH-16053-image-2026-07-03-10-14-02-054.png]]

-------

> [!note]+ 2026-07-01 15:09 · [[Volker_Boehm|Volker Boehm]]
> [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]],
>
> Please provide feedback if suggested workaround was accepted by customer.
>
> Thanks!

-------

> [!note]+ 2026-06-30 07:29 · [[Lukas_Riemenschneider|Lukas Riemenschneider]]
> Firstly, this is not a bug but a feature request.
>
> Besides, we communicated to the project that this can be mostly worked around by manually re-opening HSM sessions after reset. It remains the limitation that no new keys can be loaded into HwCsp after HSM update in the same reset cycle.
> We believe this is an acceptable limitation at this time.

-------

> [!note]+ 2026-06-30 06:07 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[Pedro_Duarte|Pedro Duarte]] ,
>
> Thanks for your information. Could you share your plan for this feature? Based on my check of the latest comment on the estimation ticket, the implementation is blocked on architecture concept clarification.
>
> ![[RH-16053-image-2026-06-30-11-05-21-681.png]]

-------

> [!note]+ 2026-06-22 14:45 · [[Pedro_Duarte|Pedro Duarte]]
> The tickets for the requested feature have been created and linked, closing this ticket.

-------

> [!note]+ 2026-06-10 13:03 · [[Lukas_Riemenschneider|Lukas Riemenschneider]]
> # Summary of the discussions
> ## Use-case
>
> VCTC is doing FOTA for updating firmware on their TC4x-based ECU.
> Even though they also update HSM over the air, they still require cryptographic features for SecOC and secure unlock during the update process.
> On TC4x, the HSM only has a single bank and thus needs to execute from RAM where most HSM features are not available.
> This can be mitigated for SecOC and secure unlock by utilizing the CSS using the Host-sided HwCsp feature for previously loaded keys.
> ## Stakeholder Requirement
>
> After the initial HSM startup, SecOC and secure unlock must always be usable by utilizing HwCsp which must not be unavailable even during the whole HSM update process incl. restarting the HSM afterwards.
> ## Problem
>
> After HSM update is completed, the sessions opened by the Crypto Driver are not valid anymore. A reinitialization also closes HwCsp sessions that must not be unavailable.
>
> During HSM startup and HwCsp Init, existing loaded keys are released and not available until loaded again.
> ## Proposed Crypto Driver Requirement
>
> The Crypto Driver shall support deinit+init or reinit of HSM sessions without preventing access to existing HwCsp sessions
> ## Proposed HSM Requirement
>
> The HSM shall support partial HwCsp initialization without affecting existing HwCsp session and loaded keys during HSM startup (i.e. after HSM soft reset)

-------

> [!note]+ 2026-06-08 10:34 · [[Lukas_Riemenschneider|Lukas Riemenschneider]]
> [[Volker_Boehm|Volker Boehm]]  and me are discussing solutions, there is no quick fix available

-------

> [!note]+ 2026-06-08 08:46 · [[Phuong_Nguyen_Le|Phuong Nguyen Le]]
> [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]] , [[Pedro_Duarte|Pedro Duarte]] : Do we have any update on this ticet?

-------

> [!note]+ 2026-05-28 11:33 · [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]]
> [[Volker_Boehm|Volker Boehm]] is in vacation now,  [[Sandra_Weigl|Sandra Weigl]] Please help to arrange Volker's proxy to support on this topic. 

-------

> [!note]+ 2026-05-26 12:43 · [[Pedro_Duarte|Pedro Duarte]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> The sequence described in my previous response is the currently supported behavior. The use case you are describing, maintaining Crypto availability across an HSM reset, is not supported by the current CryptoDriver implementation. Additionally, there is no guarantee from the CycurHSM3 side that HwCSP preserves its internal state across an HSM reset event.
>
> To move forward, you will need to request support for this feature to [[Volker_Boehm|Volker Boehm]], providing the exact use-case and expectations.

-------

> [!note]+ 2026-05-26 09:05 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Pedro_Duarte|Pedro Duarte]] ，
>
>     If I follow your process, I still have two issues: 1. When I call {{{}Crypto_Rb_Deinit{}}}, all CSM interfaces should become invalid, meaning I can no longer perform any CSM services, such as MacGen/Verify. If this is the case, the HwCsp functionality will be meaningless. 2. When I execute {{{}Crypto_Init{}}}, it calls {{{}ecy_hsm_Csai_HwCsp_Init{}}}, which releases all HwCspKeys. This will also cause the HwCsp functionality to become invalid.

-------

> [!note]+ 2026-05-25 11:24 · [[Pedro_Duarte|Pedro Duarte]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> Once Crypto_Rb_Deinit is called, Crypto services will no longer be available, so yes, this will affect Csm. However, since an HSM reset is being performed, no Crypto services can be expected to work during that window regardless.
>
> The following sequence allows Host HwCSP operations to remain available during the HSM flash procedure, while ensuring the Crypto internal state is properly maintained:
>
> `HSM self-update -> Crypto_Rb_Deinit -> HSM Reset -> Crypto_Init`

-------

> [!note]+ 2026-05-23 12:13 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Pedro_Duarte|Pedro Duarte]] ,
>
>     After I call Crypto_Rb_Deinit, can Csm still function normally? I think the status check of Crypto may result in errors;This will also result in SecOC being unavailable；

-------

> [!note]+ 2026-05-22 17:09 · [[Pedro_Duarte|Pedro Duarte]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> After clarification with the CycurHSM3 team: Host HwCSP operations can work during an HSM flash procedure, provided sessions are already open and keys are already loaded in the HwCSP keystore beforehand. However, operations that directly involve the HSM, such as ecy_hsm_Csai_HwCsp_LoadKey, cannot be performed during an HSM flash. Additionally, HwCSP behavior after an HSM reset is not currently guaranteed.
>
> With this in mind, the recommended approach is to call Crypto_Rb_Deinit before ecy_hsm_Mgmt_Reset is executed, while the HSM is still running and sessions can be cleanly closed.

-------

> [!note]+ 2026-05-22 04:59 · [[JSM_Service_Bot|JSM Service Bot]]
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-05-22 04:59 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Jozsef_Fischer|Jozsef Fischer]] ,[[Pedro_Duarte|Pedro Duarte]] ,
>
>     If the execution of Crypto_Rb_Deinit causes the failure of SecOC or other functions related to Crypto services, which is not what customers expect; The purpose of customers using hwcsp is to ensure that Crypto services such as SecOC are still available during the hsm upgrade process, ensuring that the entire power on cycle (including OTA updates to HSM) can use Crypto;

-------

> [!note]+ 2026-05-21 14:12 · [[Pedro_Duarte|Pedro Duarte]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> Please have a look at the answer above from Jozsef.

-------

> [!note]+ 2026-05-21 13:32 · [[Jozsef_Fischer|Jozsef Fischer]]
> Hello Junsheng,
>
> A partial session re-open is not recommended, since all HSM-side sessions are invalidated and other internal Crypto / HwCSP state may no longer be consistent. This applies especially when HwCSP is enabled, where regular and HwCSP sessions must be reinitialized consistently.
>
> Workaround handling:
>
> `Crypto_Rb_Deinit -> Crypto_Init`
>
> or an equivalent full stack restart after the HSM update.
>
>
> But even better option would be to deinit the cryptostack {color:#FF0000}*before*{color} the HSM update.
>
>
>
> Runtime HSM restart is currently not a supported use case for the Crypto stack. Incase HSM is restarted a full Cryptostack restart is expected for now. Even for the Deinit sequuence we expect that HSM sessions available and closed by Crypto stack. 
>
> Best regards,
> Jozsef

-------

> [!note]+ 2026-05-21 10:38 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Pedro_Duarte|Pedro Duarte]]
> As Christoph is out of office, could you please help to answer this ticket?
> Thank a lot,

-------

> [!note]+ 2026-05-18 05:31 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Phong_Tang_Dieu|Phong Tang Dieu]] ,
>
>     I believe this has nothing to do with the configuration of the RTA CAR, but rather with Crypto not considering the HSM Reset during the upgrade process；

-------

> [!note]+ 2026-05-18 03:59 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> [^Isolar(2).zip]

-------

> [!note]+ 2026-05-18 03:59 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> [^Isolar(2).zip]

-------

> [!note]+ 2026-05-15 11:48 · [[Phong_Tang_Dieu|Phong Tang Dieu]]
> Hi [[Christoph_Buttler|Christoph Buttler]]
> Could you please help to answer the questions?
> Thanks,
>
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> If possible, could you please share the configuration/project?
> Thanks,

-------

> [!note]+ 2026-05-15 11:45 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Christoph_Buttler|Christoph Buttler]], this SEC-Crypto ticket requires an assignee. As the component lead for SEC-Crypto, please ensure the 'Level 3 Assignee' field is set the appropriate person that an handle this issue.

-------

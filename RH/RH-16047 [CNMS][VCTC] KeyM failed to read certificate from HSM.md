---
jira_key: RH-16047
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16047"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: junsheng.zhang@bosch.com
reporter: junsheng.zhang@bosch.com
tags: [VNCNMS]
components: [SEC-KeyM]
fix-versions: []
epic: null
parent: null
created: "2026-05-14T12:10:11.000+0200"
updated: "2026-07-29T13:52:10.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-16047 [CNMS][VCTC] KeyM failed to read certificate from HSM

> [!jira] Closed · Critical · [[Junsheng_ZHANG|Junsheng ZHANG]] · 更新于 2026-07-29T13:52:10.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-16047)

> 标签：#jira/comp/sec-keym #jira/label/vncnms

## 描述

Hi hotline,

I found that there is a problem with the code logic of KeyM, which can cause KeyM to be unable to read certificates from HSM under certain conditions;

In KeyM_MainBackgroundFunction will call KeyM_Prv_AsyncParseCertificates to load Cert from hsm;But there is a logical error in the function;

![[RH-16047-image001.png]]

KeyM_Prv_AsyncParseCertificates will call Csm_CertificateParse and Csm_KeyElementGet; But at the moment of power on, Crypto did not complete initialization, so these two functions will not work for the first time; Regardless of whether Csm_Certificates Parse is successful or not, Csm_KeyElementGet will be executed;

Csm_CertificateParse-> CryIf_CertificateParse > rba_CryptoAuHSM3_CertificateParse> Crypto_Rb_CertificateParse-> Crypto_Prv_CertificateParse_Check-> Crypto_Prv_Check_IsModuleInitialized-> Crypto_Prv_InitState_Get to check Crypto_Prv_InitState_status_e status;

Csm_KeyElementGet-> CryIf_KeyElementGet-> rba_CryptoAuHSM3_KeyElementGet-> Crypto_KeyElementGet-> Crypto_Prv_KeyElementGet_Check-> Crypto_Prv_Check_IsModuleInitialized-> Crypto_Prv_InitState_Get

to check Crypto_Prv_InitState_status_e status;

Due to Crypto_Prv_InitState_status_e being updated on higher priority tasks, a situation may occur:

1. Crypto_Prv_InitState_status_e = CRYPTO_PRV_INITSTATE_INIT_PENDNG;
2. Csm_CertificateParse check failed,do nothing;
3. Crypto_Prv_InitState_status_e = CRYPTO_PRV_INITSTATE_INITIALIZED
4. Csm_KeyElementGet is executing normally

However, due to the abnormal execution of Csm_Certificate Parse, the status is incorrect and the certificate processing will not be executed again; In this case, the certificate will never be read again;

I think this is a bug, please help evaluate and provide a solution;

**Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com)

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)

**ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- mentions: [[RH-16029 [CNMS][VCTC] KeyM causes the HSM to return an ErrorCode]]

## 评论

> [!note]+ 2026-07-29 13:51 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> The issue code has already been fixed in the pr4 version.We can close the ticket now;

-------

> [!note]+ 2026-07-24 09:02 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[James_Haworth|James Haworth]] ,
>
> I have check the code generate by  RTA-CAR 12.11.0.VCTCESR1pr4; It have not fixed the issue;
>
> ![[RH-16047-image-2026-07-24-15-01-27-100.png]]

-------

> [!note]+ 2026-06-24 12:26 · [[James_Haworth|James Haworth]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]],
>
> I noticed this ticket has been reopened. To confirm the current status: the formal fix [ARCSEC-6938](https://jira.etas-dev.com/browse/ARCSEC-6938) is now in Acceptance and is planned for delivery in RTA-CAR 12.11.1 by 23 July, as Rohith confirmed on 2 June. Your temporary fix remains valid in the meantime.
>
> If there is an outstanding question or a new issue, please let me know. Otherwise I will move this ticket to Solution Proposed.
>
> Kind regards,
> James H

-------

> [!note]+ 2026-06-17 11:39 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-06-02 10:02 · [[Rohith_Gowdara_Prakash|Rohith Gowdara Prakash]]
> [[Junsheng_ZHANG|Junsheng ZHANG]] : Formal solution will be provided through https://jira.etas-dev.com/browse/ARCSEC-6938 which is planned to be delivered
> by 23.July (fly into RTA-CAR 12.11.1)  

-------

> [!note]+ 2026-06-02 04:16 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-06-02 04:16 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Rohith_Gowdara_Prakash|Rohith Gowdara Prakash]] ,
>
>     RH-16029 has been resolved, but RH-16047 still uses my modifications. I hope we can provide the customer with a formal solution;

-------

> [!note]+ 2026-05-25 17:45 · [[Rohith_Gowdara_Prakash|Rohith Gowdara Prakash]]
> [[Junsheng_ZHANG|Junsheng ZHANG]]
> From your image-2026-05-25-11-32-09-677.png, RH-16047 looks okie but RH-16029 needs changes in Crypto.
> Does your fix also resolves RH-16029?  Then you can use it as temporary fix, we are still analyzing  RH-16029.

-------

> [!note]+ 2026-05-25 05:32 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Rohith_Gowdara_Prakash|Rohith Gowdara Prakash]] ,
>
> Here is my fix for the issue. Is this acceptable?
>
> ![[RH-16047-image-2026-05-25-11-32-09-677.png]]

-------

> [!note]+ 2026-05-22 05:16 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Rohith_Gowdara_Prakash|Rohith Gowdara Prakash]] ，
>
>     So, please help me with a temporary fix that I can add to the customer's code to resolve this issue; also, please tell me the specific version and date of the fix, so I can confirm the plan and method of this fix with the project members.

-------

> [!note]+ 2026-05-21 15:58 · [[Rohith_Gowdara_Prakash|Rohith Gowdara Prakash]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]],[[James_Haworth|James Haworth]]
> If you look closely there is no explicit init guard also added in ARCSEC-1783, so 9.0.1 and later releases has not missed any changes.
> Csm_KeyElementGet provides the default value even if the Csm_CertificateParse is not successful and this is the ideal behavior of CSM stack.
> But, to fit into KeyM scenario we add the return value check for Csm_CertificateParse before calling Csm_KeyElementGet in 12.11.0.VCTCESR1.
> [[Balan_Arumugam|Balan Arumugam]] [[Volker_Boehm|Volker Boehm]][[Matthieu_Quesseveur|Matthieu Quesseveur]] I will create an epic for this change shortly.

-------

> [!note]+ 2026-05-19 11:12 · [[Balan_Arumugam|Balan Arumugam]]
> Hello Rohit,
>
> Could you please reply to the comment from James Haworth?
>
> [https://rtahotline.etas.com/jira/browse/RH-16047?focusedCommentId=684576&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-684576]

-------

> [!note]+ 2026-05-19 11:03 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Balan_Arumugam|Balan Arumugam]] [[James_Haworth|James Haworth]]，
>
> Currently, when initialization is complete, this status is set to CRYPTO_PRV_INITSTATE_INIT_PENDING, and it will only successfully initialize after several main function cycles.
>
>      ![[RH-16047-image-2026-05-19-17-01-24-891.png]]
>
> If you have a solution, could you please provide me with an example?

-------

> [!note]+ 2026-05-19 10:51 · [[James_Haworth|James Haworth]]
> Hi [[Balan_Arumugam|Balan Arumugam]],
>
> Thank you for the explanation. Understood; the design relies on CycurHSM returning an error for **Csm_KeyElementGet** when parsing has not completed, keeping KeyM in the retry loop. Looking at the switch in `KeyM_Prv_AsyncParseCertificates`: `CRYPTO_E_KEY_EMPTY`, `CRYPTO_E_KEY_NOT_AVAILABLE`, and `CRYPTO_E_KEY_READ_FAIL` all set `KEYM_CERTIFICATE_NOT_AVAILABLE` and advance past the certificate permanently, whereas `E_NOT_OK` falls to the default and retries. In the race scenario the reporter describes, which of these does CycurHSM return?
>
> Either way, [ARCSEC-1783](https://jira.etas-dev.com/browse/ARCSEC-1783) (your PR #499) eliminates this race by adding the init guard. The PR is merged to Bsw.SecServices main (2025-01-15) and the Jira fixVersion is AR45.9.0.0 (fly into RTA-CAR 12.6.0); however, the deployed KeyM 9.0.1 source on release/12.6.0 does not contain the init guard, and neither does KeyM 13.0.0 on release/12.10.0. The customer is on 12.11.0.VCTCESR1.
>
> Could you advise on:
>  # Whether the fix missed the 9.0.1 release cut, and which component version will include it?
>  # Whether it can be backported to the 12.11.0.VCTCESR1 line for this customer?
>
> Thanks,
> James H

-------

> [!note]+ 2026-05-19 10:37 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Balan_Arumugam|Balan Arumugam]] ,
>
>     I don't understand your response. Precisely because Csm_KeyElementGet cannot be called before Csm_CertificateParse succeeds, it's even more important to check the return value of Csm_CertificateParse;
>
>     The issue 16029 is completely unrelated to this problem.

-------

> [!note]+ 2026-05-18 19:22 · [[Balan_Arumugam|Balan Arumugam]]
> Hello James Haworth,
>
> As per my understanding, CycurHSM will definitely reports an error when Csm_KeyElementGet called before certificate parsing is done. So, if race happens between Csm_CertificateParse and Csm_KeyElementGet it will not work. KeyM could be able to read the certificate from HSM only after certificate parsing. this is reason why we will call Csm_CertificateParse with the return discarded.
>
>
>
> Best Regards,
>
> Arumugam Balan

-------

> [!note]+ 2026-05-18 18:54 · [[James_Haworth|James Haworth]]
> Hi [[Balan_Arumugam|Balan Arumugam]],
>
> The reporter (VCTC, RTA-CAR 12.11.0.VCTCESR1 per RH-16029) reports a race in KeyM_Prv_AsyncParseCertificates. At line 1566, Csm_CertificateParse is called with the return discarded; at line 1568, Csm_KeyElementGet runs unconditionally. Both gate on Crypto_Prv_Check_IsModuleInitialized(); if the state transitions to `CRYPTO_PRV_INITSTATE_INITIALIZED` between them, the `E_OK` path advances CertId_u16 for a cert whose HSM-side parse never ran. The pattern is present from 12.6.0 through 12.10.0.
>
> This is the same area as [ARCALM-2391](https://jira.etas-dev.com/browse/ARCALM-2391) / [ARCALM-5611](https://jira.etas-dev.com/browse/ARCALM-5611). [ARCSEC-1783](https://jira.etas-dev.com/browse/ARCSEC-1783) (PR #499, merged to main 2025-01-15) added the init check, but the fix is not in 12.10.0 or the customer's branch. Is this fix targeted for an upcoming release, and can it be backported to 12.11.0.VCTCESR1?
>
> I have advised the reporter to follow the §4.9.1 integration order (wait for Crypto_Rb_IsInitialized() before KeyM_Init). For context, RH-16029 (same reporter) is a separate issue on Csm_KeySetValid, with [[Christoph_Buttler|Christoph Buttler]] on SEC-Crypto.
>
> Thanks,
> James H

-------

> [!note]+ 2026-05-18 18:53 · [[James_Haworth|James Haworth]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]],
>
> The race condition you describe is confirmed by the source code. KeyM_Prv_AsyncParseCertificates discards the return of Csm_CertificateParse then calls Csm_KeyElementGet; both gate on `Crypto_Prv_InitState_status_e`, so if the state flips from `CRYPTO_PRV_INITSTATE_INIT_PENDING` to `CRYPTO_PRV_INITSTATE_INITIALIZED` between them, KeyM advances CertId_u16 for a certificate whose HSM-side parse never ran.
>
> The RTA-Sec Stack Reference Guide v12.10.0 §4.9.1 (p.152) requires that all CryptoStack components and NvM are fully initialised before KeyM_Init. The recommended integration sequence is:
>
>  # Crypto_Init, CryIf_Init, Csm_Init; schedule Crypto_MainFunction and wait for Crypto_Rb_IsInitialized() to return `TRUE`.
>  # NvM_ReadAll and wait for completion.
>  # KeyM_Init, then schedule KeyM_MainBackgroundFunction.
>
> Could you confirm whether the customer's integration already follows this sequence? The underlying code pattern is present through 12.10.0, so an upgrade alone does not resolve it. I am raising this with the development team in a separate comment.
>
> Kind regards,
> James H

-------

> [!note]+ 2026-05-15 10:01 · [[James_Haworth|James Haworth]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]],
>
> Thanks for the detailed analysis and screenshot. I'm cross-checking the KeyM_Prv_AsyncParseCertificates flow against the source on your branch and the prior tickets in this area, and will follow up here shortly with a full reply.
>
> Best regards,
> James H

-------

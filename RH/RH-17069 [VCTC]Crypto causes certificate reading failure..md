---
jira_key: RH-17069
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17069"
server: rtahotline
kind: hotline
type: Support
status: Waiting for Level 3
priority: Critical
project: RH
assignee: elvan.caliskan@etas.com
reporter: junsheng.zhang@bosch.com
tags: []
components: [SEC-CryptoAuHSM3]
fix-versions: []
epic: null
parent: null
created: "2026-08-30T06:33:15.000+0200"
updated: "2026-09-07T11:06:40.000+0200"
synced-at: "2026-09-08T01:46:06.261Z"
jira-orphaned: false
profile: Cariad
---

# RH-17069 [VCTC]Crypto causes certificate reading failure.

> [!jira] Waiting for Level 3 · Critical · [[Elvan_Caliskan|Elvan Caliskan]] · 更新于 2026-09-07T11:06:40.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17069)

> 标签：#jira/comp/sec-cryptoauhsm3

## 描述

Hi Hotline,

In the interface of RBA_CryptoAuHSM3 version 12.11pr5, I found a bug in the certificate parsing interface that causes KeyM to fail to read the certificate.

In KeyM, it calls KeyM_Prv_AsyncParseCertificates->Csm_CertificateParse to trigger certificate parsing. After that, the processing in rba_CryptoAuHSM3_Prv_DriverObject_ProcessJob is as follows:

rba_CryptoAuHSM3_Prv_DriverObject_ProcessJob

RBA_CRYPTOAUHSM3_PRV_CRYPTOPRIMITIVEIF_TRIGGER

->rba_CryptoAuHSM3_Prv_CertificateParse_Trigger

->ecy_hsm_Csai_GetTagTree

rba_CryptoAuHSM3_Prv_Session_PollStatus(session_pst);

->ecy_hsm_Mgmt_PollHandle

In a typical ecy_hsm_Csai_xx interface, there are two basic parameters: session and job. After executing the interface function, it assigns session to job; then, in the subsequent ecy_hsm_Mgmt_PollHandle, job is passed in for processing.

However, the ecy_hsm_Csai_GetTagTree function is special: it only has session and no job. This causes the session and job values not to match after the function completes, which results in ecy_hsm_Mgmt_PollHandle being unable to execute the correct job.

![[RH-17069-image001.png]]

Moreover, this leaves an invalid parameter errorCode in the HSM, causing the next time the HSM service is executed to report an error again.

Please assess and resolve this issue. It has a significant impact and risk to the customer’s current application. Also, please confirm whether there are other functions with similar problems in addition to affecting other services.

 **Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](https://www.etas.cn/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-09-07 11:06 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Elvan_Caliskan|Elvan Caliskan]] ,
>
> We only need to modify one line of code in this way; I think this would be better；
>
> ![[RH-17069-image-2026-09-07-17-05-33-717.png]]

-------

> [!note]+ 2026-09-03 14:52 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Elvan_Caliskan|Elvan Caliskan]] ,
>
> can you provide a answer for [[Junsheng_ZHANG|Junsheng ZHANG]] for the timeline fix, please?
>
> thx
>
> BR
> Christian

-------

> [!note]+ 2026-09-03 14:40 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-09-03 14:40 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Elvan_Caliskan|Elvan Caliskan]] ,
>
> Thank you very much for your proposal and your replies. The customer’s project will go into mass production soon—when can we get the fixed code? Is there a plan/schedule?

-------

> [!note]+ 2026-09-03 13:27 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] ,
>
> you can try out the preliminary fix which described by [[Elvan_Caliskan|Elvan Caliskan]] .
>
> Keep in mind that this fix is only provided for testing purposes and are **NOT** allowed for {*}production/series usage{*}.
>
> Any feedback welcome.
>
> thx
>
> BR
> Christian

-------

> [!note]+ 2026-09-03 12:40 · [[Elvan_Caliskan|Elvan Caliskan]]
> ![[RH-17069-2.png]] ![[RH-17069-1.png]]

-------

> [!note]+ 2026-09-03 12:35 · [[Elvan_Caliskan|Elvan Caliskan]]
> If you want to try it out before the official fix is released, this is the essential part in rba_CryptoAuHSM3_Prv_CertificateParse_Trigger() — the session handle has to be stored as job handle before the API call:
>
> jobHandle_u32 = RBA_CRYPTOAUHSM3_PRV_SESSION_GET_SESSION_HANDLE(session_pst);
> RBA_CRYPTOAUHSM3_PRV_SESSION_SET_JOB_HANDLE(session_pst, jobHandle_u32);
>
>
> Both ecy_hsm_Csai_GetPubkeyFromCert() and ecy_hsm_Csai_GetTagTree() are then called with jobHandle_u32. Please note this is a preliminary patch for verification only, it has not been through review yet.
>
> This is only the minimal change to verify the parse problem. The complete fix also covers ReleaseCertificate in KeyElementSet and initializes the job handle at session init, those parts belong together and will come with the official release.

-------

> [!note]+ 2026-09-03 12:30 · [[Elvan_Caliskan|Elvan Caliskan]]
> Hi [[Christian_Fuerst|Christian Fuerst]] and [[Junsheng_ZHANG|Junsheng ZHANG]] 
>
> I had a look at this, the bug is confirmed and you pointed at the right place in the code. While tracing it though, I found that the actual chain of events is a bit different from what it looks like at first.
>
> **Problem:**
>
> in the CycurHSM3 host driver every session based API does *phJob = hSession. So the job handle and the session handle are the same value, and ecy_hsm_Csai_GetTagTree() passes its first parameter on to Applet_Function() just like the session based APIs do. Passing the SessionHandle there is wrong on paper, but on its own it does not break anything. If we only swap it for the JobHandle, nothing changes.
>
> The real problem sits one level deeper. ecy_hsm_Csai_GetTagTree() and ecy_hsm_Csai_GetPubkeyFromCert() do not return a job handle. All other primitives get theirs through the phJob output parameter, and that way it ends up in their session automatically. CertificateParse is the only primitive without that return path, and it never stores the handle itself. But that field is exactly what gets polled: rba_CryptoAuHSM3_Prv_Session_PollStatus() reads the job handle from the session. After Crypto_Init it is still 0, so we end up polling a different session, which of course reports SUCCESS. The driver then thinks the job is done while the HSM is still working on it, and the certificate job never gets acknowledged. That matches what the customer describes.
>
> The reason this only shows up now is simple. Until we switched to parsing persistent certificates there was still a ecy_hsm_Csai_LoadKey() call before the parse, and that one set the sessions job handle as a side effect. Once that step was removed, the missing assignment became visible. So the bug has been in there for a while, it was just hidden.
>
> **Other affected functions:**
>
> [[Junsheng_ZHANG|Junsheng ZHANG]]  asked whether other functions have the same problem, so I went through the remaining primitives. There is one more: rba_CryptoAuHSM3_Prv_KeyElementSet_TriggerRelease() calls ecy_hsm_Csai_ReleaseCertificate(), which is also a job based API without a job handle return value, and it does not store the handle either. If the release runs on a session where no inject happened before, it works on a foreign handle in the same way. We are fixing that one together with the parse.
>
> Everything else is fine. All other primitives receive their job handle through the phJob output parameter, and for the multi step ones (Cipher, Aead) the state machine makes sure the start call always comes first.
>
> **Fix:**
>
> the trigger has to store the handle it starts the job with in the session itself. That means writing the session handle via RBA_CRYPTOAUHSM3_PRV_SESSION_SET_JOB_HANDLE before the API call, and calling both certificate APIs with that handle. Then PollStatus() asks about the same job that is actually running in the HSM. That is the same guarantee the phJob parameter gives us in all the other primitives, and it makes the call correct in terms of the API description at the same time. The same applies to the ReleaseCertificate call mentioned above.
>
> On top of that I would set jobHandle_u32 to ecy_hsm_CSAI_INVALID_JOB_HANDLE_VALUE during session init. It was the only field in the session struct without an explicit init value and ended up as 0 after startup, which is a valid handle pointing at someone else session. That does not fix anything by itself, but if some other place ever forgets to store its job handle, we get a clear ERR_INVALID_HANDLE instead of a silent poll on the wrong session.
>
> BR
> Elvan

-------

> [!note]+ 2026-09-03 09:54 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Is there any update?

-------

> [!note]+ 2026-08-31 08:52 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Elvan_Caliskan|Elvan Caliskan]], this SEC-CryptoAuHSM3 ticket requires an assignee. As the component lead for SEC-CryptoAuHSM3, please ensure that the 'Level 3 Assignee' field is set to the appropriate person that can handle this issue.

-------

> [!note]+ 2026-08-31 08:52 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Elvan_Caliskan|Elvan Caliskan]] ,
>
> can you have a look into this issue, please?
>
> It seems that there is a Bug where _ecy_hsm_Csai_GetTagTree()_ -API will be called with the sessionhandle instead of the expected JobHandle.
>
> If it is a confirmed Bug, then can you trigger the next steps to fix this bug, please?
>
> Thx
>
> BR
> Christian

-------

> [!note]+ 2026-08-31 08:49 · [[Christian_Fuerst|Christian Fuerst]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] 
>
> thx for pointing out this issue.
>
> You are correct the _ecy_hsm_Csai_GetTagTree()_ needs the JobHandle instead of the sessionhandle as shown in your screenshot, according to the API description.
>
> Can you try out to modify this part of the code and use the JobHandle, to see if it is then working as exepcted, please?
>
> Meanwhile I will try to get in touch with the L3 for further analysis.
>
> thx
>
> BR
> Christian

-------

> [!note]+ 2026-08-30 08:02 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Junsheng ZHANG. Your issue is set to "Critical" priority.
> Please ensure that there is a reasonable justification for this listed in the issue description, otherwise the priority may be reviewed and adjusted during triage.
> Kind regards

-------

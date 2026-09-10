---
jira_key: RH-16029
jira_url: "https://rtahotline.etas.com/jira/browse/RH-16029"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Critical
project: RH
assignee: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
reporter: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
tags: [jira/comp/sec-cryptoauhsm3, jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-05-13T08:41:10.000+0200"
updated: "2026-07-29T13:52:56.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

HI Hotline, 

 I found that Hsm returns an Error Code during debugging, and investigation revealed that it is caused by KeyM; 

 KeyM references intermediate and preset certificates from HSM KeySlot; 

 1.  In the background MainFunction of KeyM, the certificate will be parsed and KeyChangeFlag_ab will be changed to 1 

![[RH-16029-image001.png]] 

 2.When I call Csm_KeyElementSet for other key, KeyChangeFlag_ab will be changed to 1 several times; 

![[RH-16029-image002.png]] 

 3. And when I call Csm_KeySetValid,It will trigger ecy_hsm_Csai_WriteKeyToNvmKeyStore; Due to KeyChangeFlag_ab being set to 1, the certificate's Key will also trigger storage, but due to incorrect parameters, an error code will be returned; 

![[RH-16029-image003.png]] 

Blow picture is OK; 

![[RH-16029-image004.png]] 

 4.It will be clear which flag I trigger by Csm interface,but the flag of Cert Key will not; 

![[RH-16029-image005.png]] 

![[RH-16029-image006.png]] 

 So KeyM won't clear this flag, I think it's a bug, and this flag will be kept forever; 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](https://www.etas.cn)  

  ** ETAS – Empowering Tomorrow’s Automotive Software**

## 关联

- is mentioned in: [[RH-16047 [CNMS][VCTC] KeyM failed to read certificate from HSM]]

## 评论

> [!note]+ 2026-07-29 13:52 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> The issue code has already been fixed in the pr4 version.We can close the ticket now;Thank you very much for your support;

-------

> [!note]+ 2026-07-24 10:40 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hello all,
> After checking with the customer, we confirmed that the fix for this issue has already been implemented in {*}RTA-CAR 12.11.0.VCTCESR1pr4{*}. I have provided the plugin for this version.
>
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] , could you please verify the solution and close the ticket if the issue has been resolved? Otherwise, please let us know if you have any further concerns. Thank you!

-------

> [!note]+ 2026-07-24 09:45 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> I just uploaded the code generated from my PR4, and it didn’t modify this issue. How can I be sure that PR4 has already fixed it?

-------

> [!note]+ 2026-07-24 09:30 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> I checked the src code from **RTA-CAR 12.11.0.VCTCESR1pr4,** the solution for this issue has been {*}updated{*}. Kindly help me recheck it, if you have any concerns, you can contact me to analyze. Thank you!
>
> cc: anh [[Phuong_Nguyen_Le|Phuong Nguyen Le]] , anh [[Cuong_Phan_Manh|Cuong Phan Manh]] 
>
> ![[RH-16029-image-2026-07-24-14-29-25-242.png]]

-------

> [!note]+ 2026-07-24 09:12 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> [^rba_CryptoAuHSM3_Prv_KeyPersist-1.c]

-------

> [!note]+ 2026-07-24 09:12 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
> I have check the code of  RTA-CAR 12.11.0.VCTCESR1pr4;It is not same as the code you support before; 
>
> ![[RH-16029-image-2026-07-24-15-11-19-587.png]]

-------

> [!note]+ 2026-06-30 06:28 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] ,
>
> The bugfix is planned for inclusion in {*}AR45.14.2.0 GA (Jul 24){*}. If you have any concerns, please let us know and reopen this ticket. Thank you.
>
> ![[RH-16029-image-2026-06-30-11-27-43-572.png]]

-------

> [!note]+ 2026-06-17 11:39 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-05-28 10:39 · [[Pedro_Duarte|Pedro Duarte]]
> Hello [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]],
>
> Thank you for the feedback, a defect [ARCSEC-6944](https://jira.etas-dev.com/browse/ARCSEC-6944) has been created and linked to this ticket where this will be implemented.

-------

> [!note]+ 2026-05-28 08:54 · [[TANG_Steven_(ETAS-ECMXSF-CN)|Steven TANG]]
> Hello  Pedro Duarte:
>
> Just check with Junsheng Zhang, the walk around solution you provide is workable.
>
> Thanks a lot. 

-------

> [!note]+ 2026-05-25 11:04 · [[Pedro_Duarte|Pedro Duarte]]
> Hello [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> This looks like a bug on rba_CryptoAuHSM3 where **ecy_hsm_Csai_WriteKeyToNvmKeyStore** is triggered in a situation where it shouldn't because the actual key is not available in HSM RAM (Csm_KeyElementSet was not called).
>
> Instead of your fix, please try replacing the **rba_CryptoAuHSM3_Prv_KeyPersist.c** file by the one attached and let me know if it worked.
>
> [^rba_CryptoAuHSM3_Prv_KeyPersist.c]

-------

> [!note]+ 2026-05-25 05:31 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] ，
>
> Here is my fix for the issue. Is this acceptable?
>
> ![[RH-16029-image-2026-05-25-11-30-26-510.png]]

-------

> [!note]+ 2026-05-23 11:51 · [[JSM_Service_Bot|JSM Service Bot]]
> [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2026-05-23 11:51 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] ,
>
>     The errorCode is 0x80001201ecy_hsm_CSAI_ERR_INVALID_HANDLE;
>
>     The reason for the error is that the hKey is incorrect ；The root cause is that these two flags were not cleared, resulting in repeated writing in Crypto_MainFunction；

-------

> [!note]+ 2026-05-22 15:17 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]],
>
> Thank you for your patience, and apologies for the delay. 
>
> To help us move forward, could you capture the exact HSM error code returned when the certificate key persist fails? The error code is not visible in the screenshots you provided because the BSW flattens it to a generic **E_NOT_OK** before it reaches the Crypto layer.
>
> Best regards,
> Hritik

-------

> [!note]+ 2026-05-22 05:18 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] ,
>
>     This issue has gone unanswered for too long; can anyone else help resolve it?!!!

-------

> [!note]+ 2026-05-13 16:41 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi [[Christoph_Buttler|Christoph Buttler]], this SEC-Crypto ticket requires an assignee. As the component lead for SEC-Crypto, please ensure the 'Level 3 Assignee' field is set the appropriate person that an handle this issue.

-------

> [!note]+ 2026-05-13 16:39 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Christoph_Buttler|Christoph Buttler]], [[Elvan_Caliskan|Elvan Caliskan]],
>
> Customer (CNMS/VCTC, RTA-CAR {*}12.11.0.VCTCESR1{*}) reports that the HSM returns an error on every **Csm_KeySetValid** call. The root cause appears to be that **KeyM** background certificate parsing ({*}KeyM_Prv_AsyncParseCertificates{*}) calls **Crypto_Prv_KeyStorage_MarkKeyChanged** for the certificate key, setting the changed flag. On the next persist cycle, **Crypto_Prv_KeyStorage_StoreKeysInBlock** tries to persist the certificate key via {*}ecy_hsm_Csai_WriteKeyToNvmKeyStore{*}, which fails because certificate keys are not supported by this API. The block state becomes ERROR and the flag is never cleared, causing a permanent retry loop.
>
> The same code exists on {*}12.11.0.VCTCESR1pr4{*}.
>
> Could you please confirm whether this analysis is correct? Is there a workaround the customer can apply in the meantime? And could you let us know when a fix can be expected?
>
> Thanks,
> Hritik

-------

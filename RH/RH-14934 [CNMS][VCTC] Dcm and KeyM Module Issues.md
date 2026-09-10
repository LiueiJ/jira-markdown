---
jira_key: RH-14934
jira_url: "https://rtahotline.etas.com/jira/browse/RH-14934"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: High
project: RH
assignee: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
reporter: "[[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]"
tags: [jira/label/vncnms]
fix-versions: []
epic: null
parent: null
created: "2026-01-22T08:35:57.000+0100"
updated: "2026-04-22T11:37:33.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline,

1. Can the activation and deactivation of the interface for the validity period of the certificate be configured?

In the code, I saw the following interface for setting the validity period, But what are the enabling conditions for KEYM_TIMERCALLOUT_ENABLED?

![[RH-14934-image001.png]] ![[RH-14934-image002.png]]

Through searching the source code, we found that it is related to KeyMCertTimeBaseRef, but there is no relevant description in our documentation; StbM also does not support creating a separate TimeBase for mapping, it must be associated with Tsyn related modules; Another strange phenomenon is that the conditions for enabling KEYM_TIMERCALLOUT_ENABLED and KEYM_STBM_ENABLED in the source code are exactly the same, but the generated code is different;

![[RH-14934-image003.png]]

2. Does it support custom verification of specific Cert Elements in certificates? Is there any relevant documentation to guide me in assisting clients with configuration?

3. Does DCM's 29 service support the configuration of multiple certificate chains?

4. Does OCSP function support it? I found in the document that we only support one responder per certificate;

 **Junsheng ZHANG** 

Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

M +86 155 32928056 

[Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

[www.etas.cn](http://www.etas.cn/)  **

ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-04-22 11:37 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2026-04-07 18:48 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically moved to Solution Proposed.

-------

> [!note]+ 2026-03-24 04:04 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> Hi [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]] , as I mentioned in the previous response, if the customer does **not use** StbM to obtain the time, they can retrieve it via an external CallOut function ({*}KeyM_CertificateGetCurrentTimeCalloutFunc{*}).
>
> To enable this feature, please ensure that no reference to the StbM timer ({*}KeyMCertTimebasRef{*}) is configured. When RTA-CAR generates the code, the user can define their own logic within the **KeyM_CertificateGetCurrentTimeCalloutFunc** API to fetch the time from an external source. This API will be declared in the **KeyM_Externals.h** file.

-------

> [!note]+ 2026-03-23 03:03 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] ,
>
>     I have some additional questions about question 1. The customer just wants to no longer verify the validity period of the certificate, not use STBM；Do we support this feature？

-------

> [!note]+ 2026-03-20 13:36 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> {color:#de350b}*3. Does DCM's 29 service support the configuration of multiple certificate chains?*{color}
>
> Yes, DCM Service $29 supports the configuration of multiple certificate chains. This is achieved by defining multiple Authentication Connections in the DCM module, which reference distinct Certificate Profiles in the KeyM (Key Management) stack. During the authentication process, the appropriate chain is selected based on the Certificate Identifier or the Authentication Profile requested by the client.
>
>
>
> {color:#de350b}*4. Does OCSP function support it? I found in the document that we only support one responder per certificate.*{color}
>
> Our tool support OCSP function. The user can config the reference via KeyMRbCertOcspRef
>
> ![[RH-14934-image-2026-03-20-19-33-43-691.png]]
>
> Yes, KeyM will support only one responder certificate for each OCSP.
>
> ![[RH-14934-image-2026-03-20-19-36-42-902.png]]

-------

> [!note]+ 2026-03-20 07:07 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> {color:#de350b}*2. Does it support custom verification of specific Cert Elements in certificates? Is there any relevant documentation to guide me in assisting clients with configuration?*{color}
>
> {color:#172b4d}In case the customer asks for custom KeyM configuration, the tool provides the **KeyMCertificateCustomService** container in accordance with the AUTOSAR specification.{color}
>
> {color:#172b4d}![[RH-14934-image-2026-03-20-13-04-01-537.png]]{color}
>
>
>
> We only have the document which define all related information of Key Certificate Element, you can use it and configure your feature, you can find them in **"RTA-Sec_Stack_Reference_Guide_EN.pdf"**

-------

> [!note]+ 2026-03-20 07:00 · [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]]
> 1. {color:#de350b}*Can the activation and deactivation of the interface for the validity period of the certificate be configured?*{color}
>
> ![[RH-14934-image-2026-03-20-13-00-38-881.png]]
>
> {color:#172b4d}According to AUTOSAR, this field references **the StbM time.** If present, it retrieves the current time based on **the StbM** (StbMSynchronizedTimeBase must be configured); otherwise, it comes from **the external CallOut function** (KeyM_CertificateGetCurrentTimeCalloutFunc).{color}
>
> ![[RH-14934-image-2026-03-20-13-00-45-529.png]]
> ### ==> The {color:#de350b}KEYM_STBM_ENABLED{color} macro is set to {color:#de350b}TRUE {color}if at least one {color:#de350b}KeyMCertTimebaseRef{color} is referenced; otherwise, it is set to {color:#de350b}FALSE{color}
>
> {color:#172b4d}==> The KEYM_TIMERCALLOUT_ENABLED {color}macro is {color:#de350b}TRUE {color}unless at least one {color:#de350b}KeyMCertTimebaseRef{color} is referenced; otherwise, it is set to {color:#de350b}FALSE.{color}
> ![[RH-14934-image-2026-03-20-13-00-38-881.png]] ![[RH-14934-image-2026-03-20-13-00-45-529.png]]

-------

> [!note]+ 2026-03-19 09:35 · [[Su_Nguyen_Quoc|Su Nguyen Quoc]]
> Hi [[Khoa_Phan_Huynh_Dang|Khoa Phan Huynh Dang]] - please support as discussed.

-------

> [!note]+ 2026-03-11 17:58 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Kaiser_Marc_(ETAS-ECMESY3)|Marc Kaiser]],
>
> Please have a look at this CNMS ticket.
>
> Thanks,
>
> Hritik

-------

> [!note]+ 2026-01-28 13:55 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] 
>
> Is there any progress on this issue?

-------

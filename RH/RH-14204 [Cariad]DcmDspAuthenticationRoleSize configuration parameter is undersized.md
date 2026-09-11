---
jira_key: RH-14204
jira_url: "https://rtahotline.etas.com/jira/browse/RH-14204"
server: rtahotline
kind: hotline
type: Support
status: Closed
priority: Low
project: RH
assignee: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
reporter: "[[Junsheng_ZHANG|Junsheng ZHANG]]"
tags: [jira/comp/diagnostic-communication]
fix-versions: []
epic: null
parent: null
created: "2025-10-23T11:10:04.000+0200"
updated: "2026-03-23T10:35:37.000+0100"
synced-at: "2026-09-11T01:36:25.139Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Hi Hotline， 

 When configuring Service 29 in Dcm, I found that the maximum value for DcmDspAuthenticationRoleSize can only be set to 4. However, during actual testing, I discovered an issue；I use RTA CAR 12.7.0； 

![[RH-14204-image001.png]] 

In the function KeyM_Prv_x509ElementGet, in the code section shown in the figure below. I added test variables. According to the debug screenshot, we can see that RequiredBuffer_u32 is greater than CertElementDataLength, which will clearly result in returning KEYM_E_KEY_CERT_SIZE_MISMATCH. 

Based on the current constraints, I can only modify the maximum value definition of DcmDspAuthenticationRoleSize in Dcm_EcucParamDef.arxml to accommodate my certificate requirement of 20 bytes. The current limit of 4 bytes is insufficient for most real-world certificate use cases, and this adjustment is necessary to ensure proper functionality.  

![[RH-14204-image004.png]] 

![[RH-14204-image003.png]] 

The screenshot below shows the certificate I'm using. By reading the  **CN**  field with test variables, the results are consistent.  ** Is this issue a bug? Is my proposed modification reasonable? Could you help evaluate this problem?** 

![[RH-14204-image002.png]]![[RH-14204-image005.png]] 

 ** Junsheng ZHANG** 

 Cross Functional Regional Solution Field Management - Regional Solution Field Manager China 

 

 M +86 155 32928056 

 [Junsheng.ZHANG@bosch.com!mail_small.gif!](mailto:Junsheng.ZHANG@bosch.com) 

 

 ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS-ECM/XSF-CN 

 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 

 [www.etas.cn](http://www.etas.cn)   ** 

 

 ETAS – Empowering Tomorrow’s Automotive Software**

## 评论

> [!note]+ 2026-03-03 07:49 · [[Sobin_Peter|Sobin Peter]]
> [[Junsheng_ZHANG|Junsheng ZHANG]] 
>
> DcmAppl_GetCustomRole() cannot not extract roles from a stream of bytes(it basically don't have info to identify or locate it). The application software has to extract the roles and copy to the buffer when DcmAppl_GetCustomRole() is called.

-------

> [!note]+ 2026-03-02 08:31 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Sobin_Peter|Sobin Peter]] ,
>
>     The customer used the Nth byte out of 20 bytes as the Role; At present, it seems that we can only perform a shift in the DcmAppl_GetCustomRole() function, discarding the previous redundant elements and selecting the role specified by the customer；

-------

> [!note]+ 2026-02-19 13:55 · [[Sobin_Peter|Sobin Peter]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]] 
>
> Sorry for the confusion. Even if you enable DcmRbDspAauthenticationEnabledCustomRole, it can handle only up-to 4 bytes of role information.
>
> As per autosar, role information is only 4 bytes and the bit coded role assignment allows only 32 bits. As per my understanding the certificate element referenced in DcmDspAuthenticationRoleElementRef shall have only max of 4 bytes.
>
> Could you please recheck if you are referring to the right certificate element in DcmDspAuthenticationRoleElementRef ?
>
> I find it a bit unrealistic to have 20 bytes in the role element. This means 160 different roles are possible. could you check how many roles are defined for this project (like Development, aftersales etc as shown in the example from Autosar)
>
> ![[RH-14204-image-2026-02-19-14-12-34-867.png]]
>
>
> ![[RH-14204-image-2026-02-19-14-12-34-867.png]]

-------

> [!note]+ 2026-02-05 14:13 · [[Rohith_Gowdara_Prakash|Rohith Gowdara Prakash]]
> DCM should take care of this, not the responsibility of SEC-KEYM

-------

> [!note]+ 2026-02-04 18:05 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Raghuram_Telagamsetti|Raghuram Telagamsetti]],
>
> [[Junsheng_ZHANG|Junsheng ZHANG]] has reopened this ticket and rightly points out the inflexibility of the current access rights verification mechanism. Please confirm if this warrants a change or if there is another reason why it's done this way.
>
> Thanks,
>
> Hritik

-------

> [!note]+ 2026-01-30 03:43 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Raghuram_Telagamsetti|Raghuram Telagamsetti]] ,[[Hritik_Mehta|Hritik Mehta]] ,
>
>     During the functional verification process, I discovered another issue, so I had to reopen this problem；
>
>     By changing the DcmRbDspAauthenticationEnabledCustomRole configuration and integration code, it is possible to achieve a Role value greater than 4 bytes without reporting any errors；However, during the execution of the Dcm_Prv_CheckAccessRights() function, allowedRole_u32 only has 32 bits, and the length of the Dcm_CurrentRoleConn0_au8 array is only 4; This means that when conducting Role verification, we can only verify the first 4 bytes and cannot meet the customer's customized requirements;
>
> ![[RH-14204-image-2026-01-30-10-43-27-270.png]]

-------

> [!note]+ 2025-12-01 10:21 · [[JSM_Service_Bot|JSM Service Bot]]
> This issue has not received any response for 2 weeks and will now be automatically Closed.

-------

> [!note]+ 2025-11-17 09:38 · [[Raghuram_Telagamsetti|Raghuram Telagamsetti]]
> Hello [[Hritik_Mehta|Hritik Mehta]] 
>
> I am not sure if the below suggestion will benefit or not. Please check if it helps. Other than this I could not see any other alternatives from DCM perspective.
>
> Instead of directly reading role information from the certificate's CN field (which exceeds the 4-byte AUTOSAR limit), DCM provides a Custom Role Configuration mechanism. This can be enabled by setting the configuration parameter DcmRbDspAuthenticationEnableCustomRole to TRUE, which activates the DCM_CFG_AUTH_CUSTOM_ROLE_ENABLED flag. When enabled, this feature allows the system to bypass the standard certificate element reading and instead obtain role information through the application callback function DcmAppl_GetCustomRole(). This callback provides the flexibility to implement custom logic and provide the role information.
>
> Thanks, Raghu

-------

> [!note]+ 2025-11-11 19:00 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Balan_Arumugam|Balan Arumugam]] / [[Raghuram_Telagamsetti|Raghuram Telagamsetti]] 
>
> Please have a look at the latest comment by [[Junsheng_ZHANG|Junsheng ZHANG]]. They've mentioned that the OID is mandated by Xiaomi.
>
> Do you have any suggestions on how to limit the value length within the certificate for that OID to be no more than 4 bytes or can they explore alternate mechanisms to transmit the role information? Perhaps using a different diagnostic service or encoding the necessary data in the payload?
>
> Thanks,
>
> Hritik

-------

> [!note]+ 2025-11-11 04:39 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] ,
>
>     I'm sorry for replying to you so late；I have two more questions to ask you；
>
>     1.This Objectid is specified by the customer and cannot be changed; Do we have a way to solve this problem？
>
>     2.The extension content in my existing certificate seems to be no less than 4 bytes. What should I do？
>
> ![[RH-14204-image-2025-11-11-11-39-03-726.png]]

-------

> [!note]+ 2025-11-04 18:22 · [[Hritik_Mehta|Hritik Mehta]]
> Hi [[Junsheng_ZHANG|Junsheng ZHANG]],
>
> In the X.520 directory attribute OID namespace, 2.5.4.3 is the standardised OID for CN. It seems “EcuDiagnosticsRoles” element is currently mapped to the certificate’s CN (OID 2.5.4.3), which is ~20 bytes:
>
> ![[RH-14204-image-2025-11-04-17-12-52-381.png]]
>
> To resolve this, the role and whitelist element IDs need to point to certificate fields that carry (≤4 byte) values not CN or other variable-length fields. Please correct the intended OIDs/locations for role/whitelist from your certificate profile. 
>
> Best regards, 
>
> Hritik

-------

> [!note]+ 2025-11-04 13:28 · [[Balan_Arumugam|Balan Arumugam]]
> Hello Hritik Mehta,
>
> It seems like customer is referring a wrong certificate element in Dcm configuration or they would have configured certificate element Object Id wrongly. There is nothing to fix in the code. Configuration has to be fixed.
>
> Thanks,
>
> Arumugam Balan

-------

> [!note]+ 2025-11-04 13:27 · [[Volker_Boehm|Volker Boehm]]
> [[Balan_Arumugam|Balan Arumugam]],
>
> Could you please check with the colleagues and provide an answer to the points from [[Hritik_Mehta|Hritik Mehta]]?
>
>
>
> Thanks,
>
> Volker

-------

> [!note]+ 2025-11-04 13:16 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi KeyM Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-11-04 13:16 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Diagnostic Communication Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-11-04 13:14 · [[Hritik_Mehta|Hritik Mehta]]
> ```
> RTA-CAR 12.7.0{noformat}
> Hi [[Volker_Boehm|Volker Boehm]],
>
> Please have a look at this ticket and the latest comment by [[Raghuram_Telagamsetti|Raghuram Telagamsetti]].
>  * *AUTOSAR 7.4.2.10.5* constrains role/whitelist element sizes and DCM enforces this by hard-coding {*}DCM_CERT_ELEMENT_CHILD_MAX_LENGTH = 4{*}.
>  * Debugging indicates *Dcm_Cfg_AuthConnection_acst[...].roleCertElementId_u16* is mapped to the certificate’s CN (“{_}XCD@2023010100000001{_}”, ~20 bytes) instead of the role element, causing KeyM to return {*}KEYM_E_KEY_CERT_SIZE_MISMATCH{*}, which DCM translates to {*}DCM_E_CERTIFICATEVERIFICATIONFAILEDINVALIDCONTENT{*}.
>  * Proposed fix: correct the certificate element ID mapping for role/whitelist to the appropriate KeyM-supported elements.
>
> Please help clarify whether KeyM configuration handles this.
>
> Thanks,
>
> Hritik

-------

> [!note]+ 2025-11-04 04:01 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Hritik_Mehta|Hritik Mehta]] 
>
>     Is there an expert from KeyM who can answer this question？

-------

> [!note]+ 2025-11-03 07:02 · [[Raghuram_Telagamsetti|Raghuram Telagamsetti]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]]
>
> According to AUTOSAR specification 7.4.2.10.5 (as shown in the below image), authentication white lists/roles are constructed from elements with specific size constraints.
>
> ![[RH-14204-image-2025-11-03-11-30-40-954.png]]
> The DCM implementation correctly adheres to this specification by hard-coding DCM_CERT_ELEMENT_CHILD_MAX_LENGTH to 4 bytes, establishing a maximum buffer size for reading 
> certificate elements (role/whitelist) via KeyM APIs (KeyM_CertElementGetFirst and KeyM_CertElementGetNext). 
>
> Based on the debug screenshots, I think there is an issue in the configuration of certificate element ID mapping, where Dcm_Cfg_AuthConnection_acst[authConnectionIndex_u16].roleCertElementId_u16 is
> incorrectly pointing to the certificate's CN field instead of the actual role element. The CN field contains the certificate identifier "XCD@2023010100000001" which is 20 bytes in length, 
> significantly exceeding the 4-byte buffer limitation.
>
> When the DCM attempts to read this oversized element through KeyM_CertElementGet, KeyM returns KEYM_E_KEY_CERT_SIZE_MISMATCH, which is subsequently translated to DCM_E_CERTIFICATEVERIFICATIONFAILEDINVALIDCONTENT by the DCM module. 
>
> The solution requires correcting the certificate element ID configuration to ensure that role and all whitelist element IDs point to the appropriate certificate elements.
>
> I am not sure whether KeyM configuration handles this.
>
> Thanks, Raghu

-------

> [!note]+ 2025-10-31 09:02 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> At present, I do not have the actual certificate used by Cariad, but if the CN value in the customer's certificate exceeds 4 bytes, this problem may also occur; We cannot demand that customers' certificates must comply with specification; So, please help evaluate the solution;

-------

> [!note]+ 2025-10-31 08:58 · [[JSM_Service_Bot|JSM Service Bot]]
> [[Junsheng_ZHANG|Junsheng ZHANG]], the comment you've just made is internal. Please note that internal comments do not transition an issue to 'Waiting for Level 2'.

-------

> [!note]+ 2025-10-31 08:58 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Raghuram_Telagamsetti|Raghuram Telagamsetti]] ,
>
>     I would like to explain my debugging results to you again；
>
>    As we discussed in our previous meeting, I checked the order of calls：
>
> Dcm_ReadRoleAndAvailableWhitelists -> Dcm_ReadCertElement -> Dcm_ReadCertElementChild
>
> ![[RH-14204-image-2025-10-31-15-49-42-538.png]]
>
>
>
> KeyM_CertElementGet ->KeyM_Prv_CertElementGet  and  Result_u8 = KEYM_E_KEY_CERT_SIZE_MISMATCH
>
> ![[RH-14204-image-2025-10-31-15-55-14-393.png]]
>
> Next, call the KeyM_Prv_x509ElementGet function；
>
> ![[RH-14204-image-2025-10-31-15-55-55-333.png]]
>
> Here are the test variables I added，So the problem is still that RequiredBuffer_u32 > *CertElementDataLength results in a return value of KEYM_E_KEY_CERT_SIZE_MISMATCH (4)
>
> ![[RH-14204-image-2025-10-31-15-57-26-926.png]]

-------

> [!note]+ 2025-10-30 05:46 · [[Raghuram_Telagamsetti|Raghuram Telagamsetti]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] 
>
> **DcmDspAuthenticationRoleSize** cannot be modified as the role size is limited to maximum of 4 bytes as per Autosar Requirement. So I want to understand the error being reported by KeyM is at which stage.
>
> Can you please help to schedule a call in-order to get more clarity.
>
> Thanks, Raghu

-------

> [!note]+ 2025-10-29 07:50 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Raghuram_Telagamsetti|Raghuram Telagamsetti]] ,
>
>     There was no report of **KEYM_E_KEY_CERT_SIZE_MISMATCH** error. However, without modifying DCM_CERT_ELEMENT_CHILD_MAX_LENGTH, it will report a KEYM_SERVICE_ID_CERT_ELEMENT_GET error;

-------

> [!note]+ 2025-10-29 06:56 · [[Raghuram_Telagamsetti|Raghuram Telagamsetti]]
> Hello [[Junsheng_ZHANG|Junsheng ZHANG]] 
>
> May I know at which stage KeyM reported **KEYM_E_KEY_CERT_SIZE_MISMATCH** error. Is it while reading the role information or whitelist information from certificate ?
>
> Thanks, Raghu

-------

> [!note]+ 2025-10-27 02:52 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Hi [[Balan_Arumugam|Balan Arumugam]] ,
>
>      I think KeyM is fine, the problem lies in the Dcm module; As I previously described, modifying DcmDspAauthenticationRoleSize and DCM_CERT_ELEMENT_CHILD_MAX_LENGTH can solve the problem; So it may be due to the interface provided by Dcm being too small,And these values cannot be modified normally, I need to modify the code or paramdef file;

-------

> [!note]+ 2025-10-26 18:43 · [[Balan_Arumugam|Balan Arumugam]]
> Hello Mehta,
>
> There is no problem in the KeyM, User provide certificate element data length is less than the configured size hence KeyM is reporting **KEYM_E_KEY_CERT_SIZE_MISMATCH** error as per the requirement id SWS_KeyM_00063 and SWS_KeyM_00127.
>
> User can be able to overcome the below issue by two ways:
>
> 1. Reduce the “CN” certificate element “KeyMCertificateElementMaxLength” to ‘4’.
> 1. Increase CertElementDataLength to 20 while calling KeyM_CertElementGet api.
>
> Thank,
>
> Arumugam

-------

> [!note]+ 2025-10-24 18:22 · [[JSM_Service_Bot|JSM Service Bot]]
> Hi Diagnostic Communication Support Owner. This ticket requires an assignee.

-------

> [!note]+ 2025-10-24 18:20 · [[Hritik_Mehta|Hritik Mehta]]
> ```
> RTA-CAR 12.7.0{noformat}
> Hi [[Raghuram_Telagamsetti|Raghuram Telagamsetti]] / [[Volker_Boehm|Volker Boehm]],
>
> The customer is facing a buffer size issue in Dcm/KeyM integration during *0x29* authentication.
>
> Our BSW (Dcm/KeyM integration) calls *KeyM_Prv_x509ElementGet* to retrieve the CN with *CertElementDataLength* set to {*}4{*}.
>  * In the function, *RequiredBuffer_u32* is set to *RawDataLength_u32* (~20 bytes for the CN).
>  * The provided buffer ({*}CertElementDataLength=4{*}) is too small, causing  *KEYM_E_KEY_CERT_SIZE_MISMATCH* when {*}RequiredBuffer_u32 > *CertElementDataLength{*}.
>
> The issue seems to be unrelated to *DcmDspAuthenticationRoleSize* (limited to 1..4 bytes by AUTOSAR spec). The role field is a UDS 0x29 on-wire parameter, independent of certificate fields like CN. The failure is due to the integration using a fixed 4-byte buffer, which is insufficient for retrieving a ~20-byte CN.
>
> Please confirm if there is a known issue in the buffer size handling in the integration when fetching certificate elements with KeyM_Prv_x509ElementGet?
>
> Thanks,
>
> Hritik

-------

> [!note]+ 2025-10-24 12:00 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> I found that during debugging, it is necessary to manually change DCMcERT-ELEMENT_CILD_SAX_LENGTH to 20 in order to complete the entire process correctly；This can make RequiredBuffer_u32 less than * CertElementDataLength；
>
> ![[RH-14204-image-2025-10-24-18-00-31-054.png]]

-------

> [!note]+ 2025-10-23 12:19 · [[Junsheng_ZHANG|Junsheng ZHANG]]
> Current project details for reference
>
>
> [^20_Software_TC4_29Test.zip]

-------

---
jira_key: ARC-12575
jira_url: "https://jira.etas-dev.com/browse/ARC-12575"
server: etas
kind: motivation
type: Need (Subtask)
status: On Hold
priority: High
project: ARC
assignee: ec82abt
reporter: mas1yok
tags: [CEA2.0, PI-25.4_Prep, SEC]
components: []
fix-versions: []
epic: null
parent: "[[ARC-9902 VCTC : VW CEA2.0 (CDCU,LDCU,RDCU & RearDCU)]]"
created: "2025-09-04T07:22:04.000+0000"
updated: "2026-08-31T05:02:39.000+0000"
synced-at: "2026-09-08T01:46:40.034Z"
jira-orphaned: true
profile: CEA2.0 Needs
---

# ARC-12575 Server-Client support for TLS 1.3 (Incl. PSK feature)

> [!jira] On Hold · High · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] · 更新于 2026-08-31T05:02:39.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-12575)

> 标签：#jira/label/cea20 #jira/label/pi-254_prep #jira/label/sec

## 描述

**Cipher suite requirements.**

Symmetric cipher suites define the AEAD algorithm and hash algorithm for use with HKDF. Naming Convention: CipherSuite TLS_AEAD_hash = value; 

TLS1.3 can support multiple cipher suites, which, according to General Security requirements, should only support the following:

![[ARC-12575-image-2025-09-04-15-21-24-084.png]]

Based on the CSGR, the TLS_AES_128_GCM_SHA256 algorithm is recommended as a priority. 

Deadline for demonstration of Sever-Client working version at VCTC : 30 Nov 2025

## 关联

- is contained in: [[RTAXIP-3209 [ETCN Customer PI Planning] Dec 2025]]
- fulfills: [[ARCREL-68 Cariad - 01]]
- is satisfied by: [[ARC-12811 [Eth-Sec] TLS1.3 server functionality (incl. PSK) - Prototype]]
- is satisfied by: [[ARC-13349 [Eth-Sec] Support for pre-shared key (PSK) in TLS1.3 client - Prototype]]
- is satisfied by: [[ARC-13390 TLS1.3 server support with Pre-Shared Key (PSK)]]
- is satisfied by: [[ARC-13392 Pre-Shared Key (PSK) in TLS1.3 client]]

## 评论

> [!note]+ 2026-08-31 05:01 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> latest Info : CARIAD has de-scoped the TLS 1.3 for CEA 2.0 .  Changed the status to 'On Hold' . 
>
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  fyi

-------

> [!note]+ 2026-05-06 08:12 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> NOTE: Initially customer requested 4 cipher suites:
> - TLS_AES_128_GCM_SHA256 (Value: 0x1301)
> - TLS_AES_256_GCM_SHA384 (Value: 0x1302)
> - TLS_AES_128_CCM_SHA256 (Value: 0x1304)
> - TLS_AES_128_CCM_8_SHA256 (Value: 0x1305)
>
> However it was descoped to ONLY 1 at the later stage.
>
> In https://jira.etas-dev.com/browse/ARC-760 we implemented all four primitives on Client Side
> In https://jira.etas-dev.com/browse/ARC-13390 we implemented only TLS_AES_128_GCM_SHA256 (Value: 0x1301) on Server Side with Pre-shared Key Exchange.

-------

> [!note]+ 2025-12-30 06:40 · [[ZHANG_Junsheng_(ETAS-ECMXSF-CN)|ZHANG Junsheng (ETAS-ECM/XSF-CN)]]
> Hi [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] ,[[CHEN_Yingge_(ETAS-ECMXSF-CN)|CHEN Yingge (ETAS-ECM/XSF-CN)]] ,[[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] 
>
>     In RTA-CAR 12.11.0VCTCESR1pr1 version, HSM3 does not support CRYPTO_AEADDECRYPT and AES256, but these features are required in the customer TLS requirements;
>
> ![[ARC-12575-image-2025-12-30-14-39-53-146.png]]

-------

> [!note]+ 2025-10-16 14:47 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]] 
>
> Capabilities ARC-12811 and ARC-13349 for Demo/Prototype are now refined and planned in PI25.04.
>
> Scope for demo / prototype:
>  * TLS 1.3 PSK-only key exchange feature for Cipher suite TLS_AES_128_GCM_SHA256
>  * TLS 1.3 Handshake between Server and Client.
>  * Secure PDU data transfer utilizing the session key established during the handshake.
>
> TImeline: PI25.04 IP sprint (Demonstration by Beg'Feb26)
>
> The feature is considerably large and Nov'25 is not a reasonable option.
>
> Followup tickets for full release is addressed with ARC-13390 and ARC-13392, to be taken up in the upcoming PIs in 2026.

-------

> [!note]+ 2025-10-16 09:14 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]] Actually customer uses our CycurHSM3 on TC499 which will be released on end of Nov, 2025. For TLS1.3, the protocol part is handed on host side is OK. But the related CSM Jobs shall finally be needed from rba_CryptoHSM driver.

-------

> [!note]+ 2025-10-16 08:23 · [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] From Security side only CCL ( CycurLib) solution can be planned as CCM is currently only supported in CycurLib. CycurHSM 2/3 is out of scope. Will this meet your expectation.

-------

> [!note]+ 2025-10-09 04:00 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]]  Thanks for the summary. So we need another Capability ticket for TLS 1.3 Client support 
>  * PSK feature adaption on TLS1.3 Client.
>
> [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] fyi.

-------

> [!note]+ 2025-10-08 07:09 · [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]]
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]][[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> On the first level analysis :
> 1. For the demonstrator, I dont think HSM is need. We can do it for CCL ( Software Library)
> 2. The priority Cipher is  TLS_AES_128_GCM_SHA256
> 3. For this Cipher , I had a short discussion with Sven, for SecServices the needed algorithms for the Cipher  TLS_AES_128_GCM_SHA256 using CCL is already supported.
> 4. As per the request (comment 4 from LIU) PSK feature is required for both Client and Server
> 5. Current support for Client is only Certifiacte based,
>
> To do [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> 6. So  estimate is needed for 
>    a) PSK feature adaption on TLS1.3 Client.
>    b) A TLS1.3 Server with PSK feature.

-------

> [!note]+ 2025-10-06 10:06 · [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]]
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] It looks like you are handling the analysis for this Need based on the updates to ARC-12811. Please comment if you want any support from AAA team refining the need.

-------

> [!note]+ 2025-09-29 06:46 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]  do you think the information from [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]  is good enough ? this feature is critical for VW CEA 2.0 project and customer is expecting the solution by December'2025. Could you please help analyze this feature and provide plans for supporting it. Many thanks
>
> [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]] fyi 

-------

> [!note]+ 2025-09-26 08:30 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] 
>
> The requirement from customer is put in parent ticket with below links:
>
> [^0_TLS_Specification_v3.0_20250904_cn.pdf]
>
> [^0_TLS_Specification_v3.0_20250904_tr_en.docx]
>
> In summary, customer wants to apply tls1.3 on SomeIP services. 
>
> Since the ECU is both service provider and consumer for different services, they need both Tls1.3 server and client feature.
>
> By the way, they only need PSK feature, and certificate verification is not needed.

-------

> [!note]+ 2025-09-24 14:26 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]  could you please follow-up on the below queries. thanks 
>
> [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]] [[JI_Jiaqi_(ETAS-ECMXSF-CN)|JI Jiaqi (ETAS-ECM/XSF-CN)]] fyi

-------

> [!note]+ 2025-09-24 08:50 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] What is exactly the use case from the customer and what they like to verify? If TLS1.3 is used for example for a charging ECU, then only the TLS client feature is needed within the ECU. The TLS server is running in the charging station itself.
>
> For verification typically the same setup is used. The DUT is the ECU itself and the TLS server is running on the test setup itself (e.g. the Test PC, in the CanOE simulation or on a Raspberry Pi.

-------

> [!note]+ 2025-09-24 06:59 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> **Hotline Link:** [https://rtahotline.etas.com/jira/projects/RH/queues/issue/RH-13943]
>
> **Background:** Based on customer requirements, RTA-CAR needs to support the server and Client functions of TLS1.3, but currently we only support the Client function; Additionally, it is necessary to support DID to enable TLS functionality
>
> **Root cause:** There are currently no plans to support the server feature of TLS1.3
>
> **Impact of the problem:** The lack of server functionality will affect the verification of TLS1.3 functionality
>
> {*}Mitigation Required (Propose Needs how to solve the problem):{*}The client functionality needs to be verified for the time being. If the product team cannot support these features, we will have to manually modify the code；DID requirements need to be reconfirmed with the customer
>
> [[Mukherji_Arup_(ETAS-ECMXPC-Fe3)|Mukherji Arup (ETAS-ECM/XPC-Fe3)]]  we discussed this topic in our last meeting. any udpates? 
>
>
>
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]  this is imp. topic for VW for their CEA2.0 . can you please support.  
> Thanks both

-------

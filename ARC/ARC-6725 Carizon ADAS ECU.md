---
jira_key: ARC-6725
jira_url: "https://jira.etas-dev.com/browse/ARC-6725"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: but9fe
reporter: ec82abt
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2024-09-09T09:35:07.000+0000"
updated: "2025-08-26T06:58:52.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-6725 Carizon ADAS ECU

> [!jira] Accepted ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2025-08-26T06:58:52.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-6725)

## 描述

Carizon is a [joint venture of Cariad and Horizon Robotics](https://carnewschina.com/2023/12/08/vws-cariad-and-horizon-robotics-set-up-a-joint-venture-carizon-to-develop-autonomous-driving-system/) with focus on autonomous driving (AD) and located in Beijing, China.

The customer project (based on RTA-CAR 12.3.1) needs a CryptoDriver for CycurHSM SDK, which have the same CSAI as CycurHSM3.

 

For now the use cases which shall be supported are related to Secure Diagnosis and include UDS service $27 (Secure Access) and $29 (Authentication). To support this services the following cryptographic primitives are relevant:

- AES 128 ECB Enc
- AES 128 CBC Enc
- ECDSA 256 Verify
- SHA2-256
- RNG

and the following APIs from CycurHSM SDK have to be used for it:

- 27 ecy_hsm_Csai_CloseSessionAsync()
- 28 ecy_hsm_Csai_CloseSessionSync()
- 91 ecy_hsm_Csai_OpenSession() : ecy_hsm_csai_session.h
- 93 ecy_hsm_Csai_PollHandle() : ecy_hsm_csai_job.h
- 187 ecy_hsm_Csai_WaitForHandle() : ecy_hsm_csai_job.h
- 79 ecy_hsm_Csai_InjectKey() : ecy_hsm_csai_keys.h
- 149-156 ecy_hsm_Csai_SignVerify() related several functions

 

Customer would like to use certificates through crypto driver, especially to read the stored certificate, parse it and get the public key for verification. The following APIs from CycurHSM SDK have to be used for it:

- ecy_hsm_Csai_ParseCertificate
- ecy_hsm_Csai_GetPubkeyFromCert

- ecy_hsm_Csai_ReleaseCertificate
- ecy_hsm_Csai_InjectCertificate (lower priority because customer compromised to inject it directly through CycurHSM CSAI interfaces)

 

 

**Milestones**:

- B sample release in 19th of November, 2024 (VW China requested to have a solution completely based on HSM)
- TRNG / SecOC support is requested to provide at E11/2024
- C sample release E12/2024
- SoP 11/2025

Request is to provide CryptoDriver latest two weeks before release date.

 

contact person for snapshot delivery: [[HU_Cher_(ETAS-ECMXSF-CN)|HU Cher (ETAS-ECM/XSF-CN)]].

## 评论

> [!note]+ 2024-09-09 09:39 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] Can you please review the information and correct it in case something is wrong. Please update as well the concrete project name in the Summary.

-------

> [!note]+ 2024-09-09 09:38 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> Requested Delivery Date for CryptoDriver is not feasible as the development plan is to have it for RTA-CAR 12.x in maturity for RA in 12/2024.

-------

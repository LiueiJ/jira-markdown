---
jira_key: ARC-7685
jira_url: "https://jira.etas-dev.com/browse/ARC-7685"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: bal9yok
reporter: bal9yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2024-10-18T07:09:15.000+0000"
updated: "2026-01-15T16:54:43.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-7685 ENVISON - BMS Ford FNV2

> [!jira] Canceled ·  · [[Baldini_Luca_(ETAS-ECMXPC-Yok2)|Baldini Luca (ETAS-ECM/XPC-Yok2)]] · 更新于 2026-01-15T16:54:43.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-7685)

## 描述

- ECU: BMS, SOP is in 2027
- End Customer: Ford USA, platform: FNV2
- ETCN customer: ENVISION- T1 who supply BMS ECU to Jiangling Ford (JV between Ford and China local OEM)-> supply BMS to Ford USA.
- Car is PHEV
- ETCN sold CP to ENVISION 2 years ago

 

Quesions: 

- Question 1: OTA need to develop according to Ford spec.
- Ford USA nominate to use Vector FBL , maybe this is change for us
- If they need to update CP to be V4.4 for full CP stack (based on your mail, not all, some stack to be updated)
- IF ETAS global had experience on OTA (Ford had a file to say about how to develop OTA, can refer to Vector case)

## 评论

> [!note]+ 2024-10-18 07:10 · [[Baldini_Luca_(ETAS-ECMXPC-Yok2)|Baldini Luca (ETAS-ECM/XPC-Yok2)]]
> [Sivavarman Suresh (ETAS/CFO)]
>  * The BMS (Battery Management System) module on the Ford FNV2 platform currently supports OTA.
>  ** Needs to comply with Ford Specification C.15
>  ** Allows update of Software and Firmware
>  ** The OTA Flashing is done via OVTP and will not need to update to SWDL if is a carry over or an extension
>  ** Need to confirm memory type and network type for communication with BMS (communication assumption CAN/CANFD)
>  ** ETAS RTA can support dual stage flashing (Application + FBL) which is what I think you requested feedback on your first email
>  ** Needs to comply with OTA Security Specifications: VDOC095705
>  ** Question for the customer: Will the BMS require OTA update for both APP and FBL?
>  ** Question for the customer:  What is the ASIL rating for the the BMS module?
>  ** Question for the customer: Are there any specific requirements for the FBL?
>
>
>  * In terms of HSM:
>  * The only requirement Ford specifies is that: HSMs are hardened, tamper-resistant hardware devices that strengthen encryption practices by generating keys, encrypting, and decrypting data, and creating a verifying digital signature.
>  * My assumption here would be that the BSM module will be subject to HSM restrictions and may require CMA (Can Message Authentication) via Ford generated keys
>  * Question for the customer: Will BMS module be subject to CMA and encrypted keys?
>  * Overall, the BMS module will need to comply with Ford Cyber Assurance C.10 for the US market
>
>
>  * For the Ford FNOS, I have copies of the FNOS checklist that Vector has prepared for Ford tier 1 Suppliers.  However, I do not believe ETAS has one right now.  But this will be required as per the Ford process.
>
>
>  * I have attached all relevant specifications I can find here [https://sites.inside-share4.bosch.com/sites/037360/08580/Documents/Forms/AllItems.aspx?RootFolder=%2Fsites%2F037360%2F08580%2FDocuments%2FSupport%20Documentation%2FB01%5FOEM%5FSpecifications%2FFord%2FFNV2] 
>
>
>  * I would like to have more information on what vehicle platforms the Ford China BMS will be sold in the US market.

-------

---
jira_key: ARC-16353
jira_url: "https://jira.etas-dev.com/browse/ARC-16353"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-05-25T02:24:42.000+0000"
updated: "2026-08-07T01:58:13.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-16353 CAEA - VW Global Project

> [!jira] Canceled ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-08-07T01:58:13.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-16353)

## 描述

Chinese Tier-1 supplier, **CAEA**, Supporting Global Audi project. T 

**For Audi:**

- **Project:** iSMLS (SAS)
- **Platform:** Audi PPE platform
- **Chip:** S32K342EHT0MPAST
- **Compiler version:** NXP-GCC V10.2-1782
- **Functional safety:** ASIL-D

**VW Spec list summarized by CAEA :** [大众GEN4文件清单表格20251219更新.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/785841/785841_%E5%A4%A7%E4%BC%97GEN4%E6%96%87%E4%BB%B6%E6%B8%85%E5%8D%95%E8%A1%A8%E6%A0%BC20251219%E6%9B%B4%E6%96%B0.xlsx)

**VW Specs are shared in this location :** [ CAEA-VW](https://bosch.sharepoint.com/:f:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/CAEA-VW?csf=1&web=1&e=aiWPPh)

**Project information sheet**  [ECM_CN_CustomerName_AUTOSAR_Classic_Requirements_V14_EN 20260526.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/786716/786716_ECM_CN_CustomerName_AUTOSAR_Classic_Requirements_V14_EN+20260526.xlsx)

^**SOR** [0G0N52BACYWA-E-NCR-20260526$新零件SOR（协议栈）.docx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/786717/786717_0G0N52BACYWA-E-NCR-20260526%24%E6%96%B0%E9%9B%B6%E4%BB%B6SOR%EF%BC%88%E5%8D%8F%E8%AE%AE%E6%A0%88%EF%BC%89.docx)^

## 关联

- relates to: [[RTAXIP-3756 [RTA-RIP][CAEA][VW] SMLS S32K311/S32K342 Customer ECU]]

## 评论

> [!note]+ 2026-08-07 01:57 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] 
>
> We LOST the business. EB won the contract on the final round.  
>  # EB's price is significantly lower than us.
>  # EB offered 3 years free M&S 
>  # To reduce the timeline risk ( Project completion End .of August) CAEA decided to go with EB ( EB is their existing customer for this CAEA team and used EB tools in their previous projects.)
>
> It was a tough competition with EB.  we move on to the next opp.  I will close this ticket .
>
> Thanks all for the support. 

-------

> [!note]+ 2026-07-27 03:32 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> We will submit our bidding today to CAEA. 
>
> [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] did PF do any GAP analysis based on the shared specs ? 

-------

> [!note]+ 2026-07-21 21:24 · [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] do you have an update on this project?

-------

> [!note]+ 2026-05-29 09:31 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Sollazzo_Giuseppe_(ETAS-ECMENG-EMW)|Sollazzo Giuseppe (ETAS-ECM/ENG-EMW)]] 
>  * The CAEA‑VW project acquisition is currently in progress, and a technical review meeting with the customer is scheduled for next Tuesday (2nd June).
>  * Business value: 3.5 ~ 4 mCNY (still negotiating)
>  * Currently we are competing with Vector for this project. CAEA is currently using Vector DaVinci. Vector seems to convince CAEA to continue with Vector sighting low risk.
>  * The customer expects a **GAP analysis report** based on the shared QLAH specifications, along with timelines for addressing any identified gaps - in order to mitigate any project risks.
>  * No gap analysis has been conducted yet; this activity will be initiated with the AAA team. [[Chandran_Girish_(ETAS-ECMXPC-Yok1)|Chandran Girish (ETAS-ECM/XPC-Yok1)]] [[Fargus_Alex_(MSETA)|Fargus Alex (MS/ETA)]] fyi
>  * From what we gathered [^0G0N52BACYWA-E-NCR-20260526$新零件SOR（协议栈）_zh2en_transResult.docx] [^ECM_CN_CustomerName_AUTOSAR_Classic_Requirements_V14_EN 20260526.xlsx]project primarily focuses on **Diag, CAN/CAN‑FD, CAN ISO‑TP, and NM features, FBL development** with limited support required for **HSM integration (NXP) & support during SSW integration (** SSW integration will be done by customer, ETAS need to provide support for the CP part **)**
>  * Based on prior experience (BBM and recent ECARX projects), there is confidence that our RTA-CAR is largely compliant with VW’s QLAH specifications in these areas. We will communicate the same to the customer. If we win this bidding - We will ask customer to start with the latest RTA-CAR - 12.10 / 12.11. 
>  * However, the customer has an {*}aggressive timeline{*}:
>  ** Nomination: 30/06/2026 (we are likely to know before that if ETAS has acquired the project or not.)
>  ** A-sample: 30/08/2026
>  ** B-sample: 30/10/2026
>  * Risk we need to mitigate: {color:#de350b}Any identified gaps (from the Analysis report or during Project development) or bugs will need to be addressed within this tight schedule.{color}
>
> If we win this project, we will need PF support in meeting the project goals. 
>
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] [[Jain_Vihitha_(MSEMS-ETAS)|Jain Vihitha (MS/EMS-ETAS)]] [[Burn_Alexander_(ETAS-ECMXPC-Yok1)|Burn Alexander (ETAS-ECM/XPC-Yok1)]] xil2szh [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] 

-------

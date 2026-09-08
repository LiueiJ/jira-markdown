---
jira_key: RTAXIP-3309
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3309"
server: etas
kind: motivation
type: Change Request
status: Closed
priority: High
project: RTAXIP
assignee: puy1hc
reporter: aiu2sgh
tags: [XIP-Local-Accq]
components: []
fix-versions: [EcarX-bip-cdeh-SemiDriveE36XXghs-1290-R1911]
epic: null
parent: null
created: "2026-03-13T03:35:04.000+0000"
updated: "2026-08-10T02:56:52.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-3309 [OppEcarX-bip]_cde-SemiDrive E3620-1290

> [!jira] Closed · High · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] · 更新于 2026-08-10T02:56:52.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3309)

> 标签：#jira/label/xip-local-accq

## 描述

1. **Motivation** 
  - TNS (€): The offered <to be updated>
  - Opp status: Open
  - Motivation type: Single ECU

- - Customer: EcarX
  - OEM: VW
  - Silicon target: E3620, E3650
  - Crypto Provider: None

- - The new opportunity for **BIP/OTA integration on SemiDrive E3620**
  - Opportunity - project information colleting: [EcarX_SemiDriveE36XXGHS_Project_information_V1.0_EN-1.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/756546/756546_EcarX_SemiDriveE36XXGHS_Project_information_V1.0_EN-1.xlsx)

1. **Scoping & Timeline**
  1. Scoping
    - BIP **SemiDrive E3620**
    - FBL/OTA: **DoIP Client + TpGw + LIN** is ** **only** ** scope of FBL.
    - SOW: [ETAS AUTOSAR for EcarX SemiDriveE36XXGHS E111 SOW V05.pdf!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/762321/762321_ETAS+AUTOSAR+for+EcarX+SemiDriveE36XXGHS+E111+SOW+V05.pdf), sent on 23. Mar (email: [RE ECARX会议纪要.msg!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/762326/762326_RE+ECARX%E4%BC%9A%E8%AE%AE%E7%BA%AA%E8%A6%81.msg))
  2. Timeline is below
    - Position 0040: RTA-OS Porting Service (OS ports)
 - Schedule
Milestone: Multi cores Preview release, Delivery date: &#91;April 6th, 2026&#93;
 - Milestone: Multi cores Final release, Delivery date: &#91;May 26th, 2026&#93;
Content: Multi cores Pre-release RTA-OS port, meeting requirements in Section 3, released according to ETAS Final release process.
    - Position 0050: Basic Integration Package (BIP)
 - BIP on EVB：T + 4w
 - BIP on Customer ECU：T + 8w
    - Position 0060: OTA/Bootloader Software Integration Package（OTA/FBL工程）
 - OTA/FBL: T + 9w
 - Perfromance: TpGw over CAN: latency 5ms, TpGw over LILN: latency 5ms
    - T: when nominated, Or contract signed.**{**}
2. **Dependency**
  - Earliest start after the **first OS port pre-review on** **04.05.2026** **=> shifted to 15.Apr**
3. **Project team:**

- - Nguyen Minh Tuan (MS/ETA-Hub-CN) - Developer
  - Pham Huu Ky (MS/EPS11-SWC) - Developer
  - Nguyen Le Phuong (MS/ETA-Hub-CN) - Solution lead
  - Nguyen Quoc Su - Delivery Lead
  - FENG Tom (ETAS-ECM/XSF-CN) - PjM
Current updates:

- - The team already started to BIP-Integration for SemiDriveE36XX wo OS port
  - Waiting Os port by mid/Apr

1. **Preparation for BIP Integration**
  - (from Tan Yang) Quick aligned:
    - EcarX will use E3620B + GHS 2022.1.4
2. - - OS will be available as preview mid-of-Apr
For VN: I can take **SemiDrive EvaluationBoard E3620P** hardware where VN can start project after E3620B OS preview available by configure chi variant E3620B.
    - For Shanghai: after OS preview for E3620B + GHS 2022.1.4 is available, will setup remote at Shanghai where Shanghai team can also use it.
3. **Communication:**

- - Opp ticket: [https://jira.etas-dev.com/browse/RTAXIP-3309](https://jira.etas-dev.com/browse/RTAXIP-3309)
  - Instant talk on teams here: [[Opp-BIP] ECARX Hongqi cockpit project (E3620)](https://teams.microsoft.com/l/channel/19%3A7216426bfa8247f69bcc2c947f39eafa%40thread.tacv2/%5BOpp-BIP%5D%20ECARX%20Hongqi%20cockpit%20project%20(E3620)?groupId=28c76bdb-6d94-4275-b359-365e4f9fe8b2&tenantId=0ae51e19-07c8-4e4b-bb6d-648ee58410f4)

## 关联

- satisfies: [[RTAXIP-3316 [RTA‑BIP] BIP for SemiDrive E3620P on RTA-CAR 12.9.0]]

## 评论

> [!note]+ 2026-04-07 00:19 · [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]
> Hi [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] 
>  # BIP scope was changed as TpGW is added:  [Tanyang]yes TpGW is added in SOW v06 as our scope
>  ** note: the SOW is not officially accepted by customer with a response confirmation
>  ** RISK: even LOI received with price indicated by sales, the price is current been argue by Darren for discount and terms which is not mutual agreed between ETAS and EcarX.
>  # DoIP Client:
>  ** the DoIP client is not required for the current project for Hongqi E111, therefore agreed with customer DoIP Client is out of scope for BIP
>  ** info: it's only required to be supported in RTA-CAR by end of 2026. (https://jira.etas-dev.com/browse/ARC-15269 )

-------

> [!note]+ 2026-04-02 13:08 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] , [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]] , [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]] , [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] 
>
> After checking the latest SOW at [https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000029653_PJ_ECM_ECARX_Autosar_CP_E3620_3650_RTL9071_/01_Draft/00_Start/10_Offer/ETAS AUTOSAR for EcarX SemiDriveE36XXGHS E111 SOW V06.pdf,](https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000029653_PJ_ECM_ECARX_Autosar_CP_E3620_3650_RTL9071_/01_Draft/00_Start/10_Offer/ETAS%20AUTOSAR%20for%20EcarX%20SemiDriveE36XXGHS%20E111%20SOW%20V06.pdf), there are some open point:
>  # BIP scope was changed as TpGW is added
>  ** ![[RTAXIP-3309-image-2026-04-02-20-03-49-554.png]]
>  # DoIP Client is requested --> {color:#de350b}*RISK: This feature will not ready in RTA-CAR until E09/2026* {color}as [[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]  shared expected date for this NEED is E09/2026 (in ARC-15269)
>
> Please help to clarify these points! 
>
> Is this SOW applicable for this ECARX project?

-------

> [!note]+ 2026-03-26 06:42 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Please review/move to CCN, thanks! [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] , [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] 

-------

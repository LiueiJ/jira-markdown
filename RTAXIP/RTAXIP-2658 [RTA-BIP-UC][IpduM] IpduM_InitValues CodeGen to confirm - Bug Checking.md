---
jira_key: RTAXIP-2658
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-2658"
server: etas
kind: motivation
type: Story
status: Open
priority: Low
project: RTAXIP
assignee: ""
reporter: "[[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/rta-bip-rh]
fix-versions: [RTA-BIP-cdes-tc397tk-1210, RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2025-10-28T11:45:49.000+0000"
updated: "2026-07-27T02:25:53.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

#### 1. **Motivation**

- **Context**: This NEED originates from customer project **Cariad** and hotline ticket &#91;RH-13446&#93;. The issue was observed in RTA-CAR 12.6 and persists in 12.7.
- **Use-Case support**:
  - BIP includes IpduM as part of its baseline feature set. Customers like Cariad use BIP as a starting point to import their own CAN matrix and configure multiplexing.
  - This issue is a **generic IpduM bug**, not limited to Cariad. Any customer using multiplexed CAN messages in BIP will face ECU reset during startup.
  - Fixing this in BIP ensures a stable baseline and prevents propagation of known defects into customer projects, aligning with BIP’s purpose as a validated reference integration package.
- **Problem**: In **IpduM_InitValues**, the index of IpduM_TxSubParts_acst is generated incorrectly due to inconsistent sorting logic:
  - IpduM_getTxDynSubPartList() sorts dynamic segments by shortName.
  - IpduM_getTxInitDynPartList() preserves ARXML order. This mismatch causes overlapping IDs and invalid memory writes during buffer initialization, leading to ECU resets.
- **Impact**:
  - **Developers** face runtime crashes during initialization.
  - **Testers** cannot validate multiplexed CAN message scenarios reliably.
  - **Stakeholders** risk project delays and increased support costs.
- **Urgency**: Without fixing this, projects using IpduM multiplexing will encounter critical runtime errors, blocking SOP timelines.

#### 2. **Proposed Change**

- Update requirement documents to specify deterministic ordering for dynamic segments.
- Validate changes with regression tests for multiplexed CAN messages.
- Update User Manual and configuration guidelines to reflect deterministic initialization behavior.

#### 3. **Impact Analysis with Confirmation**

Area
Description
Impact

Requirement
Will new requirements be added or existing ones updated?
Yes

Design
Will architecture or interface definitions change?
Yes

Configuration/

Integration
Will new parameters or software/ templates be introduced?
Yes

Testing
Will new test cases be needed or regression testing impacted?
Yes

Documentation
Will user guides or onboarding materials be updated?
Yes

Toolchain / CI
Will automation scripts or CI pipelines be affected?
Possible

Stakeholders
Will this improve delivery or collaboration with partners?
Yes

Compliance
Will this help meet internal/external process standards or audit readiness?
Yes

#### ✅ Definition of Done (DoD)

- Requirement and design documents reviewed and approved.
- Software will be updated and verified.
- Regression tests executed for IpduM multiplexing scenarios.
- User Manual updated with configuration and troubleshooting guidance.

#### 🔍 **Workaround Until Fix ([ARCCOM-8476](https://jira.etas-dev.com/browse/ARCCOM-8476))**

- **Fix planned in RTA-BSW 12.9.0** (Defect tracking: [ARCCOM-8476](https://jira.etas-dev.com/browse/ARCCOM-8476)).
- Temporary workaround implemented in **ConfGen**:
  - Customization ensures consistent sequence between IpduM_getTxDynSubPartList() and IpduM_getTxInitDynPartList().
  - Patch available in RTA_CONF_GEN_Installer_12.6.0_CN_IPDUM_workaround_07_25_pr_pw.zip.
  - Limitation: Works only up to 9999 segments.
- Customers should apply this workaround until official fix is delivered.

**Reference**: Hotline Ticket [RH-13446](https://rtahotline.etas.com/jira/browse/RH-13446). (attached exported [RH-13446.pdf!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/656948/656948_RH-13446.pdf))

## 评论

> [!note]+ 2026-07-17 07:58 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] We don't have Caraid project and target board here. Since BIP has IpduM feature, could you please verify it in BIP?

-------

> [!note]+ 2026-07-16 02:15 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] , can you help to veriffy this bug with CARIAD project?
>
> Check if RTA-CAR 12.11 fixed it or not?

-------

> [!note]+ 2026-04-08 02:50 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> Low priority for now. 
>
> We need to check it with BIP 12.10 later 

-------

> [!note]+ 2026-03-24 14:01 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> [RH-13446](https://rtahotline.etas.com/jira/browse/RH-13446) Defect fixed on 12.10.0 --> [https://jira.etas-dev.com/browse/ARCCOM-8476]
> We need to validate: RTAXIP-2658
>
> jie.liu8@etas.com , phuong.nguyenle@vn.bosch.com: please review priority for CNN. 

-------

> [!note]+ 2025-10-29 07:26 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Thanks [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]] - I definitely agreed with you.
>
> I'm trying to make some good BIP_NEEDs ticket examples from a real project hotline issue.

-------

> [!note]+ 2025-10-29 07:08 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Aligned with [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]], 
>
>
> BIP_NEEDs confirmation:
>  * changed {color:#4c9aff}NEEDs_seed{color} to {color:#4c9aff}BIP_NEEDs{color}

-------

> [!note]+ 2025-10-29 06:36 · [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]]
> Hi [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] , issue found by us is always better than found by customers. So please plan to add this feature into BIP. 
>
> Yes, it's clear enough. Make BIP as a continuous iteration baseline needs more features.

-------

> [!note]+ 2025-10-29 06:27 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Thanks [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]] to make the motivation more concrete.
>
> I documented the use-case that we need to support under BIP, could you please confirm or address if any gaps.
>
> {*}Use-Case Suppport justification{*}:
>  * BIP includes IpduM as part of its baseline feature set. Customers like Cariad use BIP as a starting point to import their own CAN matrix and configure multiplexing.
>  * This issue is a {*}generic IpduM bug{*}, not limited to Cariad. Any customer using multiplexed CAN messages in BIP will face ECU reset during startup.
>  * Fixing this in BIP ensures a stable baseline and prevents propagation of known defects into customer projects, aligning with BIP’s purpose as a validated reference integration package.
>
>
>
> Action plan,
>  # BIP_NEEDs confirmation
>  # Updated the BIP NEEDs ticket
>  # plan to next release RTA-BIP-cdes-tc397tk-1290
>
> Hi [[ZHANG_Cong_(ETAS-ECMXSF-CN)|ZHANG Cong (ETAS-ECM/XSF-CN)]] , [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]: could you please review /share if this BIP NEEDs ticket is clear enough motivation/ impact/ priority?

-------

> [!note]+ 2025-10-29 05:51 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]
> Hi，[[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] 
>
> I don't agree the analysis. Although this issue is identified in Cariad, but BIP still support IpduM feature. This issue is confirmed as IpduM bug. Customer will take BIP as their baseline project to import their own Can Matrix. That's also the meaning of BIP. We need to identify all possible issues customer will encounter in the future and to make sure all bug fixes not missing, we need to confirm they are fixed in product.

-------

> [!note]+ 2025-10-28 12:23 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Hi [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]],
>
> I checked a motivation of one rat-hotline ticket from the dashboard that you suggested.
> And the team seeing that it should not scope of BIP improvement. 
> Would you please share your view-point if it's difference for this ticket from the team analysis?
>
> {*}Second point{*}, could you please hints if any hotline ticket should follow up to verify in BIP improvement? 
> Many hotline tickets, lack of content to suggest for BIP improvement - hard to figure it out.
>
> {*}Third point{*}, we last sync, we agreed that customer project members to raise NEEDs ticket for BIP improvement. Could you please create BIP NEEDs ticket then we will follow hotline ticket - that's case might more efficiency.
>
> **How do you think?** 
> | Needs from Sisi: |
> - features list &bugsfixed (hotline): high demands
> [Dashboard - RTA Hotline](https://rtahotline.etas.com/jira/secure/Dashboard.jspa?selectPageId=18001)
> e.g. RH-13446, RH-12551
> TODO: to check and plan to test again for next RCAR 1280|

-------

> [!note]+ 2025-10-28 12:03 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> #### **Impact Analysis with Confirmation**
>
>
> NEEDs ticket [Cariad][IpduM] IpduM_InitValues CodeGen Issue is **invalid for BIP NEEDs ticket**
> ### **Reason for Invalidity**
>  * The reported issue occurs **only when multiple Tx PDUs exist in IpduM** because the index of each Tx message differs between initialization and transmission copy.
>  * {*}BIP software currently supports only one Tx IpduM PDU{*}, so this index mismatch scenario does {*}not apply to BIP{*}.
>  * The actual problem described in the hotline ticket relates to {*}RIP (RTA-CAR) for Cariad{*}, not BIP.
>  * The issue you observed in BIP is different: {*}initial values of Com signals not matching configuration{*}, which is unrelated to the IpduM_InitValues index bug.

-------

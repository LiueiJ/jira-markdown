---
jira_key: ARC-9725
jira_url: "https://jira.etas-dev.com/browse/ARC-9725"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-03-21T01:04:46.000+0000"
updated: "2026-09-03T07:54:03.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-9725 ECarX VW SmartCabin MCU

> [!jira] Accepted ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-03T07:54:03.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-9725)

## 描述

# Background

- Customer: Ecarx CN & Sweden
- ECU: Smart Cabin- GEI
- Chip: Infineon T2G CYT4BB (OS available or not) + Siengine SOC
  - Note that the original project discussion talked about the using the S32K, but is seems like the customer has decided on the TraveoII
- End customer: VW Germany, MQB platform

ECARX has been nominated by VW in Germany for the project.

 

# **Project Scope**

Our target client, Ecar-x, has directly negotiated with Volkswagen Germany to get a navigation instrument cluster project within Volkswagen's global MQB platform. Their components are set to be supplied across Volkswagen's global MQB vehicle lineup. The chip they are utilizing is the **CYT4BB**, and they are preparing to procure Classic Autosar along with HSM (VKMS) for their productions.

 

Currently, they have outlined a configuration featuring two CAN buses and one Ethernet channel:

1. ​**CAN Buses**: Primarily designated for the transmission of instrument cluster signals and communications related to cyber security.
2. ​**Ethernet Channel**: Intended for the deployment of Service-Oriented Architecture (SOA), although specific details regarding the Ethernet component are still under discussion with Volkswagen.THe

**Ecarx requirements are collected in** [VW_Autosar Requriments_Ecarx.docx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/559112/559112_VW_Autosar+Requriments_Ecarx.docx) and [VW MCU Autosar -Etas20250312_Cus_Feedback_form.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/559111/559111_VW+MCU+Autosar+-Etas20250312_Cus_Feedback_form.xlsx) . 

 ** 

**Key Points for the Client's Choice of Classic Autosar:**

1. ​**Prior Experience with Autosar Products:**

- Ecarx has previously purchased and implemented products from Etas and Vector, gaining practical project experience.

1. ​**Challenges in Volkswagen's Global MQB Project:**

- Unlike traditional European Tier 1 suppliers (e.g., Bosch, Continental), Ecarx has no prior experience with Volkswagen's global projects.
- They have not mastered Volkswagen's platform documentation requirement nor undergone Volkswagen's global testing and validation processes.

1. ​**Domestic vs. Global Application of Autosar:**

- While experienced in implementing Autosar for domestic projects in China, they are uncertain about how to apply Autosar within Volkswagen's technical framework.

1. ​**Expectations from Toolchain Suppliers:**

- They seek extensive support and expertise from toolchain suppliers regarding Volkswagen's technical system.
- Specifically, they value suppliers with a proven track record in Volkswagen projects, understanding of QLAH standards, pre-integration experience with Volkswagen-specific modules, knowledge of Volkswagen's enterprise standards versus standard Autosar configurations, and the ability to provide pre-integrated software packages compliant with QLAH standards.

**Request for Verification:**

Please verify the accuracy and authenticity of the described advantages to ensure they align with our actual capabilities and past experiences.

**Initial Collection of Client Requirements:**

1. ​**Compilation of Client Requirements:**

- With the assistance of Sathish and Markus, the ETCN team has organised the client's rough requirements.
- The primary document is an Excel file listing([VW MCU Autosar -Etas20250312_Cus_Feedback_form.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/559111/559111_VW+MCU+Autosar+-Etas20250312_Cus_Feedback_form.xlsx)) all the software requirements Volkswagen has provided to Ecarx.

1. ​**Review of the Excel List:**

- Upon reviewing the list, we noted that the standard is quite recent, even newer than the E3 1.1 2022 standard.
- We speculated that it might be E3 1.2, indicating that it is not based on older MQB requirements and could pertain to new MQB vehicle models.

1. ​**Focus Areas in the Standard:**

- ​**Cyber Security (VKMS):** We paid particular attention to the VKMS aspects related to information security.
- ​**Diagnostics:** The diagnostic requirements were thoroughly examined.
- ​**Network Communication:** The network communication specifications need to be analyzed.
- ​**Basic Volkswagen BSW:** The foundational BSW (Basic Software) components related to Volkswagen need to be scrutinized.
- ​**Ethernet:** The Ethernet section remains uncertain as the client is still in discussions with Volkswagen.

1. ​**Autosar Component List:**

- Additionally, we received a bilingual (Chinese-English) Autosar component list from the client.
- This list outlines the most rudimentary Autosar procurement component requirements the client could provide.
- It also serves as a reference for the German headquarters to conduct further analysis.

 

**What We Need from the German Headquarters:**

1. ​**List of Successfully Implemented Projects on Volkswagen Platform:**

- We require a list of ten successfully implemented projects on the Volkswagen platform from the German headquarters.
- Preference is given to projects related to MQB, IVI, or involving the CYT4BB chip.

1. ​**Previous E3 1.1 Software Architecture:**

- We need the German headquarters to provide the software architecture of previous E3 1.1 implementations with ETAS Autosar(RTA-CAR or Cubas).
- Focus should be on the integration of Volkswagen-specific modules such as SSW, SOK, VKMS, FDS, DK, BAP, etc.

1. ​**Volkswagen Flash Bootloader Architecture:**

- We require the German headquarters to provide the architecture of Volkswagen's Flash Bootloader.

1. **Volkswagen VKMS Architecture:**

- We require the German headquarters to provide the architecture of Volkswagen's VKMS.

1. ​**Comparison of Volkswagen BSW Configuration vs. Standard Autosar Configuration:**

- We need a detailed description from the German headquarters on how Volkswagen's BSW configuration differs from the standard Autosar configuration.
- Include any special modifications made in past projects, particularly if BSW code was changed.

1. ​**Review of Attached Documents:**

- We request the German headquarters to review the attached documents.
- Identify which Qlah standards have not been implemented and mark the standards they are confident in implementing.

1. ​**Rough Quotation for BSW Part of the Project:**

- We need a rough quotation from the German headquarters for the BSW part of this project.
- Hardware integration and client implementation discussions can be handled in China, but the configuration of Volkswagen's enterprise-standard BSW must be managed in Germany, meaning the foundational engineering work should originate from Germany.

 

**Why ETCN Needs Support from the German Headquarters:**

1. ​**Lack of Experience in Volkswagen Global Projects:**

- ETCN has not previously undertaken Volkswagen global projects and lacks experience in this specific area.

1. ​**Proposed Task Allocation:**

- ETCN intends to transfer the responsibility for Volkswagen's enterprise-standard BSW (Basic Software) tasks to the German headquarters.
- ETCN will focus on local integration and local support tasks.

1. ​**Inability to Independently Handle Volkswagen Global Standards:**

- If the Volkswagen global enterprise-standard tasks were solely assigned to China, ETCN would be unable to manage them due to limitations in technical capabilities and team resources.

1. ​**Expected Collaboration and Pricing Strategy:**

- ETCN aims to include the cost of German team support in the final quotation to the client.
- The goal is to convince the client to accept and pay for this collaborative approach.
- This strategy will enable ETCN and the German headquarters to jointly implement the project.

 

**Why ETCN Has Been Urgently Requesting Support from the German Headquarters:**

1. ​**Client's Aggressive Timeline:**

- The client has imposed an extremely tight deadline, pushing ETCN to its limits.
- Specifically, the client demands that Etas prepares the technical SOW (Statement of Work) document and undergoes a technical assessment by next Tuesday.

1. ​**Key Points of the Technical Assessment:**

- ​**Experience with Volkswagen Projects:** The client requires a list of successful project cases where Etas has worked on Volkswagen global projects.
- ​**Implementation Experience with Volkswagen System Documents:** The client wants to know if Etas has experience implementing the Volkswagen system documents they provided and if there are any areas where Etas does not meet the project requirements.
- ​**Software Architecture Presentation:** The client expects Etas to present the software architecture, particularly focusing on the integration of Volkswagen-specific modules (SSW, SOK, VKMS, FDS, DK, BAP, etc.).
- ​**Differences Between Volkswagen-Configured Autosar and Standard Autosar:** The client is keen to understand the differences between the Volkswagen-configured Autosar and the standard Autosar. This means they want detailed description on how the Qlah documents deviate from the standard Autosar definitions.

1. ​**Simultaneous Quotation Requirement:**

- The client also requires a quotation by next Tuesday, which implies that the costs associated with the German team's involvement must be included in this quotation.
- Therefore, we need the German team to provide a rough estimate of their fees by Tuesday to incorporate into the client's quotation.

# 3rd Party SW Integation

Customer needs to integrate the VW SSW modules:

- BAP - customer has BAP_v1.12.2_Distribution_2023-10-10.zip (see [VW MCU Autosar -Etas20250312.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/559281/559281_VW+MCU+Autosar+-Etas20250312.xlsx))
- FvM - version unknown
- KS - version unknown
- SFD - customer has SCM-release07-202409.7z (see [VW MCU Autosar -Etas20250312.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/559281/559281_VW+MCU+Autosar+-Etas20250312.xlsx))
- VKMS - customer has VKMS 02.10.00.zip (see [VW MCU Autosar -Etas20250312.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/559281/559281_VW+MCU+Autosar+-Etas20250312.xlsx))

Actual versions are **not** currently known

# Timeline

ECARX Project schedule:

- A sample: Beginning of April 2025 - ETAS shall release related BSW to ECARX at this time
- B sample: Middle of June 2025
- Full functions: Beginning of Oct 2025 - VW standards shall be fulfilled, ETAS delivery time can be discussed later.
- SOP: June of 2027

## 关联

- satisfies: [[RCT-156 RTA-CAR v12.7.1-ECarX]]
- satisfies: [[ARCREL-67 RTA-CAR 12.9.0.HF1]]

## 评论

> [!note]+ 2025-10-12 04:40 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Mandatory features & defect fixes ECARX must be delivered in Week 49/50 .  We identified some risks and have come up with some mitigation plans.
>
> **Mandatory for ECARX** :
>
> [RH-13755, ](https://rtahotline.etas.com/jira/browse/RH-13755) [RH-13117,](https://rtahotline.etas.com/jira/browse/RH-13117) [RH-13487,](https://rtahotline.etas.com/jira/browse/RH-13487) ARC-12458
>
> {*}Risks{*}:
>  # Considering the timeline criticality for ECARX and our planned release of 12.10.0, delivering the mandatory features through RTA-CAR 12.10.0 production SW is not feasible.
>  # Feature readiness around Week 50/51 is close to Christmas / New year holidays. It will be very hard to find experts to fix any issues identified by Hub / Customer during integration testing.
>
> {*}Mitigation{*}:
>  * After discussing with CN Hub , PF experts & SF experts, the viable option is to deliver the Mandatory defect fixes and features required for ECARX through 12.9.1 engineering release.
>  * Currently, [@Nandita Prasad (MS/EBD-ETAS)](mailto:Nandita.Prasad@etas.com)’s team is evaluating the workaround solution proposed by SF/CN hub for the feature ARC-12458 . Once we have positive confirmation from product team, we shall deliver this solution in the 12.9.1 ENG .
>  * Likewise, we can integrate another mandatory feature from RTE - ARC-12047 into the same 12.9.1 ENG.
>  * COEM integ. team to integrate the solution & defect fixes into 12.9.1 ENG [ R : Alex F, Lan T]
>
> For this mitigation plans to work effectively, we request the PF team to prioritize the ECARX features and defects fixes in their earliest possible **PI25.4** sprints such that we can integrate , test & release the 12.9.1 ENG by Week 50 to ECARX.
>
>
>
> email attached [^Reg_ ECARX  Deliverables  & Risk mitigation plans.msg]
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Patil_Mahesh_(MSPJ-ETH-BSW)|Patil Mahesh (MS/PJ-ETH-BSW)]]  fyi

-------

> [!note]+ 2025-07-14 09:19 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> latest email conversation & status updates are attached here [^RE ECARX Requesting roadmap alignment bw ETCNSFPF.msg] .
>
> analysis summary can be found in this [^ECARX_Requirements_ALL_wClusters (3).xlsx]

-------

> [!note]+ 2025-07-09 11:14 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Link to OPL list managed by SEF1 team working on the EcarX project in an engineering service capacity

-------

> [!note]+ 2025-04-28 08:23 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Verbally awarded to us according to feedback from Nigel.

-------

> [!note]+ 2025-04-16 08:17 · [[Hotz_Ingo_(ETAS-ECMPRM-EMW)|Hotz Ingo (ETAS-ECM/PRM-EMW)]]
> In our Regular Sync' Tang Yi and myself discussed that we need a deep dive discussion (e.g. even workshop) to discuss how we adress this customer engagement as global development team if we win this opportunity. In our next session we need to sync' about this w/ Tang yi, Tang Yan, Sathish, Tobias, Darren, Ingo.

-------

> [!note]+ 2025-03-24 14:02 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]] - Cypress was sold to Infineon in 2020 and they to kill the Cypress branding - its now the Infineon TRAVEO branding. 

-------

> [!note]+ 2025-03-24 12:15 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] Can you provide the final version of the VKMS specifications to be able to do an analysis and identif potential changes needed in the SW? So far we only have the optimized versions for the purchasing process.

-------

> [!note]+ 2025-03-21 06:52 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> There is a needs described in [^VW_Autosar Requriments_Ecarx.docx]for an FBL - there isn't an RTA-FBL  product for VW, so this would need SEF2 to be involved to provide an FBL as an engineering service.

-------

> [!note]+ 2025-03-21 06:25 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Via [[ZHAN_Huihui_(ETASCCN1)|ZHAN Huihui (ETAS/CCN1)]] & [[Hummel_Markus_(ETAS-ECMBUD)|Hummel Markus (ETAS-ECM/BUD)]]:
> ECARX request us to give a first feedback regarding following questions, could you please help double check on the answers (in RED part)?
>
> Thank you very much for your great help!
>
> Thank you very much for your great help!
>  # Support Infineon T2G CYT4BB/CYT3BB, and support both dual-core and single-core configurations.
> ETAS: Yes (both the TraveoII/GHS & TraveoII/WR ports supports both devices), but see compiler question below.
>  # The Bootloader must be customized to meet Volkswagen's requirements, supporting flashing and routing.
> ETAS: [[Hummel_Markus_(ETAS-ECMBUD)|Hummel Markus (ETAS-ECM/BUD)]]  (do we have experience on this
>  #  Must support hardware-based HSM, including algorithms, SecureBoot, Crypto, Key management, and VKMS core.
> ETAS: Yes, lots of experience on VW projects [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]]
>  # Must include Volkswagen-customized BSW modules.
> ETAS: [[Hummel_Markus_(ETAS-ECMBUD)|Hummel Markus (ETAS-ECM/BUD)]]
>  # The OS must comply with SC3.
> ETAS:Yes
>  # Must support dual CAN core isolation.
> ETAS:[[Hummel_Markus_(ETAS-ECMBUD)|Hummel Markus (ETAS-ECM/BUD)]] 
>  # Must support an external WDG driver - MAX6753KA29/V+T.
> ETAS:Yes? [[Hummel_Markus_(ETAS-ECMBUD)|Hummel Markus (ETAS-ECM/BUD)]] 
>  # Five additional licenses for the EB toolchain must be purchased.
> ETAS: Commercial issues @LI Zuowen (ETAS/CCN1)
>  #  CAN transceiver: TJA1043.
> ETAS:Yes
>  # Ethernet switch: SJA1005.
> ETAS:Not found in the latest CP Sales slides [[Hummel_Markus_(ETAS-ECMBUD)|Hummel Markus (ETAS-ECM/BUD)]] 
>  # Ethernet PHY: RTL9000BRG.
> ETAS: Not found in latest CP sales slides(but support RTL9000AN / RTL9000AA) [[Hummel_Markus_(ETAS-ECMBUD)|Hummel Markus (ETAS-ECM/BUD)]]
>  # The functional safety level of the overall code package shall be QM.
> ETAS: Yes, can support up to ASIL D
>  # The compiler shall be IAR.
> ETAS: Not support yet, propose GHS and WR to meet the project timeline

-------

> [!note]+ 2025-03-21 06:25 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Merged content of ARC-9610 here and cancelled earlier ticket.

-------

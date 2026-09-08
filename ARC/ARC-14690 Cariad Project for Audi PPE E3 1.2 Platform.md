---
jira_key: ARC-14690
jira_url: "https://jira.etas-dev.com/browse/ARC-14690"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: but9fe
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-01-30T03:50:44.000+0000"
updated: "2026-06-19T08:16:07.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: true
profile: CN Motivation
---

# ARC-14690 Cariad Project for Audi PPE E3 1.2 Platform

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-06-19T08:16:07.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-14690)

## 描述

### **Acquisition phase:**

### **Project Requirements Summary**

### **1. ECU & Chip**

- **ECU:** ADCU
- **Chip:** Horizon J6P
- **Vehicle Platform:** Audi PPE E3 1.2

### **2. Scope**

- Full delivery of **R-Core + A-Core middleware** plus **engineering services**, per the RFQ.

### **3. Technical Needs**

#### **R-Core Requirements**

- Must comply with **VW Q‑LAH** specification.
- Includes:
  - HSM
  - CP
  - BIP
  - FBL
  - COM & DIA
  - **SSW Integration**

#### **A-Core Requirements**

- Some/IP integration
- SSW integration
- VW Q‑LAH spec integration

### **4****. Project Timing**

- **RFQ issued:** Jan 26
- **Quotation due:** Feb 6
- **Nomination:** Before Feb 27
- **Deliveries:**
  - 1st Delivery: **April 30, 2026**
  - Final Delivery & Acceptance: **June 30, 2026**

### **5. Customer‑Highlighted Risks in comparison to Vector's offering**

1. **RTP/RTCP Streaming Capability**

- - Vector CP already supports mature RTP/RTCP streaming.
  - Customer asks whether **ETAS RTA‑CAR** can support this requirement.

1. **A‑Core + R‑Core SSW Integration Experience**

- - Vector has strong experience in this area.
  - Customer perceives ETAS China as having limited experience (only ECARX VW R‑Core project).
  - Customer want to know how ETAS will:
    - Transfer know‑how from ETAS HQ/Bosch
    - Ensure expert resources for the project

1. **Q‑LAH Engineering Service Capability**

- - Customer notes that Bosch has Tier‑1 Q‑LAH experience.
  - They expect ETAS to explain:
    - How it will transfer Bosch/ETAS expertise
    - How expert resources will be guaranteed

1. **Project Delivery Schedule**

- - Customer requests a concrete plan showing how ETAS will **secure on‑time delivery**.

[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]  major risks I see are highlighted in Red.

## 评论

> [!note]+ 2026-03-13 07:00 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> latest customer meeting updates  can be found here [^RE_ CARIAD J6P CP+HSM 项目技术评审结果Pre-alignment 会议更新.msg]

-------

> [!note]+ 2026-02-04 11:24 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Via Huihui:
>
> Hello Darren, Tan.Yang,
>
>                From the meeting with customer today, it is much more positive than our expectation.
>
>                It is high chance that we can win this project (even extend to Audi / Porsche brand for mass production) if we can:
>  * Find a way to provide RTP/RTCP solution.
>  * Get the resource commitment from global team on the SSW integration.
>
> We need provide the SOW with quotation price to customer on this Friday.
>
> Could you please help give us quick feedback on this request?
>
> If need any more information, we can organize a on-line meeting to discuss how to proceed to next step.
>
>
>
> Take following meeting munities as a reference.
>
> It summarized the current competition state and possible deviation acceptance after a long & tough negotiation with customer.
>
>
>
> **Meeting Minutes: Cariad Audi PPE Platform J6P Project Meeting**
>  * **Customer:** Cariad
>  * **Meeting Date:** February 4, 2026
>  * **Location:** Cariad Offices
>  * **ETAS Attendees:** Huang Song, Tang Steven, Liu Jie, Pan Tianyang, Zhan Huihui
>  * **Client Attendees:** Zhou Peize, Wang Cong, Zhang Zhehua
>  * **Subject:** Audi PPE J6P Project Customer Meeting
>
>  ** 
>  # **Competitor Intelligence Update**
>
> The customer has issued RFQs to approximately 10 Tier-1 and Toolchain Tier-2 suppliers.
>  * **HiRain / Neusoft:** Already disqualified/out of the bidding.
>  * **Vector:** Has not officially participated in the quotation as of yet.
>  * **EB (Elektrobit):** Technical communication scheduled on Feb 4th.
>  * **Desay SV:** Has not officially participated as of yet.
>  * **CalmCar (?):**
>  * **Carizon (Cariad-Horizon JV):** Declined the project due to heavy workload and resource constraints on existing lots of projects.
>
>  # **Customer Feedback on Competitive Landscape**
>
>  * **General Status:** No single supplier can 100% meet the requirements. The customer seeks a partner whose strengths complement **Cariad’s** capabilities.
>  * **Position of ETAS:** The customer encourages ETAS to participate actively. Among all suppliers, discussions with ETAS started earliest and are the most in-depth, providing a "first-mover" and technical advantage.
>
> **SWOT Comparison: Vector vs. ETAS (from customer vocie)**
> | **Feature** | **Vector** | **ETAS** |
> | **Main Risk** | **J6P chip adaptation risk.** | **E3 1.2 PPE platform SW integration risk.** |
> | **Strengths** | SSW integrated into toolchain; supports RTP/RTCP; HSM white-box delivery. | Experience in J6P adaptation; Bosch (parent company) has extensive SSW integration/BSW development experience. |
> | **Weaknesses** | 1) No J6P adaptation experience; |
> 2) SSW/BSW expertise lies with Harman (Tier 1);
> 3) China team lacks SSW integration experience (expertise sits in Germany).|1) Toolchain-SSW adaptation risks;
> 2) RTP/RTCP protocol development and integration risks.|
>  # **ETAS Technical Deviations**
>
>  * **RTP/RTCP:** Currently no product or protocol stack available. The customer stated this is a **non-negotiable** requirement.
>  * **HSM White-box Delivery:** Customer verbally agreed that concessions/alternatives are open for discussion.
>
>  # **Quotation Information**
>
>  * Provide a production license fee quote for a **Single Platform / Multiple Vehicle Models** as an optional reference.
>
>  # **Timeline Updates**
>
>  * **Nomination (Sourcing):** May be delayed to March, but the final delivery deadline remains unchanged.
>  * **Milestone:** Cariad expects the first delivery by late March/early April to showcase prototype functions at the {*}Beijing Auto Show{*}. Success here is critical to securing Phase 2 work packages and mass production plans.
>
>  # **Technical Clarifications**
>
>  * **Gateway Functionality:** 4{_}CAN + 1{_}Ethernet. Must support **PduR routing** (CAN-to-Ethernet bi-directional conversion), including **IPv6** and **VLAN TAG** features.
>  * **Q-LAH Standards:** Full implementation is not required for Phase 1. For example, a simple Demo suffices for Diagnostics, refer to RFQ definitions for details.
>  * **SSW (Security Software):** Refer to Liu Jie for the SSW list; ETAS can propose the SSW version based on ETAS’s mature experience.
>  * **VKMS & HSM:** Horizon "Mini-HSM" can be Black-box. Others like **HSM Core, Key Storage, and A-Core drivers** must be delivered as {*}White-box{*}. The ultimate goal is 100% white-box delivery.
>  * **A-Core Middleware:** The customer suggests using the **Vector AP stack** for SOME/IP due to its superior VKMS compatibility. If ETAS is confident in adapting **ETAS AP** to VKMS, it is acceptable, but no additional fees can be charged for this.
>
>
>
> **Huihui ZHAN** 
> Customer Team Leading Chinese OEMs
>
> M +86 139 17338365 
> [Huihui.ZHAN@bosch.com](mailto:Huihui.ZHAN@bosch.com)
>
> ETAS Automotive Technology (Shanghai) Co., Ltd., ETAS/CCN1 
> 333 Fuquan Road North, IBP, Changning District, Shanghai 200335, P.R. China 
> [www.etas.cn](http://www.etas.cn/)
>
> **ETAS – Empowering Tomorrow’s Automotive Software**

-------

> [!note]+ 2026-02-04 06:59 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> attached [^030_199_LAH.DUM.035.F_IP_Audio_Video_Transport_DE_EN_V1.3.pdf]document explaining RTP & IEEE1733 RTCP use
>
> [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] fyi

-------

> [!note]+ 2026-01-30 14:22 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> I see our ability to do this business is predominantly an integration job and this needs to be either done in CN hub or through involvement of a 3{^}rd{^} party engineering service provider.
>
> My assessment
>  * {color:#00875a}*Low risk*{color}: RTA-CAR is well aligned with the VW architecture and most customers have very few challenges making things work (they take RTA-CAR and manage to ship ECUs without the need for product extensions). This includes importing the SSW ParamDefs and using the tools from Vector, Akku, and EB (amongst others) for SSW code generation. There is more info about the SSW modules in the OEM Handbook here: [https://rtahotline.etas.com/confluence/pages/viewpage.action?pageId=203522152]
>  * **{color:#de350b}High risk:{color}** we know that supporting VKMS in the HSM is non-trivial for us and we both designed that SW for VW and have decades of experience in building solutions. I would expect a lot of surprises when integrating Horizon’s own HSM SW because that will not be mature yet.
>  * **Custom engineering:** RTA-CAR does not have RTP support and we have no plans to build it (this is only the second time we have had a request for this ever so it’s a rarity). On that basis it would need custom engineering and you’d need to find an engineering partner able to do this work or be prepared to build that yourselves. I've added a need, so we can track the number of requestors in case we get demand in the future or see a different trend.

-------

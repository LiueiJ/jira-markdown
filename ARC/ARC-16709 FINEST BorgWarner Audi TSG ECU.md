---
jira_key: ARC-16709
jira_url: "https://jira.etas-dev.com/browse/ARC-16709"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: but9fe
reporter: rew1sgh
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-06-23T03:54:01.000+0000"
updated: "2026-09-03T15:42:32.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: true
---

# ARC-16709 FINEST/BorgWarner Audi TSG ECU

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-03T15:42:32.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-16709)

## 描述

Here is requirement from Tier1 - Finest,

Our partner Finest is participating in the bidding for the Volkswagen Audi E³ project. To help everyone accurately assess the technical feasibility, here is a brief introduction to the project background:

- This is an Audi global project. BorgWarner is the Tier 1 supplier, and Finest is the Tier 2 supplier.
- The product is TSG (Transmission Side Generator) ECU in P3 position.
- The microcontroller (MCU) platform will be selected between TC389 and U2B.
- **It is particularly important to note that the communication method of this product only supports FlexRay, explicitly excluding CAN, ETH (Ethernet), and LIN.**
- In previous technical exchanges, Audi explicitly recommended Vector (primarily responsible for the AUTOSAR stack) and ETAS (primarily responsible for software platform-related business) to Finest.

To help Finest win this project, we need to provide convincing answers to the technical gaps raised by the customer.

The customer’s current core focus is: **After project nomination, how exactly will Finest fill these technical gaps?** They do not want to just see a list of risks and problems; they expect every gap to have a clear owner (e.g., ETAS), a solution path, a timeline, and a risk assessment.

Below are the questions raised by the customer in five core areas. We kindly ask our experts to evaluate, taking into account the project background (especially the chip selection and the FlexRay-only communication limitation), whether we have relevant materials, ready-made solutions, or case studies to support our response:

**1. Immobilizer System**

- **Customer Question:** How will the immobilizer function be handled? Are there suppliers in the market that can provide an E³-compliant solution? What is the solution’s maturity? Has it been used within the VW system? What are the integration effort and risks? If developed in-house, what are the resource requirements, timeline, and risks?
- **Internal Consultation:** Under this FlexRay-only architecture, do we have a ready-made solution or partnership ecosystem for the immobilizer system tailored to the VW E³ architecture? Can we provide application cases within the VW system to demonstrate its maturity?

**2. AUTOSAR / BSW**

- **Customer Question:** Which partner supports the AUTOSAR stack? Which version is supported? Who is responsible for BSW integration and maintenance? What experience does this partner have on the E³ architecture?
- **Internal Consultation:** The basic stack will likely be provided by Vector, but on the TC389 or U2B platforms, what role can we play in BSW integration, maintenance, and E³ architecture adaptation? Which AUTOSAR version is supported? Can we output an experience summary regarding the E³ architecture?

**3. Cybersecurity**

- **Customer Question:** How are HSM, key management, secure boot, secure flashing, and certificate management implemented? Which are standard components and which require development? Which partner supports this?
- **Internal Consultation:** Without Ethernet (ETH), what challenges will functions like secure flashing and certificate management face? What standard components do we have for cybersecurity, and what needs customization? Can we act as the primary cybersecurity support partner to provide solutions for Finest?

**4. Diagnostics / UDS-based OBD**

- **Customer Question:** How do we bridge the current diagnostic gaps? Which functions already exist and which need development? Is external support required?
- **Internal Consultation:** For the Audi E³ requirements, based on the FlexRay bus, what ready-made functions in our diagnostic stack or toolchain can be reused? How can we help Finest quickly fill its diagnostic shortcomings?

*5. E³ Architecture*

- **Customer Question:** Which partner supports E³ requirement interpretation, system analysis, architecture definition, and integration? How is compliance with Audi requirements ensured?
- **Internal Consultation:** Do we have a dedicated internal team capable of supporting Audi E³ requirement interpretation, system architecture definition, and integration? In terms of ensuring compliance with Audi standards and specific communication architectures, what methodologies or services can we provide?

Our strategy is to prove to the customer: **Choosing ETAS means choosing certainty and risk elimination.** To prepare the external clarification materials as quickly as possible, your inputs are urgently needed.

## 评论

> [!note]+ 2026-06-23 07:16 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> Thanks [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] for your swift response. 
>
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]]  fyi

-------

> [!note]+ 2026-06-23 07:11 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Q: our FR stack support for UDS.  What ISO standard we support for UDS on Flexray ? ( ISO 14229 ??? ) 
> {color:#0747A6} - Yes, UDS on FlexRay (UDSonFR) is supported in our stack, 
> UDS is based on ISO 14229 while the  AUTOSAR FlexRay Transport Protocol (FrTp) conforms directly to the ISO 10681-2 standard{color}
>
> Q: Our FR stack completeness for VW - E3 specs. ? Do we have any VW project experience involving FlexRay stack. Any customer experience with FR stack is also ok 
> {color:#0747A6}- Our Flexray stack has been used extensively in BBM projects (in series)
> We recently secured a flexray project at the India Hub from VW Signata - Motivation - ARC-16354
> Seems like they are interested to have the FrArTp module (an older proprietary module adapted from CAN (ISO 15765-2)). 
> While this is not included in our standard RTA-Flexray package, we have an existing version delivered to BBM. 
> We are offering this module to Signata as an add-on engineering service. 
> I am not aware of any gaps until now, but to provide a more concrete feedback we would need to evaluate/analyze the VW flexray specifications.{color}

-------

> [!note]+ 2026-06-23 06:17 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] 
>
> There is biz. opp. for GOEM project. ( VW - E3 arch). This is based on FlexRay. 
>
> customer want to know 
>  #  our FR stack support for UDS.  What ISO standard we support for UDS on Flexray ? ( ISO 14229 ??? ) 
>  # Our FR stack completeness for VW - E3 specs. 
>  ## Do we have any VW project experience involving FlexRay stack. 
>  ## any customer experience with FR stack is also ok 
>
> There is a follow-up customer meeting tomorrow morning (CN time) with the customer. any useful info you share will support our Sales/CCE's to engage with the customer. 
> Thanks 
> [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 

-------

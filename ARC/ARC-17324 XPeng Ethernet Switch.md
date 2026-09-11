---
jira_key: ARC-17324
jira_url: "https://jira.etas-dev.com/browse/ARC-17324"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]"
reporter: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-08-06T07:15:49.000+0000"
updated: "2026-08-26T09:56:45.000+0000"
synced-at: "2026-09-11T01:13:09.700Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

XPeng requires ETH Switch solutions for their next-generation vehicle architectures .

SOP Timeline: 2027-2028  ( exact timeline - TBC)

The target HW : **Broadcom BCM89586M** Ethernet switch

XPeng's initial requirements include:

Area
Requirements

Switch Management
Read/write access to switch and PHY registers

Port Management
Port status, link speed, Master/Slave configuration

Diagnostics
MIB counters, test mode, cable diagnostics

Traffic Control
Flow control, Priority Flow Control (PFC)

Layer 2 Networking
VLAN, static L2 forwarding tables

Time Synchronisation
gPTP

Security
ACL / TCAM based access control

QoS
QoS and Strict Priority (SP) scheduling

TSN Features
802.1Qci, 802.1Qav, 802.1Qbv, 802.1CB, 802.1Qbu

 

**Our ETH Switch Current Status :**

**PoC already exists**, but it is currently limited.

- Demonstration has been completed at the **application layer**.
- Initial work has already been done on **BCM89586M**.
- Product management believes Broadcom support can be prioritized in the development backlog

our product team sees no major technical gap at a high level against XPeng's listed requirements. 

- The feature set can be fulfilled
- Work on the Broadcom chip as part of the backlog requires prioritization
- Alignment with Broadcom required : [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]
- concern is the schedule. When does the customer expect initial SW delivery on this target device? - TBD

**Gaps** 

1. **RTA-OS port is needed. [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]]**
2. Full integration with the Broadcom SDK.

Technical Lead in China : [[WANG_Yiqiang_(ETAS-ECMXSF-CN)|WANG Yiqiang (ETAS-ECM/XSF-CN)]] 

business : [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]

## 评论

> [!note]+ 2026-08-25 16:10 · [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]  and [[WANG_Yiqiang_(ETAS-ECMXSF-CN)|WANG Yiqiang (ETAS-ECM/XSF-CN)]] apparently, Broadcom device doesn't have AUTOSAR MCAL drivers yet, and this is a bottleneck for the integration of RTA-SWITCH in this device. The key drivers like Ethif and switch (EthSwt and EthTrcv) are not available, so it is not possible to utilize the hardware without Broadcom including these drivers in their SDK. Broadcom is working with a 3rd party company to develop the MCALs, which is not known to us by when they can get these drivers sorted out. We are in touch with Broadcom team to find out from them re the availability of these drivers. 
>
> Perhaps we follow a strategy to get XPeng to push Broadcom to make these AUTOSAR MCAL drivers developed ASAP, and then it would make the integration of RTA-SWITCH onto this device easier and the timeline feasible somehow. What do you think of this approach? Of course, we need to be careful here and not to play man in the middle. Thoughts?  

-------

> [!note]+ 2026-08-14 15:03 · [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] and [[WANG_Yiqiang_(ETAS-ECMXSF-CN)|WANG Yiqiang (ETAS-ECM/XSF-CN)]] 
>
>
>  * Broadcom SDK is available and can be analyzed by Tobias and the team
>  * We have the following tasks that need to be followed and run in parallel:
>  * Work with Broadcom to align on the SDK integration --> Omar emailed Broadcom already
>  * Work on the RTA-SWITCH product and tool:
>  * 90% of the AUTOSAR components can be generated out of the code generator tools outside of the device - the switch manager configuration exists in ISOLAR already
>  * This is requires work with Broadcom and ISOALR colleagues to align on the configuration and integration of all different components
>
>
>  * The target Broadcom device will need to be configured using CycurGATE tool for the firewall
>  * Configuration of TCAMs and how they can configured using CycurGATE tool --> this requires technical alignment with Broadcom as well
>
>
>  * RTA-OS port is required for Broadcom device - This requires alignment with RTA-OS colleagues [[Hudson_Tom_(ETAS-ECMXPC-Yok1)|Hudson Tom (ETAS-ECM/XPC-Yok1)]] , here is the link of this device and we appreciate your support let us know if this CPU is already supported [BCM89586M Product Brief](https://docs.broadcom.com/doc/89586M-PB)
>
>
>  * Ultimately the goal is to have the AUTOSAR switch components generated using ISOLAR and the firewall code and configuration done using CycurGATE tool
>  * We will build the binary to the customer that includes the firewall, Diagnostic, TNS and RTA-OS

-------

> [!note]+ 2026-08-13 17:33 · [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]
> - I tried to understand your proposal, and I guess it is good one if this can be done on time, however, there are some clarifications that I would like to understand from your side and hopefully we can meet tomorrow and discuss them such as:
>  * You are suggesting to not use RTA-SWITCH, but rather use RTA-CAR on the VCU with a CDD driver component to interface and use the switch as a hardware device only, correct?
>  * It doesn’t make sense to integrate an SDK into a configuration tool, but the ultimate goal here is to configure the networking parameters in the hardware using our tool. The SDK is a generated library by Broadcom and it doesn’t change and or no need to re-generate it or develop it.
>  * We could use ISOLAR tool to generate a configuration ARXML file for the HW and then generate a switch driver that runs as a CDD in the VCU à This requires a change in ISOLAR to do this function and I can’t see it happening by end of Sep.
>
>
>  * Ideally, we should have our RTA-SWITCH running in the Broadcom chip and no need for any CDD components in the VCU. However, the timeline might be an issue here.
>  * This requires RTA-OS port for Broadcom switch, which could take sometime beyond Sep.  
>
>
>  * The timeline is not clear to me, are you saying that end of of Sep should have configuration, and CDD all an and running?
>  * To support Broadcom device, we need to have a joint technical work with Broadcom to integrate their SDK into our stack, in addition to understand the configuration parameters that need to be configured. This is requires closer collaboration with Broadcom, which affects the timeline as well.
>  * If we end up using ISOLAR tool to configure and then generate CDD driver code, I envision this is the flow:
>
> ![[ARC-17324-image-2026-08-13-13-33-37-179.png]]

-------

> [!note]+ 2026-08-13 03:04 · [[WANG_Yiqiang_(ETAS-ECMXSF-CN)|WANG Yiqiang (ETAS-ECM/XSF-CN)]]
> After technical discussion with XPeng on August 12th:
>
> The current status of the Broadcom switch project:
>  # **Project Schedule:** The Pre-A sample hardware for the BCM89586M is complete. The A-sample will be completed in October, vehicle integration in November, and winter testing in December.
>  # **Current Progress:** Xpeng has already received the SDK provided by Broadcom. By the end of August, they will complete the integration of the basic switch register configuration functions via SPI. By the end of September, they will complete the full functional integration of the SDK on the MCU side (the SDK will be integrated as a CDD on the MCU).
>
> Since the winter testing schedule is already fixed, if ETAS is to participate in this project, I recommend implementing our Switch solution in two steps:
>  * **Step 1:** Integrate the SDK into ISOLAR to generate the driver code and ARXML files.
>  * **Step 2:** Use ISOLAR for the configuration and development of the Switch firmware (please refer to the attachment for the customer's expectations regarding this part). The timeline for Step 2 is relatively flexible, as it will not impact the winter testing in December.
>
> Therefore, for {*}Step 1{*}, we need to evaluate the following:
>  #  **Feasibility of ISOLAR Integration:** Can we use ISOLAR to configure and develop the Broadcom-provided SDK, generate the Switch driver code and ARXML files, and complete the integration into the MCU-side RTA-CAR project as a CDD (including integration testing) by the {*}end of September{*}?
>
> The required functionalities for adapting and integrating the SDK via ISOLAR must include:
>  * **a.** Read/write access to the Switch and built-in PHY registers.
>  * **b.** Port Up/Down status, link speed, Master/Slave configuration, MIB counters, Flow Control or PFC settings, and Jumbo Mode.
>  * **c.** VLANs and L2 static forwarding tables.
>  * **d.** Test Mode and cable diagnostics.
>  * **e.** gPTP.
>  * **f.** ACL or TCAM access control.
>  * **g.** QoS (including SP scheduling settings), 802.1Qci, 802.1Qav, 802.1Qbv, 802.1CB, and 802.1Qbu.
>
> *(Note: Items **f** and **g** can be completed by the end of November.)*
>
> **Critical Note on Requirements:** The customer explicitly informed us that if we cannot participate in the Phase 1 SDK integration, the current switch setup will not be changed. This means they will abandon trying our Switch solution altogether. Given the tight timeline, please have the product team evaluate the feasibility of this as soon as possible.
>
>
>
> [[Alshabibi_Omar_(ETAS-ECMXPC-Wte)|Alshabibi Omar (ETAS-ECM/XPC-Wte)]]   Need product team to evaluate the feasibility of the Xpeng project 

-------

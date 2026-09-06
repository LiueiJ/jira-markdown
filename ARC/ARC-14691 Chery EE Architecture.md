---
jira_key: ARC-14691
jira_url: "https://jira.etas-dev.com/browse/ARC-14691"
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
created: "2026-01-30T05:25:35.000+0000"
updated: "2026-07-29T07:18:37.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-14691 Chery EE Architecture

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-07-29T07:18:37.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-14691)

## 描述

Currently in acquisition of Chery.  Quoting comprehensive package 

This Proposal is customized to support the extensive ** Infineon Aurix TC2x/TC3x Family and ** XG Tech GUA platforms, with an Optional add-on for ** Horizon Robotics J6P, ensuring a unified and efficient development environment with our latest RTA-CAR version

1 : AUTOSAR Development & Maintenance Package (12 sets) 

2 : AUTOSAR production License 

3 : Basic Integration Packages 

Optional 

4 : Optional Extension (Horizon Robotics J6P) 

5 : Engineering services 

Platform requirements:

 

**Participants**:

• Customer EEA Architecture & Software Platform Team

• ETAS Technical Support & Tools Experts

**I. Meeting Background**

This joint meeting, organized by Bosch Central Research Institute and the Customer EEA team, focused on two main topics:

1. BSW Distribution and System Performance Optimization on Multi-Core AUTOSAR Architecture – focusing on efficient load balancing and inter-core communication mechanisms on high-performance multi-core MCU platforms such as TC499;

2. Application and Integration of IEEE1722 AVTP in Automotive TSN Networks – exploring real-time audio/video and control signal transmission under TSN, and AUTOSAR integration strategies.

**II. Topic 1**: **BSW Distribution and Performance Optimization on Multi-Core Architecture**

**1. Motivation for Multi-Core Design**

• Single-core (especially Core0) load reaches 90–100%, causing task congestion;

• Multi-core distribution aims to achieve CPU load balancing and system response optimization;

• Multi-core deployment is a performance optimization tool, not the ultimate goal.

**2. Single-Core Optimization Measures**

Optimization Direction Description

Task Cycle Separation COM main tasks should not scan all 5ms signals together; separate main functions according to DBC signal periods (5/10/20/40ms) to reduce CPU idle time.

Interrupt Optimization Reduce complex logic in interrupts to prevent CPU blocking and OS performance degradation.

Tool Support RTA-CAR tools can analyze Runnables, tasks, COM, and CAN interrupt bottlenecks to support further optimization.

**3. Multi-Core Communication and Architecture Models**

(1) Master-Slave Model

• Master core centrally manages resources (e.g., Flash, NVM); slave cores access via queues asynchronously;

• Asynchronous communication avoids master core blocking;

• Suitable for NVM, Watchdog, Diagnostics, and other centralized modules.

(2) Multi-Master Model

• Each core runs BSW modules independently; inter-core PDUR bridges data synchronization;

• ETAS supports cross-core PDU communication between SFCs;

• Supports Ethernet and CAN signal routing across cores.

(3) RTE Adapter Fast Path

• Establish Fast Path tables for high-priority signals;

• Directly access IOC cross-core channels via RTE Adapter, bypassing PDUR lookup;

• Pure software implementation, reduces latency.

**4. Software and Hardware Acceleration Coordination**

Comparison Software PDUR Cross-Core Hardware Routing Engine (DRE/CDE)

Implementation Level AUTOSAR communication stack (PDU-level) Physical layer frame-level

Functional Feature Data distribution, protocol encapsulation Fast payload forwarding

Typical Use Case CAN↔Ethernet routing with semantic awareness Frame-level forwarding

Collaboration Software handles logical routing; hardware handles accelerated forwarding

**5. Atomic Queue & Lock-Free Mechanism**

• ETAS uses atomic operation queues for lock-free inter-core communication;

• Improves parallel efficiency, avoids critical section conflicts;

• Adaptable to multiple MCU platforms (e.g., TC397, R52, U2B).

**6. Performance and Customer Feedback**

**• Replacing Vector with ETAS in a main OEM project:**

o More balanced CPU load;

o Improved system stability;

o No system crashes during testing.

• ETAS RTE and OS performance leads in industry; multi-core deployment is flexible.

**7. Interim Conclusion**

1. The core goal of multi-core deployment is load optimization;

2. Single-core optimization and multi-core migration can proceed in parallel;

3. ETAS supports both Master-Slave and Multi-Master architectures;

4. PDUR cross-core communication and RTE Fast Path are key differentiators;

5. Further hardware platform validation is required.

**III. Topic 2: IEEE1722 AVTP Application in TSN Networks ( Discussion points )**

1. Protocol Overview

• IEEE1722 (AVTP) is a time-sensitive audio/video transport protocol based on Ethernet MAC layer;

• Supports audio (IEC61883-6), video (MPEG-TS), and control signal encapsulation (CAN over AVTP);

• Uses IEEE802.1AS (gPTP) for clock synchronization; 

• Enables deterministic data transmission in automotive TSN networks.

2. AVTP Frame Structure & CAN Encapsulation

Field Description

Subtype Data type (audio/control)

StreamID Stream identifier, usually mapped to MAC address

Timestamp Synchronization timestamp

Payload Data payload (CAN frame encapsulation)

• CAN messages (ID, DLC, Data) embedded in payload;

• AVTP module in AUTOSAR CP decapsulates and restores COM signals;

• Application layer remains unaware of the transmission medium.

3. TSN Key Mechanisms

Mechanism Function Feature

QBV Time-aware scheduling Ensures deterministic transmission timing (1ms cycle, 120–150µs window)

QBU Preemption High-priority frames can interrupt low-priority frames

QAV Traffic shaping Smooth transmission, bandwidth control

gPTP Time synchronization Nanosecond-level accuracy (±100ns)

Recommended Strategy: Combine QBV + QBU + QAV to balance latency and determinism.

4. Performance and System Considerations

• Time Sync Accuracy: Microsecond-level tolerance;

• Bandwidth Overhead: QBV fixed window may waste 10–15% bandwidth;

• Determinism vs. Latency Tradeoff:

o QBV ensures determinism;

o QBU reduces latency;

o QBU-only may cause disorder or packet loss.

5. AUTOSAR Integration & Application

• AVTP module can interface with UDP/IP or directly with MAC;

• PDUR ensures medium-independent routing;

• Application layer signal model remains consistent;

• Enables deterministic signal transport between central computing and domain controllers;

• Coexists with SOA framework:

o SOA (SOMEIP/DDS) for service invocation;

o TSN+AVTP for real-time control signal transport.

6. Industry Case Studies & Verification

Region Status

North America (Tesla, Rivian) Production with IEEE1722+TSN co-network

China Validation stage (Bosch 104 project)

Hardware Requirements Switches/NICs supporting QBV, QBU, gPTP

Temporary Solution Use PWM gating to simulate QBV on non-TSN MCUs

**7. Summary & Next Actions**

Task Description Responsible Party

Technical Validation Validate QBV/QBU/QAV combination for deterministic control by Joint Technical Teams ( Chery & ETAS )

Performance Assessment Evaluate bandwidth overhead and timing offset by ETAS

Architecture Optimization Maintain application layer consistency with PDUR abstraction by Chery EEA Architects 

Demo Verification Set up AVTP-CAN transmission demo environment by ETAS

Training & Support Provide TSN configuration tools and demo guidance by ETAS

**IV. Overall Conclusions**

1. Multi-core BSW distribution and TSN network application are parallel directions in EEA evolution.

2. ETAS multi-core solutions enable soft real-time optimization via Master-Slave and PDUR cross-core mechanisms.

3. IEEE1722+TSN provides a unified path for deterministic in-vehicle communication.

4. Combined, they enable deterministic computation and communication in next-generation domain controller architectures.

## 关联

- relates to: [[ARC-16886 [Chery_ACTECO] TC499 CycurHSM3.X+CyrptoDriver support Vector Davinci]]
- duplicates: [[ARC-13729 Chery - EEA Architecture requirements]]

## 评论

> [!note]+ 2026-07-29 07:18 · [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]]
> [Chery_ACTECO] TC499 CycurHSM3.X+CyrptoDriver support Vector Davinci with QA release

-------

> [!note]+ 2026-02-12 07:40 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] sure lets discuss and check how we can enable our customer.
> We can definitely explore acceleration of the core use cases needed.

-------

> [!note]+ 2026-02-12 06:27 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  [[Dillmann_Vadim_(ETAS-ECMXPC-Abt1)|Dillmann Vadim (ETAS-ECM/XPC-Abt1)]]  thanks for your feedback. well noted. post Chinese new year - we can align on this topic in a meeting. Since we are offering comprehensive packages, the scope for Chery has widened. hence  I have moved the TSN topic to needs ticket : ARC-14857
>
>
>
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]  reg. >> *Audio streaming is targeted by the end of this year, followed by video streaming next year. <<* 
>
>    __   - needs alignment.  In the last meeting Customer hinted AV streaming is needed in their arch. but we can have a deep dive and understand whats needed for the Chery arch. 

-------

> [!note]+ 2026-02-02 07:18 · [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]]
> Our current status with respect to - IEEE1722 AVTP in Automotive TSN Networks:
> - We already support gPTP as per IEEE 802.1AS. - Hardware clock support, which is critical to achieving nanosecond-level precision, is currently under development.
> - As part of IEEE 17222, we currently support bus encapsulation from CAN to Ethernet using ACF frames.
> - TSCF currently not suppored
> - "AVTP module to interface with UDP/IP or directly with MAC;" , currently our stack supports only use case on top of MAC, interface with Udp/ip is not supported and use case not clear, as it would be mostly be the same as routing through Pdur
> - Native audio and video streaming over Ethernet using the respective AVTP frame formats is on our roadmap. Audio streaming is targeted by the end of this year, followed by video streaming next year.
> - We are also planning an audio-over-Ethernet demonstration to cohesively showcase AVTP transmission and deterministic behavior.
>
> That said, to go deeper and ensure alignment, it would be helpful to better understand the expectations, especially around mandatory protocol support, hardware assumptions, and demo scope. 

-------

> [!note]+ 2026-01-30 17:02 · [[Dillmann_Vadim_(ETAS-ECMXPC-Abt1)|Dillmann Vadim (ETAS-ECM/XPC-Abt1)]]
> very nice structured description!
> looks like an Etas marketing slide!
>
> i see following 
>
>  # **Action Items**
>
> | **No.** | **Task** | **Responsible** |
> | 1 | Provide RTA-CAR performance analysis examples | ETAS |
> | 2 | Submit CPU load profiling data | Customer EEA team |
> | 3 | Define preliminary multi-core BSW distribution (TC499) | Joint |
> | 4 | Build AVTP-CAN transmission demo environment | ETAS |
> | 5 | TSN tools training and configuration guide | ETAS |
>
>
> for the first one
> | 1 | Provide RTA-CAR performance analysis examples | ETAS |
>
> we can probably provide [Multicore Gateway Demonstrator - RTA Knowledge Base - Article proposals - RTA Hotline Confluence](https://rtahotline.etas.com/confluence/display/RKBI/Multicore+Gateway+Demonstrator)
> this page is still under Review process. to be published soon.
>
> for
> | 4 | Build AVTP-CAN transmission demo environment | ETAS |
>
> we have to check if and how we can reuse our 1722Tp Can-Tunneling Demo.

-------

> [!note]+ 2026-01-30 07:32 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> [[Nandita_Prasad_(MSEMS-ETAS)|Nandita Prasad (MS/EMS-ETAS)]] can you run through Chery's needs and work out if there is anything from that product side that would block us from meeting Chery's needs? Thanks

-------

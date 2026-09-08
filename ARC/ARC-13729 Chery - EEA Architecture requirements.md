---
jira_key: ARC-13729
jira_url: "https://jira.etas-dev.com/browse/ARC-13729"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: ""
reporter: mas1yok
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2025-11-26T06:35:22.000+0000"
updated: "2026-03-26T07:59:40.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-13729 Chery - EEA Architecture requirements

> [!jira] Canceled ·  ·  · 更新于 2026-03-26T07:59:40.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13729)

## 描述

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

- is duplicated by: [[ARC-14691 Chery EE Architecture]]

## 评论

> [!note]+ 2026-03-26 07:59 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Cancelling as this is duplicated by ARC-14961. The newer ticket has the technical discussion on it so its easier to kill this and keep the later ticket. I have copied the description over.

-------

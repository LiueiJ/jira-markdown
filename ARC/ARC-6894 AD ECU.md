---
jira_key: ARC-6894
jira_url: "https://jira.etas-dev.com/browse/ARC-6894"
server: etas
kind: motivation
type: Motivation
status: Canceled
priority: ""
project: ARC
assignee: ""
reporter: "[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]"
tags: [jira/label/motivation_wo_need]
fix-versions: []
epic: null
parent: null
created: "2024-09-23T12:35:03.000+0000"
updated: "2025-07-09T07:31:22.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

AD ECU for Leapmotor

During our market exploration in China, we identified our first major opportunity with a Qualcomm chip through Leapmotor's Cockpit and ADAS division. They have selected the Qualcomm SA8797 to power their future cockpit systems, ADAS systems, and integrated cockpit-driving fusion systems.

A key advantage in this opportunity is that Leapmotor's Base Software (BSW) Team has already purchased ETAS' RTA-CAR and successfully implemented it in a previous project (using the Renesas U2A MCU). As a result, BSW-layer development poses no significant challenge for them.

We aim to leverage this SA8797 project to fully unlock Qualcomm's expansion in the Chinese automotive market. According to confirmed intelligence, Vector initially quoted RMB 12-15 million for the SA8797 platform. However, upon learning of ETAS' involvement, they offered a discounted price of RMB 8 million.

**Core Requirement:**

Leapmotor insists that Qualcomm must publicly confirm ETAS as an officially supported partner for the SA8797 platform by June 30th (their project acquisition finalization deadline).

**Immediate Escalation to Qualcomm Global:**

• Request Qualcomm to issue a formal letter of support explicitly naming ETAS as:

**"A recommended Base Software (AUTOSAR) solution provider for the SA8797 automotive platform."**

**Contingency Plan:**

o If formal certification takes longer, propose a Qualcomm-signed interim statement confirming:

"Technical collaboration with ETAS on SA8797 is underway."

**Technical Challenge:**

The 6 efficiency cores use Qualcomm’s custom 3rd-gen Oryon architecture (non-ARM R core), potentially OS porting challenge for UK team.

Pre-ported RTA-OS for Oryon cores maybe needed.

Leapmotor’s acceptable price: RMB 5M (for basic AUTOSAR, excluding cybersecurity/hsm/Adaptive Autosar).

**Key Win Conditions:**

o Match Vector’s functional scope (Classic AUTOSAR, MCAL, BSW).

o Guarantee Qualcomm’s endorsement by deadline.

o Absorb Oryon porting risk via joint technical support by Qualcomm.

**Simplified AUTOSAR Requirements Analysis**

Key Advantages in Current Scope

- Streamlined Classic AUTOSAR Implementation
- Primary focus on multi-channel CAN FD message processing
- Ethernet limited to gPTP time synchronization only (no complex IP/SOME/IP stacks required)
- Critical benefit: Avoids the complex gateway system seen in Xiaomi's project requirements

Function

Function
Implemenation
Complexity

Multi-channel CAN
 multi CAN buses 
Low

Ethernet 
gPTP time sync only (No IP/SOME/IP)
Minimal

Gateway Logic
Basic routing (No complex scenario)
Low

Security 
Excluded from scope
N/A

![[ARC-6894-LeapMotor-AD-Architceture.png]]

## 评论

> [!note]+ 2025-07-09 07:19 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Via [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
>
> - Latest update : Despite all our efforts, we lost the Leapmotor’s QC8797 project opportunity. Leapmotor has decided to go with Vector. 
> - Reflecting on the QC situation, it looks like the local collaboration between QC-China & Vector is quite strong. This partnership has promoted Vector above ETAS. 

-------

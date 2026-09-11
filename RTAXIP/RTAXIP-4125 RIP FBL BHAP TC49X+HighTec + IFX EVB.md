---
jira_key: RTAXIP-4125
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-4125"
server: etas
kind: motivation
type: Story
status: Open
priority: Medium
project: RTAXIP
assignee: "[[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]"
reporter: "[[TAN_Yang_(ETAS-ECMXSF-CN)|TAN Yang (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/xip-local-accq]
fix-versions: []
epic: null
parent: null
created: "2026-09-04T03:49:54.000+0000"
updated: "2026-09-07T02:43:51.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Needs ticket /Acquisition support**

**Customer**: BAIC

**Project**: BHAP TC49X+HighTec + IFX EVB

**Phase**: acquisition &#91;x&#93;, Initial phase &#91;o&#93;

**Motivation** ($): 1M CNY

**SOR** link (Version):  <TBD>

**Requirements Gathering** link (Version): <TBD>

**Specifications** (Version): <TBD>

**SOW** links (Draft): <TBD>

**Contract** links (Draft): <TBD>

Acquisition folder: 

Needs ticket to PF: None

Acquisition difficult situation & Strategy (if any):   <None>

Project Manager: [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]] 

Project Team: <TBD>

 

Background: [ECM_CN_(BHAP)_AUTOSAR_Classic_Requirements_template_V16_EN_0903.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/826948/826948_ECM_CN_%28BHAP%29_AUTOSAR_Classic_Requirements_template_V16_EN_0903.xlsx)

## 1. Project & Target Baseline

 

Area
Consolidated scope

Customer / project
海纳川技术中心, General Chassis Domain Controller

Target MCU
Infineon TC499, TriCore TC1.8

Compiler
HighTec v4.9.4.1

MCAL / configuration
AURIX TC4x MC-ISAR with EB tresos Studio v29

Target hardware
Customer ECU; TC4xx kit board currently referenced

Development environment
Customer preference: HighTec

Delivery format
Source code with build infrastructure

Functional safety
ECU requires FuSa certification or external assessment

## 2. Confirmed FBL Functional Scope

### Reprogramming concept

- **PBL/SBL architecture**
- **A/B swap** dual-partition reprogramming
- Separate downloadable application entities required
- Customer-defined memory partition between bootloader and application
- Application interface through **NVM**
- Download image format: **.hex**
- **SBL Updater** support
- Recovery through **forced reprogramming / back-door entry** and A/B swap

### Communication and diagnostics

- Physical channel: **CAN FD**
- Transport: **CAN ISO-TP**
- Diagnostic protocol: **UDS**
- Bus transceiver: **TPT1145N**
- Internal code flash
- Internal DFLASH for non-volatile data
- Time-based watchdog handling

### Applicable BAIC specifications

1. **QBAIC C230041-2021**, Reprogramming Specification for Component ECUs over CAN (FD) Bus Based on the UDS Protocol
2. **QBAIC C235845-2022**, Embedded ECU Dual-Partition Reprogramming Specification

### Deliverables indicated

- FBL source code and build infrastructure
- Configuration and integration for TC499 / HighTec / MCAL target
- Documentation, specific document list not yet defined
- Bootloader memory-size compliance, actual limit not yet provided
- Delivery training
- Onsite and remote support, duration not yet defined

## 3. Explicitly Out of Scope Based on Current Input

- Secure Boot
- Secure Flashing
- Software authentication
- Encryption or compression of downloaded data
- Customer-specific security algorithms
- Third-party software or customer CDD integration
- Customer-specific download tool or container generation
- External flash or FPGA reprogramming
- Bootloader gateway functionality

## 4. Critical Open Points Before Estimation / SOW

Priority
Open point
Required clarification

**Blocker**
FBL delivery milestone
First software due date is empty

**Blocker**
Hardware
Confirm customer ECU availability, debugger, schematics, memory map and flashing access

**Blocker**
Memory constraints
Provide exact PBL, SBL, application, A/B-bank and DFLASH layout

**High**
Delivery Acceptance
Define test environment, required reports and pass/fail criteria

**Medium**
Documentation
Specify expected delivery documents

**Medium**
Support
Confirm onsite location, remote hours, response expectations and duration

## 评论

> [!note]+ 2026-09-04 12:28 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> **Proposal:**
>
> Thanks for the updates for this acquisition support,
>
> Could you please let us know the target date when the customer expects to share the specifications with ETAS (contract sign)?
>
> For planning purposes, can we expect a project start in {*}Oct 2026{*}? Based on our previous experience, an initial standard FBL setup would require approximately {*}1-2 weeks{*}, which could be completed by {*}mid-October{*}.
>
> For the BAIC-specific FBL adaptation, we propose to start once the specifications are available. Tentatively, we would reserve around 1.5 months capacity for development, with the schedule to be +refined+ after receiving the OEM specification &estimate.
>
> Please comment/ confirm then I book the resource plan accordingly. Thanks!
>
> Best regards,
> Su Nguyen

-------

> [!note]+ 2026-09-04 12:28 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> **Contract not signed:**
>
> Customer can’t release the Spec before the contract is signed.
>
> About the timeline, please proposal according to existed experience.
>
> **Wanwei REN**

-------

> [!note]+ 2026-09-04 12:26 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Fwd question to [[REN_Wanwei_(ETASCCN1)|REN Wanwei (ETAS/CCN1)]] 
>
> 1.b FBL A/B swap (BAIC spec): would you please share the BAIC Spec? The team would need to estimate & propose the resource plan.
>  * QBAIC C230041—2021 — Reprogramming Specification for Component ECUs over CAN (FD) Bus Based on the UDS Protocol
>  * QBAIC C235845—2022 — Embedded ECU Dual-Partition Reprogramming Specification
>
> Is there any customer expected timeline behind for FBL?

-------

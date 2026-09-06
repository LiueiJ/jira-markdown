---
jira_key: ARC-14384
jira_url: "https://jira.etas-dev.com/browse/ARC-14384"
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
created: "2026-01-15T15:11:56.000+0000"
updated: "2026-06-19T09:29:24.000+0000"
synced-at: "2026-09-06T06:58:54.667Z"
jira-orphaned: false
---

# ARC-14384 PATAC - CADILLAC Project based on VIP24 for CAEA

> [!jira] Accepted ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-06-19T09:29:24.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-14384)

## 描述

**Project Info:**

- Customer: CAEA Shanghai
- Product: ADAS Domain Controller
- **MCU:** **Horizon J6B**
- **OEM: PATAC/VIP24**
- Vehicle Brand: Cadillac
- **SOP: E09/2026**
- **HSM is purchased from Horizon Robotics**

- project revenue: about 600 - 700K EUR
- we want to fight to WIN and delivery it, however only with PF support on below **mitigation 1/2/3/4** need.

**Required support for mitigation 1/2/3/4 below** 

Milestone (ETAS deliver to CAEA):

- 1/31/2026 – 2/14/2026
- PATAC PA0A01 / PA0A1x / PA0A3x / PA0A4x **CAN LIN requirements analysis**
- PATAC **F14 security requirement analysis**
- PATAC PA0A04/PA0A2K **diagnostic requirements analysis**
- EcuExtract/Importer
- CAN/LIN communication
- Onsite support to customer

- **2/28/2026:**
- Customer hardware integration
- Customer application ARXML integration

- **3/30/2026**
- DiagStack configured and tested
- SUM configured, Integrated and tested
- HSM integrated with SSC and tested

 

**RISK and Mitigation:**

**No.**
**Risk Item**
**Impact**
**Probability**
**Impact**
**Mitigation**
**Expected Owner**

1
Requirement Analysis:

Cybersecurity requirement

CAN/LIN requirement

Diagnostic requirement
PATAC requirements, F14 / CYS2300 / national standards are extensive with gaps will lead to unidentified product gaps
Medium
Medium
Requirement analysis for Cybersecurity, CAN, LIN, Diagnostic
ETAS / RTA-CAR Integration Team

2
J6B HSM for GM
Missing J6B HSM will block HSM/SUM integration delivery
High
High
Request HSM PF concretely plan and support for Horizon J6B for GM
ETAS / HSM PF

3
Potential ARXML import issues with UBSW
CAN / UDS ARXML import may generate incorrect configs or fail, block Phase 1 / 2 delivery
High
Medium
Engage UBSW product team for tooling support and prepare local manual or automated configuration scripts
ETAS / UBSW PF

4
Gap between SUM software/RTA-CAR and OEM standards, especially deviated PATAC needs.
Test fail may deviating from OEM standards resulting into feature missing
High
High
SUM PF on-project support for issue fix

RTA-CAR PF on-project support for issue fix
ETAS / SUM PF

ETAS / RTA-CAR Integration Team

5
A-sample hardware bring-up risk
Failure to bring up A-sample hardware could delay Phase 2
Low
Medium
CAEA to validate hardware functionality and MCAL in advance
CAEA

Based on the current assessment and the division of responsibilities (annexed),  it is unlikely we meet the customer's time point in the first phase of engineering services

Based on current evaluation and RASIC from CAEA (attached), we cannot meet the milestone of CAEA regarding phase1

**Assumption**: Phase1 does not involve the features of SUM/GM related enterprise targets

**Suppose**：Phase1 does not include features of SUM/GM

Situation A: If the following Phase1 timeline can be optimized as much as possible based on the above opening points, the CAEA may still have room for discussion and adjustment with us

Situation B: Reply directly to the CAEA according to the following time points, there is a possibility of loss engineering services and license business

 

**Release** **Window** 
**工作包** **Work Package** 
**关键范围** **Key Scope** 
**依赖** **Dependencies** 
**2026.1.14 Comments**

**Customer Request:** **CPPhase1: 2/13/2026** 

 

ETAS Assessment::

-1/16 Delivered the existing version of the J6B development board to run software

- 1/28 Delivered J6B software ported to RTA-CAR12.3.4
- 2/13 CAN/LIN import completed, BSW/RTE/OS code generation
- 2/25 CAEA on-site integration of MCAL for sample A, MCAL configuration and code provided by CAEA to ensure that sample A can be brought upETAS is responsible for configuring and integrating CanTrcv, Can/Lin Driver
- 3/20 Completed the smoke test based on the CAN/LIN/XCP function of the A sample, due to time issues, ETAS only completed the keyframe test and recorded the test results, and could not provide the full test report, before 3/30If there is a problem with the CAEA test, ETAS provides support

搭建BIP Package Baseline
J6B BIP 版本移植和Baseline搭建 (RTA-CAR 12.3.4)
J6B's current BIP Baseline project
GHS compiler, evaluation version (all-in-one version). # Ported to CAR 12.3.4

1. Join LIN

1.16, the current state is issued for customers to understand the code structure

Synchronous ETAS Version Porting (1 week) – Sisi, 1.21|

Baseline basic testing (CAN, power-up, storage).
 
 

Training
RTA-CAR, database generation, RTE read/write interface
Phase 1 delivery
1.22~1.31, 2 to 3 days

CAN configuration and drive integration
Import Pan-Asian Arxml to configure 4-way CANFD
Pan-Asian CAN database, hardware interface.
CAN database, local schematic - CAEA

MCAL driver configuration and integration to form an RTE interface
 
 

CAN communication test and test report, each CAN has sent and received
PA0A01/PA0A1D/PA0A1E 文档
PA specification provided - CAEA Yuan Gong, 1.14

CANNM test and test report
 
Customer requirements: 2.13 PATAC tests the key signals and feeds back on correctness

LIN configuration and master node development
Configure 1 LIN master node based on Pan-Asia LDF
Pan-Asian LDF
 

MCAL driver configuration and integration
 
 

LIN communication test and test report
PA0A4G/PA0A31 文档
 

XCPonCAN integration testing
XCP通讯，A2L生成，XCP on Inca测试
The CAN communication function is normal
Supports CANape, A2L compatible, CANape version 20.0 (CAE can provide).

Time synchronization (see arxml).
 
 
 

OS Task scheduling
 
 
 

Phase2: 3/20/2026
Training
BIP Training
Phase 1 delivery
 

Customer board porting
Porting AUTOSAR engineering to customer A type hardware
Customers provide hardware and proven MCAL configurations
 

Integration testing
 
 

RTE configuration and support
Based on Pan-Asian Arxml, RTE generation is completed to bind application tasks to maintain interface consistency.
Application software interface list, model input.
 

ETAS评估：Phase3: 4/30/2026

 

**Customer demand:** **3/1/2026** 
UDS/Diagnostic Services
Complete UDS, DEM, DCM, and FIM configuration based on Pan-Asian Arxml
Pan-Asian Diagnostic Questionnaire
 

PA0A04/PA0A2K需求分析
J6B Diagnostic Requirements Documentation
 

Diagnostic Services Tests
 
 

SUM module
SUM Spec Requirements Analysis
SUM requirements
 

Complete the configuration of the SUM upper-layer interface to connect with MACT/application requirements.
SUM requirements, MACT tables, RTE interfaces.
 

NVM data management
Configure NvM/Fee to meet DID/DTC data storage and erase policies.
EEPROM specifications, diagnostic data layout, test environment.
 

Integration services and test delivery
Provide on-site support, complete integration tests, and deliver test cases and reports.
CAEA joint team, lab resources, demand base.
 

HSM 集成 (HSM driver available + 3 weeks)
HSM for SSC integration and testing
F14 文档、安全团队支持，**J6B HSM MCAL provided to ETAS, HSM crypto driver for J6B**
Risk Points: ETAS's SUM and Horizon HSM integration will be a risk point

## 关联

- relates to: [[ARC-13556 PATAC Cadillac Platform project based on GM VIP24 for SunWoda]]

## 评论

> [!note]+ 2026-01-16 08:27 · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]
> Info from [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] : a J6B HSM is **no longer required** as the CAEA plan to use the Horizon HSM.
>
> Background info from [[Weigl_Sandra_(ETAS-ECMXPC-Fe3)|Weigl Sandra (ETAS-ECM/XPC-Fe3)]]: Horizion have their own "HSM solution", which is also used by some Bosch projects. As far as we know, their solution is not much more than enabling the HW crypto. 

-------

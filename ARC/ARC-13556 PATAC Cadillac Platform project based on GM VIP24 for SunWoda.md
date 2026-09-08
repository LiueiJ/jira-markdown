---
jira_key: ARC-13556
jira_url: "https://jira.etas-dev.com/browse/ARC-13556"
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
created: "2025-11-05T08:39:50.000+0000"
updated: "2026-06-03T06:43:13.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-13556 PATAC Cadillac Platform project based on GM VIP24 for SunWoda

> [!jira] Accepted ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-06-03T06:43:13.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-13556)

## 描述

**Project Background**

- The Sunwoda project is used in PATAC Cadillac cars.  This is first project transfer from GM-America to PATAC. Based on this project there will a lot extend project in future in PATAC and PATAC will use TC4 as platform. The project is critical for PATAC .
- Project use **CLEA architecture** which is **tailored from VIP24**. No new requirements will add on VIP24
- PATAC want ETAS to develop based on RTA-CAR 12.3.4, Multicore architecture shall reuse from XiaoMi project
- TC4xx HSM is not ready yet in ETAS
- FBL support is required. 
- Decide from PATAC: next release on 11.30 shall not contain GM specific. PATC will send Email to tiers
- **SOP data: June 2026**
  - 6/5/2026---25 Vehicle manufacture for Service Store for promotion.
  - 6/15-6/19-----250 Vehicle manufacture for Service Store for promotion.
  - 6/22-6/26-----300 Vehicle manufacture for  End Customer.
  - 6/29-7/03-----500 Vehicle manufacture for  End Customer

- **Production quality SW is expected by April 2026**

**Decision points** 

1. Use RTA-SUM 3.x and RTA-CAR12.3.4 to develop project
2. Tailoring RTA-SUM 3.x to fit Clear Architecture.
3. PATAC share CAN/DIAG requirements to ETAS and ETAS will develop first working version to Sunwoda using UBSW confgen
4. Customer choose Feishu for communication purposes (CN local application)

**Project Likely start date : Mid Nov'2025**

## 关联

- relates to: [[ARCANA-1176 GM Specification Analysis for PATAC]]
- relates to: [[ARC-14384 PATAC - CADILLAC Project based on VIP24 for CAEA]]

## 评论

> [!note]+ 2026-02-04 08:42 · [[CHEN_Yi_(ETAS-ECMXSF-CN)|CHEN Yi (ETAS-ECM/XSF-CN)]]
> The customer feedback indicates that this project does not require a gateway, and PACYS-1010 is the specification for gateways.

-------

> [!note]+ 2026-02-03 22:31 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> Dear all,
>
>
>
> within the customer specification *PACYS-1007* is several times a reference to the customer specification {*}PACYS-1010{*}, which is not available, yet. Can you please discuss with the customer to get the **PACYS-1010** as well?

-------

> [!note]+ 2025-12-30 02:55 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> Dear [[CHEN_Yi_(ETAS-ECMXSF-CN)|CHEN Yi (ETAS-ECM/XSF-CN)]] or [[LIU_Qing_(ETAS-ECMXSF-CN)_X|LIU Qing (ETAS-ECM/XSF-CN) [X]]],
>
>
>
> for the applicability of the following CRSs some conditions for the customer project are relevant. Can you please let us know whether the conditions are fullfilled or not for this customer project(s):
>
>
>  # *CYS1300* and *CYS1600* are applicable to all ECUs **storing PI** (Personal Information) **and/or SPI** (Sensitive Personal Information) data as determined by ePIA process. [https://epia.cpi.gm.com/]. {*}Follow up with your GM DRE to determine if PI/SPI is applicable{*}.
>  # *CYS5502* is applicable only in case the ECUs are {*}communicating via Erthernet{*}. Is this the case for these projects or not?
>  # *CYS6000* is applicable to all ECUs **supporting the IP Protocol** (like Ethernet, Wi-Fi, Ethernet over USB, Bluetooth Tethering, etc.). Is this the case for these projects or not?
>  # *CYS7100* is applicable to ECUs that {*}use a Non-Android operating system{*}, {*}connect to the GM Backoffice{*}, and {*}perform device registration{*}. Is this the case for these projects or not?
>  # *CYS8200* is applicaple to ECUs that communicate **using TCP/IP protocol outside of the vehicle network** or {*}use Android Auto{*}.

-------

> [!note]+ 2025-12-30 02:35 · [[Schran_Sven_(ETAS-ECMXPC-Fe3)|Schran Sven (ETAS-ECM/XPC-Fe3)]]
> Initial CRSs check for **Product Security** (F14) done. There are different documents related to GM's VIP Platform (former known as Global B) and additional some AddOns from PATAC.
>
>
>
> The analysis status of GM Product Security CRSs are available on the related [confluence page](https://confluence.etas-dev.com/x/YokMFg).
>
>
>
> Valid requested CRSs are:
>  # {+}GM's GB specifications{+}:
>  ** **GB4001** - ECU Unlock Specification v25.25.158 (newest available version: v26.26.165) - {color:#de350b}*not analysed yet*{color}
>  ** **GB4002** - In Vehicle Message Authentication Specification v23.23.154 (newest available version: v26.26.171) - 
>  ** **GB4007** - Supplier Controller Provisioning Portal Manual v23.23.154 (newest available version: v23.23.154) - {color:#de350b}*not analysed* *yet*{color}
>  ** **GB4008** - Secure Diagnostics Requirements v23.23.163 (newest available version: v23.23.163) - {color:#de350b}*not analysed* *yet*{color}
>  ** **GB6002** - Bootloader Specification v1.8.2 - mainly relevant for **FBL Team**
>  ** **GB8001** - AUTOSAR Implementation Specification - **Section 8** Security Requirements v1.15 - {color:#de350b}*not analysed* *yet*{color}
>  ** **GB8002** - AUTOSAR Standard Utility Modules Specification - **Section 7** Security Service Coordinator (SUM_SSC) Requirements v25.25.163 (newest available version: v26.26.167) - mainly relevant for **SUM Team**
>  # {+}GM's CYS specifications{+}:
>  ** **CYS1300** - Secure Isolation Requirements v24.24.155 (newest available version: v24.24.155) - {color:#de350b}*not analysed* *yet*{color}
>  ** **CYS1600** - Secure Storage Requirements v24.24.155 (newest available version: v27.27.176) - {color:#0747a6}*only 8.1% open*{color}
>  ** **CYS2000** - Anti-Reverse-Engineering and Debug Security v23.23.142 (newest available version: v27.27.181) - {color:#de350b}*not analysed* *yet*{color}
>  ** **CYS2300** - HSM Core Requirements v23.23.154 (newest available version: v26.26.170) - **{color:#de350b}must be analysed for VIP{color}**
>  ** **CYS2301** - Hardware Security Module Enhanced Cryptography Suite Specification v23.23.155 (newest available version: v27.27.170) - {color:#0747a6}*only 1.2% open*{color}
>  ** **CYS2310** - Hardware Security Module Programming Requirements v25.25.162 (newest available version: v24.24.178) - **{color:#de350b}must be analysed for VIP{color}**
>  ** **CYS3000** - Embedded System Run-Time Environment Security v23.23.154 (newest available version: v27.27.183) - {color:#0747a6}*only 18.6% open*{color}
>  ** **CYS4000** - Secure Coding Practices v23.23.146 (newest available version: v27.27.176)
>  ** **CYS5502** - Ethernet In-Vehicle Security Requirements v24.24.163 (newest available version: v27.27.180) - {color:#0747a6}*only 15.7% open*{color}
>  ** **CYS6000** - Firewalls and Packet Filters v25.25.162 (newest available version: v27.27.180) - {color:#0747a6}*32% open*{color}
>  ** **CYS8200** - Transport Layer Security Requirements v24.24.153 (newest available version: v27.27.171) - **{color:#0747a6}48,8% open{color}**
>  ** **CYS9000** - Random Number Generator Security v20.20.131 (newest available version: v25.25.165) - {color:#0747a6}*only 4.7% open*{color}
>  ** **CYS9100** - The Per-ECU Password Utility v23.23.151 (newest available version: v24.24.176) - **{color:#0747a6}54,6% open{color}**
>  # {+}PATCYS specification AddOns{+}:
>  ** **PACYS1007** - Security Information Alarm Mechanism v3.0.0 - {color:#de350b}*not analysed* *yet*{color}
>  ** **PACYS1012** - PATAC_Add_On_Static_Code_Check_Specification v1.1.0 - {color:#de350b}*not analysed* *yet*{color}
>  ** **PACYS1018** - Hardening Add on Specification v1.0.4 - {color:#de350b}*not analysed* *yet*{color}
>  ** **PACYS1020** - PATAC_Vulnerability_Management_Requirement v1.0 - {color:#de350b}*not analysed* *yet*{color}
>  ** **PACYS7003** - Vehicle Charge Module Isolation Specification v1.0.0 - {color:#de350b}*not analysed* *yet*{color}
>  ** **PACYS-A001** - Cybersecurity Requirements Specification for Data Security v2024_09_10 - {color:#de350b}*not analysed* *yet*{color}
>
>
>
> to be continued...

-------

> [!note]+ 2025-12-22 08:17 · [[CHEN_Yi_(ETAS-ECMXSF-CN)|CHEN Yi (ETAS-ECM/XSF-CN)]]
> There are too many PATAC specs and the compressed package is too large to upload. You can obtain all the specs in this link:[https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000025287_PJ_ECM_Sunwoda_Autosar_CP_PDF3_project_SW_T/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments] 

-------

> [!note]+ 2025-12-17 01:54 · [[LIU_Qing_(ETAS-ECMXSF-CN)_X|LIU Qing (ETAS-ECM/XSF-CN) [X]]]
> Related specs：
>
> [https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000025287_PJ_ECM_Sunwoda_Autosar_CP_PDF3_project_SW_T/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments/%E4%BC%81%E6%A0%87.rar]
>
> [https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000025287_PJ_ECM_Sunwoda_Autosar_CP_PDF3_project_SW_T/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments/%E4%BC%81%E6%A0%8727.74.0%20%E8%A1%A5%E5%85%85.rar]
>
> [https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000025287_PJ_ECM_Sunwoda_Autosar_CP_PDF3_project_SW_T/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments/%E4%BF%A1%E6%81%AF%E5%AE%89%E5%85%A8F14%E8%A7%84%E8%8C%83.zip]
>
> [https://etasdms.de.bosch.com/svn/Projects.RTA/01_Projects/3000025287_PJ_ECM_Sunwoda_Autosar_CP_PDF3_project_SW_T/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments/F14_SGM_program_MY26_C1UL-2_PHEV_PDF_20250704.xlsx]

-------

> [!note]+ 2025-11-06 06:43 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> From [[Risoli_Antonio_(ETAS-ECMXPC-Tn1)_X|Risoli Antonio (ETAS-ECM/XPC-Tn1) [X]]]  [  [^RE_ Supported RTA-CAR version for GM-SUM VIP 23_24.msg]
>
> On Friday, 31 October 2025, RTA-CAR UBSW VIP **12.3.4** was released, which includes **RTA-SUM 2.5.0** supporting **VIP24 only** (as agreed with GM, no VIP23 support).
>
> **Key points to address your questions:**
>  # **VIP23/VIP24 support:** The latest release (12.3.4) supports VIP24; VIP23 is not included per GM alignment.
>  # **RTA-SUM version & download:** Use {*}RTA-SUM 2.5.0{*}, included with [RTA-CAR UBSW VIP 12.3.4](https://artifactory.etas-dev.com/artifactory/rtacar-generic-release-local/release/RTA-CAR_UBSW_VIP/RTA-CAR_UBSW_VIP_V12.3.4_Windows.zip). After installation, all related documentation is available at:
> C:\ETAS\RTA-CAR_UBSW_VIP_12.3.4\Documents\RTA-SUM_2.5.0
>  # **Migration notes (2.5.0 context):** Version 2.5.0 is essentially 2.3.X with interfaces adapted to Autosar 21.11+, plus support for:
>  * Burst message reception in SSC
>  * SUSD wakeup update (uses the last NvM power mode value if CAN messages haven't arrived/validated yet)
>
> If you're already familiar with the old VIP24, migrating the SUM will be relatively smooth, BSW migration will require more effort.
>  # **Reference for porting:** You can refer to the ongoing RIP 24 porting to the released version by the FAE team:
> RTAFAE-3487
>
> **Regarding training:** Yes, CN-Hub will benefit from some familiarization sessions on using GM SUM with RTA-CAR for the Sunwoda project. The documentation and the FAE Jira ticket should provide a solid starting point.
>
> Many Thanks [[Risoli_Antonio_(ETAS-ECMXPC-Tn1)_X|Risoli Antonio (ETAS-ECM/XPC-Tn1) [X]]] for your speedy response and support. 

-------

> [!note]+ 2025-11-05 08:43 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> [[LIU_Qing_(ETAS-ECMXSF-CN)_X|LIU Qing (ETAS-ECM/XSF-CN) [X]]]  please add details about FBL and HSM once you have access to specs. 
>
> [[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]] fyi

-------

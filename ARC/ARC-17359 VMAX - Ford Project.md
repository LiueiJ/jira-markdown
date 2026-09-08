---
jira_key: ARC-17359
jira_url: "https://jira.etas-dev.com/browse/ARC-17359"
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
created: "2026-08-14T10:18:51.000+0000"
updated: "2026-09-04T03:14:45.000+0000"
synced-at: "2026-09-08T02:03:07.632Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-17359 VMAX - Ford Project

> [!jira] New ·  · [[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]] · 更新于 2026-09-04T03:14:45.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-17359)

## 描述

Currently in acquisition . 90% chance of winning. 

Initial information is documented in the [ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN.xlsx!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/820373/820373_ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN.xlsx) . 

More information to follow.

## 评论

> [!note]+ 2026-09-04 03:00 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> I stored the file in Accq folder: [Acquisition Project Docs](https://bosch.sharepoint.com/:f:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs?d=w2cfe21a0e0e6422a9f53bab7c14ccaec&csf=1&web=1&e=wuqGVZ)/ [VMAX-Ford/ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN0902.xlsx](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/VMAX-Ford/ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN0902.xlsx)

-------

> [!note]+ 2026-09-02 07:44 · [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]]
> update project requirement ，refer to"ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN0902.xlsx"

-------

> [!note]+ 2026-08-27 09:12 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> ARC-17439 - In the meanwhile, could you check if any assets could share or support? [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 

-------

> [!note]+ 2026-08-27 09:09 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]] Ford specifications after NDA completion (ARC-17443)
>
> - can it be available within this week? The delivery E/Oct is superb aggressive delivery schedule.

-------

> [!note]+ 2026-08-27 06:33 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> **Decision / Ownership**
>  * China team has no capacity for RIP development; {*}VN team is requested to evaluate and potentially take over the RIP scope{*}, in addition to the ongoing Ford FBL work. [[HE_Jiankang_(ETAS-ECMXSF-CN)|HE Jiankang (ETAS-ECM/XSF-CN)]]  explicitly requested BGSV's team to assess the effort and feasibility.
>  * Scope: both RIP &FBL
> ### Key Project Scope
>
> **AUTOSAR Classic**
>  * No SecOC.
>  * VMAX uses its own HSM.
>  * Current scope includes only basic protocol stack (no Ethernet, LIN, J1939, etc.).
>  * RTA-BSW is expected to cover current requirements.
>
> **BIP (Basic Integration Package)/ AUTOSAR CP**
>  * ETAS to provide a minimal working system first, then support application porting.
>  * BIP includes standard functions (e.g., diagnostics communication) but excludes Ford proprietary adaptations.
>  * Ford-specific BSW requirements (e.g., DM, NM) will be decomposed by VMAX and provided to ETAS for implementation.
>  * Memory protection (SC3) configuration to be added on top of BIP.
>  * Customer target: {*}BIP delivery by end of Oct 2026{*}.
>
> **FBL (Flash Bootloader)**
>  * Two-stage architecture: {*}PBL + SBL{*}.
>  * Phase 1: Base bootloader without Ford adaptation.
>  * Phase 2: Ford-specific adaptation.
>  * Customer target:
>  ** Phase 1 delivery: **end of Sep 2026**
>  ** Phase 2 delivery: {*}end of Oct 2026{*}. 
>
> ### Technical Prerequisites
>
> Customer (VMAX) will provide:
>  * XDS110 debugger.
>  * Project board with harness.
>  * MCAL project and code.
>  * Memory layout information.
>  * Ford testing tools (DET/DSP).
>  * Ford specifications after NDA completion. 
>
> ### Open Items for ETAS
>  * Confirm whether RTA-SEC is still required.
>  * Assess BIP delivery feasibility for October.
>  * Assess FBL delivery feasibility for September/October milestones.
>  * Confirm availability of Ford baseline/FBL assets from previous projects.
>  * Assign engineering support for TI F29H85x, TI compiler, and SC3 memory protection setup. 
>
> ### Customer Milestones
>  * **Dec 2026:** VMAX delivers A-sample software to Ford.
>  * **Mar 2027:** VMAX delivers full-function software to Ford.

-------

> [!note]+ 2026-08-27 06:26 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> **Meeting minutes** shared from [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]] on 25.Aug,
>
> The following are the requirements clarified during today’s meeting with Vmax. To avoid any ambiguity in the translation, the original Chinese version is attached below the email for your reference. Please review it..
>
>
>
>
>  # **Classic AUTOSAR Requirement Clarification**
>
>  * This project will {*}not use SecOC{*}.
>  * The HSM used in this project is {*}Vmax’s self-developed HSM{*}.
>  * This project only involves the **basic protocol stack** and does **not** involve **Ethernet, LIN, J1939, etc.** The current quoted **RTA-BSW** can cover the project requirements. If there are additional protocol stack requirements in later phases, they can be purchased separately.
>  * **To be confirmed:** Whether **RTA-SEC** is still required @Vmax
>
>
>  # **OS Port Requirement Clarification**
>
>  * Chip: **F29H85x**
>  * Compiler: **TI V4.99.3**
>  * In the early phase, Vmax will provide ETAS with one {*}XDS110 debugger{*}; ETAS will handle this on its own later.
>  * In the early phase, Vmax will provide ETAS with one {*}project board with wiring harness{*}.
>  * Vmax will provide ETAS with the **configured MCAL project and code** (it is recommended to remove the {*}Wdg configuration{*}).
>  * **To be confirmed:** The delivery timing of the debugger, project board, and MCAL @Vmax
>
>
>  # **BIP Sample Project + Ford Spec Requirement Clarification**
>
>  * Vmax requires ETAS to first get the **minimal system** up and running, and then perform application porting on top of this system.
>  * The BIP provided by ETAS shall include basic functions such as {*}diagnostic communication{*}, but shall **not** include {*}Ford proprietary specification adaptation{*}.
>  * For Ford proprietary spec adaptation, Vmax will break down Ford’s BSW-related requirements and provide them to ETAS (for example, {*}DM, NM{*}, etc.), and ETAS will perform the related adaptation.
>  * ETAS will further iterate and implement **memory protection-related configuration** based on the BIP.
>  * Vmax expects the **BIP delivery** by the {*}end of October{*}.
>  * **To be confirmed:**
>
>  # Whether the BIP delivery schedule can be met @ETAS
>  # Whether the Ford specification can be shared with ETAS at this stage, and when it can be shared @Vmax
>
>
>  # **FBL Requirement Clarification**
>
>  * The bootloader in this project needs to support a {*}two-stage startup architecture with PBL + SBL{*}. The {*}SBL runs in RAM and can be erased{*}, while the {*}PBL is not erasable{*}.
>  * In the first phase, the FBL shall provide a **base version bootloader** without Ford proprietary specification adaptation. In the second phase, it shall be adapted to Ford proprietary specifications.
>  * Vmax expects the **first phase** to be delivered by {*}the end of September{*}, and the **second phase** by {*}the end of October{*}.
>  * **To be confirmed:**
>
>  # The memory partition definition and address layout @Vmax
>  # Provide Ford’s proprietary test tools **DET/DSP** to ETAS for bootloader testing; please confirm the delivery timing @Vmax
>  # Confirm whether the flashing channel is **CAN** or **CAN FD** @Vmax
>  # Evaluate whether the delivery schedule for the two FBL phases is feasible @ETAS
>
>
>  # **Project Milestone Confirmation**
>
>  * By the {*}end of December 2026{*}, Vmax will deliver the **A-sample software** to Ford.
>  * By the {*}end of March 2027{*}, Vmax will deliver the **full-function software** to Ford.
>
>
>
>  ** 
>  # Classic Autosar 需求澄清
>
>  * 本项目不使用SecOC功能
>  * HSM使用Vmax自研HSM
>  * 本项目仅涉及基础协议栈，不涉及ETH、LIN、1939等，当前报价中的RTA-BSW可cover项目需求，后续项目如有其他协议栈需求可增购
>
>            待确认：确认RTA-SEC是否还需要@Vmax
>  # OS Port需求澄清
>
>  * 芯片F29H85x 编译器TI V4.99.3
>  * 前期Vmax给ETAS提供一套“XDS110调试器”，后期ETAS自行解决
>  * 前期Vmax给ETAS提供一套带线束的项目板子
>  * Vmax提供配置好的MCAL工程及代码给到ETAS(建议去掉wdg配置)
>
>           待确认：确认调试器、项目板、MCAL的提供时间@Vmax
>  # BIP 示例工程+Ford Spec需求澄清
>
>  * Vmax需要ETAS提供最小系统先运行起来，并在此系统之上做应用移植
>  * ETAS提供的BIP包含如诊断通信等基本功能，不包含Ford 企标适配
>  * 关于Ford企标适配，Vmax把Ford 关于BSW的需求拆解给到ETAS（例如DM、NM等），ETAS做相关适配
>  * ETAS在BIP基础上迭代实现memory protection相关配置
>  * Vmax希望BIP交付时间为10月底
>
>           待确认：1. BIP交付时间是否能满足 @ETAS
>
>                          2.Ford SPEC现阶段能否共享给ETAS，什么时候可以共享给ETAS @Vmax
>  # FBL 需求澄清
>
>  * 本项目Bootloader 需要支持PBL+SBL两级启动，SBL在 RAM中运行可擦除，PBL不可擦除
>  * FBL第一阶段提供base 版bootloader不适配Ford企标，第二阶段适配Ford企标
>  * Vmax希望第一阶段在9月底交付，第二阶段10月底交付
>
>          待确认：1.提供memeory 分区定义几地址规划 @Vmax
>
>                         2.提供Ford专有测试工具DET/DSP给到ETAS测试bootloader，请确认提供时间@Vmax
>
>                         3.确认刷写通道是CAN 还是CANFD? @Vmax
>
>                         [4.评估FBL两个阶段释放时间是否满足 @ETAS](mailto:4.%E8%AF%84%E4%BC%B0FBL%E4%B8%A4%E4%B8%AA%E9%98%B6%E6%AE%B5%E9%87%8A%E6%94%BE%E6%97%B6%E9%97%B4%E6%98%AF%E5%90%A6%E6%BB%A1%E8%B6%B3@ETAS)
>  # 项目时间节点确认
>
>  * 2026年12月底 Vmax给Ford交付A样软件
>  * 2027年3月底Vmax给Ford交付全功能软件
>
>
>
>
>
> **Yanan WU**

-------

> [!note]+ 2026-08-26 09:03 · [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]
> latest updates from [[WU_Yanan_(ETASCCN1)|WU Yanan (ETAS/CCN1)]]  attached here : [^RE_ [RTA-RIP][VMAX-Accq][Ford] Ford - Motor controller RTA-CAR __RTAXIP-4053.msg]

-------

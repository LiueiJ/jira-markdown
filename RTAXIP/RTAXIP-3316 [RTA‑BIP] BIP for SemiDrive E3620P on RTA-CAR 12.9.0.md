---
jira_key: RTAXIP-3316
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3316"
server: etas
kind: motivation
type: Story
status: Closed
priority: High
project: RTAXIP
assignee: tgu9hc
reporter: puy1hc
tags: [XIP-Projects]
components: []
fix-versions: [Ecarx-bip-cde-E3620ghs-1290]
epic: null
parent: null
created: "2026-03-13T11:06:47.000+0000"
updated: "2026-08-20T05:17:13.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-3316 [RTA‑BIP] BIP for SemiDrive E3620P on RTA-CAR 12.9.0

> [!jira] Closed · High · [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]] · 更新于 2026-08-20T05:17:13.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3316)

> 标签：#jira/label/xip-projects

## 描述

EcarX requested BIP/OTA for **SemiDrive EvaluationBoard E3620P** 

- Hardware  **EvaluationBoard E3620P** and Customer board later
- Compiler: **GHS 2022.1.4**
- **Feature:**

**EcuExtract:**

- ETAS BIP NON-OEM specific template EcuExtract (DEXT, DBC, LDF, TpGw, ETH)
  description will be used for automatic configuration generation to deploy system
  description for I-Signal communication, Network management, Diagnostic Description etc.

 

**CAN & CANSM & COM**

- CAN Communication: Provides one channel of CAN communication with a baud rate of
  5Mbps, both sending and receiving in polling mode.
- Example DBC File: Provides the DBC file ETAS_CanCom.dbc for application messages,
  containing 4 standard CAN messages (2 receive, 2 send), all are FULLCAN type.
- System Description File: Provides SysDesc_IpduM.arxml, including a multiplexed Tx/Rx
  PDU use case.
- Periodic Transmission: Sends messages triggered periodically, with unused bits padded
  with 0xFF.
- CompuMethod Example: Provides examples of CompuMethod for receiving and sending
  signals.
- ComIPduGroup Management: Enables and disables ComIPduGroup through BswM,
  divided into two groups based on the sending and receiving directions of application
  messages.
- Test SWC and Code: Provides test SWCs (INP_SWC, OUTP_SWC) and sample test
  code for application messages.
- BusOff Recovery Strategy: Provides fast and slow recovery strategies and fault handling
  mechanisms for BusOff.

 

**CAN & NM**

- Network Management Implementation: Provides an example of network management
  implementation based on AUTOSAR.
- Active Wakeup: Provides an example of active network wakeup.
- Network Management DBC File: Provides ETAS_CanNm.dbc, containing 1 send and 1
  receive NM message.
- User Data Interface: Supports receiving and sending 6-byte user data through the user
  data interface function.
- Callback Function Examples: Provides definitions for NM state transition notification
  callback functions and NM message reception notification callback functions.
- Test SWC and Code: Provides test SWC (NmUT) and sample test code for network
  management, supporting user data read/write, network request/release, and callback
  function definitions.

 

**DCM**

- DEXT File Import: Supports DEXT file import.
- Diagnostic Service Support: Supports the following
  services: 0x10, 0x27, 0x3E, 0x11, 0x28, 0x85, 0x22, 0x2E, 0x19, 0x14, 0x2F, 0x31,0x23,0
  x34(Provide configuration only),0x36(Provide configuration only), 0x37(Provide
  configuration only).
- UDS Buffer: The RX/TX buffer size for UDS transmission is 4095.
- NRC78 Limit: The maximum number of NRC78 responses for a single diagnostic service
  is 5.
- Session Switch Interface: Provides Rte mode switch interfaces for
  Default/Programming/Extended sessions.
- Bootloader Jump: Provides the processing flow interface before jumping to Bootloader for
  UDS 10 02 service.
- NRC Before Bootloader Jump: Sends NRC 0x78 before jumping to Bootloader.
- DID Read Limit: A maximum of 5 DIDs can be read at a time.
- Rte Interfaces: Provides Rte interfaces for DID-supported 2E write service, 2F IO control
  service, 22 read service, and 31 routine control service.
- Security Access Interface: Provides Rte interfaces for key seed acquisition and key
  comparison functions for 27 service.
- Mode Switch Interfaces: Provides Rte mode switch interfaces for EcuReset and
  ComControl services.
- Test SWC: Provides DiagUT test SWC for DCM services.

 

**CANTP**

- Custom Padding: Supports custom padding, with the default padding byte as 0x00.
- Full Duplex Mode: Configures CanTp in full duplex mode.
- Addressing Mode: Configures CanTp in Normal addressing mode.
- Transmission Cancellation: Enables CanTp transmission cancellation.
- PDU Channel Configuration:
  o Physical Request: 0x740
  o Functional Request: 0x7DF
  o Physical Response: 0x748.

 

**DEM**

- Operation Cycle: Sets the operation cycle to POWER.
- DTC Examples: Provides 1 BSW DTC and 11 ASW DTC examples.
- Snapshot Record Encoding: Uses CONFIG type for snapshot record encoding.
- Snapshot Record Examples: Provides snapshot record and data examples
  (e.g., 0x10B, 0x112, 0xD001, 0xD901, 0xE101).
- Extended Data Support: Supports extended record encoding, including fault occurrence
  counter, fault pending counter, aged counter, and ageing counter.
- NVM Storage: Supports NVM storage for DTCs, with storage type as PrimaryMemory.
- Rte Interfaces: Provides Rte interfaces for DTC setting and status reading.
- Test SWC: Provides DiagUT test SWC for DEM services.

 

**TpGw:**

- Support TpGw ETH-CAN

 

**Power Management (Startup & Shutdown):**

- Startup and Shutdown Phases: AUTOSAR EcuM manages startup and shutdown phases
  (Startup-I, Startup-II, RUN, POST-RUN, PRE-SHUTDOWN, SHUTDOWN) with BswM.
- Timestamps: EcuM measures timestamps for startup and shutdown.
- Wakeup Source Interface: Provides RE_ExeMgr_GetWakeupSource interface to get the
  wakeup source (IO).
- Mode Switch Interfaces: Provides user mode switch interfaces for RUN -> APP_RUN and
  APP_RUN -> POST-RUN.
- GoOff Interfaces: Supports user-flexible integration
  for EcuM_OnGoOffOne and EcuM_OnGoOffTwo.
- Shutdown Test: Provides TstM_PostRun() for shutdown
  testing, NvM_Integration_WriteAll() for NVM storage, RE_ExeMgr_ExecuteShutdown() for
  user actions, and Ecu_SwitchOff() for power supply shutdown.
- Test SWC: Provides test SWC for power management.

 

**Wakeup & Sleep**

- Wakeup: Supports active wakeup coordinated with AUTOSAR NM.
- Sleep: Supports MCU power-down.
- Test SWC: Provides test SWC for wakeup and sleep.

 

**NVM**

- NvBlock Examples: Provides 3 NvBlock examples (Cyclic, Immediate, Shutdown).
- Callback Notification: Supports notifying SWC through a callback function after completing
  a block write operation.
- Block Types: All NvBlocks are Native type, each containing 1 RamBlock and 1 RomBlock.
- Initialization Phase: Supports NvM_ReadAll.
- Default Data Recovery: Supports restoring default data from ROM during initialization if
  Flash data is corrupted.
- Shutdown Phase: Supports NvM_WriteAll.
- Test SWC: Provides NvMUT test SWC and sample test code.

 

**WDGM WdgM Master & Satellite**

- Supervision Modes: Supports Alive, Deadline, and logical supervision, divided into Fastmode
  and Slowmode.
- Rte Interfaces: Provides Rte interfaces for getting WdgM global status, supervised entity
  status, mode setting, global supervision status, first expired entity ID, and WdgM reset.
- WdgIf Interfaces: Supports internal watchdog (MCAL integration).
- Split WdgM instance on different cores. Master on Core0, Satellite on other cores.
- Master set mode, collect satellite status and perform reset.
- Test SWC: Provides test SWC for WdgM.

 

**OS**

- Multi-Core Configuration: SC1 multi-core configuration, with each core corresponding to one
  OsApplication.
- Stack Monitoring: Enables stack monitoring, supporting StackOverrunHook() for user
  extension.
- Error Handling: Supports ErrorHook() for handling integration errors.
- Shutdown Hook: Supports Os ShutdownHook() for coordination with EcuM_Shutdown().
- Default Interrupt Handler: Provides a default handler for unhandled interrupts.
- Schedule Table: Schedules Rte-generated tasks.

 

**EcuHw Service & MCAL**

- MCAL Integration: Configures and integrates MCAL modules required for BIP (MCU, PORT,
  DIO, Timer, CAN, etc.) and related interrupts.

 

**Memory Allocation**

- Software Partitioning: Supports software partitioning and memory map generation.
- Reference Files: Provides reference linker files and startup code.

 

**Baseline Environment**

- Build Environment: Python SCons-based build environment.
- Compiler Integration: Integrates target compilers.
- One-Click Build: Supports one-click fast build.
- User Environment: Provides a unique user environment adaptable to other compilers.
- Hex Post-Processing: Supports user-extended Hex post-processing.

 

**Rtm & StackM & Tstm**

- CPU Load Calculation: Supports CPU load calculation for each core.
- Stack Monitoring: Supports stack usage calculation for each core.

 

**XCP onCan**

- Import DBC for XCPonCan.
- SeedNKey based access authorization for measurement, calibration.
   -Timestamp based measurement synchronization.
- Dynamic DAQ.
- Measurement rasters: 10ms,50ms,100ms.
- One-page SERAM Calibration management (WP).
- Test SWC: Provides test SWC for XCP.

 

**Eth SomeIp-SD & SomeIpTp & EthTSyn & DoIp**

- UDP/TCP/SomeIp-SD/EthTSyn/DoIp described by system description arxml file.
- UDP: 4Bytes signal.
- TCP: Signal length 2816Bytes, support signal-based SOME/IP communication, support
  SOME/IP Transformer.
- SomeIpTp: RTM information sent via SomeIpTp protocol.
- DoIp: UDP for TEST_EQUIPMENT AND DISCOVERY, TCP for TCP_DATA.
- Eth Rx/Tx: The BSW Ethernet stack (e.g., TCPIP) shall support MCAL configuration for
  reception and transmission of ethernet packages in Interrupt mode.
- Test SWC: Provides test SWC for Eth.

## 关联

- is depended on by: [[RTAXIP-3705  [RTA‑BIP][ECARX][SemiDrive] TpGW integration and testing]]
- is satisfied by: [[RTAXIP-3309 [OppEcarX-bip]_cde-SemiDrive E3620-1290]]
- is satisfied by: [[RTAXIP-3467 [SemiDrive][E3620B] Porting BIP Tc397 to E3620B-Tasks Run successfully]]
- is satisfied by: [[RTAXIP-3420 [SemiDrive] Collect all inputs for start (compiler, MCAL, Os port)]]
- is satisfied by: [[RTAXIP-3421 [SemiDrive] Bring up Hardware (Find demo software and run on hardware with T32)]]
- is satisfied by: [[RTAXIP-3422 [SemiDrive] MCAL generation]]
- is satisfied by: [[RTAXIP-3450 [SemiDrive] COBRA Memlay generation]]
- is satisfied by: [[RTAXIP-3466 [Semidrive][E8620] Porting Startup code]]
- is satisfied by: [[RTAXIP-3510 [SemiDrive][E3620B] Lin Integration and Testing]]
- is satisfied by: [[RTAXIP-3511 [SemiDrive][E3620B] Nvm Integration and Testing]]
- is satisfied by: [[RTAXIP-3650 [RTA‑BIP][ECARX][SemiDrive] Eth integration and Testing]]

## 评论

> [!note]+ 2026-08-20 05:17 · [[FENG_Tom_(ETAS-ECMXSF-CN)|FENG Tom (ETAS-ECM/XSF-CN)]]
> BIP final package ready, QG2 planed on 21st Aug. I'll close this ticket.

-------

> [!note]+ 2026-07-23 10:36 · [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]
> The SOW has been copied to the description of this ticket.

-------

> [!note]+ 2026-07-22 08:13 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]] : Can you copy contain of feature list to here? 

-------

> [!note]+ 2026-07-22 07:59 · [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]]
> Here's the latest SOW for this project [^ETAS AUTOSAR for EcarX SemiDriveE36XXGHS E111 SOW V09.pdf]

-------

> [!note]+ 2026-07-22 02:36 · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]
> [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]] , [[Nguyen_Minh_Tuan_(MSETA-Hub-CN)|Nguyen Minh Tuan (MS/ETA-Hub-CN)]] : Can you help to share feature list of this project in this ticket?

-------

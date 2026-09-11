---
jira_key: RTAXIP-3323
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3323"
server: etas
kind: motivation
type: Story
status: Closed
priority: High
project: RTAXIP
assignee: "[[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]"
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/xip-projects]
fix-versions: []
epic: null
parent: null
created: "2026-03-16T06:54:43.000+0000"
updated: "2026-09-03T07:52:34.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

PATAC Specification location: [Projects.RTA/01_Projects/3000003534_PJ_RTA_XIP/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments/15_RequirementsGathering/CAEA/02_Specs — VisualSVN Server](https://etasdms.de.bosch.com/!/#Projects.RTA/view/head/01_Projects/3000003534_PJ_RTA_XIP/01_Draft/20_Requirements_and_Design/10_RequirmentsDocuments/15_RequirementsGathering/CAEA/02_Specs)

- Hardware: J6B Customer Board
- RTA-CAR Version: UBSW VIP 12.3.4 （RTE: 12.9.0 because Data Conversion shall be supported between float32 and UINT)
- HSM : Horizon provided driver
- Customer Input files:
  - System Description ARXML file
  - DEXT ARXML file
  - MACT Table in excel
  - Fault Table in excel
- 4 Channels CANFD Communication
  - Can Transceiver: TCAN1145
  - Signal Routing between Can and Lin by Com Callout
  - Selective wake up by CAN Transceiver
- 1 Channel LIN Communication
- XCP on CAN. Verified on CANape environment. 1 page calibration.
- SUM:
  - SSC Message MAC Generation (Transmitter)
  - SSC Message MAC Verification (Receiver)
  - 6 SSC Messages are MIXED (Triggered + Period) which is  not supported by UBSW 12.3.4. Workaround: Triggered by SWC.
  - Sync Counter Message (Transmitter)
  - Freshness Counter Generation (Transmitter)
  - Freshness Counter Verification (Receiver)
  - Key Provisioning: Support for loading symmetric keys into security peripheral memory slots (key slots) using M1, M2, and M3 inputs
  - ARC rolling counter Generation and Verification. Support multiple ARC signals in one ComIPdu by editing SSC Code manually.
  - ERRH Error handling for:
    - MAC Verification Error: FailedSecurity - DEM Event 0xXXXX83
    - ARC Verification Error: FailedContinuousOperation - DEM Event 0xXXXX82
    - KeySlotVerify Error per Slot - DEM Event 0x500X00
    - KeySlotVerify Error Overall - 0xD96200
  - LossOfCom error is handled by customer integration code in Com Callback function by themselves.
  - Ssc Diag Features:
    - DID: F080, F081, F084, E05F
    - RID: 200, 204, 205, 21E, 272, 3D9, 4DB, 4DC

## 关联

- is satisfied by: [[RTAXIP-3126 Position 0040: Hardware integration package (HIP) for RTA-CAR]]

## 评论

> [!note]+ 2026-07-20 07:50 · [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]
> Hi [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] 
> I added feature list in description. [[XU_Yinchuan_(ETAS-ECMXSF-CN)|XU Yinchuan (ETAS-ECM/XSF-CN)]] please check if anything else can be added.

-------

> [!note]+ 2026-07-17 07:40 · [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]]
> [[TAO_Sisi_(ETAS-ECMXSF-CN)|TAO Sisi (ETAS-ECM/XSF-CN)]]  or [[XU_Yinchuan_(ETAS-ECMXSF-CN)|XU Yinchuan (ETAS-ECM/XSF-CN)]] , could you please just add the feature list of this project here as reference for further incoming projects?

-------

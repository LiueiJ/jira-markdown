---
jira_key: RTAXIP-4053
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-4053"
server: etas
kind: motivation
type: Story
status: In Acquisition
priority: Medium
project: RTAXIP
assignee: nus1hc
reporter: hejcsgh
tags: [XIP-Local-Accq]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-20T03:54:44.000+0000"
updated: "2026-09-04T10:00:10.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-4053 [RTA-RIP][VMAX-Accq][Ford]- Motor controller RTA-CAR

> [!jira] In Acquisition · Medium · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]] · 更新于 2026-09-04T10:00:10.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-4053)

> 标签：#jira/label/xip-local-accq

## 描述

**Needs ticket /Acquisition support**

**Customer**: VMAX

**Project**: Ford - Motor controller RTA-CAR

**Phase**: acquisition &#91;x&#93;, Initial phase &#91;o&#93;

**Motivation** ($): **200W CNY**

**SOR** link (Version):  <TBD>

**Requirements Gathering** link (Version): <TBD>

**Specifications** (Version): <TBD>

**SOW** links (Draft): <TBD>

**Contract** links (Draft): <TBD>

Acquisition folder: [VMAX-Ford](https://bosch.sharepoint.com/:f:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/VMAX-Ford?d=wccead0ee46134718be0d3f3e7db140e7&csf=1&web=1&e=lOchkf)

Needs ticket to PF: [https://jira.etas-dev.com/browse/ARC-17359](https://jira.etas-dev.com/browse/ARC-17359)

Acquisition difficult situation & Strategy (if any):   <None>

Project Manager: <TBD>

Project Team: <TBD>

Customers
Project
Project win rate
Project budget
Project begins
Project ended
Technical service content
August
September
October
November
December

VMAX
Ford - Motor controller RTA-CAR
80%
200W
Sep-26
Feb-27
● RIP package development compatible with Ford corporate standards
0.5
5
3
3
2

Background:

#### 1. Severe Resource Gap from September

- The South China team expects to have only **three engineers available from September**, while multiple ongoing and new projects require support. HE Jiankang explicitly states that manpower will be insufficient even with four engineers.
- Several projects are marked as**"无人开发" (no developer assigned)**.

#### 2. High-Priority Opportunity: VMAX

- Customer: **VMAX**
- Project: **Ford Motor Controller RTA-CAR**
- Win rate: **80%**
- Budget: **200W CNY**
- Duration: **Sep 2026 – Feb 2027**
- Scope:
  - Ford-specific RIP package development
  - Ford-specific FBL development
  - Technical support and training
- Estimated demand:
  - Aug: 0.5 FTE
  - Sep: 5 FTE
  - Oct: 3 FTE
  - Nov: 3 FTE
  - Dec: 2 FTE
- Current status: **No developer assigned.**

## 关联

- relates to: [[LUX-258 VMAX-RIP-cdhm-F29H85x-1290]]

## 评论

> [!note]+ 2026-09-04 09:32 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> [ETAS-AUTOSAR SOW to Vmax V4.0.docx](https://bosch.sharepoint.com/:w:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/VMAX-Ford/ETAS-AUTOSAR%20SOW%20to%20Vmax%20V4.0.docx?d=wd97e601e46d04d5eb972fb3e88abc478&csf=1&web=1&e=zbkDAr) stored the SharePoint [Acquisition](https://bosch.sharepoint.com/:f:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs?d=w2cfe21a0e0e6422a9f53bab7c14ccaec&csf=1&web=1&e=PqODJh) folder.
>
> Email Exchanged: [^Fw 回复：VmaxFord 项目需求澄清会议纪要-1.msg]
>
>
>
> ^Project requirement gathering, inputs for SOW: [Acquisition Project Docs](https://bosch.sharepoint.com/:f:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs?d=w2cfe21a0e0e6422a9f53bab7c14ccaec&csf=1&web=1&e=wuqGVZ)/ [VMAX-Ford/ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN0902.xlsx](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/VMAX-Ford/ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN0902.xlsx)^

-------

> [!note]+ 2026-09-04 09:29 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Updates from **Yanan WU** on 09.04.26
> **Meeting Minutes between ETAS & VMAX**
>  # How many CANs? Vmax replied: 1 channel
>  # Whether the project DBC needs to be imported into the BIP, if so, please confirm the date   DBC provided to ETAS on 9/2
>  # Is OBD diagnostic Vmax necessary ? Answer: No
>  # Is XCP calibration Vmax required? Answer: Yes
>  # CAN Trcv型号 Vmax回复：TCAN1145
>  # Is Code flash built-in flash or external flash Vmax reply: F29 built-in
>  # Is NVRAM built-in EEP or external EEPVmax reply: Built-in EEP
>  # Is OTA required? Vmax replied: TBD
>  # Does flashing support A/B partition Vmax reply: No
>  # Is a rollback mechanism needed for flashing? If so, please activate the Vmax rollback mechanism. Vmax replied: TBD
>  # Is the flash tag between the app and FBL done via NVM, RAM, or registers? Vmax replied: TBD
>  # Clarification on Secure Boot and Secure Flashing Development: ETAS adds a stub function corresponding to calling Vmax HSM in the bootloader(HSM initialization startup API/firmware signature verification API, etc.), Vmax performs system-level secure boot and flash solution integration verification. Vmax replies: TBD
>  # Network management, diagnostics , bootloader, power-on and power-off , related specification document names and test cases Vmax reply: TBD

-------

> [!note]+ 2026-09-04 03:14 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Updates from **Yanan WU** 
>
> Update the preparation plan for the test bench, if any question please contact me.
>  # Board & debugger delivery——11-Sep
>  # DSP/DET validation tools——11-Sep
>  # MCAL delivery——4-Sep
>  # Memory layout definition
>
> 5.Ford specification sharing (after NDA) ——done, refer to [VMAX-Ford Spec](https://bosch.sharepoint.com/:f:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/VMAX-Ford/VMAX-Ford%20Spec?d=w6360f66377894b8e8ef9abfa4388c7ed&csf=1&web=1&e=hV63lp)
>
>
>
> ![[RTAXIP-4053-image-2026-09-04-10-14-16-347.png]]
>
> ![[RTAXIP-4053-image-2026-09-04-10-14-22-330.png]]

-------

> [!note]+ 2026-09-04 03:10 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> update project requirement ，refer to the file in Accq folder: [Acquisition Project Docs](https://bosch.sharepoint.com/:f:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs?d=w2cfe21a0e0e6422a9f53bab7c14ccaec&csf=1&web=1&e=wuqGVZ)/ [VMAX-Ford/ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN0902.xlsx](https://bosch.sharepoint.com/:x:/r/sites/msteams_9477696/Shared%20Documents/ECM/Customer/Acquisitions/2026/Acquisition%20Project%20Docs/VMAX-Ford/ECM_CN_Vmax_AUTOSAR_Classic_Requirements_template_V16_EN0902.xlsx)

-------

> [!note]+ 2026-08-27 13:34 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> **_Updates on 08.27.2026_**
>
>
> **_Hi@ Su_**
>
>  **__** 
>
>             **__**            *As per discuss the VMAX, we need to first delivery ETAS any RIP to replace OS&mcal in two weeks/three weeks.* 
>
>
>
>                For the test bench, VMAX is willing to give ETAS. Right now, due to the timeling pressure. I hope Yanna could quickly to intial the SOW, and Vmax agree with the SOW, then setup the enviroment.
>
>                So, Internal ETAS, VN team can use the same verion of TI&TI compiler to compiler the RIP firstly, then wait VMAX to give their MCAL configuraiton & CDD. Don’t to wait VMAX’s input because we can take it as stub fucntion or integration function firstly.
>
>
>
>                Dedicated plan from my propose:
>  # Choose RIP baseline from RTA12.x. to RTA12.9hf1 or.
>  # Port OS to the 12.9.
>  # Gen bsw,rte, os. Succesfully.
>  # Use the TI mcal to compiler the whole project.
>  # Compiler the asw,bsw,rte,os,mcal to waiting VMAX input.
>  # VMAX give their mcal configuration and mcal generate code to ETAS.
>  # ETAS replace with VMAX mcal and CDD (power like SBC and wdg else) to compiler whole project.
>  # Debug and loop 1)—8) to make it CAN and FLS work.
>
>
>  # To configure the OS to SC3, VMAX will implement the MPU by themselves. ETAS need to provide the hook and usages. And also to initial all memmap files to apply VMAX memory layout.
>
>
>
>
>
> VMAX input:
>  # Memory layout for the project
>  # Ford’s specical reuiqments need to ETAS to give configuration advise.
>  # Their MCU board and connective lines.
>  # Their MCAL configuration and code. Like SBC and other CDD impact the power or Wdg function.
>  # HW support
>
> VMAX expection:
>  # Delviery working RTA-CAR project in 1 month, VMAX need to base it to do their configuration.
>  # Delivery SC3(memory proection) in two month, this is not highly priority. But VMAX need to finish this in end of 2026 by themselves.
>  # Supporting from ETAS when they encouter issues from ETAS tool or failure test case of Ford Spec.
>
>
>
> The timeline need to be finish in 1 month, after  customer also in the paralle to work for Ford spec to extract their project needs reqruiements and try configure by themselves, we need to support them for these special requiments and analysis with highly priority.
>
>
>
> For the FBL team.
>  # If we have Ford FBL on hand, we need to check the document version with VMAX.
>  # Wait VMAX to give ETAS Ford Spec, one/two analsis the spec.
>  # Initial like the RIP. To port currenlty FBL to TI&TI comiler.
>  # SBL should be run in the RAM. PBL could not to erase/write the Flash(Code&Data). Highlighted by VMAX in the meeting.
>  # Run the FBL basic function and let it work firstly.
>  # Wait VMAX to share Ford tool DSP to do the validation FBL basic funtion.
>  # Verification that the Ford FBL spec application to the baseline FBL.
>
>
>
> VMAX expection for the FBL: 
> ![[RTAXIP-4053-image-2026-08-27-20-34-14-982.png]]

-------

> [!note]+ 2026-08-25 07:44 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> Needs ticket to PF: [https://jira.etas-dev.com/browse/ARC-17359] by SM/ [[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]] 

-------

> [!note]+ 2026-08-20 04:15 · [[Nguyen_Quoc_Su_(MSETA-Hub-CN)|Nguyen Quoc Su (MS/ETA-Hub-CN)]]
> **Request**
>  * TAN Yang confirmed that, in addition to the existing **RBCD S32G399** work, there is **another project called VMAX** that requires BGSV support. [^RE_ Resoruce status-1.msg]
>
> **Action / Next Step**
>  * Jiankang will provide the project background, context, and technical details for the VMAX project.
>
> Cc: [[LIU_Jie_(ETAS-ECMXSF-CN)|LIU Jie (ETAS-ECM/XSF-CN)]] , [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] 

-------

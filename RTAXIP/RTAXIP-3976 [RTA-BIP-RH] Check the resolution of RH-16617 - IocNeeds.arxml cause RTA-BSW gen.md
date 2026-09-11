---
jira_key: RTAXIP-3976
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3976"
server: etas
kind: motivation
type: Task
status: Open
priority: Medium
project: RTAXIP
assignee: ""
reporter: "[[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Phan Huynh Dang Khoa (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-rh]
fix-versions: []
epic: null
parent: null
created: "2026-08-03T05:36:19.000+0000"
updated: "2026-08-03T05:36:19.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Issue**: 

 I got the below when run RTA-BSW code gen.

The number of instances of element "OsIocDataProperties" in parent

"/RTA_BIP/EcucModuleConfigurationValuess/Os/IocOs/Rte_RamBlk_NvBlock_Core1_NvBlockDescriptor_NvBlock0_Core1_NvBlock0_Core1_RamBlock " is less than the lower multiplicity of "1".

![[RTAXIP-3976-image-2026-08-03-12-29-43-598.png]]

**Solution**: This issue shall be fixed in RTA-RTE 12.11.1 --> Check RTA-CAR 12.12.0

![[RTAXIP-3976-image-2026-08-03-12-33-37-852.png]]

## 关联

- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

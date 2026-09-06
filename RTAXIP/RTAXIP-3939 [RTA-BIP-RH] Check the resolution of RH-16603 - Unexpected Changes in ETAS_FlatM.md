---
jira_key: RTAXIP-3939
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3939"
server: etas
kind: motivation
type: Task
status: Closed
priority: Medium
project: RTAXIP
assignee: dyn9hc
reporter: pka3hc
tags: [RTA-BIP-RH]
components: []
fix-versions: [RTA-BIP-cdes-tc397tk-1290-r2.0]
epic: null
parent: null
created: "2026-07-24T06:51:37.000+0000"
updated: "2026-08-05T03:24:01.000+0000"
synced-at: "2026-09-06T06:57:27.567Z"
jira-orphaned: false
---

# RTAXIP-3939 [RTA-BIP-RH] Check the resolution of RH-16603 - Unexpected Changes in ETAS_FlatMap.arxml After Running Generate ECU Configuration Wizard

> [!jira] Closed · Medium · [[Nguyen_Hoang_Danh_(MSETA-Hub-CN)|Nguyen Hoang Danh (MS/ETA-Hub-CN)]] · 更新于 2026-08-05T03:24:01.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3939)

> 标签：#jira/label/rta-bip-rh

## 描述

**Issue**: 

After updating the system configuration, I ran the **Generate ECU Configuration Wizard**. However, unexpected changes were generated in **ETAS_FlatMap.arxml ,** including the removal of RTE_RIPS_CSSAFETY for BswMSwcGenericRequest .

**Solution**: Update **EcuExtract_CLI_Input.txt** file within the project [EcuExtract_CLI_Input.txt!link_attachment_7.gif!](https://jira.etas-dev.com/secure/attachment/811044/811044_EcuExtract_CLI_Input.txt)to resolve issue.

![[RTAXIP-3939-image-2026-07-24-13-49-35-331.png]]

## 关联

- satisfies: [[RTAXIP-3957 [RTA-BIP-RH] Check the resolution of RH-16603 - Unexpected Changes in ETAS_FlatMap.arxml After Running Generate ECU Configuration Wizard]]
- is satisfied by: [[RTAXIP-3893 [RTA-BIP-RH] Check the resolution of Hotline ticket planned in RTA-CAR 12.11]]
- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

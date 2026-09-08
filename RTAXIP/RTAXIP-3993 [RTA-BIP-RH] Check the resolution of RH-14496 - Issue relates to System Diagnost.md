---
jira_key: RTAXIP-3993
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3993"
server: etas
kind: motivation
type: Task
status: Open
priority: Medium
project: RTAXIP
assignee: ""
reporter: pka3hc
tags: [RTA-BIP-RH]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-08-06T05:00:23.000+0000"
updated: "2026-08-17T11:27:11.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-3993 [RTA-BIP-RH] Check the resolution of RH-14496 - Issue relates to System Diagnostic for DIAG

> [!jira] Open · Medium ·  · 更新于 2026-08-17T11:27:11.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3993)

> 标签：#jira/label/rta-bip-rh

## 描述

All points are found after performing ConfGen feature of RTA-CAR. Please **ensure these request/issue below have been resolved in RTA-CAR 12.12.0**. 

- **DcmDspDidUsePort**

+ If DID is configured for **using SID 0x2F** ==> **DcmDspDidUsePort** is **USE_ATOMIC_SENDER_RECEIVER_INTERFACE** as **default data**.

+ Check this information in documentation in RTA-CAR 12.12.0

- **DcmRbAtomicSenderReceiverCommunication**

+  When a DID is configured for **using SID 0x2F ==>** This configuration is TRUE after using conf-gen

- **DcmDspDidControlEnableMask**

![[RTAXIP-3993-image-2026-08-06-11-50-58-036.png]]

+ Ensure this parameter will be generated after running **Confgen**. This configurations are being used for DIDs which are configured for using SID 0x2F.

- **DemStorageConditionGroup**

+ After enabling this configuration, ensure this container will be generated after running **Confgen**

- **DemEnableConditionGroup**

+ After enabling this configuration, ensure this container will be generated after running **Confgen**

- **The "DemClient" in "DemGeneral" of DEM module**

 I expected **only DemClients** as below are generated:

"DemClient_<my_DcmDslProtocolRow_name>" not "DemClient"

## 关联

- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

## 评论

> [!note]+ 2026-08-17 11:27 · [[Nguyen_Le_Thanh_Tu_(MSETA-Hub-CN)|Nguyen Le Thanh Tu (MS/ETA-Hub-CN)]]
> Point 4,5,6 are fixed in RTA-CAR 12.11

-------

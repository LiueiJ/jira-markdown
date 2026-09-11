---
jira_key: RTAXIP-4042
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-4042"
server: etas
kind: motivation
type: Task
status: Open
priority: Medium
project: RTAXIP
assignee: ""
reporter: "[[Phan_Huynh_Dang_Khoa_(MSETA-Hub-CN)|Phan Huynh Dang Khoa (MS/ETA-Hub-CN)]]"
tags: [jira/label/rta-bip-rh]
fix-versions: [RTA-BIP-cdes-tc397tk-1212]
epic: null
parent: null
created: "2026-08-14T09:39:44.000+0000"
updated: "2026-08-19T13:51:56.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Issue**:

SoAd has one ExclusiveArea SoAd_TxRxReq who have many nested ExclusiveArea in it’s code (example below)

SoAd_TxRxReq -> SoAd_RemoteAddrUpdate

SoAd_TxRxReq -> SoAd_OpenCloseReq

SoAd_TxRxReq -> SoAd_SocConModeProperties

…

When these ExclusiveArea need to be Spinlock, it means SoAd_TxRxReq need to be configured with several successor Spinlock.

However, RTA-OS does not support more than one successor.

**Rootcause**:

![[RTAXIP-4042-image-2026-08-14-16-30-53-686.png]]

**Solution:**

PF team confirmed the issue and will provide the bugfix in **RTA-CAR 12.12.0**

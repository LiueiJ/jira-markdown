---
jira_key: RTAXIP-4097
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-4097"
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
created: "2026-08-27T06:45:16.000+0000"
updated: "2026-08-27T06:45:16.000+0000"
synced-at: "2026-09-11T02:40:28.533Z"
jira-orphaned: false
profile: CNN
---

## 描述

**Background**: We are experiencing an issue when migrating projects **from RTA-CAR 12.9.0 to 12.11.0**: some paramdef files fail to update to the newer version, and the tool provides no logs or documentation explaining the omission.

![[RTAXIP-4097-image-2026-08-27-13-39-44-818.png]]

**Workaround:**

For now, Our temporary workaround is to create a new 12.11.0 project and manually copy the paramdef files into the migrated workspace. Since this is a tedious process for our users and customers, we need a smoother long-term solution.

**Proposed solution:**

- Kindly validate this issue in **RTA-CAR 12.12.0.** This issue has been confirmed as fix in [ARCTOOLS-20030](https://jira.etas-dev.com/browse/ARCTOOLS-20030)

## 关联

- is tracked by: [[RTAXIP-2678 [RTA-BIP] RTA-CAR Hotline issue list and tracking]]

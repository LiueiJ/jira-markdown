---
jira_key: RH-17173
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17173"
server: rtahotline
kind: hotline
type: Support
status: Investigation Required
priority: High
project: RH
assignee: ""
reporter: "[[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-09-10T04:14:03.000+0200"
updated: "2026-09-10T05:26:48.000+0200"
synced-at: "2026-09-10T03:48:22.681Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Sometimes when we open the project, it intermittently reports **BSW invalid**. The sequence is:

1. Switch the BSW from version **12.11** to **12.11 PR4/PR5**.
2. Open using a new workspace, and we still get **BSW invalid**.
3. Switch back from **12.11 PR4/PR5** to **12.11**, and the issue is resolved.

![[RH-17173-image-2026-09-10-10-17-54-283.png]]

## 关联

- split from: [[RH-17023 [VCTC] RTA-CAR 12.11 Migration RTA-CAR Toolchain Issues]]

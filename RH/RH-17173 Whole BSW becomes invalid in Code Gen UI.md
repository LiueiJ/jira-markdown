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
reporter: jie.liu8@etas.com
tags: []
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-10T04:14:03.000+0200"
updated: "2026-09-10T04:17:56.000+0200"
synced-at: "2026-09-10T03:06:42.188Z"
jira-orphaned: false
profile: Cariad
---

# RH-17173 Whole BSW becomes invalid in Code Gen UI

> [!jira] Investigation Required · High ·  · 更新于 2026-09-10T04:17:56.000+0200
> [在 Jira 中打开](https://rtahotline.etas.com/jira/browse/RH-17173)

## 描述

Sometimes when we open the project, it intermittently reports **BSW invalid**. The sequence is:

1. Switch the BSW from version **12.11** to **12.11 PR4/PR5**.
2. Open using a new workspace, and we still get **BSW invalid**.
3. Switch back from **12.11 PR4/PR5** to **12.11**, and the issue is resolved.

![[RH-17173-image-2026-09-10-10-17-54-283.png]]

## 关联

- split from: [[RH-17023 [VCTC] RTA-CAR 12.11 Migration RTA-CAR Toolchain Issues]]

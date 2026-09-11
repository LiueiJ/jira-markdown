---
jira_key: RH-17173
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17173"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: High
project: RH
assignee: "[[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]"
reporter: "[[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-09-10T04:14:03.000+0200"
updated: "2026-09-10T11:38:43.000+0200"
synced-at: "2026-09-11T00:31:48.001Z"
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

## 评论

> [!note]+ 2026-09-10 11:38 · [[James_Butterfield|James Butterfield]]
> Hi [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> This issue will be fixed in RTA-CAR 12.12.0 and can be tracked from [ARCTOOLS-23627](https://jira.etas-dev.com/browse/ARCTOOLS-23627).
>
> Please let me know if there is anything further you require from this ticket.
>
> Best Regards,
> James

-------

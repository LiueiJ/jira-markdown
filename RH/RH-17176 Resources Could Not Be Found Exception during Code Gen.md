---
jira_key: RH-17176
jira_url: "https://rtahotline.etas.com/jira/browse/RH-17176"
server: rtahotline
kind: hotline
type: Support
status: Solution Proposed
priority: High
project: RH
assignee: "[[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]"
reporter: "[[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]]"
tags: [jira/label/regional]
fix-versions: []
epic: null
parent: null
created: "2026-09-10T04:45:41.000+0200"
updated: "2026-09-11T19:14:30.000+0200"
synced-at: "2026-09-12T07:38:52.171Z"
jira-orphaned: false
profile: Cariad
---

## 描述

Code Gen Error -> Clear output files and reopen workspace can solve this issue

![[RH-17176-image-2026-09-10-10-43-14-600.png]]

## 关联

- relates to: [[RH-17193 Resources Could Not Be Found Exception during Code Gen]]
- split from: [[RH-17023 [VCTC] RTA-CAR 12.11 Migration RTA-CAR Toolchain Issues]]
- mentions: [[RH-17023 [VCTC] RTA-CAR 12.11 Migration RTA-CAR Toolchain Issues]]
- is mentioned in: [[RH-17193 Resources Could Not Be Found Exception during Code Gen]]

## 评论

> [!note]+ 2026-09-10 11:54 · [[James_Butterfield|James Butterfield]]
> Hi [[LIU_Jie_(ETAS-ECMXSF-CN)|Jie LIU]],
>
> Please see feedback from [[Karthik_M_S_(MSEMT-ETAS)|M S Karthik]] in [this comment](https://rtahotline.etas.com/jira/browse/RH-17023?focusedCommentId=722483&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#comment-722483) regarding this issue:
> {quote}
> - "`\.buildframework`" folder is not delivered to SCM (like GIT).
> - *General Instruction*: When user store the generated output in SCM, then it is mandatory to deliver also the "`\.buildframework`" folder into SCM in order to automatically clean the generated artifact during previous run or to detect the configuration changes and automatically regenerate the output to keep artifacts in sync.
> {quote}
>
> Could you please try this and let me know if it resolves the problem?
>
> Best Regards,
> James

-------

---
jira_key: RTAXIP-3381
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3381"
server: etas
kind: motivation
type: Change Request
status: Review
priority: Medium
project: RTAXIP
assignee: lno2hc
reporter: zco7sgh
tags: [RTA-BIP-UC]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-25T09:25:28.000+0000"
updated: "2026-07-13T02:32:15.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-3381 Use FeeFs2 as the default Fee option for the TC397 BIP project and provide supporting analysis capability for field issue investigation.

> [!jira] Review · Medium · [[Le_Hong_Nhung_(MSPJ-ETA-HN_MSETA-Hub-CN)|Le Hong Nhung (MS/PJ-ETA-HN MS/ETA-Hub-CN)]] · 更新于 2026-07-13T02:32:15.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3381)

> 标签：#jira/label/rta-bip-uc

## 描述

## Summary

Use FeeFs2 as the default Fee option for the TC397 BIP project and provide supporting analysis capability for field issue investigation.

## Description

#RTA-BIP-UC

This need is a use case improvement for the current BIP project implementation.

For the TC397 BIP project, FeeFs2 should be available as the default Fee type option so that the project can evaluate and adopt it as the standard non-volatile memory handling approach where appropriate.

To support this decision, the project also needs a clear performance comparison between FeeFs2 and FeeFs1, with focus on the practical differences relevant to BIP usage, such as access behavior, execution time, and overall impact on the application.

In addition, a DFlash dump analysis script is needed to support issue investigation in field situations where the original system state must not be changed or damaged. This analysis capability shall help engineers inspect flash content offline and speed up root-cause analysis for non-intrusive troubleshooting.

Expected outcome:

- FeeFs2 is supported as the default Fee type option for the TC397 BIP project.
- The project has a documented comparison of FeeFs2 and FeeFs1 performance for technical evaluation and decision making.
- A DFlash dump analysis script is available for offline investigation of field issues without altering the original target state.
- The overall solution improves feasibility assessment, technical transparency, and field troubleshooting efficiency for BIP projects using TC397.

## 关联

- is implemented by: [[RTAXIP-3506 RTA-BIP-UC] Change to FeeFs2]]
- is implemented by: [[RTAXIP-3504 [RTA-BIP-UC] Study and Sharing FeeFs2]]
- is implemented by: [[RTAXIP-3505 [RTA-BIP-UC] Report for FeeFs1 and FeeFs2 comparasion]]

---
jira_key: RTAXIP-3923
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3923"
server: etas
kind: motivation
type: Story
status: Open
priority: Medium
project: RTAXIP
assignee: ""
reporter: puy1hc
tags: [BIP]
components: []
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2026-07-20T09:22:30.000+0000"
updated: "2026-07-20T09:22:30.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-3923 [BIP][Improvement] Use RteScheduleTablePerCore to support Multiple-ScheduleTable

> [!jira] Open · Medium ·  · 更新于 2026-07-20T09:22:30.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3923)

> 标签：#jira/label/bip

## 描述

**Motivation**: As RTE support to generate Multiple-Schedule table and BIP is multi-core project.

![[RTAXIP-3923-image-2026-07-20-16-21-59-955.png]] So that;

- It's better if we can support multiple-schedule table.
- Multi-schedule table will help to balance cpu-load between 5 cores

**Expectation**: 

- Change RteScheduleTablePerCore to TRUE

**![[RTAXIP-3923-image-2026-07-20-16-22-24-469.png]]**

- Check if Multiple scheduletable is generated in Os_Need or not
- Run regession test again

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
reporter: "[[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]]"
tags: [jira/label/bip]
fix-versions: [RTA-BIP-cdes-tc397tk-1211]
epic: null
parent: null
created: "2026-07-20T09:22:30.000+0000"
updated: "2026-07-20T09:22:30.000+0000"
synced-at: "2026-09-11T01:13:18.603Z"
jira-orphaned: false
profile: CNN
---

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

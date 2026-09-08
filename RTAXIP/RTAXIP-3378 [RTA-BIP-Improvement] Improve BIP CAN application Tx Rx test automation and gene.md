---
jira_key: RTAXIP-3378
jira_url: "https://jira.etas-dev.com/browse/RTAXIP-3378"
server: etas
kind: motivation
type: Change Request
status: Open
priority: Medium
project: RTAXIP
assignee: puy1hc
reporter: tao9sgh
tags: [RTA-BIP-UC]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-03-25T08:11:48.000+0000"
updated: "2026-04-23T06:32:56.000+0000"
synced-at: "2026-09-08T01:46:31.431Z"
jira-orphaned: false
profile: CNN
---

# RTAXIP-3378 [RTA-BIP-Improvement] Improve BIP CAN application Tx/Rx test automation and generated code readability

> [!jira] Open · Medium · [[Nguyen_Le_Phuong_(MSETA-Hub-CN)|Nguyen Le Phuong (MS/ETA-Hub-CN)]] · 更新于 2026-04-23T06:32:56.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/RTAXIP-3378)

> 标签：#jira/label/rta-bip-uc

## 描述

## Summary

Improve BIP CAN application Tx/Rx test automation and generated code readability

## Description

#RTA-BIP-UC

This need is a use case improvement for the current BIP project implementation.

The BIP project needs a more automated and maintainable workflow for CAN application testing and code generation. The objective is to reduce manual effort and shorten the test cycle by using CAPL scripts to automate recurring test execution, generate test reports automatically, and create CANoe test cases directly from system descriptions so that a report can be produced immediately after the test run.

In addition, the generated SWC template code should be improved to replace generic variable names such as `Read1` and `Read2` with signal-name-based variables, making the generated code easier to read, review, and maintain.

Expected outcome:

- Generate CANoe test cases directly from system descriptions.
- Run CAN application Tx/Rx test cycles automatically through CAPL-based automation.
- Produce test reports automatically after execution.
- Improve generated SWC template code so that variables use meaningful signal names.
- Reduce manual engineering effort and improve maintainability of test assets and generated code.

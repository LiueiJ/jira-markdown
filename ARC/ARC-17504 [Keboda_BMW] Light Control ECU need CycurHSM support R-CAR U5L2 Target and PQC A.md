---
jira_key: ARC-17504
jira_url: "https://jira.etas-dev.com/browse/ARC-17504"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: wea2bo
reporter: tst1sgh
tags: [BMW, EES30, SEC, U5L2, pqc]
components: []
fix-versions: []
epic: null
parent: null
created: "2026-09-08T08:58:41.000+0000"
updated: "2026-09-08T13:08:54.000+0000"
synced-at: "2026-09-09T13:46:40.498Z"
jira-orphaned: false
profile: CN Motivation
---

# ARC-17504 [Keboda_BMW] Light Control ECU need CycurHSM support R-CAR U5L2 Target and PQC Algorithm

> [!jira] New ·  · [[Wegmann_Alexander_(ETAS-ECMXPC-Bo)|Wegmann Alexander (ETAS-ECM/XPC-Bo)]] · 更新于 2026-09-08T13:08:54.000+0000
> [在 Jira 中打开](https://jira.etas-dev.com/browse/ARC-17504)

> 标签：#jira/label/bmw #jira/label/ees30 #jira/label/sec #jira/label/u5l2 #jira/label/pqc

## 描述

Keboda already get this ECU project Contract from BMW, we are try to get the contract from Keboda as soon as possible. 

Opportunity from Keboda for Light Control ECU need support the R5L2 target and PQC Algorithm.

**PQC requirement:**

1, MLDSA65-ECDSA-P384-SHA2/512  for signature verification.

2, MLKEM1024-ECDH-P384-SHA3/256  for Public key encryption.

3, AES-256 CBC for Encryption

4, x9.63-KDF with SHA2/512,  x9.63-KDF with SHA3/384

5, HMAC-SHA3/384

 

**Project time line:**

CycurHSM DEV package needed by end of November, 2026

CycurHSM QA package needed by end of April, 2027

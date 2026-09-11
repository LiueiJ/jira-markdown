---
jira_key: ARC-17504
jira_url: "https://jira.etas-dev.com/browse/ARC-17504"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Wegmann_Alexander_(ETAS-ECMXPC-Bo)|Wegmann Alexander (ETAS-ECM/XPC-Bo)]]"
reporter: "[[TANG_Steven_(ETAS-ECMXSF-CN)|TANG Steven (ETAS-ECM/XSF-CN)]]"
tags: [jira/label/bmw, jira/label/ees30, jira/label/sec, jira/label/u5l2, jira/label/pqc]
fix-versions: []
epic: null
parent: null
created: "2026-09-08T08:58:41.000+0000"
updated: "2026-09-08T13:08:54.000+0000"
synced-at: "2026-09-11T01:13:09.700Z"
jira-orphaned: false
profile: CN Motivation
---

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

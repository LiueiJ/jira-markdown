---
jira_key: ARC-16740
jira_url: "https://jira.etas-dev.com/browse/ARC-16740"
server: etas
kind: motivation
type: Motivation
status: New
priority: ""
project: ARC
assignee: "[[Buttle_Darren_(ETAS-ECMPRM1-EMW)|Buttle Darren (ETAS-ECM/PRM1-EMW)]]"
reporter: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
tags: []
fix-versions: []
epic: null
parent: null
created: "2026-06-26T05:42:14.000+0000"
updated: "2026-07-07T12:37:34.000+0000"
synced-at: "2026-09-11T01:13:09.700Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

**Enpower** expects **CP Flex** to be a standard feature within RTA-CAR. 

**Customer Expectation:**

1. **AUTOSAR Version:** Customer is looking for latest AUTOSAR version support in RTA-CAR i.e. AR 25-11
2. **Cluster Partitioning Support:** They have a critical need for **AUTOSAR Cluster partitioning**. This is for a domain controller project where different software modules on the same Microcontroller Unit (MCU) must be developed and updated independently. The provided image of the "Com Proxy" architecture illustrates the type of partitioning they require, showing two separate partitions (EcucPartition X and EcucPartition Y) within a host software cluster.
3. The customer has purchased the development license for RTA-CAR 12.10.0 this year. They plan to utilize cluster partitioning for their Domain Controller project in **2027**.• They expect this feature to become available/supported during their active maintenance window i.e. before Q3.2027

**CP Flex current status** 

- Infrastructure exists, but is NOT supported in standard RTA-CAR. • 
- **Tooling Available:** ISOLAR-A CP Flex Mapping Editor and RTE cross-cluster generation are present in 12.10.0.
-  **Proxy Module Readiness:** 
  - OsProxy is at **RELEASE** status; 
  - ComProxy, LdComProxy, NvMProxy, DemProxy, and FiMProxy are currently only at **Prototype** status.
  - **Product Gap:**  CPFlex is not supported in the standard RTA-CAR context.

## 评论

> [!note]+ 2026-06-26 07:20 · [[Kristoferitsch_Jakob_(RBOSPJ-GM)|Kristoferitsch Jakob (RBOS/PJ-GM)]]
> Please note my caveats regarding the com proxy in [RH-16272 comment #8](https://rtahotline.etas.com/jira/browse/RH-16272?focusedCommentId=698418&page=com.atlassian.jira.plugin.system.issuetabpanels%3Acomment-tabpanel#comment-698418)

-------

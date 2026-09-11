---
jira_key: INSYNC-50
jira_url: "https://jira.etas-dev.com/browse/INSYNC-50"
server: etas
kind: motivation
type: Motivation
status: Accepted
priority: Medium
project: INSYNC
assignee: "[[Madanmohan_Sathish_Kumar_(ETAS-ECMXSF-CN)|Madanmohan Sathish Kumar (ETAS-ECM/XSF-CN)]]"
reporter: "[[Vishak_Nikesh_(ETAS-ECMECP-PJM)|Vishak Nikesh (ETAS-ECM/ECP-PJM)]]"
tags: [jira/label/hesai]
fix-versions: []
epic: null
parent: null
created: "2025-04-16T18:46:35.000+0000"
updated: "2026-07-02T13:04:15.000+0000"
synced-at: "2026-09-11T02:40:23.945Z"
jira-orphaned: false
profile: CN Motivation
---

## 描述

**Scope of work as follows :** 

**DoIP Change Request :** 

1. DOIP as TCP Client shall support configurable periodically(e.g. 5ms periodic) to establish connection until connection succeed. E.g., after sent SYN, incase ECU not receive response or receive RST, DoIP shall still sending SYN with 5ms interval until connection established.
2. configurable periodically for retransmit is not TcpIpRetransmissionTimeout, but a separate retransmit parameter (multiple of Tcp_MF).
  a) this extended timer for retransmit for SYNC is only applicable for the Tcp socket for DoIP.
  b) this extended timer for retransmit for SYNC is mutual-exclusive with existing Tcp segment timers.

**EthTSyn Change Request**

- EthTSyn shall support GlobalTimeDomain to be configured with parameter EthTSynGlobalTimeDomainId from 0 – 31, without functional/feature change requests.
- !noimage.png!

**Tcp Change Request**

DoIPLite: (background info: this is used in DoIP bootloader)

• ParameterDef/EcucValues:

▪ Tcp support a vendor specific timing parameter T_ConnectTcp

▪ timing parameter T_ConnectTcp can be pre-compile configured TRUE or FALSE

▪ an configurable timeout notification with notification type

1. callout function

2. C/S interface Functional：

▪ When to start the timer T_ConnectTcp: an software start (ECU code start/warm start) will automatically start the timer &#91;Hesai-2&#93;: agreed to take the alternative proposal that ETAS Recommendation: the timer T_ConnectTcp will be start automatically during Doip_OpenConneection between DoIP and Tcp, without providing an external interface that user has to take

Page 6 of 12

care during integration e.g. at an software start (ECU code start/warm start).

▪ Timer suspend/reload: no require

▪ Timer stop: stop timer T_ConnectTcp on successful Tcp connection

▪ Timer notification:

1. timeout: an timer timeout will call the callout function or C/S interface

2. successful Tcp connection: a successful Tcp Connection will call an callout function or C/S interface Functional (Dcm):

▪ S3Server: Provide an standardized interface API to start/stop S3Server

• For variable type/range of timer values for global timer

▪ min value: per MainFunction period

▪ max value: uint32

## 关联

- relates to: [[ARC-9667 HESAI Customized RTA-CAR for Xiaomi Spec]]
